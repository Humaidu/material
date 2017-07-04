# ![Intro to Python: Labs](../blob/master/assets/img/logo-128.png?raw=true)

Welcome to the Python lab! Work through this sheet in pairs, making sure that you understand
each bit of code before you move on.

If you get something wrong, let us know! Other people may have done the same thing; maybe you
can help them.

## 1: Basics
Try the following in the Python REPL. What do they do?
* `print "hello"`
* `print 'hello'`
* `print hello`

Let's do some maths!
* `4 + 5`
* `8 * 3`
* `4 / 3`
* `4.0 / 3`
* `3 + 5 * 9`

Adding Strings?
* `"abc" + "def"`
* `"hello" + " " + "world"`
* `"123" + "5"`

Variables!
* `first = "hello"`
* `second = "world"`
* `first + " " + second`
* `type(first)`
* `print first`

User input?
* `name = raw_input("What is your name?")`
* `type(name)`
* `age = int(raw_input("What is your age?"))`
* `type(age)`

Write some code that:
* Converts 32 degrees to radian (HINT: `math.pi`!).
* Asks the user for a _radius_ then prints out the surface area and volume of a sphere.
* Tells the user what time of day it is, in a nice format.
* Splits a sentence into its words
* Joins a list of words into a sentence. Find TWO ways to do this!


## 2: Functions
In a file called `person.py`:
* Write a function called `get_age` that asks the user for their age, and returns it as an `int`
* Write another function called `get_name`, which does the same but for the users age
* Call both these functions and tell the user what you know about them!

In a file called `my_maths.py`:
* Write a function called `calculate` that takes one `string` and two `int` arguments. The string should be "add", "subtract", "multiply" or "divide", or any of those words in uppercase. The `calculate` function should then do the right operation with the two numbers and return the result.

## 3: Loops
In a file called `while_loop.py`, write the following code:

    i = 0
    while(i < 10):
        i = i + 1
        print i

* Explain what's happening. Can you print the numbers from 7 to 19?
* Can you print all the `even` numbers between 12 and 20?
* Write a function called `evens` that takes two numbers and prints all the even numbers between them.
* Write another function, `reverse_evens`, that does the same but prints the numbers in reverse.

In a file called `for_loop.py`, write the following code:

    for i in range(1,11):
        print i

* Explain what's happening. What is `i`? What is `range`?

Type the following code:

    for j in [1, 2, 3]:
        print j

* Explain what's happening. How can you use `range` to do the same thing?
* What's the `type` of `[1, 2, 3]`? What `type` of data does `range` return?
* Can you use `range` to return the list `[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]`?
* Write a function to produce the following output:

```
    ****
    ****
    ****
    ****
```

* Write a function to produce the following output:

```
    *
    **
    ***
    ****
    ***
    **
    *
```

* Write a function that takes a `string` and returns `True` if the string contains the letter 'a', otherwise returns `False`. Don't use Python's `in` operator, write the code yourself!

* Change your function to work for _any_ letter.

* Use your function in _another_ function that returns `True` if the string contains the letters 's' and 'm', otherwise returns `False`.

## 4: If
In a file called `conditional.py`, write the following code:

    i = 8
    if(i % 2):
        print "Odd Number"
    else:
        print "Even Number"

* What is `%`? What is `i % 2`?
* Write a function called `evens` that takes a list of numbers and returns the sum of all the even numbers
* Copy your function that asks for a persons age. Tell them if you think they're old or not!
* Write a function that asks the user for the *year* they were born, then calculates roughly how old they are. 
* Find out the definition of a leap year. Write a function that asks the user the year they were born, and then tells them if that year was a leap year.

## 5: Lists
In a file called `lists.py`, type the following code:

    list = []
    list.append(‘a’)
    print list

* Explain what each line does.
* Using the python you've already learned, write a function that:
  * Takes two arguments - the min and max values
  * Returns a list of the even numbers between min and max

## 6: Tuples
In the file `tuples.py`, write two functions:
* `partition` should take a number and return a 2-tuple, with the number on the *left* if it's even, and
on the *right* if it's odd. The other slot should be filled with the constant `None`
* `partition_list`, which takes a list of numbers and returns a 2-tuple of *lists*. It should use your
`partition` function to split the input list into the odd numbers and the even numbers.

# Book
Great work! If you got this far, you'll know enough Python to finish the programme. Well done!

If you want to learn more, there's a great book that's available for *free* online. Take a look: [Think Python, by Allen B. Downey](http://greenteapress.com/wp/think-python/)

# Stretch
Well done if you've come so far. Below are some harder labs that will take more time. Everyone should hopefully get at least this far :)

## Stretch: Roman Numerals
Write a function that takes a number and prints out its value in *Roman Numerals*

e.g. 3 = III, 56 = LVI etc...

## Stretch: Complex numbers
Investigate the `complex` numeric type. In a file called `mandelbrot.py`, write a function called `mandelbrot`
that takes a number `n` and prints out the <a href="en.wikipedia.org/mandelbrot_set">Mandelbrot Set</a>
using ascii characters in an `n` x `n` matrix.

## Stretch: tic-tac-toe
Write a tic-tac-toe game. Firstly, it should print out an empty grid, then wait for input. Players take
turns entering coordinates in the form (x, y). The game adds a O or an X in the right square, then prints
out the grid again.

Make good use of functions to split up your code. For example, you could write a function `print_grid`
which takes the grid state as an argument and prints it to the console.

## Stretch: Write a single-player game where the computer plays against you. Are you better at Python than
you are at tic-tac-toe? :)