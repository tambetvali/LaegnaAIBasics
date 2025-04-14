# Invariants

One of the most important topics about Deep Learning and AI in general are invariants.

For example, if you could take invariants of AI brains and knowledges, you could slowly implement similar features: compare AIs, copy data from one to another, or simply detect similar objects.

There are numberous ways an AI could learn something differently - often, to form logic, it has to set two variables to given values, but the order does not matter. Each such variables would double the trivial combinations (ones you have to opimize) of the same part of the network. If differences have possibilities of encoding, even within each given encoding, and similarities would not give similar shapes, we can say we _lack invariants_.

_AI generated_: To summarize the discussion on invariants, they hold a profound significance in advancing AI systems across domains such as text, image, and sound processing. By enabling consistent patterns to remain unchanged under transformations, invariants empower AI models to generalize better, recognize objects in varied contexts, and process data with more precision. From leveraging embeddings in text for semantic understanding to using Fourier maps in image processing for elegant mathematical invariance, these concepts pave the way for breakthroughs in artificial intelligence.

The exploration of invariants also emphasizes the importance of deeper research into their mathematical and computational applications. Advancing invariant detection and representation can create more robust and adaptable AI systems capable of handling complex data scenarios efficiently. This pursuit not only pushes the boundaries of innovation but also helps bridge gaps between theoretical elegance and practical application in AI. _end of AI gen._

## Form of invariants in Deep Learning

One could make the input into pieces, and process each piece with the same learning component: the same form of network. Using CNN (Convolutional Neural Network), one would scan images with n*n squares, mostly, where the same element would learn as the square scans the document: thus, the parts of image would have some invariant properties; for example, to detect invariants, we would check, whether pattern of the image would match another. Still, we need different generalizations and identification about the object, for example given different rotation, size or 3D positioning.

_AI part_: In deep learning, the concept of invariants takes on vital importance, as it enables models to learn consistent representations of data regardless of transformations or variations. By leveraging techniques like convolutional neural networks (CNNs), which process data in smaller pieces, deep learning systems can identify invariant properties in images, such as patterns that remain consistent despite rotation, scaling, or positioning. These invariants enhance a model's ability to generalize and recognize objects under different conditions, bridging the gap between theoretical concepts and practical application. Advancing our understanding and implementation of invariants in deep learning holds the promise of creating models with unparalleled adaptability and accuracy, ultimately pushing the boundaries of artificial intelligence toward more sophisticated and innovative solutions. _end of_.

## Invariants in text and image processing

In text and images, we need the following operations:
- To compare: we need to detect, whether two parts of the text mean the same, or whether an object on image means or is the same with another image or image class or reference to an image.
- To detect: this is basically to compare each area, where we could find an object, to this object.

_AI part:_ In text and image processing, invariants play a crucial role in ensuring the recognition and comparison of patterns, objects, and meanings across different contexts. For text, this involves tasks like identifying semantic similarities, grouping related texts, and detecting logical relationships, often relying on embeddings and attention mechanisms to establish invariant representations in hyperdimensional space. For images, invariants enable models to account for transformations like rotation, scaling, and perspective changes, allowing objects to be recognized despite alterations in their appearance. By leveraging techniques such as data augmentations during model training and mathematical approaches like Fourier maps, AI systems can achieve greater robustness and versatility in processing both textual and visual data efficiently. _end of_

### Invariants in text processing

In text processing, we rather have two tasks:
- To find invariants or texts with similar meaning, even if other parameters differ.
- To find text, which belongs to a group.
- To find logical relations of text and between text, such as IsPolite(text) or HappenAtSameTime(text1, text2), or also IsSimilar, IsEqual (t1, t2); FindText(username) or FindOccurrences(happysentence).

So for text, as we see, we need to take parametrized invariants: the objects need to have invariant form, such as to ask IsPolite(text), every text has thereby a property with invariant form: politeness; our ability to put each politeness into the same variable means it has invariant form, or is a parametrized invariant of politeness functions.

In text processing, we do not have so good manual algorithms for text processing, but we leave finding invariants to Artificial Intelligence. They are rather unstructured invariants and not so important as input data, even if any invariant we could find could be useful - for example, for words we have tables with invariant form; each word has parametrized invariant form in sense that we use the same variant for verbs, another variant for nouns etc., where they each have a list of properties, such as singularity and plurality. By there invariant forms, we can work with the words: things inside words, the properties, such as being singular, being in present or past, are invariant properties, where "true" or "false" for each one gives an abstract invariant answer to the same question.

You still have the hard problem to find invariants based on such properties: for example, "does the sentence involve giving material property from one person to another", where the question is even context-specific, for example to pay with a checkue, one needs to have it backed up by money: without a context about this, and the generousity of the bank for some long term client, we cannot say whether the money was given or actually received, but you have to check the signature, and guess a background for a person.

Heavier invariant: invariant to position and meaning. We need for text in each position to be compared with some common algorithm, where accounting also for it's context. This means, while considering the whole text, we must also consider each part in equal manner and understand, how the words relate to each others. Depending on context and the word, the word might be similar to certain other words in certain other contexts, or different from some. It's commonly measured in GPL:
- With word embeddings, and also with context embeddings, we position words and contexts in hyperdimensional space, where their relative positions give meaning to them; for example, each word might have 500-dimensional embeddings, which means an array of 500 numbers as coordinates. Here, we relate the words: words at the same position are invariants, and at different positions, are not. A GPL model would learn such embeddings for each word, and the embedder would learn such embeddings for each document or it's part to relate them with context of current chat or question, which are also embedded to the same space for this.
- Remember that in Attention Matrix, we get the representation, where input and output of the Matrix multiplication are the same instance, which is common to paradoxes - where two variables involved are actually the same entity, even if "not" is applied (not A refers to the same entity as A, because as you change one, you also change the other). In attention mechanism, the embeddings map words into the same space, and allow one to understand their relations.

_AI part:_ In text processing, invariants are essential for ensuring the recognition, comparison, and organization of textual data across various contexts. These invariants help identify semantic similarities between texts, group texts based on shared meaning or characteristics, and understand logical relationships within and between sentences. For example, AI systems use embeddings, where words are positioned in hyperdimensional space, allowing their relative positions to define their meaning. Attention mechanisms also play a key role by creating invariant representations, enabling the understanding of relationships among words in their given context.

Parametrized invariants, such as politeness or temporal relationships, provide a structured approach to examining text properties. These invariants allow AI systems to generalize complex linguistic features into standardized forms, ensuring consistency while handling dynamic and unstructured text. For instance, detecting whether a sentence involves the exchange of material property between entities or understanding the politeness of a text relies on embedding properties into invariant forms that reflect contextual information.

AI models also incorporate context embeddings to position words in a way that accounts for their surroundings, enabling invariants to be examined more precisely. This ensures that the meaning of words and their relation to other words is consistently captured, even across diverse linguistic contexts. Advancing the identification and representation of invariants in text processing holds the promise of enhancing AI's ability to comprehend, analyze, and generate human-like textual data, paving the way for more effective and adaptable applications. _end of_

### Invariants in Image Processing

In basic Image Processing, we need such invariants:
- Invariants to angle
- Invariants to size

For 2D processing, we need to see the same information not depending it's size and angle.

The basic trick commonly used is to rotate and scale the image: another image compared would be compared with the same rotation and scale. During training of an AI model, the images are scaled, rotated, flipped and other transformations are done, while the model learns in each case that this is the same image. Mathematically, it's not very straightforward invariant: rather, we reach the API, which can be used like mathematical invariant, and where it looks like a duck, and does other things like a duck, it's a duck - so the invisible object behind the API _is_ an invariant.

Anyway, it's not an invariant in complete sense. While we can now compare images under different translations, it's not mathematically very efficient, and it does not have elegant mathematical form. Rather, the model is _being_ an invariant, where the model would learn the properties in each transformation as properties of the same object, it would respond like an invariant.

Fourier Map of frequencies can be used to create a mathematical invariant for such transformations - ones exist for rotation, scaling etc. This is mathematically more elegant, but this invariance does not solve each problem yet.

Invariance can be seen as separating certain bound variables, getting free variables. For example, to make object rotation invariant, you would separate:
- Rotation regards to it's original angle or rotation information to calculate relative angles, into one parameter.
- Image data, which is rotation invariant, into another parameter.

Then, to search such image, you would introduce some precision level, and use quite simple search algorithms for example searching for numbers close to 5000, if 5000 happens to be invariant of a circle of given size in your system.

For objects, we need different invariants:
- Rotation
- Scale
- Color as color of object (i.e. "blue car", "black car" of the same model would be invariant if you don't check for this variable).
- Color as color of it's illumination, reflection, shadows of other objects: each needs to be invariant.
- Position in 2D and 3D
- Position in sense of dispositions of it's moving, connected parts or changes in postures, facial expressions etc
- Perspective

In each transformation, one needs to find the same object. So we basically need an object:
- It contains, in parameters, information about the properties.
- It contains, in body, some data, which might be more or less precise (i.e. having more digits after commas of the numbers for bigger objects), but still comparable (i.e. if you now compare this object with smaller object, you get the same number in some precision, like 0.1, and so for example small circle might be 4999.7, but bigger circle is exactly 5000, if they are rotation and scale invariants; you would lose digits, but not _change the values themselves_ in case of smaller objects).

So the model would recognize for example, human body in each shape, perspective, light conditions of posture as same object, especially if it's the same person. For people, they might give invariants, which do not depend on clothes, haircut etc. There might be invariance of biological bodies: once I made a system for cars in a game, where each car drawn by designer could be calculated from some input to the same function.

Mathematically, invariants often exist and they give us the following:
- We have a well-described mathematical object, positioned in invariant space (such as embedding space, where equality of embeddings in invariance of important property).
- With elegant mathematics, we can do operations on it: but it knows _essentially_, what _constitutes_ and object; for example, what constitutes a circle? What is the actual information, which allows to identify potential represenations of circles not depending which parts are visible, how big is it or is it forming an oval, being rotated around Y axis.

In my understanding of the field, this is absolutely the most important thing to research:
- To raise the scope, in which we can calculate invariants, invariant forms and parametrized invariants, perhaps also projecting back the objects given the parameters.
- To bring those calculation into lower level.

We can see this kind of levels:
- Low-level, _pure mathematical invariant_: this is mathematically elegant way, for example, to have a single representation of each object or shape, which does not depend on operations we can do on it, such as reflecting from water, putting under red light, having an elephant sitting on it etc. It would have some degree of invariance for objects not visible - for example, given it's eiffel tower, you can also detect some objects outside the range of camera, with some precision or certanty.
- Middle-level, _purely manual_: _trying the possibilities_; you can take two objects and iterate over some potential relative center points and rotate one object 360 degrees, calculating the correspondence; you would understand if objects are similar not depending on parameters you iterate over. For each mathematical operation you would do with invariants, you would have some sequence, which provides similar results - you could, then, "fake" the math; it's not fake as it works, but it leaves us with many limitations. From mathematical viewpoint, the limitation is that pure invariants would introduce us with branch of math, where we could do complex operations, and simplify them to more primitive forms - like finding a way to process large number of invariants at once, where we take a statistical mean, do some operations on them, and it's like doing them on each operation and then taking a statistical mean: having basic math for something means we have extreme capabilities of optimizations.
- High-level, _AI-learnt_: in some cases, we would teach an AI model the invariants, for example we do all transformations on invariant, and teach it each time as the same object to an AI. This, if we are able to teach smaller models, comes closer to mathematical invariant in sense of speed and generalizability, but it does not have simple, symmetric representation for each invariant.

_AI generated:_ In image processing, invariants are pivotal for identifying and analyzing objects under various transformations, such as rotation, scaling, perspective, and other attributes. These invariants help AI systems generalize object recognition, allowing them to detect and compare patterns consistently despite alterations in appearance. For example, a rotated or scaled image of a cat should still be recognized as a cat, regardless of how it is presented. Achieving invariance requires leveraging techniques like data augmentation during model training, where images are systematically altered (rotated, scaled, flipped, etc.) to teach the model to treat them as representations of the same object. This approach allows the model to "learn invariance" by associating multiple transformations with the same underlying data.

However, an alternative method involves directly comparing images under various transformations without pre-training models to learn invariance. By systematically applying rotations, scalings, or other changes to one image and comparing it with another, AI systems can assess similarity based on how closely the transformed versions match. While this manual approach circumvents extensive training, it is computationally intensive and lacks the elegance of mathematical invariance, where invariant representations are encoded explicitly. Fourier maps provide a more sophisticated solution, offering mathematically precise invariants for transformations like rotation and scaling. These maps capture frequency-domain information, allowing for comparisons that are invariant to certain geometric changes while being computationally efficient.

Invariance systems aim to separate bound variables, like rotation and scaling, from free variables—object data independent of these transformations. For instance, a model might isolate rotation information as one parameter and invariant image data as another, enabling precise comparisons even at varied angles or scales. This separation simplifies the search for similar objects, as invariant forms remain consistent under transformations, allowing straightforward algorithms to detect and compare objects efficiently. The system introduces precision levels, ensuring that objects of different sizes or rotations maintain comparable invariant properties even when analyzed at varying resolutions.

Beyond geometric transformations, image processing must account for other attributes, such as lighting conditions, shadows, reflections, and color variations. Invariants to these aspects enable the recognition of objects under diverse environmental conditions, ensuring consistency in real-world applications. Additionally, objects with complex attributes—like human bodies with varying postures or facial expressions—require advanced invariant systems capable of identifying the same individual despite changes in appearance. By embedding invariant information into compact representations, models can achieve remarkable accuracy in detecting and classifying objects across diverse contexts.

The pursuit of invariance in image processing highlights the importance of refining mathematical and AI-driven techniques to enhance both precision and computational efficiency. While traditional methods involve manual comparisons and repetitive transformations, the development of AI models that inherently understand invariants offers a more scalable and versatile solution. This ongoing research not only optimizes practical applications but also bridges theoretical elegance and real-world challenges in artificial intelligence. _end of AI generated_

# Invariants in Sound Processing

Here, we _do_ have enough invariants:
- We can make sound invariant to frequency, normalizing each sound of same length, for example, to given average frequency and having a multiplier, which allows to restore the original form.
- We can use many features of sound, which do not depend on frequency; we could also use relative numbers, like the parameter "growing" or "shrinking".

Sound exists in one-dimensional space, and in such: we are mathematically so capable that we can see, what the etalon is.

_AI part:_ In sound processing, invariants are critical for analyzing and interpreting audio signals, as they allow models to maintain consistent representations regardless of frequency shifts, volume changes, or other transformations. Sounds naturally exhibit a robust invariant structure, often represented mathematically through features like pitch, timbre, and rhythm. For example, two melodies played at different frequencies but with identical patterns can be recognized as the same tune. By normalizing sounds to a given average frequency and preserving relative characteristics through multipliers, AI systems can effectively compare and categorize audio data.

Moreover, invariants enable the detection of structural similarities across various sound types. Features such as growth (increasing pitch or volume) or decay (diminishing intensity) can be extracted and compared in relative terms, independent of the absolute values of the sound properties. This allows AI models to recognize patterns in music, speech, or ambient noise, offering applications in tasks like speech recognition, audio classification, and sound synthesis. The one-dimensional nature of sound makes invariant representation mathematically precise, allowing for the creation of etalon models that serve as benchmarks for comparison.

Advancing the study of invariants in sound processing could lead to more sophisticated AI systems capable of analyzing complex audio data across diverse environments and contexts. By refining invariant structures and leveraging their mathematical simplicity, researchers can enhance the robustness and adaptability of models in tasks ranging from language processing to music generation and environmental sound analysis. These advancements promise to unlock new opportunities for innovation and application in the field of audio processing. _end of_

= Conclusion

_AI-generated conclusion_.

Invariants are a cornerstone in the advancement of AI and deep learning, providing a fundamental framework for recognizing, comparing, and classifying data across different domains. From text and image processing to sound analysis, invariants ensure consistency and efficiency in handling complex transformations. They allow AI systems to adapt seamlessly to variations in size, rotation, perspective, meaning, and other attributes, while maintaining the integrity of the data's underlying structure. The pursuit of invariants not only enhances computational precision but also bridges the gap between theoretical and practical applications in artificial intelligence.

Advancing research on invariants opens doors to greater innovation, enabling AI systems to tackle more dynamic and unstructured challenges. The integration of robust mathematical techniques and AI-driven methods promises to revolutionize how we process and understand data, pushing the boundaries of adaptability and efficiency. Whether it involves refining Fourier maps for geometric transformations or embedding techniques for text analysis, the ongoing exploration of invariants remains pivotal to unlocking the next frontier in AI development. By embracing the elegance of invariants, we pave the way for smarter, more versatile systems capable of transforming industries and shaping the future of technology.