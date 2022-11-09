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
* Skim everything else except

#### 1.3.3. Left-handed versus Right-handed Coordinate Spaces

## 1.4 Odds and Ends
* SKIP

## 1.5. Exercises
* SKIP

===

# Chapter 2: Vectors
* MY: Important primer to LA

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