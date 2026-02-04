# Complex Numbers with Octaves, Backgradient, and Triadic Propagation
### A compact experimental architecture for octave‑driven nonlinear flows

---

## 1. Overview

This article introduces a **backgradient‑supported complex number class** that:

- Behaves like a normal complex number  
- Defines an **octave** as a static function of magnitude  
- Supports octave‑preserving transformations  
- Implements asymmetric backgradient:
  - **Real part:** first‑order derivative  
  - **Imag part:** second‑order derivative  
- Participates in a **triad cycle** where octaves propagate forward and gradients propagate backward

We then run the system on the pair **$(2+2i,\;2+2i)$**.

---

## 2. Octave Geometry

We define:

$$
\text{octave}(z) = \log_2(|z| + \varepsilon)
$$

This gives a smooth octave space.  
`getOctave()` simply delegates to the static function.

---

## 3. Octave‑Preserving Transformations

Given a target octave $o$:

$$
r_{\text{target}} = 2^o
$$

To preserve the imaginary part:

$$
a = \pm\sqrt{r_{\text{target}}^2 - b^2}
$$

To preserve the real part:

$$
b = \pm\sqrt{r_{\text{target}}^2 - a^2}
$$

These operations shift the number to the desired octave while keeping one component fixed.

---

## 4. Backgradient

We treat components asymmetrically:

- **Real part:** first‑order derivative of octave  
- **Imag part:** second‑order derivative (curvature)

This is the “integral‑differential vs second‑order integral‑differential” split.

---

## 5. Triad Mechanism

Given a pair $(x, z)$:

1. Compute octaves  
2. Build mediator  
   $$
   y = o_x + i\,o_z
   $$
3. Build next pair using $y$’s components as octave targets  
4. Compute activation  
5. Backpropagate through octave into $x$ and $z$

This creates a nonlinear octave‑driven loop.

---

## 6. Full Implementation

```python
import math
from dataclasses import dataclass

EPS = 1e-9


def octave_of_complex(z: complex) -> float:
    return math.log2(abs(z) + EPS)


def second_derivative_imag_octave(z: complex, h: float = 1e-4) -> float:
    x, y = z.real, z.imag
    o0 = octave_of_complex(complex(x, y))
    o_plus = octave_of_complex(complex(x, y + h))
    o_minus = octave_of_complex(complex(x, y - h))
    return (o_plus - 2 * o0 + o_minus) / (h * h)


@dataclass
class ComplexNode:
    value: complex
    grad_real: float = 0.0
    grad_imag: float = 0.0

    @staticmethod
    def octave_of(z: complex) -> float:
        return octave_of_complex(z)

    def getOctave(self) -> float:
        return ComplexNode.octave_of(self.value)

    def setOctaveKeepImg(self, octave: float) -> None:
        target_r = 2.0 ** octave
        b = self.value.imag
        inside = max(target_r * target_r - b * b, 0.0)
        if inside == 0.0:
            a = 0.0
        else:
            sign = 1.0 if self.value.real >= 0 else -1.0
            a = sign * math.sqrt(inside)
        self.value = complex(a, b)

    def setOctaveKeepRl(self, octave: float) -> None:
        target_r = 2.0 ** octave
        a = self.value.real
        inside = max(target_r * target_r - a * a, 0.0)
        if inside == 0.0:
            b = 0.0
        else:
            sign = 1.0 if self.value.imag >= 0 else -1.0
            b = sign * math.sqrt(inside)
        self.value = complex(a, b)

    def backprop_from_octave(self, upstream: float) -> None:
        x, y = self.value.real, self.value.imag
        r = abs(self.value) + EPS

        do_dx = x / (r * r * math.log(2.0))
        d2o_dy2 = second_derivative_imag_octave(self.value)

        self.grad_real += upstream * do_dx
        self.grad_imag += upstream * d2o_dy2

    def magnitude(self) -> float:
        return abs(self.value)

    def __repr__(self) -> str:
        return (f"ComplexNode(value={self.value}, "
                f"grad_real={self.grad_real:.6f}, grad_imag={self.grad_imag:.6f})")


def triad_step(x: ComplexNode, z: ComplexNode):
    ox = x.getOctave()
    oz = z.getOctave()
    y = ComplexNode(complex(ox, oz))

    x_next = ComplexNode(complex(x.value.real, x.value.imag))
    z_next = ComplexNode(complex(z.value.real, z.value.imag))

    x_next.setOctaveKeepImg(y.value.real)
    z_next.setOctaveKeepImg(y.value.imag)

    loss = x_next.magnitude() ** 2 + z_next.magnitude() ** 2

    x.backprop_from_octave(1.0)
    z.backprop_from_octave(1.0)

    return {
        "x": x,
        "y": y,
        "z": z,
        "x_next": x_next,
        "z_next": z_next,
        "loss": loss,
    }
```

---

## 7. Example: Starting from $(2+2i,\;2+2i)$

```python
if __name__ == "__main__":
    x0 = ComplexNode(complex(2.0, 2.0))
    z0 = ComplexNode(complex(2.0, 2.0))

    result = triad_step(x0, z0)

    print("=== First triad ===")
    print("x:", result["x"])
    print("y:", result["y"])
    print("z:", result["z"])

    print("\n=== Next pair ===")
    print("x_next:", result["x_next"])
    print("z_next:", result["z_next"])
    print("loss:", result["loss"])

    print("\n=== Backgradient ===")
    print("x grad:", result["x"].grad_real, result["x"].grad_imag)
    print("z grad:", result["z"].grad_real, result["z"].grad_imag)
```

---

## 8. Interpretation

- Octaves propagate forward through the triad  
- Backgradients propagate backward through octave  
- Real and imaginary parts respond differently  
- The system exhibits nonlinear “implication” due to octave‑driven unit shifts
