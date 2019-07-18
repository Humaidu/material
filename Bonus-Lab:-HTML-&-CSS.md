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

> When working with code (and especially HTML and CSS), it's important to make small changes, then try them out. This makes it easier to find the small mistakes you might have made.

Even though we not always use it, Paragraph-type text has it's own special tag too! `p`

You can write it like this:

```
<p>
  Some text <br />
  A new line
</p>
```

Hey, what's that there? a `br` tag with a `/` in the end of it?  
Jep, this is what we call **self-closing tags**. These special tags already close themselves, so there's no need to write a `</br>` after. `br` means "line-break" and will create... you guessed it a line-break!

## Images
No page is finished without a nice picture. let's write bit of a hard tag to get our image in place.

```
  <img src="https://media0.giphy.com/media/d1FGkFLpizR8yQne/giphy.gif" alt="Awesome">
```

Our image has 2 special `attributes`; the `src=""` will tell the browser where to find the image and the `alt=""` attribute will tell the browser to show "place-holder" text when the image can't be loaded.
## Links
It's nice to put some links in our page to help people find other pages. let's try one!

```
<a href="https://www.google.com" target="_blank">Go to Google</a>
```

The `target` attribute here tells the browser that is should open the link in a new window or tab.

## Divs
Divs are a bit harder, and commonly used to style up the page. Divs are blocks that you can put on the page to position text, provide background-colours and all kinds of other shenanigans.

We're going to wrap all that we've done so far in a div called container. Later when we get to CSS we'll do things with this div.

With the div in place, our body should look something like this:

```
<body>
  <div>
    <h1>Hello World!</h1>
    <h2>Foo bar</h2>
    <p>
      Some text <br />
      A new line
    </p>
    <img src="https://media0.giphy.com/media/d1FGkFLpizR8yQne/giphy.gif?cid=790b76115d3034d33045472f4d47b0cb&rid=giphy.gif" alt="Awesome">
    <a href="https://www.google.com" target="_blank">Go to Google</a>
  </div>
</body>
```

> I'm writing the rest of this page now, refresh the page if you managed to get this far already ;)