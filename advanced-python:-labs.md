# ![Advanced Python: Labs](../blob/master/assets/img/logo-128.png?raw=true)

Welcome to the Advanced Python lab! Work through this sheet in pairs, making sure that you understand
each bit of code before you move on.

If you get something wrong, let us know! Other people may have done the same thing; maybe you
can help them.

## 1: Filter, Map, Lambda!
Write a function (using `def`!) that takes a number and returns True if it's even. Let's call the function `is_even`

Use your `is_even` function to return only the even numbers from the following list:

    numbers = [1,56,234,87,4,76,24,69,90,135]

Now, rewrite your code to use a _lambda_: write the is_even code in-line, rather than defining and then using your function. Look at the slides for a hint.

Next, re-write your code to return all the _odd_ numbers in the `numbers` collection.

## 2: Combinations
Investigate the function called `not`. What does it do?

Using the built-in function `not` and your function `is_even`, find another way to return all the _odd_ numbers in the `numbers` collection from the previous section.

## 3: Fold
Remember that a folding operation (sometimes called _reduce_) takes a collection of data and returns one piece of data, by applying a function to all the items in order. An example might be to add up all the numbers in a list:

    total = fold(lambda item, running_total: item + running_total, [1, 2, 3, 4, 5])

Write a function called `join` that takes a list of words and uses `+` to join them all together. For example:

    words = ["hello", "world"]
    helloworld = join(words) # "hello world"

