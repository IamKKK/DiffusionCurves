# Project Design Documentation

## Brief

This document describes the design of this project.

## Design Principles

The design of this project should be focused on modules and applications, and 
the development should utilize modern and advanced software engineering 
methods.

 * There should be maximum orthogonality between modules.
 * There should be maximum composibility between modules.
 * Each module should have maximum reusability.
 * The development of this project should be driven by document.
 * The development of this project should be driven by test.

## Module Design

This project can be divided into following modules and sub modules:

 * Modeling
   Containing core data structures and core algorithms. Note that the data 
   structures should be consistent with the file format.

 * Rendering
   Containing naive rendering methods and some acceleration methods.

 * Interactivity
   This is not a necessary module. But it is important, since it provides a 
   graphical user interface for efficient user input to create art works based 
   on vector graphics.

## Application Design

By types of app:

 * Desktop App
 * Mobile App
 * Web App

By types of usage:

 * Vector graphics creation, with the ability of
   * Diffusion Curves
   * Vector Graphics Complex

 * Vector graphics generation from real photographs.

 * Vector graphics animation, including primitive interactions and primitive 
   deformation.

## Use cases

### Diffusion Curves

 * User can sequentially add control points to a blank sheet to get a bezier 
   curve. For a exsiting curve, user can move/delete certain control points, 
   and can also add new control points before/in/after exsiting points.

 * Given a bezier curve, user can add to it three attributes (left color, right 
   color and blurness) by adding attribute points. User can arbitrarily 
   add/delete attribute points along the curve and specify its attribute. The 
   changing of the underlinng bezier curve (for example, by adding/deleting 
   some control points) will not affect the attribute points since they are 
   fixed by parameter t (t ranges from 0 to 1 inclusive) along the curve.

 * Given a bezier curve with its attributes (if not given, default values will 
   be used), user is able to view the complete graphics generated by the 
   diffusion curve, at arbitrary zooming level.

   This involves the core algorithms of diffusion curve, i.e. solving a Poisson
   equation. Different methods are available:

   * Multigrid (indicated by the original paper)
   * Conjugate Gradient
   * Fast Multipole Method

 * (Optional) When take a curve (and its all control and attribute points) as 
   a whole, user can arbitray transform the curve by means of translation, 
   rotation along arbitray center, scaling along arbitray direction, and etc.

### Vector Graphics Complex

(To be filled in)
