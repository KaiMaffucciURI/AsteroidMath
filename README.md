# AsteroidMath
A small module written in the Asteroid language to help me do Calculus II homework. Skip to the "global functions" section if you simply want to know how to use

## Integral structure:
### Member variables
- a - lower bounds of definite integral
- b - upper bounds of definite integral
- f - the integrand; function (as a first-class citizen) being integrated
- Dx - change (delta) in x value until next rectangle is calculated (for when calculating the integral); calculated in the constructor
- p - number of parts the function is split into for the approximation
### Member functions
- Constructor - uses multi-dispatching to see if “parts” parameter (integer) is given or not (determines how many times the integral is being split up for approximations: in other words, how many rectangles there are)
- calc_Dx - re-calculates the change in x value (Dx) based on bounds and number of parts
- dec_b - calculates a new upper bound by decrementing Dx from the old upper bound; returns new Integral instance

## Global functions
I could've made these methods of the Integral structure, but I elected not to for now. The module works as-is, and any efforts to simplify it is extra work I unfortunately don't have time for right now. 
Each of these functions takes an Integral instance as input. They also have recursive versions of itself inside of it which includes an additional "total" parameter, but that's irrelevant for someone simply trying to use the module rather than modify it. 
- left(I:%Integral) - left-hand integral approximation. 
- right(I:%Integral) - right-hand integral approximation. 
- mid(I:%Integral) - midline integral approximation. 
- trap(I:%Integral) - trapezoid integral approximation. 
- simp(I:%Integral) - integral approximation using Simpson's rule. 
