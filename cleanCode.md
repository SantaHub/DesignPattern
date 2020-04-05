# Clean Code

## Chapter 1 : Clean Code

When the code is a mess the `productivity exponentially decrease over time`. The only way to go fast is to keep your code clean, like a sushi chef keeps his table clean. For the we should accure `code-sense`, the sense for code cleanliness. 

What is clean code?
A clean code has clean variable names, clean functions and a clean class name.

The Boy Scout Rule : Keep the ground better than you found it.

## Chapter 2 : Meaningful names

- Use descriptive names, avoiding variable comments.
- Avoid giving false clues :
  - Avoid long names with small differences
  - Avoid `l` or `o` as variable names as they are similar to `1` and `0`
- Make meaningful distinciton :
  - Dont use noise characters like an alphabet or number to distinquish the variables
  - You may use `a` for local variable or `the` for functions
- Avoid noise words prefixing:
  - `nameString`, `customerObject` are redundant.
- Use Pronounceable names. 
  - So developers can discuss about the varaibles or errors.
  - Avoid the prefixes `I` for Interface. or the hungarian notations
  - prefix the fn name with the verbs like `get, post, add`.
  - use `is` for boolean functions or variables
  - use Cappropriate classes of speech for varaibles classes and functions
  - derived classes can have adjustives on them
- class names should not be verbs
- pick one word per concept
  - pick `get` over fetch, whatIs, retrieve.
  - if you have many `add` methods then consider `append` for a different use case.
- Use searchable names, avoiding single-character variables
- the length of the name can be a `proportional` to its scope
  - the `variables` name are `directly proportional` to scope
  - the `function and class` names are `inversely proportional` to scope. Since public functions are called from many places, try to give short names.
- Dont give concrete names to abstract class

## Chapter 3 : Functions

Function should be small.
Small scoped functions should have long discriptive names.
Long functions could be made into classes. 
Functions do one thing. Well.
