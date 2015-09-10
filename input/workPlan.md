# Development Of A 3D CAD System For 3D Woven Structures



## 1. Introduction

3D Weaving is an emerging field of interest in the domain of Textile Technology. With applications  ranging from engine mountsAerospace Engineering to I beams in Civil Construction, there are several opportunities for new and exciting technological developments.

Three-dimensional, orthogonal woven fiber fabrics are woven structures containing a set of yarn or tows laying in an X-axis, Y-axis, and Z-axis. The orthogonal woven structure affects the physical properties in three planar directions as compared to a traditional woven composite form with yarns laying in only the X-axis and Y-axis. Three Dimensional woven structures can create composite materials with fiber volume fractions around 50% in both 3D unit cell and 3D orthogonal structures.

Due to the complexities and unique properties of these  structures,  it is often useful to model their behavior and appearance in software before production/testing begins. Such applications are often called CAD(Computer Aided Design) applications. Computer-aided drafting (CAD) is the use of computer systems to assist in the creation, modification, analysis, or optimization of a design.

For the design and rapid prototyping of 2D woven fabrics, several software products have been developed and are being commercially used. These include Arahne(Slovenia) ArahWeave and NedGraphic(Italy)'s fashion design tools. Such user friendly applications, however, do not exist for 3D weaving, to the best of our knowledge

Various attempts to create such applications, have, however been made. Examples include TexEng and Texgen developed by research groups in Manchester and Nottingham.

The problems with the current crop of tools mainly lies with the architecture behind them. Possibly due to the nascent level of progress in the research and the less-than-capable software engineers available, the CAD systems are often slow and buggy, often demanding ridiculous compatibility requirements. In addition to this, they are not often available across platforms like OSX and various linux distributions.

Due to these requirements, we have decided to build our own CAD system based on modern technologies which will work across platforms, while still being user friendly ,reasonably fast and stable.

In lieu of the above, we will try to begin to understand the methodologies, challenges and algorithms in building such a product.



### 1.1 Orthogonal structure

There are 3 sets of yarns in an orthogonal structure, the straight warp yarn , the straight weft yarn and the binding warp yarn.

There are 2 kinds of orthogonal structures- ordinary(where there is only one binding warp set, and enhanced with 2 binding warp sets with inverse binding weaves).

The relationship between  number of layers in warp(  $N_w$  ) and weft($N_f$) can be explained as :-

$$ N_f = N_w + 1 $$

Warp repeats Re and Rp of an orthogonal weave can be represented as :-  
$$ R_e = (N_w + t) \times B_e $$  
$$ R_p = N_f \times B_p $$

where t is 1 in case of ordinary and 2 in enhanced


### 1.2 Angle Interlock Structures



## 2.Primary Objective

To devise and develop a CAD application for 3D woven structures based on modern technologies and is user friendly.


### Sub-objectives

- 2.1 Devise a mathematical scheme for representing 3D fabric structure. This may range from a weave matrix, to other more complex statements.
- 2.2 Generate 3D models/paths of the individual yarns within the fabric and pass these to the rendering program
- 2.3 The rendering program, will now draw the entire structure for the user.
- 2.4 Allow the user to make changes to the fabric parameters and observe the changes in the model.
- 2.5 Lastly, allow the user to simulate stresses and/or compression and model the behaviour of the fabric under these conditions

## 3. Literature Review

We are referring to


## 4. Methodology

- 4.1 First, we shall create mathematical models of all 3D fabric structures that are possible. An encoding scheme will have to be created to represent a lifting plan, drafting plan, and all other parameters that may need to be represented.

    In our case, we plan on using numpy, a Python library. NumPy is an extension to the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large library of high-level mathematical functions to operate on these arrays. Due to it's speed and ability to handle multiple matrices and mathematical functions with ease, numpy seems ideal for this problem.

- 4.2 We will then send this data, packaged as a request(or stored in a file) to a server. This server will then pass on data to a rendering program, which in this case, we are planning to use webGL.

- 4.3 We are planning to use a specific library called Three.js for creating the application. This is for the simple reason that it is well documented and has been widely used in several web applications. Three.js allows the creation of GPU-accelerated 3D animations using the JavaScript language as part of a website without relying on proprietary browser plugins. This is possible thanks to the advent of WebGL.

    High-level libraries such as Three.js or GLGE, SceneJS, PhiloGL or a number of other libraries make it possible to author complex 3D computer animations that display in the browser without the effort required for a traditional standalone application or a plugin
