Bonus class: HTML & CSS
-----------------------

In this class we're taking a small step back from all the python programming we've done during the last couple of weeks and take a look at 2 markup languages. 

HTML and CSS. 

HTML (Hyper Text Markup Language) is a markup language used to create the structure of most web pages on the web.
CSS (Cascading Style sheet) is used to prettify those pages with colours, shapes, fonts, etc.

In this small lab You're going to write some HTML followed by some CSS.

First things first. Go back to the flask project you've been working on (the one that made it to Heroku.com) and remove the section we created for `/foo`)

So this code should be gone now:

```
@app.route('/foo/<name>')
def foo(name):
    return render_template('index.html', to=name)
```

next we're going to clean up the `templates/index.html`. file and begin afresh, so clean it out, remove all the text in it and let's start.

## A basic html file.
When we write HTML files, we first need to tell the browser that will open the file later what it's dealing with. Through the years different versions of HTML have been written and published. Currently (and for the last couple of years) we've been at version 5

![HTML5](http://www.experience-it-all.com/wp-content/uploads/2011/01/html5logo.jpg)  
*html 5's popular logo*

So our document will need to start with the following 2 lines:

```
<html lang="en">
```

In XML-based markup languages each tag also needs to be closed or ended to mark the end of in this case the document. so make a new line underneath the first and add the following:

```
</html>
```

From now on we're going to close everything we open. 

Each HTML file needs to contain some information. first of all we need a `head` "tag" marking an area where we can give some extra information to the browser like the title of the page, where it can find it's style-sheets, some information for websites like Facebook & Twitter. We also need to specify what kind of text encoding we have (UTF-8). This will allow the website to show weird text like `ä ö`, `Å`, `%`, etc.

this head tag would look something like this:

```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>My fancy title!</title>
</head>
```

> Although HTML is not an indentation based language, it's smart to indent it anyway. This will make sure that your code is readable!

Let's save this file and go back to our `app.py` (or `myapp.py`).  
We'll make sure that the already existing route to `/` now loads our index.html.

```
@app.route('/')
def index():
    return render_template('index.html')
```

With this done, lets start the server and visit `localhost:5000` in the browser. Can you see where the "My fancy title!" we set is shown?

With our head set up, it's time to define the second important part of our HTML: the "Body".

The body in HTML is the part where we put everything that's visible. Let's insert something like this:

```
<body>
  Hello World!
</body>
```

With this done let's safe the document and open it in the browser!

Do you see text?


## Text styles
In html we can use all kinds of text styles. some of them come built-in with the markup language.

Try wrapping your hello world in `h1` tags:

```
<h1>Hello World!</h1>
```

Then create a new row and write an `h2` tag:

```
<h2>Sub-titles</h2>
```

Let's save it and open it!

> When working with code (and especially HTML and CSS), it's important to make small changes, then try them out. This makes it easier to find the small misstakes you might have made