# 3D Math

# Table of Content

```
Introduction
1. Cartesian Coordinate Systems: 1D mathematics, 2D Cartesian Space, 3D Cartesian Space, Odds and Ends, Exercises
2. Vectors: Mathematical Definition of Vector, and Other Boring Stuff, Geometric Definition of Vector, Specifying Vectors with Cartesian Coordinates, Vectors versus Points, Negative a Vector, Vector Multiplicaiton by a Scaler, Vector Addition and Subtraction, Vector Magnitude (Length), Unit Vectors, The Distance Formula, Vector Dot Product, Vector Cross Product, Linear Algrebra Identities, Exercises
3. Multipl Coordinate Space: Why Bother with Multiple Coordinate Spaces, Some Useful Coordinate Spaces, Basis Vectors and Coordinate Space Transformation, Nested Coordinate Spaces, In Defense of Upright Space, Exercises
4. Introduction to Matrices: Mathematical Definition of Matrix, Geometric Interpretation of Matrix, The Bigger Picture of Linear Algebra, Exercises
5. Matrices and Linear Transformation: Rotation, Scale, Orthographic Projection, Reflection, Shearing, Combining Transformation, Classes of Transformations, Exercises
6. More on Matrices: Determinant of a Matrix, Inverse of a Matrix, Orthogonal Matrices, 4*4 Homogeneous Matrices, 4*4 Matrices and Perspective Projection, Exercises
7. Polar Coordinate Systems: 2D polar Space, Why Would Anybody Use Polar Coordinates, 3D Polar Space, using Polar Coordinates to Specify Vectors, Exercises
8. Rotation in Three Dimension: What Exactly is "Orientation", Matrix Form, Euler Angles, Axis-Angle and Exponential Map Representation, Quaternions, Comparison of Methods, Converting between Represetnation, Exercises
9. Geometric Primitives: Representation Techniques, Lines and Rays, Spheres and Circles, Bounding Boxes, Planes, Triangles, Polygons Exercises
10. Mathematical topics from 3D Graphics: how Graphics Works, Viewing in 3D, Coordinate Spaces, Polygon Meshes, Texture mapping, The Standard Local Lighting Model, Light Sources, Skeletal Animation, Bump Mapping, The Real-Time Graphics Pipeline, Some HLSL Examples, Further Reading, Exercises
11. Mechanics 1: Linear Kinematics and Calculus: Overview and Other Expectation-Reducing Remarks, Basic Quantities and Units, Average Velocity, Instananeous Velocity and the Derivative, Acceleration, Motion under Constant Acceleration, The Integral, Uniform Circular Motion, Exercises
12. Mechanics 2: Linear Rotation Dynamics: Newton's Three Laws, Some Simple Force Laws, Momentum, Impulsive Forces and Collisons, Rotational Dynamics, Real-Time Rigid Body Simulators, Suggested Reading, Exercises
13. Curves in 3D: parametric Polynomial Curves, Polynomial Interpolation, Hermite Curves, Bezier Curves, Subdivision, Splines, Hermite and Bezier Splines, Continuity, Automatic Tangent Control, Exercises
14. Afterword: What Next? Exercises
A Geometric Tests: Closest Point on 2D Implicit Line, Closest Point on a Parametric Ray, Closest Point on a Plane, Closest Point on a Circle on Sphere, Closest Point in an AABB, Interesction Tests, Intersection of Two implicit Lines in 2D, Intersection of Two Ray in 3D, intersection of a Ray and Plane, Intersection of an AABB and Plane, Intersection of Three Planes, Intersection of Ray and a Circle or Sphere, Intersection of Two Circles or Spheres, Intersection of a Sphere and AABB, Intersection of a Sphere and a Plane, Intersection of a Ray and a Triangle, Intersection of Two AABBs, Intersection of a Ray and an AABB
Answers to the Exercises
```

(MY): Study Plan: Chapter 1-6, 8, Focus on Chapter 10

## Introduction
Who Should Read This Book
* This book is about 3D math, the geometry and algebra of 3D space. It is designed to teach you how to describe objects and their positions, orientations, and trajectories in 3D using mathematics. This is not a book about computer graphics, simulation, or even computational geometry, although if you plan on studying those subjects, you will definitely need the information here.
* This is not just a book for video game programmers. We do assume that a majority of our readers are learning for the purpose of programming video games, a diverse audience in mind. If you're a programmer or interest in learning how to make video games, welcome aboard! if you meet neiter of these criteria, there's still plenty for you here. We have made every effort to make the book useful to designers and technical artists. Although there are several code snippets in the book, they are (hopefully) easy to read even for nonprogrammers. Most important, even though it is always necessary to understand the surrounding concepts to make sense of the code, the reverse is never true. We use code samples to illuminate how ideas can be implemented on a computer, not to explain the ideas themselves.
* The title of the book says it is for "game development", but a great deal of the material that we cover is applicable outside of video games. Practicall anyone who wants to simulate, render, or understand a three-dimensional world will find this book useful. While we do try to provide motivating examples from the world of video game development, since that is our area of expertise and also our primary target audience, you won't be left out if the last game you completed was Space Quest. If your interests lie in more "grown up" things than video games, rest assured that this book is not filled with specific examples from video games about head-shots or severed limbs or how to get the blood spurt to look just right.

Why you Should Read This Book
* This book has many unique features, including its topic, approach, authors, and writing styles.
* `Unique Topic` This book fills a gap that has been left by other books on graphics, linear algebra, simulation, and programming. It's an introductory book, meaning we have focused our efforts on providing thorough coverage on fundamental 3D concepts--topics that are normally glossed over in a few quick pages or relegated to an appendix in other books (because, after all, you already know all this stuff). We have found that these very topics are often the sticking points for beginners! in a way, this book is the mirror image of gluing together books on graphics, physics, and curves. Whereas that mythical conglomeration would begin with a brief overview of the mathematical fundamentals, followed by in-depth coverage of the application area, we start with a thorough coverage of the math fundamentals, and then give compact, high-level overviews of the application areas.
* This book does try to provide a graceful on-ramp for beginners, but that doesn't mean we'll be stuck in the slow lane forever. There is plenty of material here that is traditional considered "advanced" and taught in upper-level of gradual classes. In reality, these topics are specialized more than they are difficult, and they have recently become important prerequisites that need to be taught earlier, which is part of what has driven the demand for a book like this.
* `Unique approach` All authors think that they strike the perfect balance betweeen being pedantic and being chatty in order to best reach their audience, and we are no exception. We recognize, however, that the people who disagree with this glowing self-assessment will mostly find this book too informal (see the index entry for "stickler alert"). We have focused on perspicuous explanations and intuition, and sometimes we have done this at the expense of rigor. Our aim is to simplify, but not to oversimplify. We lead readers to the goal thorugh a path that avoids the trolls and dragons, so why begin the journey by pointing them all out before we've even said what our destination is or why we're going there? However, since we know readers will be crossing the field on their own eventually, after we reach our goal we will turn around to point out where the dangers lie. But we may sometimes need to leave certain troll-slaying to another source, especially if we expect that your usual path won't take you near the danger. Those who intend to be on that land frequently should consult with a local for more intimate knowledge. This is not to say that we think rigor is unimportant; we just think it's easier to get rigor after intuition about the big picture has been established, rather than front-loading every discussion with definitions and axioms needed to handle the edge cases. Frankly, nowadays a reader can pursue concise and formal presentations free on wikipedia.org or Wolfram MathWorld (mathworld.wolfram.com), so we don't think any book offers much worth paying for by dwelling excessively on definitions, axioms, proofs, and edge cases, especially for introductory material targeted primarily to engineers.
* `Unique authors` Our combined experience bring together academic authority with in-the-trenches practical advice. Fletcher Dunn has 15 years of professional game programming experience, with around a dozen titles under his belt on a variety of gaming platforms. He worked at Terminal Reality in Dallas, where as principal programmer he was one of the architects of the Infernal engine and lead programmer on BloodRayne. He was a technical director for the Walt Disney Company at Wideload Games in Chicago and the lead programmer for Disney Guilty Party, IGN's E3 2010 Family Game of the Year. He now works for Valve Software in Bellevue, Washington. But his biggest claim to fame by far is as the name sake of Corporal dunn from Call of Duty: Modern Warfare 2
* Dr. Ian parberry has more than a quarter century of experience in research and teaching in academia. This is his sixth book, his third on game programming. he is currently a tenured full professor in the Department of Computer Science & Engineering at the University of North Texas. he is national known as one of pioneers of game programming in higher education, and has been teaching game programming classes at the University of North Texas continuously since 1993.
* `Unique writing style` We hope you will enjoy this math book (say what?) for two reasons. Most important, we want you to learn from his book, and learning something you are interested in is fun. Secondarily, we want you to enjoy reading this book in the same way that you enjor reading a work of literature. We have no delutions that we're in the same class as Mark Twain, or that this book is destined to become a classic like, say the Hitchhikers Guide to the Galaxy. But one can always have aspirations, Honestly, we are just silly people. At the same time, no writing style should stand in the way of the first priority: clear communication of mathematical knowledge about video games.

What You Should Know Before Reading This Book
* SKIM

Overview
* SKIM

# Chapter 1: Cartesian Coordinate System

## Intro
* SKIP

## 1.1. 1D Mathematics
SKIM

## 1.2. 2D Cartesian Space
SKIM

## 1.3. 3D Cartesian Space
* The previous sections have explained how the Cartesian coordinate system works in 2D. Now it's time to leave the flat 2D world and think about 3D space.
* It might seem at first that 3D space is only "50% more complicated" than 2D. After all, it's just one more dimension, and we already have two. Unfortunately, this is not the case. For a variety of reasons, 3D space is more than incrementally more difficult than 2D space for humans to visualize and describe. (One possible reason for this difficulty could be that our physical world is 3D, whereas illustrations in books and on computer screens are 2D.) It is frequently the case that a problem that is "easy" to solve in 2D is much more difficult or even undefined in 3D. Still, many concepts in 2D do extend directly into 3D, and we frequently use 2D to establish an understanding of a problem and develop a solution, and then extend that solution into 3D.
* This section extends 2D Cartesian math into 3D. It is divided into four major subsection.

        * Section 1.3.1 begins the extension of 2D into 3D by adding a third axis. The main concepts introduced are
                * The z-axis
                * the xy, xz and yz planes
        * Section 1.3.2 describes how to specify the location of a point in the 3D plane using Cartesian (x, y, z) coordinates
        * Section 1.3.3 introduces the concepts of left-handed and right-handed 3D coordinate spaces. The main concepts introduced are
                * the hand rule, an informal definition for left-handed and right-handed coordinate spaces
                * differences in rotation in left-handed and right-handed coordinate spaces
                * how to convert between the two
                * neither is better than the other, only different

### 1.3.1 Extra Dimension, Extra Axis
* In 3D, we require three axes to establish a coordinate system. The first two axes are called the x-axis and y-axis, just as in 2D. (However, it is not accurate to say that these are the same as the 2D axes; more on that later.) We call the third axis (predictably) the z-axis. Usually, we set things up so that all axes are mutually perpendicular, that is, each one is perpendicular to the others. Figure 1.10 shows an example of a 3D coordinate space.
* As discussed in Section 1.2.2, **it is customary in 2D for +x to point to the right and +y point up. (Or sometimes +y may point down, but in either case, the x-axis is horizonal and the y-axis is vertical)** These conventions in 2D are fairly standardized. In 3D, however, the conventions for arrangement of thee axes in diagrams and the assignment of the axes onto physical dimensions (left, right, up, down, forwawrd, back) are not very standardized. Different authors and fields of study have different conventions. Section 1.3.4 discusses the conventions used in this book.
* As mentioned earlier, it is not entirely appropriate to say that the x-axis and y-axis in 3D are the "same" as the x-axis and y-axis in 2D. In 3D, any pair of axes defines a plane that contains the two axes and is perpendicular to the third axis. For example, the plane contains the x- and y-axes is the xy plane, which is perpendicular to the z-axis. Likewise, the xz plane is perpendicular to the y-axis, and the yz plane is perpendicular to the x-axis. We can consider any of these planes a 2D Cartesian coordinate space in its own right. For example, if we assign +x, +y, and +z to point right, up, and forward, respectively, then 2D coordinate space of the "ground" is the xz plane, as shown in Figure 1.10.

### 1.3.2 Specifying Location in 3D
* In 3D, points are specified using three numbers, x, y, z, which give the signed distance to the yz, xz, and xy planes, respectively. This distance is measured along a line parallel to the axis. For example, the x-value is the signed distance to the yz plane,  measured along a line parallel to the x-axis. Don't let this precise definition of how points in 3D are located confuse you. It is a straightforward extension of the process for 2D.

### 1.3.3. Left-handed versus Right-handed Coordinate Spaces
* As we discussed in Section 1.2.2, all 2D coordinate systems are "equal" in the sense that for any two 2D coordinate spaces A and B, we can rotate coordinate space A such that +x and +y poin in the same direction as they do in coordinate space B. (We are assuming perpendicular axes.) Let's examine this idea in more detail.
* Figure 1.5 shows the "standard" 2D coordinate space. Notice that the difference between this coordinate space and "screen" coordinate space shown Figure 1.6 is that the y-axis points in opposite directions. However, imagine rotating Figure 1.6 clockwise 180 degrees so that +y points up and +x points to the left. Now rotate it by "turning the page" and viewing the diagram from behind. Notice that now the axes are oriented in the "standard" directions like in Figure 1.5. No matter how many times we flip an axis, we can always fin a way to rotate things back into the standard orientation.
* Let's see how this idea extends into 3D. Examine Figure 1.10 once more. We stated earlier that +z points into the page. Does it have to be this way? What if we made +z point out the page? This is certainly allowed, so let's flip the z-axis.
* **Now, can we rotate the coordinate system around such that things line up with the original coordinate system? As it turns out, we can not.** We can rotate things to line up two axes at a time, but the third axes always points in the wrong direction! (If you have trouble visualizing this, don't worry. In just a moment we will illustrate this principle in more concrete terms).
* All 3D coordinate spaces are not equal, in the sense that some pairs of coordinate systems can not be rotated to line up with each other. **There are exactly two distinct types of 3D coordinate space: left-handed coordinate spaces and right-handed coordinate spaces.** If two coordinate spaces have the same handedness, then they can be rotated such that the axes are aligned. If they are of opposite handedness, then this is not possible.
* What exactly do "left-handed" and "right-handed" mean? The most intuitive way to identify the handedness of a particular coordinate system is to use, well, your hand! With your **left hand**, make an 'L' with your thumb index finger. Your `thumb` should be pointing to your `right`, and your `index finger` should be pointing `up`. Now extend your third finger so it points directly forward. **You have just formed a left-handed coordinate system.** Your thumb, index finger, and third finger point in the +x, +y, and +z directions, respectively. This is shown in Figure 1.12. Now perform the same experiment with your right hand. Notice that your index finger still points up, and your third finger points forward. However, with your right hand, your thumb will point to the left. This is a right-handed coordinate system. Again, your thumb, index finger, and third finger point in the +x, +y, and +z directions, respectively. A right-handed coordinate system is shown in Figure 1.13.
* Try as you might, you can not rotate your hands into a position such that all three fingers simultaneously point the same direction on both hands. 
* Left-handed and right-handed coordinate systems also differ in the definition of "positive rotation". Let's say we have a line in space and we need to rotate about this line by a specified angle. We call this line an axis of rotation, but don't think that the word axis implies that we're talking only about one of the cardinal axes (the x-, y- or z-axis).  An axis of rotation can be arbitrarily oriented. Now, if you tell me to "rotate 30 degree about the axis", how do I know which way to rotate? We need to agree between us that one direction of rotation is the positive direction, and the other direction is the negative direction. The standard way to tell which is which in a left-handed coordinate system is called the left-hand rule. First, we must define which way our axis "points". Of course, the axis of rotation is theoretically infinite in length, but we still consider it having a positive and negative end, just like the normal cardinal axes that define our coordinate space. The left-hand rule works like this: put your left hand in the "thumbs up" position, with your thumb pointing toward the positive end of the axis of rotation. Positive rotation about the axis of rotation is in the direction that your fingers are curled. There's a corresponding rule for right-handed coordinate spaces; both of these rules are illustrated in Figure 1.14.
* As you can see, in a left-handed coordinate system, positive rotation rotates clockwise when viewed from the positive end of the axis, and in right-handed coordinate system, positive rotation is counter clockwise. Table 1.1  shows what happens when we apply this general rule to the specific case of the cardinal axes.
* **Any left-handed coordinate system can be transformed into a right-handed coordinate system, or vice versa. The simplest way to do this is by swapping the positive and negative ends of one axis.** Notice that if we flip two axes, it is the same as rotating the coordinate space 180 degree about the third axis, which does not change the handedness of the coordinate space. Another way to toggle the handedness of a coordinate system is to exchange two axes.
* Both left-handed and right-handed coordinate systems are perfectly valid, and despite what you might read in other books, neither is "better" than the other. People in various fields of study certainly have preferences for one or the other, depending on their backgrounds. For example, **some newer computer graphics texts and more math-oriented linear algebra people tend to prefer right-handed coordinate systems.** Of course, these are gross generalizations, so always check to see what coordinate system is being used. The bottom line, however, is taht in many cases it's just a matter of a negative sign in the z-coordinate. So, appealing to the first law of computer grahpics in Section 1.1, if you apply a tool, technique, or resource from another, web page, or article and it doesn't look right, try flipping the sign on the z-axis.

### 1.3.4 Some Important Conventions Used in This Book
* When designing a 3D virtual world, several design decision have to be made beforehand, such as left-handed or right-handed coordiante system, which direction is +y, and so forth. The map makers from Dyslexia had to choose from among eight different ways to assign the axes in 2D. **In 3D, we have a total of 48 different combinations to choose from; 24 of these combinations are left-handed, and 24 are right-handed**.
* Different situations can call for different conventions, in the sense that certain tasks can be easier if you adopt the right convention. Usually, however, it is not a major deal as long as you establish the conventions early in your design process and stick to them. (In fact, the choice is most likely thrust upon you by the engine or framework you are using, because very few people start from scratch these days). All of the basic principles discussed in this book are applicable regardless of the convention used. For the most part, all of the equations and techniques given are applicable regardless of convention, as well. However, in some cases there are some slight, but critical, differences in application dealing with left-handed versus right-handed coordinate spaces. When those differences arise, we will point them out.
* We use a left-handed coordinate system in this book. The +x, +y, and +z directions point right, up, and forward, respectively, as shown in Figure 1.15. In situations where "right" and "forward" are not appropriate terms (for example, when we discuss the world coordinate space), we assign +x to "east" and +z to "north".

### 1.4 Odds and Ends
* In this book, we spend a lot of time focusing on some crucial material that is often relegated to a terse presentation tucked away in an appendix in the books that consider this material a prerequisite. We, too, must assume a nonzero level of mathematical knowledge from the reader, or else every book would get no further than a review of first principles, and so we also have our terse presentation of some prerequisites. In this section we present a few bits of mathematical knowledge with which most readers are probably familiar, but might need a quick refresher.
* [SM] Summation and product notation
* [SM] Inteval notation
* [SM] Angles, degrees, and radians
* [SM] Trig function


### 1.5. Exercise
SKIP

===

# Chapter 2: Vectors
* MY: Important primer to LA
* Vectors are the formal mathematical entities we use to do 2D and 3D math. The word vector has two distinct but related meanings. Mathematics books, especially those on linear alebra, tend to focus on a rather abstract definition, caring about the numbers in a vector but not necessarily about the the context of actual meaning of those numbers. Physics books, on the other hand, tend towards an interpretation that treats a vector as a geometric entity to the extent that they avoid any mention of the coordinates used to measure vector, when possible. It's no wonder that you can sometimes find people from these two disciplines correcting one another on the finer points of "how vectors really work". Of course the reality is that they are both right (But the perspective taken by physics textbooks is probably the one that's more appropriate for video game programming, at least in the beginning), and to be proficient with 3D math, we need to understand both interpretations of vectors and how the two interpretations are related.
* This chapter introduces the concept of vectors. It is divided into the following sections.

        * Section 2.1 covers some of the basic mathematical properties of vectors
        * Section 2.2 gives a high-level introduction to the geometric properties of vectors
        * Section 2.3 connects the mathematical definition with the geometric one and discusses how vectors work within the framework of Cartesian coordinates
        * Section 2.4 discusses the often confusing relationship bewtwen points and vectors and considers the rather philosophical question of why it is so difficult to make absolute measurements
        * Section 2.5-2.12 discuss the fundamental calculations we can perform with vectors, considering both the algebra and geometric interpretations of each operation
        * Section 2.13 presents a list of helpful vector algebra laws

### 2.1 Mathematical Definition of Vector, and Other Boring Stuff
* **To mathematicians, a vector is a list of numbers.** Programmers will reorganize the synonymous term array. Notice tthat the STL template array class in C++ is named vector, and the basic java array container class is java.util.Vector. So mathematically, a vector is nothing more than an array of numbers.
* Yawn... If this abstract definition of a vector doesn't inspire you, don't worry. Like many mathematical subjects, we must first introduce some terminology and notation before we can get to the "fun stuff".
* Mathematicians distinguish between vector and scalar (pronounced "SKAY-lur) quantities. You're already the expert on scalars--scalar is the technical term for an ordinary number. We use this term specifically when we wish to emphasize that a particular quantity is not a vector quantity. For example, as we will discuss shortly, "velocity" and "displacement" are vector quantities, whereas "speed" and "distance" are scalar quantities.
* The dimension of a vector tells how many numbers the vector contains. Vectors may be of any positive dimension, including one. **In fact, a scalar can be considered a 1D vector.** In this book, we primarily are interested in 2D, 3D and (later) 4D vectors.
* When writing a vector, mathematicians list the numbers surrounded by square brackets, for example, [1,2,3]. When we write a vector inline in a paragraph, we usually put commas between the numbers. When we write it out in an equation, the commas are often ommitted. In either case, **a vector written horizontally is called a row vector**. Vectors are also frequently written vertically

$$
\begin{bmatrix}
1 \\
2 \\
3 \\
\end{bmatrix}
$$

* A vector written vertically is known as a column vector. This book uses both notations. For now, the distinction between row and column vectors won't matter. **However, in Section 4.1.7 we discuss why in certain circumstances the distinction is critical.**
* When we wish to refer to the individual components in a vector, we use subscript notation. In math literature, integer indices are used to access the elements. For example $v_1$ refers to the first element in $\boldsymbol{v}$. However, we are specifically interested in 2D, 3D and 4D vectors rather than vectors of arbitrary dimension n, so we rarely use this notation. Instead, we use x and y to refer to the elements in a 2D vector; x, y, and z to refer to the element in a 3D vector; and x, y, z, w to refer to the elements in a 4D vector. This notation is shown below.

$$
\begin{equation*}
a = 
\begin{bmatrix}
1 \\
2 \\
\end{bmatrix}
\end{equation*}
$$

$$
\begin{equation*}
b = 
\begin{bmatrix}
3 \\
4 \\
5 \\
\end{bmatrix}
\end{equation*}
$$

$$
\begin{equation*}
c = 
\begin{bmatrix}
6 \\
7 \\
8 \\
9 \\
\end{bmatrix}
\end{equation*}
$$

* Notice that the components of a 4D vector are not in alphabetical order. The fourth value is w (Hey, they ran out of letters in the alphabet!)
* Now let's talk about some important typeface conventions that are used in this book. As you know, variables are placeholder symbols used to stand for unknown quantities. In 3D math, wee work with scalar, vector and (later) matrix quantities. In the same way that it's important in a C++ or Java program to specify what type of data is stored by a variable, it is important when working with vectors to be clear what type of data is represented by a particular variable. In this book, we use different fonts for variables of different types:


* Scalar variables are represented by lowercase Roman or Greek letters in italics: $\it{a}$, $\it{b}$, $\it{x}$, $\it{y}$, $\it{z}$, $\it{\alpha}$,$\it{\beta}$, $\it{\gamma}$,
* Vector variables of any dimension are represented by lowercase letters in boldface: $\bf{a}$, $\bf{b}$, $\bf{x}$, $\bf{y}$, $\bf{z}$, $\bf{\alpha}$,$\bf{\beta}$, $\bf{\gamma}$
* Matrix variables are represented using uppercase letters in boldface: $\bf{A}$, $\bf{B}$, $\bf{M}$, $\bf{R}$

page 34

# Chapter 3: Multiple Coordinate Spaces
* MY: Very important. Talks about different spaces

# Chapter 4: Introduction to Matrices
* MY: The full chapter to LA

# Chapter 5: Matrices and Linear Transformation
* MY: The continuition of last chapter

# Chapter 6: More on Matrices
* MY: The advanced stuff. 
* SKIP

# Chapter 7: 2D Polar Space
* MY: Never need it. SKIP

# Chatper 8: Rotation in Three Dimensions
* MY: Will be useful for debugging

# Chapter 9: Geometric Primitives
* MY: All about drawing shapes. Skip

# Chapter 10
* MY: About the advanced stuff. Look deeper into skeletal animation

# Chapter 11: Mechanics 1: Linear Kinematics and Calculus
* MY: About physics. SKIP

# REST OF THE BOOKS
* SKIP

MY: So to finish this book. I just need to read through chapter 2, 3, 4, 8, 10