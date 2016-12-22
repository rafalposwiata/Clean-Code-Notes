# Smells and Heuristics

### Comments

- Inappropriate Information

  Comments should be reserved for technical notes about the code and design.

- Obsolete Comment

  A comment that has gotten old, irrelevant, and incorrect is obsolete.

- Redundant Comment

  A comment is redundant if it describes something that adequately describes itself.

- Poorly Written Comment

  A comment worth writing is worth writing well.

- Commented-Out Code

### Environment

- Build Requires More Than One Step

  Building a project should be a single trivial operation.
  
- Tests Require More Than One Step
  
  You should be able to run all the unit tests with just one command.

### Functions

- Too Many Arguments
  
  Functions should have a small number of arguments (max 3).
  
- Output Arguments

  Output arguments are counterintuitive.
  
- Flag Arguments

  Boolean arguments loudly declare that the function does more than one thing. They are confusing and should be eliminated.
  
- Dead Function

  Methods that are never called should be discarded.
  
### General

- Multiple Languages in One Source File

- Obvious Behavior Is Unimplemented

  Any function or class should implement the behaviors that another programmer could reasonably expect.
  
- Incorrect Behavior at the Boundaries

  Every boundary condition must be found and test.
  
- Overridden Safeties

  Never turn off failing tests and tell yourself you’ll get them to pass later.
  
- Duplication

  Don’t Repeat Yourself!
  
- Code at Wrong Level of Abstraction
  
  It is important to create abstractions that separate higher level general concepts from lower level detailed concepts.
  
- Base Classes Depending on Their Derivatives

  In general, base classes should know nothing about their derivatives.
  
- Too Much Information

  Well-defined modules have very small interfaces that allow you to do a lot with a little.
  
- Dead Code

  Dead code is code that isn’t executed. When you find dead code delete it from the system.
  
- Vertical Separation

  Variables and function should be defined close to where they are used.
  
- Inconsistency

  If you do something a certain way, do all similar things in the same way.
  
- Clutter

  Keep your source files clean, well organized, and free of clutter.
  
- Artificial Coupling

  Things that don’t depend upon each other should not be artificially coupled.
  
- Feature Envy

  The methods of a class should be interested in the variables and functions of the class they belong to, and not the variables and functions of other classes.
  
- Selector Arguments

  In general it is better to have many functions than to pass some code into a function to select the behavior.
  
- Obscured Intent

  We want code to be as expressive as possible.
  
- Misplaced Responsibility

  Code should be placed where a reader would naturally expect it to be.
  
- Inappropriate Static

  If you want a function to be static, make sure that there is no chance that you’ll want it to behave polymorphically.
  
- Use Explanatory Variables

  More explanatory variables are generally better than fewer.
  
- Function Names Should Say What They Do

  If you have to look at the implementation (or documentation) of the function to know what it does, then you should work to find a better name or rearrange the functionality.
  
- Understand the Algorithm

  Before you consider yourself to be done with a function, make sure you understand how it works.

- Make Logical Dependencies Physical

  If one module depends upon another, that dependency should be physical, not just logical.
  
- Prefer Polymorphism to If/Else or Switch/Case

- Follow Standard Conventions

  Every team should follow a coding standard based on common industry norms.

- Replace Magic Numbers with Named Constants

- Be Precise

  When you make a decision in your code, make sure you make it precisely. Know why you have made it and how you will deal with any exceptions.
  
- Structure over Convention

  Enforce design decisions with structure over convention.
  
- Encapsulate Conditionals

  Extract functions that explain the intent of the conditional.
  
- Avoid Negative Conditionals

- Functions Should Do One Thing

- Hidden Temporal Couplings
  
  Structure the arguments of your functions such that the order in which they should be called is obvious.
  
- Don’t Be Arbitrary

  Have a reason for the way you structure your code, and make sure that reason is communicated by the structure of the code.
  
- Encapsulate Boundary Conditions

  Boundary conditions are hard to keep track of. Put the processing for them in one place.
  
- Functions Should Descend Only One Level of Abstraction

- Keep Configurable Data at High Levels

  For example create class with all configuration constants.
  
- Avoid Transitive Navigation

  In general we don’t want a single module to know much about its collaborators. More specifically, if A collaborates with B, and B collaborates with C, we don’t want modules that use A to know about C.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
