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


### Text styles
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

### Images
No page is finished without a nice picture. let's write bit of a hard tag to get our image in place.

```
  <img src="https://media0.giphy.com/media/d1FGkFLpizR8yQne/giphy.gif" alt="Awesome">
```

Our image has 2 special `attributes`; the `src=""` will tell the browser where to find the image and the `alt=""` attribute will tell the browser to show "place-holder" text when the image can't be loaded.
### Links
It's nice to put some links in our page to help people find other pages. let's try one!

```
<a href="https://www.google.com" target="_blank">Go to Google</a>
```

The `target` attribute here tells the browser that is should open the link in a new window or tab.

### Divs
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

## CSS
Let's dive into the awesome world of CSS!
With css we can give HTML pages colours, change font-faces, position elements, create animations and much more. In this lab we'll do some small css things, but feel free to spice up your own new start-page when you're done!

To get things working we'll need a few new things in our project. First of all we need to create a new folder in our project called `static`. This static folder will hold our own images and css files.

in the static folder create a new file called `style.css`

You should now have a file structure like this:

```
- hello_world_site/
  - static/
    - style.css
  - templates/
    - index.html
  - app.py (or myapp.py)
  - Procfile
  - requirements.txt
  - runtime.txt
```

Nice! let's tell our html page that we've gotten a nice new css file! in your index.html file add a new line to the header like this:

```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>My fancy title!</title>
  <link rel="stylesheet" href="/static/style.css" type="text/css">
</head>
```

Awesome. let's see if this works!

Open your page, then hit either `F12` on your keyboard. or right click the page and tick `inspect element`. Are there any red errors?

## Styling tags
The first thing we're going to do is to change the background colour of the page a bit. 
Let's select the body-tag in our CSS and assign a background to it. Write the following in your style.css file.

```
body {
  background: green;
}
```

This looks quite aggressive doesn't it? Let's change that colour for a "hash value" that's slightly less green.

```
body {
  background: #EEE;
}
```

You can find your own "hash value" colours on this [handy website](https://www.w3schools.com/colors/colors_picker.asp).

Now that we have the background-colour down, it's time to spice up the text a bit.

Let's begin with fonts in general. The font-face that comes standard is quite boring, let's make it a bit fancier.
Let's change the font for the entire page:

```
body {
  background: #EEE;
  font-family: Arial, Helvetica, sans-serif;
}
```

We specify 3 fonts here so Microsoft Windows can use Arial, OSX can use Helvetica and Linux/Android can use sans-serif.

Awesome. While we're at it, let's change the colour of the text a bit, so it's less black (again you can use your own hash codes). 

```
body {
  background: #EEE;
  font-family: Arial, Helvetica, sans-serif;
  color: #111;
}
```

Now that looks a bit better for the eyes right?

> So let's look back here for a second. when we want to style an element -- in this case `<body>` we can style it using its name in css.

### Styling classes
Sometimes, it happens that your page has a lot of `<p>` tags, and you only want to apply some style a few. For this we have a system called classes. With this we can "classify" special cases. Lets try it!

Go back into your index.html and create a copy of the `<p>` block and put it underneath it. A bit like this:

```
    <p>
      Some text <br />
      A new line
    </p>
    <p>
      Some text <br />
      A new line
    </p>
```

Okidoki. let's give the first block a class now.

```
<p class="important-notice">
```

With this down, we can now write a special bit of css markup. Let's head back to the style.css file and insert some new css underneath our body css.

```
.important-notice {
  text-decoration: underline;
}
```

The `.` in front of the name in css, tells the browser that this applies to objects with classes called "important-notice".
You could also write `p.important-notice` to only apply the style on `paragraph`-tags with the class `important-notice`

### Styling Id's

In the previous step we styled something using classes. When you style something with classes, any number of objects can have the same class-name. Sometimes, you want to apply a style only to one object. When that happens you probably want to use an `id` instead. Let's try that out!

Let's take the second `p`-tag (the one you haven't given a class) and give it an ID.

```
<p id="italic-notice">
  Some text <br />
  A new line
</p>
```

Okay, that's in place now isn't it? Let's head back to the style.css file and insert some code.

```
#italic-notice {
  font-style: italic;
}
```

Okay, so when you want to style an `id` you prefix its name with `#` in CSS. This `#` will work in other places too.

The title to the section you're reading on this website right now was written like this: 

```
<h3 id="styling-ids">Styling Id's</h3>
```

so when you visit: https://github.com/glblcd/material/wiki/Bonus-Lab:-HTML-&-CSS#styling-ids the browser will automatically scroll to it! Awesome huh?

> Now is probably a good time to commit your work to git.

### Styling blocks
With our classes, ids and other things behind us now, let's look at that `Div` we made earlier. We can style this one up in a lot of funny ways. 

Lets begin by giving our existing div a class called `container`

```
<div clas="container">
```


Then in our CSS we'll give it a nice background colour:

```
.container {
  background: #FFF;
}
```

when looking at this in the browser, the page is waaay to big. so lets give it a max-width.

```
.container {
  background: #FFF;
  max-width: 960px;
}
```

Okay, that's better, but the text is a bit to close to the sides right?

```
.container {
  background: #FFF;
  max-width: 960px;
  padding: 10px;
}
```

But now we start to see that the entire page has some kind of space around it. that's pretty bad. To fix this we'll need to write a small new rule in the css:

```
html, body {
  padding: 0;
  margin: 0;
}
```

When we add a `,` to our invocation, the rules below will apply to both the `<html>`-tag and the `<body>`-tag. 

> Remember, spaces between things have big impact in CSS!

Now that weird spacing is gone! But the page isn't really centered. For this we're going to hack CSS a bit. Go back to the `.container` block in css and add a few new lines.

```
.container {
  background: #FFF;
  max-width: 960px;
  padding: 10px;
  margin-top: 20px;
  margin-right: auto;
  margin-bottom: 20px;
  margin-left: auto;
}
```

Now we have a fancy page!

Let's commit your work and commit it away, then try to make your own home-page that includes a nice header, some info about yourself and a footer.

You can also experiment with background pictures, an example of that can be found on this page [Peter made earlier](https://ssb-pub.picodevelopment.nl/). 

When you want to go next level, you can also make some "brutalist websites" like the ones below:

- https://davidmerrique.hashbase.io/
- https://coolguy.website/chill/
- https://coolguy.website/
- http://sometimesredsometimesblue.com/