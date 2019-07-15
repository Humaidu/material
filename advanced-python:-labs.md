# ![Advanced Python: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

Welcome to the Advanced Python lab! Work through this sheet in pairs, making sure that you understand
each bit of code before you move on.

If you get something wrong, let us know! Other people may have done the same thing; maybe you
can help them.

## 1: Pip
Hit `ctrl`+`alt`+`t` to bring up a terminal. Using the `pip` command:
* Show a list of all the packages installed on your system. Using only terminal commands, find out how many there are.
* Use pip to install the `pandas` library. Pandas is a popular numerical library for Python. You can read about it [here](http://pandas.pydata.org/)
* Using terminal commands, find out if `beautifulsoup4` is installed. If it isn't, install it.

## 2: Filter, Map, Lambda!
Write a function (using `def`!) that takes a number and returns True if it's even. Let's call the function `is_even`

Use your `is_even` function to return only the even numbers from the following list:

    numbers = [1,56,234,87,4,76,24,69,90,135]

Now, rewrite your code to use a _lambda_: write the is_even code in-line, rather than defining and then using your function. Look at the slides for a hint.

Next, re-write your code to return all the _odd_ numbers in the `numbers` collection.

## 3: Combinations
Investigate the function called `not`. What does it do?

Using the built-in function `not` and your function `is_even`, find another way to return all the _odd_ numbers in the `numbers` collection from the previous section.

## 4: Fold
Remember that a folding operation (sometimes called _reduce_) takes a collection of data and returns one piece of data, by applying a function to all the items in order. An example might be to add up all the numbers in a list:

    total = fold(lambda item, running_total: item + running_total, [1, 2, 3, 4, 5])
    
_**hint:**_ _`from functools import reduce`_
###

Write a function called `join_strings` that takes a list of words and uses `+` to join them all together. For example:

    words = ["hello", "world"]
    helloworld = join_strings(words) # "hello world"

## 5: List comprehensions
Python has a very powerful way to perform the `map` and `filter` operations in one go: List comprehensions. The following code splits a sentence into its constituent words, we've seen this kind of code before:

```python
sentence = "the quick brown fox jumps over the lazy dog"
words = sentence.split()
```
The following comprehension returns a list of the lengths of each word. Enter the following code in the `python` REPL:

```pythonn
[len(word) for word in words]
```

Now, let's do the same for words that aren't "the":

```python
[len(word) for word in words if word != "the"]
```

* Create a list out of only the _positive_ numbers from this list:

```python
numbers = [34.6, -203.4, 44.9, 68.3, -12.2, 44.6, 12.7]
```

* Create a list containing only the _even_ numbers from this list:

```python
numbers = [12, 54, 33, 67, 24, 89, 11, 24, 47]
```

* Create a list containing _tuples_ of the _uppercase_ version and the _length_ of the following words:

```python
words = ["hello", "my", "name", "is", "Sam"]
```

for example, the _first_ element in your list would be

    ('HELLO', 5)


## 6: Modules
Investigate the python module system. Learn how to call out to functions in code that you've already written (e.g. Web APIs, GPIO labs) from another file.

## 7: Classes
What's a class? You should know this from your studies.

Write a Python class for a Person. The person should inherit from Object and have the following methods:
* A `constructor` which takes the persons name and date of birth
* speak() - prints "hello"
* walk() - prints "walking away"
* get_name() - returns the person's name
* get_age() - returns the person's age

Write another class called Student. Student inherits from Person and has the following methods:
* The `constructor` also takes a String List of course names
* get_courses() - returns the course list
* speak() - in the subclass, prints "I'm so tired!"