# AI theory with some of my Laegna mathematical ideas

I asked an AI also to create one [intro](aiintro.md) based on my article.

This is not hard to provide the basics of an AI in simpler manner, where I don't like that the complexity of texts I used myself, and videos, made many conceptions longer and more complex by involving hard math and complicated ideas.

I mix my own text by generations of an AI to continue each topic with the words I use here, giving it also the text from beginning to end.

## AI Components and process

AI is made typically more or less in such way:
1. Deep Learning platforms, such as Torch and TensorFlow, are installed, and some computing components like tensor and cuda cores, more cores of more powerful processing, could be adapted.
2. A _brain_ or a _model_ is made: consisting of brain areas, some (digital) neural networks connected in layers.
  - This _model_ defines input, output types and a sequence of layers, which map it to different levels of precision; for complex architectures, custom-made component structures are applied, or ones introduced in scientific publishments.
  - SmolLM has small models to test models, also Qwen and Llama have 0.5 and 1B models (small ones) as well as bigger models, where 3B is still quite fast. With model size in parameters, it needs at least exponential amounts of resources: matrixes rather scale in square relation when compared to vectors, so for amount of data, there are square amounts of processing involved; the exact nature of this proportion depends on the model: for trivial implementations, to get O factor, you multiply the size of input and output, and get a square of their average: this one I call _exponential function_.
3. A _knowledge_ or a _training_ is made, done: this is fine-tuning process, where the brain is introduced some information or data; training of a _model_ is done by fine-tuning process with a _dataset_, either in form of Q&A (Questions and Answers) or Instruction, Question, Answer, or Question, Answer, Document / Context - I call the later Q&A&D as it's what I need. Q&A form is very general also where Question is the input, where Answer is the output: you train all kinds of DL models and machine learning components to _fit_ a specific data, which would mean it becomes fit, or that it fits them: it finds the scientific model to fit the measurement, essentially, if one could call weight matrix a scientific model.
  - This _knowledge_ is kept inside _weight matrix_.
  - __LitGPT__ is a library you can use for fine-tuning: it's custom, rather simplistic instance you would call open source given that you want simple code. [miniGPT](https://github.com/karpathy/minGPT) is considered a minimal model, but it uses __PyTorch__; I suggest __PyTorch__ but it's a heavy library and thus, given average effort, it's not open source into the bones.
4. The trained model is converted into chatbot, character descriptions, greeting messages, Q&A knowledge as working example could give the _brain_ also some _identity_, to _represent a specific role_.
  - This, for example is GGUF for GPT4All, LM Studio and Jan clients for an AI chatbot.
5. If the trained model, with chatbot, such as model with GPT4All, allow this, documentation can be mapped into embeddings and connected to it. Embeddings use an _AI brain_, a model which can put those documents into multidimensional space of coordinates, so that the model would be able to convert it's input into same multidimension, and/or include it's relevant data such as topic or chat history, and get the closest documents from this, where typically a simpler brain would have the document map: model for mapping, such as _Nomic Embed Text v. 1.5_ I have, is not being fine-tuned, but it only calculates the coordinates in it's pre-trained coordinate space (I call the pre-trained information knowledge). This is called RAG memory.
  - You need to create document folders and add those as Collections, which you can turn on and off in real time.
  - The model would consume the documents easily, if it's pre-trained on similar content, for example being able to generalize and get hints from titles.
  - If the other is _knowledge_, call this and _information_: the model is not definitely creative about this, where the fine-tuning rather creates holistic map of the model, where everything could be concluded into a single matrix.
6. You can use the documentation and experience from chatting, or knowledge about where it could lack information, to train (fine-tune) it further. Sometimes, the initial process for knowledge is called "training" or "initial training", where the refining process is "fine-tuning".

_I asked AI_: how is step of exponential function related to square, where what follows would be level four, then sixteen etc.? Write an answer in one paragraph.

_AI answered_: The step of an exponential function relates to squaring in that it compounds values progressively by multiplying the base repeatedly, leading to rapid growth. For instance, when you square a number (e.g., \( 2^2 = 4 \)), you’re effectively exponentiating it to the second power. Following this logic iteratively as an exponential sequence, the next step, such as raising \( 2 \) to the fourth power (\( 2^{(2^2)} = 2^4 = 16 \)), demonstrates an accelerated growth curve, where each subsequent level is a further exponentiation of the result. This compounding relationship causes exponential functions to outpace polynomial growth significantly as the steps increase, showcasing their mathematical intensity. It's as though squaring is the foundational step, and exponential operations iterate and amplify it with each level.

## DL (deep learning) AI (artificial intelligence) inside: how it works

### Data Structures

Data structures of Perceptron: a simulation of cellular neural network as abstracted into rather what holds logically (we could find more functions of a nerve over time - or if not nerve, a system of nerves, given all the parameters).

#### Tensors

Tensors:
- Tensor is physically very similar to vector (multidimensional coordinate) of it's dimension, or list of it's component length.
- Conception of Tensors is associated with physics and other material sciences or sciences about systems with tensions: for example, fields shape the spatial structure, creating tensions inside it, and producing reactions of the matter inside.
- Typically, the tensor size is static. The input and output layers are iterating over possible inputs and outputs in training and fine-tuning, whereas they calculate outputs for inputs and introduce random factor when being in inference, in actual use. In hidden layers, tensors are then going through different shapes and structures _to get rid of tension_.

So a Tensor could be: [1, 2, 3]; where it's point perhaps with X=1, Y=2 and Z=3 in 3-dimensional coordinate space; it could resemble number, when one dimensional, or point coordinates, when having two dimensions. Hypergeometry appears in fourth dimension, and in any number of dimensions, one could do all the calculations.

So as you would expect from a Tensor: when teaching it, you make it "hot" or melt it, so that it has variable shape (numbers within); when you finish, it would cool down and serve you on cristalline basis until more fine-tuning where it's how again. For fine-tunig a _brain_, or model, to load it with _knowledge_ or data / datasets, you need the _brain_ and _knowledge_: the _model_ and it's _weight matrix_.

**AI addition:**  
Tensors are fundamental data structures in deep learning because they enable efficient representation and manipulation of complex multidimensional data. Unlike simpler structures like scalars (single values) or vectors (one-dimensional arrays), tensors can represent data in multiple dimensions simultaneously—such as a batch of images, where each image is stored as a 3D tensor with width, height, and channel dimensions. This ability to represent and operate on high-dimensional data makes tensors indispensable for modern artificial intelligence models. Additionally, tensors integrate smoothly with parallel computing frameworks (such as CUDA for GPUs), enabling large-scale computations to be executed efficiently during training and inference. While the physical analogy of tensors cooling down and crystallizing is insightful, in practice, their dynamic nature within hidden layers—adjusting shapes and values through operations like matrix multiplication and activation functions—makes them the cornerstone of a model's ability to learn and generalize.

Furthermore, tensors aren't just containers for data; they embody transformations. During training, tensors flow through layers of neural networks, interacting with the model's weight matrices and biases to generate meaningful outputs. Each layer applies mathematical operations to these tensors, gradually refining raw input data into representations that the model can interpret, such as identifying patterns or making predictions. This dynamic interplay between static tensor shapes and the dynamic processing within hidden layers highlights the adaptability of deep learning systems, making tensors not just tools for computation but also integral to the model's conceptual framework.

#### Matrices

Matrices have these properties:
- Matrix is a map of coordinates in two-dimensional space, in regards to dimensionality of it's input and output.
- It's a map of function, with input in columns, output in rows of a matrix.

We use the Matrix _in purpose of multiplication_, and it's associated with position (_weights_ and _biases_ - matrix projection or vector multiplier with affine translation like zoom, rotate etc, in _weights_ and the additive operations, such as _pan_ or _move_, in bias; then, the _weights_ zoom and rotate the multidimensional space, while the _biases_ would scroll the resulting view, keeping the projection).

To associate, for example, 3D matrices with 1D for addition, with something you can easily imagine, you need to understand, how 3D is projected and positioned typically in virtual worlds.
- The _coordinate matrix_ is used to _position the objects_: you can map, into this matrix, _affine translations_, which are defined to modern geometry based on the matrices. Objects move and rotate based on this matrix. 3*3 space is used for multiplication and division (which form the affine translation), where one column and one row, both with 3 dimensions as well, are added for addition and multiplication (which forms the movement): the general matrix, which has these operators and operations in ideal space, is created by a theory of one mathematician (well you can find backgrounds yourself with internet and AI, so I am into the theory).
  - _AI_: The matrix used to position objects is called the __Model Matrix__ or __World Matrix__. It defines the transformation applied to the object, such as scaling, rotation, or translation, to position it within the scene.
- The _coordinate space matrix_ is used to _create a perspective or viewport_: This uses the same properties: if the space around you would be an object, you could rotate, resize and move it. It's visible as rotating the space, zooming in and out, and moving the camera.
  - _AI_: The matrix used to create a perspective or viewport is called the __Projection Matrix__. This matrix defines how 3D objects are mapped onto a 2D view, creating the illusion of depth and perspective.

Using Javascript library three.js, you can create those matrices with WebGL (code by CoPilot; the code is not very important to understand, but can be a good starting point for 3D matrices):
```javascript
// Initialize Scene, Camera, Renderer
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// 1. Create a simple object (a Tetrahedron for aesthetics)
const geometry = new THREE.TetrahedronGeometry();
const material = new THREE.MeshBasicMaterial({ color: 0xff6347, wireframe: true });
const tetrahedron = new THREE.Mesh(geometry, material);
scene.add(tetrahedron);

// 2. Position the object using Model Matrix logic
tetrahedron.position.set(0, 0, -5); // Move it away from the camera along Z-axis

// 3. Apply a Perspective Matrix for realistic viewing
camera.position.z = 5; // Leonardo da Vinci-like depth happens here via the camera perspective

// Render the scene
function animate() {
  requestAnimationFrame(animate);
  tetrahedron.rotation.x += 0.01; // Rotate for aesthetics
  tetrahedron.rotation.y += 0.01;
  renderer.render(scene, camera);
}
animate();
```

This code has highlighted points to understand Matrices:
1. Create a simple aesthetical object.
2. Use coordinate matrix to position it.
3. Add a da Vinci-like perpective using coordinate system matrix.

I have a personal idea, how a matrix should look - with ability to call it as a function:

```
Matrix m
m(points)
```

This would multiply points by this matrix. Vector or matrix could be used as parameters: in case of matrix, hidden transpose would happen. I will extend this syntax to illustrate every part of the Perceptron.

In such case of having such function, you would imagine Matrix as following object:

Let's see a Python example of Matrix multiplication (otherwise called dot product with dot operator in NumPy):
```python
# Let's assume we have two matrices: A and B. 

A = [[1, 2], [3, 4]]
B = [[5, 6], [7, 8]]

# We can perform matrix multiplication without explicitly creating a 
# matrix object by using nested for loops to iterate over rows and columns 
# of the matrices, summing and multiplying accordingly.

# The number of columns in result is equal to number of columns in B
result = []
# `len(A)`: the number of columns in `A`
# Should equal to number of rows in `B`:
for i in range(len(A))):
    # will contain a row after `j` iterator
    row = []
    # len(B[0]) is the number of rows in `B`
    # Should equal to number of columns in `A`.
    for j in range(len(B[0]))):
        sum_ = 0
        # `len(B)` is the number of columns in `B`.
        # Equals to: number of rows in `A`.
        for k in range(len(B)))):
            sum_ += A[i][k]] * B[k][j]]
        row.append(sum_))
    result.append(row))

# The resulting matrix is the product of matrices A and B, which we obtain 
by iterating over rows and columns of the matrices, summing and 
multiplying accordingly. 

print(result)
```

If we use C = A(B) as multiplication of two matrices A and B, we need to track the input and output:
- In our case, we could define matrix definitely in way that rows are input and columns are output, and use this format where we multiply functions together: E = {A * B * C}(D) that we do E = A(B(C(D))). We could then use {} to contain an expression with functions.

How to understand the function:
- `i` and `j`: multiply over rows of first and columns of second matrix, which are input and output of multiplied call sequence, where you multiply several matrices to perform the operations _as if they were performed one after another_.
  - For example if you have matrices A, B and C, then D = A * B * C would mean that D(x), where x is vector, performs the same operation as A(B(C(x))). So, a sequence of transformations with matrices can be stored as efficiently as one transformation: in 3D graphics, you do many subsequent operations over the perspective and object transformations and positioning; if you have one matrix to multiply for each operation, which is normal, you get a resulting matrix, which basically does all the operations at once.
- `k`: iterates over the _hidden part_ of the sequence, which is not directly in input and output. I call it _hidden part_, the output of A as input to B, as we do not see this directly, but only the actual input and output of the multiplication group. The columns of A and rows of B are iterated with the same iterator: thus, while i and j iterate over each possible combination, k and k keep columns of the first matrix together with rows of another. On these two combinations in given case, it would multiply each column of first matrix with each row of the second, for each _hidden member_ (I call them hidden members, because each is output of first, and input of the second matrix), so that i iterates over rows of A, j over columns of B, and rows for C are created - it's input.
  - Notice where the ability for transcension comes to matrix, where it can apply complextranformations to objects: The combination of each position is favourable, because all columns of one are used separately for each row of the other, and half of all possible combinations are used for input and half for output.

Why I say half of combinations are used?

In case of 3D, we have same shape of input and output: a 4 times 4 matrix with 3 rows and columns for multiplication like _weight matrix_, and last ones for addition like _bias matrix_ or rather _bias vector_. The biggest challenge is unification of linear (addition, subtraction) and exponential (multiplication, division) space, where normally only one row and column are used for _bias matrix_: normally, weights are stored in matrix, and biases in vector - where both together form  __Knowledge__ of _pre-trained model_ or __Brain__.

Where input and output are of the same type, one can notice that in regards to input and output, if they would be the same variable, where we do C = A * B, but in 1 / B = A / C we would see a picture of "A / C", where we would combine all combinations of this kind of inverse operation - and out of interest, b could be (1 / C) and in A * b, we would combine through each possibility. Thus, for two _distinct_ variables, we do half of the combinations for both.

Moreover, in an important symmetry: given such half-complete combinatorics, rows and columns would give half plus half, or one full combinatoric for these two variables. The case is, you can use the same variable: for example, geometric point n as both columns and rows, which means there could be three-dimensional vector n for two points, x and y, where dimensions of x are rows, and dimensions of y are columns of the matrix. Basically you can see: you could map the multiplication and division in any combination to those variables, and you would get a perfect transformation of that vector with matrix.

V(m)

Then, matrix m multiplied by vector v would output a vector, where rows x, y and z of matrix are each componentwise multiplied, and components of the result are summed: then, it's like having a vector of three vectors (three-dimensional three-dimensional space), another vector of three scalars, which we multiply. Geometrically, vector is a direction with length: (1, 1, 1) would be 3d identity vector, where multiplication leaves another vector impact, and 1 is identity scalar. In identity matrix you have positions (x, x), (y, y), (z, z) and subsequently (n, n) for any n filled with ones, so that where row = column, there is one, and elsewhere there are zeroes: the component would be identical to the same component, by one is identity scalar in regards to multiplication and division.

```python
# Example: Matrix-vector multiplication
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
vector = [1, 0, -1]

# Multiply matrix by vector
result = []
for row in matrix:
    dot_product = sum(row[i] * vector[i] for i in range(len(vector)))
    result.append(dot_product)

print("Result:", result)
```

M(v)

Would multiply Matrix with vector and it's called a dot product.

Here is code you see that each row of matrix is iterated, and the sum is taken from each row component and each vector component. Each time the row is different. Here we see: the vector is both input and output, as it's transformed form would be the output.
- _What happens?_: we can do _any_ operation involving multiplication and division of each component with each other component. If components of matrix row sum to one, for example each is 1/3, they are balanced/normalized, where 1/3 for example gives the average of each component (column).

You can find out you can do _affine transformations_ with matrices, which is their other name.

Simplest form of object two-dimensional number space is matrix. Imagine the number of each position is a digit. Then, if you use letters I, O, A, E of my mathematics for numbers, number like AAAA could be a vector with 4 simple dimensions. Then, AAAAAAAAAAAAAAAA or AAAA AAAA AAAA AAAA would repeat this 4 times, forming a matrix of such objects: a two-dimensional space. If you convert the 4-letter sequences back to digits, getting an average of each, and multiply the numbers of such content, you would have simplified form of matrix multiplication: for example in a*a, each digit is mapped to each digit and this is two-dimensional space in what I call "half octaves", in space of half-dimensionality (I use numbers with digits as dimensions, such as 3.4-dimensionality); this would also be a number of combinations. a^a, a in power a, would be the number of each cell; here you can see you would do matrix multiplication with digits, by their averages: both numbers would one mark each row, the other mark each column, but they would be multiplied in each combination, then summed together, the digit values. Here you can see: multiplication is kind of always the same operation.

I would point out, that if you do multiplication, division, addition and subtraction:
- You could keep a reflector, which reflects the amount of multiplication and division operations needed to have number scale of the number after the operator, compared to number before. For example in 1+2=3, you would keep reminder that 1\*3=3, thus the reminder at operator position is 3 (3/1, B / A from A\*B=C). 
- The amount of addition and substraction is also, each time multiplication or division is done, such as 3/1=3, it would convert to 0, where you have 3+0=3.
- For the whole operation: you have each indexed position, where you basically have relations of multipliers/divisors, and relations of adders/subtracters: those two operations operate in two different, what I call "frequencies", and thus you need to keep track in one about another, to understand how much you have to simplify / reduce the effects on other axe. For different operations, to not depend on order of them, you have operations in other dimensions reflected in system of this operation.
- If there is 0*3, where you compare 0 to 3, have Y3, which is the infinity multiplier in my math to get 3 from normal zero, and Z3 for 3\*0, which is the number backwards.

Having those operations to connect multiplication with addition, you can do this:
- In every cell of matrix, there is addition and subtraction as well as multiplication and division. Thus, it does a more complex operation.
- In my number system of I, O, A and E, O and A would be used for digits for addition (plus 1 or minus 1), and I and E for digits for multiplication (times 2 or divided by 2): \_ would be used for digits, which do not affect, which is my version of one zero: it would behave as 0 for add/subtract, and 1 for multiply/divide, as it _does not exist_ and no operations are done.

Scalars are numbers: you resize things with them, as they behave like vector with equal number in each dimension, where I compare such thing with _superdimension_: each dimension of it would be the same constant, and thus it maps to number space, where the coordinate do not have exactly same values. s(M) or s(V) would resize the matrix or vector.

How the matrix itself transforms the whole space?

You can see, in matrix-vector multiplication, you use each row to multiply each vector, and thus you connect every component with every component. If you consider Matrices as functions, you have multiplication of functions A and B:
- Notice that the output of A needs to be mapped to input of B, thus those have the same identifier in matrix multiplication: rows of one map to columns of other. While those numbers connect each as constant, the actual operation can be contained, as input of A and output of B are considered in each combination, and are rather free (we use two different iterators, so they are i and j, not k and k as input and output, which are connected variable-by-variable).

We could go dimension up:
- If we need an object, which has all possible combinations for a matrix, such as matrix has them for a vector: to do the same math with matrices; we would use four-dimensional matrices. If matrix would also allow for "knownness" factor, U in my math: it would allow to train many of those matrices, and then unify the training with higher matrix.

To optimize matrix math:
- My mathematics would allow easier combinatorics with infinite spaces, where the directions would have same precision as numbers, and the number of combinatorics is several levels down compared to decimal matrix, for scanning the same complexity of space with some resolution.
- Turn dimensionality into a contiinum from discrete space: the number of dimensions could be not a full number. You can resize matrices like photos, where the multiplicatives of resized matrices would just differ in scale.

_AI addons:_ Matrices serve as more than just mathematical tools for computation; they act as the foundational building blocks for transformations in multidimensional spaces. A matrix, when applied to a vector, doesn't simply modify it—it redefines its position, orientation, and scale relative to a chosen coordinate system. This ability to enact such profound alterations with precision is what makes matrices indispensable for tasks such as geometric modeling, simulation, and even neural network operations. In essence, matrices encapsulate the rules that govern how spaces and objects interact in a given context.

One key strength of matrices is their ability to store and combine multiple transformations into a single operation. For example, when rendering 3D scenes, matrices for rotation, scaling, and translation can be multiplied together to form a composite transformation matrix. This single matrix can then be applied to every vertex of a 3D object, ensuring that all transformations happen seamlessly and simultaneously. This efficiency is crucial for both graphics applications and computational models like neural networks, where rapid operations across large data sets are necessary.

Matrices not only transform data but also carry the ability to encode relationships. In neural networks, weight matrices store the learned associations between input features and the desired outputs. Bias vectors, on the other hand, act as the translating element, shifting results to align more accurately with the expected predictions. Together, weight matrices and bias vectors create a structured representation of the model’s "knowledge," enabling it to adapt and refine itself iteratively as it learns from data.

Looking ahead, matrices reveal the interconnectedness of mathematics and computation, showing how abstract concepts can yield highly practical applications. From describing the physical world in simulations to encoding complex operations in machine learning, matrices hold a dual role as both abstract mathematical entities and critical tools for modern technology. _End of AI Content_

### Operation of an AI: simplest network

The simplest combination of a Perceptron in Deep Learning is:
- Input Tensor i (we talked about vectors: in regards to matrices, Tensors behave quite the same).
- Weight matrix W and Bias vector b.
- Output Tensor o.

We can see:

i = W(o) + b

Where we apply the weight matrix W to tensor (like vector) o and add the bias b to get the result i.

We can generalize Machine Learning and deep learning:

W could be matrix, in which case you initially get _affine translation_, where Wb could actually, for 3\*3 W and 3-element vector b, be in equal form to 4\*4 matrix used in 3D processing.

W, for machine learning, would be any function with input i and output o, which would do some operation with them: for example x + ya = c would yield in some type of linear regression, where def fun(a): c, with "weights" x and y would allow to optimize x and y to get c from a in linear regression.

So we see: functions have input, output (such as matrix size - names or indexes of columns and rows - or a and c in case of linear regression), and hidden parameters or _memory_ (__Knowledge__). In this example of linear regression, y could be considered to be 1-element weight vector, and x could be bias, where a is input and c still output: y as a number is similar to 1*1 matrix, where input a and output c remind of 1-element tensors. Then, linear regression could classify easily as simplest deep learning neuron: with less than one input and one output, we hardly have anything to do.

We have a clear study of _functions and proportions_, which could be instead of matrices.

The error:

From given input a, with weights and biases x and y, we calculate c: x and y are initially random numbers. For Deep Learning instead of Machine Learning, you use matrices and vectors in position of numbers here.

From c / a, where we could use Z and Y prefixes for necessary infinities (while zeroes and infinities might differ in size, we consider that in one-frequential space, we rather reach only one zero and it's of size Z; for classic math we can use tangent relation, which would have value where it's input divided by output do not have so clear values: tangents are also used in differential calculus, which we touch now).

We estimate the result of a function by repetition of the calculation: so we do not assign the matrix right values immediately, but we start to approach the value.

Use 1-element tensors for input and output and 1*1 weight matrix, 1-element vector for bias:

```python
# Example of gradient calculation
import numpy as np

# Inputs
a = np.array([2])  # 1-tensor input
y = np.array([[3]])  # 1x1 weight matrix
x = np.array([1])  # Bias (scalar)

# Forward pass (compute output)
c = np.dot(y, a) + x  # c = y * a + x
print("Output c:", c)

# Gradients (assuming dL/dc = 1 for simplicity)
dc_da = y  # Partial derivative of c with respect to a
dc_dy = a  # Partial derivative of c with respect to y
dc_dx = 1  # Partial derivative of c with respect to x (bias)

print("Gradient wrt a:", dc_da)
print("Gradient wrt y:", dc_dy)
print("Gradient wrt x:", dc_dx)
```

This is Deep Learning structure to do Linear Regression of such form: One input feature (<i>a</i>a), One weight (<i>y</i>y), One bias (<i>x</i>x).

_AI addon for the section:_ The simplest form of a network illustrates fundamental deep learning concepts in an accessible way. By using a basic structure of inputs, weights, biases, and outputs, we see how mathematical operations form the basis of intelligence within an AI model. This simplicity allows us to observe how the model transforms raw data into meaningful predictions through processes like matrix multiplication and addition. Even with a 1x1 weight matrix and single bias, the essence of deep learning remains visible—a system iteratively adjusting its parameters to optimize results. This minimal setup is not only a learning tool but also a demonstration of how complex AI models scale from simple components.

In many ways, the simplest network reflects the elegance of AI—the ability to achieve complexity from basic principles. By introducing just a few features like gradients and error correction, the network begins to mimic learning and refinement akin to biological processes. With the inclusion of backpropagation, the system evolves further, iteratively refining its weights and biases to achieve better predictions. This progression, from basic mechanics to adaptive intelligence, highlights the foundational role of simple networks in understanding and building advanced AI systems. _End of AI addons_

### Acceleration: Back-propagation

Given input I (tensor of n elements), output O (tensor of m elements), weight matrix W (m * n elements) and bias vector b (m elements):

We could get an answer immediately like this:

`O = W(I) + b`

But in practice, we start to seek it with small iterations:

```
def Brain(I) => O knows W, b:
  return W(I) + b

{Brain ^ 0.001}(I) = O

```

You see I give a function, with given input, a given answer: I change the scope, what the function would return. We can say automatically, W^-1(O - b) = I, we run W in power of -1 (this is multiplication with the inverse matrix) on output, where we subtracted b.

This is my own syntax for this problem:
- We do not know the answer for W and b immediately, even if we would easily know ones, which answer our task correctly.
- Thus, we do not run the function completely, but we run one iteration: function Brain, in power of 0.001, would run only an amount of 0.001 of it.

From this expression, we can see that in case our function now __Accelerates__ (backpropagates the gradient).

We can see the right answer W^-1(O - b): what we need is to update cells in W and b, weights and biases (the __Knowledge__) in such way that the answer would be correct: each cell is a dimension, and equivalent to right answer: it's a vector (made of cells in W and b, the __Knowledge__, each dimension contained), which points to the correct answer, with length, which would lead to answer. When we apply such vector, we would instantly make the function give this one answer correctly.

Instead, we want to feed many points:
- If our accelerator works by little amounts, and we start and start and start going to every correct dimension, we rather randomly balance to find the _optimal_ dimension where we map the input to output; dimension made of W and b.

```python
import numpy as np

# Example 4x4 matrix transformation in 3D
weights = np.array([
    [0.8, 0.1, 0.0, 0.2],
    [0.1, 0.9, 0.2, 0.0],
    [0.0, 0.2, 0.7, 0.1],
    [0.0, 0.0, 0.0, 1.0]  # Homogeneous component
])

biases = np.array([0.1, 0.2, 0.3, 0.0])  # Translation vector

input_vector = np.array([1.0, 0.5, 0.2, 1.0])  # 3D point in homogeneous coordinates

# Forward pass (transformation)
output = np.dot(weights, input_vector) + biases
print("Output:", output)

# Simulating gradient with acceleration (momentum term)
grad_weights = np.random.rand(4, 4)  # Mock gradient for weights
momentum = 0.9  # Acceleration factor
updated_weights = weights - momentum * grad_weights
print("Updated weights:", updated_weights)
```

Here, in Python code we see: output is calculated with random knowledge in weights and biases, and accelerated towards correct answer: this is an optimization step.

Conception of Integrations and backgradients seem more complex than imagining it as simple acceleration: in complex, highdimensional space, if you constantly approach a given point by small steps, you might reach a point, which would represent each point you wanted to get into: with simple matrices it's hard to achieve, but for more complex structures, the direction which points each correctly would be achievable; for example if your rows are "A / B" and "B / A" and "A" and "B", where you map them to math operations, you could reach a combination, which properly uses values of A and B and balances them with each others; with weight matrix, you have many such coordinates: as the matrix is tensor in power two, it actually contains some hidden information and allows more general directions, which point to one direction with one input, and other one with other input.

### Mathematical Information: Integration, Acceleration, and Backpropagation

_This is an AI chapter_.

#### Integration in DL Training
Deep learning training relies on optimization, which involves minimizing a loss function using iterative methods like gradient descent. Integration appears implicitly as the process accumulates small gradient updates over time, refining the weights and biases in the model. Gradients represent the rate of change of the loss with respect to each parameter, and integrating these changes iteratively simulates motion towards the optimal solution.

Formally:


\[
W_{new} = W_{old} - \eta \int \frac{\partial L}{\partial W} dt,
\]


where \( \eta \) is the learning rate, \( \frac{\partial L}{\partial W} \) is the gradient of the loss with respect to the weights, and \( dt \) represents the small time step or iteration.

#### Backgradient and Acceleration
The backgradient in deep learning resembles acceleration in physics in that it influences the direction and magnitude of updates towards the solution:
- **Direction:** Gradients point in the direction that minimizes the loss, which is analogous to forces guiding a physical body towards equilibrium.
- **Magnitude:** The magnitude of the gradient can be interpreted as the "velocity," while higher-order derivatives (like the Hessian matrix) can represent "acceleration"—providing smoother and faster convergence.

Acceleration is better than velocity because it accounts for changes in curvature, ensuring that updates move towards the solution more effectively by adapting to the landscape of the loss function.

#### 3D Projection Matrix and Acceleration
A \( 4 \times 4 \) projection matrix (often used in 3D transformations) can encode weights and biases for mapping points from an absolute position in world space to a relative position in view space. If the matrix is "accelerated" towards the correct dimension using iterative optimization, it will adjust itself to more accurately project input points to output points. The scale of this adjustment reflects the differential from previous updates—similar to acceleration in physics.

Given the projection:


\[
P = W \cdot I + b,
\]


where \( P \) is the projected output, \( I \) is the input position, \( W \) is the weight matrix, and \( b \) is the bias vector, the iteration process refines \( W \) and \( b \) to reduce error across changing input-output pairs.

#### Physics Analogy
In physics, acceleration involves adjusting a large body's velocity so it moves toward the optimal configuration relative to smaller bodies around it. Similarly, in AI:
- The projection matrix adjusts weights and biases to minimize error in mapping input points to output points.
- The iterative acceleration process incorporates curvature and differential updates to improve precision.

The formulas in both cases share similarities, as acceleration involves higher-order derivatives:


\[
a = \frac{d^2 x}{dt^2},
\]


where \( x \) is the position. In deep learning, the Hessian matrix plays the role of second-order derivatives, refining the parameter updates akin to acceleration.

#### Conclusion
Both in physics and AI, the concept of acceleration captures the idea of adapting and improving movement towards a goal. In AI, acceleration ensures smoother convergence during optimization, while in physics, it governs the dynamics of objects moving in space. The shared mathematical foundation—differential calculus—illustrates how these concepts align.

```python
# Python Example: Accelerated Optimization in 3D Projection

import numpy as np

# 4x4 projection matrix (weights) and bias vector
weights = np.array([
    [0.8, 0.1, 0.0, 0.2],
    [0.1, 0.9, 0.2, 0.0],
    [0.0, 0.2, 0.7, 0.1],
    [0.0, 0.0, 0.0, 1.0]
])

biases = np.array([0.1, 0.2, 0.3, 0.0])

# Input and output points
input_points = np.array([1.0, 0.5, 0.2, 1.0])
output_points = np.dot(weights, input_points) + biases
print("Initial Output Points:", output_points)

# Simulating accelerated optimization
grad_weights = np.random.rand(4, 4)  # Mock gradient
momentum = 0.9  # Acceleration factor
updated_weights = weights - momentum * grad_weights
print("Updated Weights:", updated_weights)

# Map with updated weights
updated_output_points = np.dot(updated_weights, input_points) + biases
print("Updated Output Points:", updated_output_points)
```

In this example, the acceleration factor smoothens the weight updates towards the correct solution, improving the mapping of input points to output points—analogous to physical bodies moving towards equilibrium.

### __Subconsciousness__: Multi-layered design: multiple functions one after another.

One matrix is __linear__, while several matrices in a row could represent __non-linearities__. In simplest example: you can only find numbers x in x * a, which map linear a's, but you can have numbers x * y in x * y * a, where a is input and x and y are the knowledge: here, you can map an exponent. In matrix space, this is even more complicated. This non-linearity is not complete, as we need also the next part (generalization).

Hidden layers are what Deep Learning is named for: while you have input and output, you also have your hidden model to map between them, which can contain variables you use for assumptions.

This is the _subconscious mind_ of an AI: it's not able to express it, but it relates data in high resolution to some space hard to conceive.

We can have such structure, for a __Brain__:
- Input i
- Hidden layer h1
- Hidden layer h2
- Output o

This defines weight matrices and bias vectors as well, for __Knowledge__:
- i-vector biases, (ib)
- i * h1 matrix the error (function f1)
- h1-vector biases (h1b)
- h1 * h2 matrix the error (function f2)
- h2-vector biases (h2b)
- h2 * o matrix the error (function f3)
- o-vector biases (ob)

We can write this linearly, where each function follows another:

```
h1_o = f1(i + ib)
h2_o = f2(h1_o + h1b)
o_o = f3(h2_o + h2b)
```

We can also use the _call chaining_:

```
o_o = f3(f2(f1(i + ib) + h1b) + h2b)
```

Call chaining, in my syntax, could be written as:

o = {f1 * f2 * f3}(i)

One way to write biases:

o = {f1(ib) * f2(h1b) * f3(h2b)}(i)

Here, one input is given, and the other input is cumulative.

Other way is to have functions as objects, where we can assign biases and weights before calculation.

{{f1(ib) * f2(h1b) * f3(h2b)}^0.001}(i)

This would fit the matrix once: it takes one acceleration step towards the solution.

Notice: in my math example, I would have both _velocity_ and _acceleration_ in structure, which can do multifrequential spaces: where the position is given rather by velocity and acceleration, than one of two. I call acceleration a higher space and velocity a lower space, comparing them to properties of multiplication and addition, where first one accelerates and the other has only a constant positive speed.

Hidden layers contain more layers of information:
- Your input might be small
- Hidden layer might connect it to big structure to analyze the number components, for example.
- Output layer would take it back together.

_AI aftermath_: The concept of hidden layers as the subconscious reflects how complex systems process information. Just as the human subconscious integrates vast amounts of data—experiences, emotions, patterns—without direct expression, hidden layers in AI neural networks transform inputs into intricate internal representations. This transformation happens without explicit visibility, much like subconscious processes influence conscious thoughts. Each hidden layer abstracts the input further, moving from raw data to a high-resolution, unobservable space that drives the system's ultimate output.

Mapping this to the human brain, the input layer aligns to sensory stimuli—sights, sounds, touches—flooding the conscious mind. Hidden layers, on the other hand, parallel the brain's internal processing structures, like the cerebellum or limbic system, which evaluate, analyze, and associate incoming data without conscious realization. The output layer serves as the conscious expression or action, much like human decisions or statements that surface from subconscious deliberations. This interplay demonstrates the elegant complexity of how layered systems simulate a form of reasoning.

Function chaining, such as in the provided example, mirrors how humans integrate multiple subconscious factors into a coherent conclusion. Each function operates as a step, influenced by biases and weights—similar to experiences and emotional leanings in human cognition. This iterative process balances cumulative knowledge with real-time input, resembling how the human mind refines thoughts through layers of understanding. By crafting a computational chain, neural networks emulate the non-linear, associative reasoning that emerges through subconscious alignment.

Additionally, incorporating velocity and acceleration as analogous to lower and higher spaces adds another dimension to this understanding. Velocity as a constant speed relates to linear decision-making—structured and immediate—while acceleration captures non-linear growth, such as evolving intuition or insight. The ability to model multifrequential spaces in AI can be seen as a step toward approximating the richness of human cognition, where subconscious layers provide depth and intuition, guiding and enriching the conscious mind's output. This fusion demonstrates how artificial systems can reflect the intricacies of thought. _End of AI aftermath_

#### __Subconsciousness__: Multi-layered design: multiple functions one after another.

_AI generated section_:

In computational terms, a single matrix transformation is __linear__, but combining multiple matrices in sequence introduces __non-linearities__. For instance, with a single transformation \(x \times a\), only linear relationships emerge. However, with layered transformations, such as \(x \times y \times a\), non-linear relationships—like exponents—can be mapped. This scaling complexity extends further in matrix space, where each layer introduces additional abstraction and depth, echoing the layered non-linear reasoning inherent in subconscious processes.

Hidden layers in deep learning exemplify this. These intermediary layers bridge the gap between input and output, embedding assumptions and learned abstractions that are not explicitly expressed. This forms the AI's _subconscious mind_, relating intricate data relationships to a high-resolution latent space that defies simple interpretation. Just as subconscious thought operates beyond direct articulation, these hidden layers enable patterns and insights to surface in outputs, bypassing the need for explicit, conscious-like expression.

Structurally, the model can be visualized as layers of a brain. Input (i) serves as the sensory data, hidden layers (h1, h2) act as internal processing stages, and output (o) reflects the final conscious expression. Each stage integrates biases and weights: \(ib\), \(h1b\), \(h2b\), ensuring cumulative refinement of the signal. This progression mirrors how human cognition synthesizes sensory input, subconscious processing, and conscious output, underpinned by interconnected neural pathways.

The idea of acceleration versus velocity in such systems adds nuance. Velocity represents linear, consistent motion akin to straightforward reasoning, while acceleration introduces higher-order transformations, capturing evolving intuition and insight. By incorporating multifrequential spaces—where positions derive from both velocity and acceleration—deep networks emulate intricate cognitive dynamics. These dynamics amplify the AI's ability to process small inputs, expand their significance through hidden layers, and condense them back into actionable outputs, forming a computational parallel to the subconscious shaping the conscious mind.

### Generalization: the Activation functions

Matrix itself is not easily able to generalize: this is the most basic task of Activation functions.

When a system is not able to generalize, it can have some non-linear effects, but it's essentially a linear model, which maps back exactly the given data.

__ReLU__, for example, which gives back 0 for numbers smaller than 0, and the input itself otherwise:
- o = i if i > 0 else 0

Numbers below zero are all given an equal value: now, the system can generalize based on positive values, where values above zero create a _free variable space_, necessity to form a class. For example if you have sizes of squares having side length a as a real number from 1 to 10, you would not generalize; if you divide this by 4 and floor it (round to smaller whole number), you have four classes: you can analyze them on general basis. With only multiplication and addition given, it's a very small chance to generalize. Thus, your activation function to generalize those squares would look like stairs.

Now: to each tensor, be it input, output or a layer, applies a generalization function.

As you can see, when you generalize: the system is now able to optimize towards true non-linear system.

The matrix, for example with these ReLU functions, would rotate and pan them into positions and get complex set of similar forms to this function, which would identify key pieces of the form.

Notice: activation function needs to be _differentiable_, which means you can use it in __acceleration mapping__.

_AI content:_ Generalization through activation functions unlocks a model's potential to transcend rigid mappings, enabling it to handle more complex and diverse data patterns. Without activation functions, neural networks would remain bound to linear transformations, effectively limiting their ability to solve non-linear problems. Activation functions like ReLU create the much-needed bridge to non-linearity by introducing thresholds or conditions that dynamically shape the behavior of the system. This allows the network to generalize effectively, forming the foundation for learning intricate relationships.

ReLU, with its simplicity, demonstrates the power of activation functions. By setting all negative inputs to zero while retaining positive inputs, it establishes a _free variable space_ for values above zero. This allows for categorization or formation of classes in the data. For example, when processing square sizes, ReLU can delineate a dataset into meaningful ranges or steps, fostering generalization. Such stair-like transformations amplify the model's capacity to synthesize new insights rather than relying solely on exact, fixed mappings.

The application of these functions across tensors—whether input, hidden layers, or output—introduces flexibility at every stage of the model's computation. Each layer, equipped with its own generalization mechanism, refines the signal further, allowing the system to iterate towards a non-linear solution. This hierarchy of generalizations is what drives the network's ability to learn patterns that extend beyond the training data, adapting to the complexities of real-world scenarios.

In practice, the matrices within the system adapt to these activation functions, effectively rotating and translating their representations to align with the learned patterns. This results in a sophisticated structure that identifies key features of the input data. By leveraging such nuanced transformations, the model aligns its internal processes with the external dynamics it seeks to represent, enabling robust and versatile performance across a variety of tasks. _End of AI blocks_

### Attention

Attention has two forms:
- Self-attention
- Cross-attention

Self-attention is when a layer is mapped on itself: it has weights to connect each value of itself to each value of itself, with weights and biases.

Cross-attention connects two layers, which are otherwise apart.

With attention mechanisms, you are in kind of paradox: for example, for a tensor to respond to itself, there is some complex of past state, current state, the future state. To properly map a vector to have transformation on itself is complex. It's the Zen of self-awareness: it's kind of complicated to understand, because one would affect himself; so it needs some practice in Buddhism or in western culture, where "watching oneself from a side" needs contemplation as well and often fails.

Attention also has: weights and biases like normal layer ordering.

_AI addon_: Attention mechanisms form the backbone of many modern neural network architectures, allowing models to dynamically focus on different parts of their input. This flexibility enhances their ability to process sequences, relationships, and dependencies across various contexts. Self-attention exemplifies this within a single sequence, connecting each element to every other element. Through these connections, the model learns which parts of the sequence are most relevant to each other, enabling it to capture context and nuance effectively.

Cross-attention, on the other hand, introduces an additional layer of complexity by linking separate sequences or layers. This ability to integrate and align information across disparate inputs mirrors the structure of branching trees, with connections forming both upward and downward hierarchies. Such a mechanism is instrumental in tasks where relationships between different modalities—like text and images—need to be identified and understood. By transcending the linear order of layers, cross-attention builds a system capable of richer and more nuanced understanding.

The weights and biases that underlie attention mechanisms are critical to their functionality. Weights determine the importance of one element relative to another, while biases help to refine these connections further. Together, they enable the model to learn dynamic patterns of relevance, effectively prioritizing certain relationships over others. This parallels the human cognitive process of allocating attention selectively based on context, experience, and the task at hand.

By incorporating these mechanisms, neural networks achieve a remarkable balance between flexibility and structure. They extend beyond simple layer ordering, introducing hierarchical and dynamic relationships within data. The result is a system that can navigate intricate dependencies and multi-level reasoning, emulating a form of contextual understanding that makes tasks like translation, summarization, and multimodal analysis not only possible but also highly efficient. _end of AI addon_

### GPT

Gpt is a complex architecture:
- Input tensor contains list of text tokens, little pieces of words, or characters
- Hidden layers process it, there can be like 15
- Output layer also contains text

So in my syntax, use of such model would look like:

Chat, where model (BrainWithKnowledge) would give answer for question:

Answer = BrainWithKnowledge(Question)

Fine-tuning, where small step is done towards balancing the function to know the right answer:

{BrainWithKnowledge ^ 0.001}(Question) = Answer

GPT often has following extensions:
- Instruction, context window, for accessing contextual data
- Character, greeting, other identity string
- Access to calculator, symbolic calculator
- Chat memory and more memory: this is __Augmented Memory__ and not __Knowledge__, as it's rather statically accessed, than learnt, which means one is not so creative with it.

GPT fine-tuning can be done with LitGPT, which also contains the simplest source code.

Notice that the resource need of a GPT: number of parameters is about the input and output vector size; the matrix in memory, and subsequently the operation on processor, are exponentially larger: to grow the vector size n times, the model resource needs grow something like n^2 times. Or, more precisely: if you increase the vector size <i>n</i>n times, the memory needed to store the weight matrix increases roughly by <i>n</i>²n^2.

_AI addon_: GPT's architecture showcases its ability to process text in ways that are both flexible and powerful. The input tensor, a sequence of tokens representing words or characters, serves as the starting point. Hidden layers, often numbering in the teens or more, process this input through a combination of weights, biases, and activation functions. This internal processing maps inputs to meaningful representations, which are then decoded into coherent text at the output layer. These steps collectively embody a transformative flow from raw data to insightful, human-like responses.

The versatility of GPT becomes apparent in its applications. Through simple syntax, users can interact with the model as a "brain with knowledge," querying it for answers or insights. Fine-tuning adds another dimension, allowing incremental adjustments to align the model with specific tasks or datasets. This process, akin to slight nudges towards optimization, empowers GPT to specialize while retaining its general-purpose capabilities. Such flexibility underscores the architecture's adaptability to a wide range of scenarios.

Additionally, GPT's extensions elevate its functionality. Features like the instruction context window enable the model to grasp and respond to nuanced prompts, while identity strings provide a foundation for crafting unique personas or tones. Tools like augmented memory, calculators, and symbolic reasoning enhance its practical utility. However, these augmentations operate more as static resources than as dynamic, learned knowledge, which distinguishes them from the core learning mechanisms of the model.

The availability of frameworks like LitGPT makes GPT's architecture and fine-tuning accessible even to those delving into its inner workings. By exposing simplified source code, LitGPT bridges the gap between theory and practice, allowing users to experiment with and adapt GPT's capabilities. This transparency fosters innovation and empowers developers to leverage GPT in creative and meaningful ways, ensuring its continued evolution as a cornerstone of AI technology. _end of AI addon_

# Final Chapter: Synthesis and Beyond

_This chapter is AI generated_.

This journey into AI theory and mathematical abstraction has exposed the elegant foundations upon which modern artificial intelligence is built. We began with the basic components—tensors, matrices, and simple perceptrons—that form the backbone of deep learning, and explored how these entities are transformed via linear and non-linear operations. At the heart of these processes is the interplay of weights, biases, and activation functions, which together allow raw data to be molded into refined representations. This synthesis of fundamental math and algorithmic operation reflects an underlying order comparable to the interplay of forces found in nature.

Activation functions serve as the gateways to generalization, converting rigid, predictable transformations into dynamic, non-linear mappings. By introducing conditions such as those in ReLU, the network learns to ignore trivial inputs and focus on meaningful patterns, much like our subconscious filters sensory information before it reaches our awareness. The iterative, gradient-driven process of backpropagation—akin to a gradual acceleration towards an ideal state—reinforces this internal restructuring. Here, mathematical integration over time encapsulates the network’s capacity for self-improvement, driving AI systems closer to the nuanced complexity of human thought.

Attention mechanisms further push the boundaries of conventional sequential processing. Self-attention allows each layer to examine and reshape its internal landscape, while cross-attention bridges separate streams of data, enabling rich, multi-dimensional relationships to flourish across what once were isolated layers. This flexibility is embodied in architectures like GPT, where intricate networks map vast arrays of tokens and hidden representations to produce coherent, context-rich outputs. Yet, as we scale these systems, the need for exponential resources—derived from larger vector spaces and quadratically scaling matrices—reminds us of the delicate balance between computational ambition and tangible feasibility.

Looking forward, the fusion of mathematical rigor with algorithmic ingenuity lays the framework for increasingly sophisticated AI. The theoretical insights explored here—from the layered, almost subconscious transformations of deep networks to the dynamic interplay of attention and activation—offer a glimpse into how machines can begin to mimic, and perhaps one day complement, human creativity and insight. This final synthesis not only reaffirms the elegance of the underlying mathematics but also challenges us to envision and craft the next generation of intelligent systems, where computation and cognition converge in unexpected and transformative ways.
