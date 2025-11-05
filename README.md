# blogtest
Made using StackEdit



<!-- This is an HTML comment and will be hidden in the rendered output. 
## Outline:
1) Mention what we have done
2) Challenge to print as an exercise.
3) Note the difficulty
4) Introducing: F Strings
5) Mention it can work for ANY expression, but remind not to overdo it.

-->

## A Practical Guide to Python's f-Strings

In your Python journey so far, you've gotten comfortable with storing data in variables and using the `print()` function to display it.

A typical script might start like this:
 
``` python
# Storing some basic data
course_name = "Deep Learning"
student_count = 35
is_advanced = True

```

In this code, we've defined a string, an integer, and a boolean. Printing them one by one is straightforward, but what about combining them?

**Here's an exercise:** Try to print a single, descriptive sentence using all three variables above, like this:

> "The 'Deep Learning' course has 35 students and its advanced status is True."

----------

### The "Old Way" and Its Difficulties

Your first attempt probably involves **string concatenation** using the `+` operator.

You might have written something like this:

```python
# The 'old way' using concatenation
course_name = "Deep Learning"
student_count = 35
is_advanced = True

message = ("The '" + course_name + "' course has " + 
            str(student_count) + 
            " students and its advanced status is " + 
            str(is_advanced) + "."
          )

print(message)

```

This code works, but it's a pain to write and even harder to read.

-   You have to manually add space characters (`" "`).
    
-   You must remember to convert `student_count` and `is_advanced` to strings using `str()`. (That is, Python needs to know these integers are being treated as Strings.)
    
-   The mix of variables and `+` signs makes it hard to see the final sentence structure.
    

----------

### Introducing: f-Strings (Formatted String Literals)

To solve this problem, f-strings were introduced in Python 3.6. They provide a clean, concise, and efficient way to embed Python expressions directly inside a string.

Let's rewrite our example using an f-string:

```python
# The modern way using an f-string
course_name = "Deep Learning"
student_count = 35
is_advanced = True

message = f"The '{course_name}' course has {student_count} students and its advanced status is {is_advanced}."

print(message)

```

The output is identical, but the code is far superior. To use f-strings, you:
1) Place an **`f`** before the opening quote `"`, then
1) Use curly braces `{}` to plug your variables right where they belong. 

From the Python docs:

> Formatted string literals (also called f-strings for short) let you include the value of Python expressions inside a string by prefixing the string with `f` or `F` and writing expressions as `{expression}`.

----------

### The Real Power: Expressions and Format Specifiers

The curly braces `{}` in an f-string can hold **any valid Python expression**. This unlocks a whole new level of formatting power.

This means, that you can perform mathematical calculations, or even call functions, right inside the curly braces. 

For example:

```python
num = 2
print(f"The square of {num} is {num**2}")
```

Be sure not to overdo it though! Remember, code readability matters.

**Avoid this:**

```python
# Hard to read!
print(f"Final score: { (some_value * other_value) / my_func(my_list) + offset }")

```

#### Self-Documenting Expressions

We will end with a little known use-case of f-strings.
This is one of the best features for debugging. If you add an equals sign (`=`) at the end of your expression, the f-string will print the expression itself _and_ its value.

```python
bugs = "roaches"
count = 13
area = "living room"

# Using the = specifier for debugging
print(f"{bugs=} {count=} {area=}")

```

This saves you from typing `print(f"bugs = {bugs}")`. 
The output:

 ` bugs="roaches" count=13 area="living room"` 

tells you everything you need to know.

---
