**Python Functions**

A function is a block of code which only runs when it is called.

A function can return data as a result.

A function helps avoiding code repetition.

When you call a function, Python creates a dedicated namespace for that function call. This namespace will hold the names you define inside the function. It’s a namespace distinct from all other existing ones, such as the global and built-in namespaces.Even when function’s local variables have the same names as outer variables, there will be no confusion or interference because they’re in separate namespaces. So, you can’t modify the function’s behavior by altering the value of a given local variable from the outside, whether by accident or on purpose.

**Calling Functions in Python**

You’ve already called a few functions so far. The syntax consists of writing the function’s name followed by a pair of parentheses, which encloses an optional series of arguments:
function_name([arguments])


Note: There’s a subtle distinction between the terms parameter and argument. Parameters are those names used in the function definition, while arguments are the concrete values that you supply for each parameter in the function call. In Python, the term argument is often used informally to refer to both.

There are mainly 2 types of Arguments in Python 

1. Positional Arguments : In the function definition, you specify a series of comma-separated parameters inside the parentheses. For example, consider the following function that computes the cost of a product and displays a message to the screen:

<img width="522" height="94" alt="image" src="https://github.com/user-attachments/assets/c1fb89ea-28d4-4d69-a84a-6236263b7409" />

Drawbacks of Positional Arguments
a) The order of the arguments in the call must match the order of parameters in the definition. If you change the order, then you may get unexpected behavior or an error
b) Positional arguments is that they can make the code hard to read at times. For example, consider the following hypothetical function call:

<img width="522" height="61" alt="image" src="https://github.com/user-attachments/assets/c4467c30-2eb3-4a1a-a0fe-25c56ac0c46e" />

2. Keyword Arguments: When calling a function, you can specify arguments in the form argument=value. This way of passing arguments to a Python function is known as using keyword arguments. For example, you can call the calculate_cost() function as shown below:

<img width="527" height="85" alt="image" src="https://github.com/user-attachments/assets/1f0e8fcd-d564-4288-a9f7-4d2b8d284a0a" />


**Note**:-When you use positional and keyword arguments in a function call, all the positional arguments must come first. Otherwise, you’ll get a syntax error.Once you’ve specified a keyword argument, you can’t place any positional arguments after it.

