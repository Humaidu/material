Welcome to the Introduction to Linux lab!

This time, we're going to discover how to use terminal commands to get work done. Let's get started!

## Prep
Hit the keys `ctrl`+`alt`+`t` to open a terminal. You could hit the icon at the top of the screen, but using the keyboard is quicker and easier.

## Simple commands
Firstly, we're going to discover the `man` command. `man` shows a _manual_ page for a certain topic. Type `man pwd` `<enter>` to see what the `pwd` command does. Use the ⬆️  and ⬇️  keys to scroll around the page, or hit the spacebar to skip a whole page.

Once you've found out what `pwd` does, hit `q` to exit the man system. Now, type `pwd` again: what does the output tell you?

Type `cd \` `<enter>`, then try `pwd` again.
* What happened? What does `cd` do? (hint: there's no 'man page' because `cd` is so simple!)
* Use `cd` to go back to the directory you were in. This is your _home_ directory - it's where all your stuff goes. You can always get back here by typing `cd ~`.
* type `cd ..`, then check where you are with `pwd`. What does `..` mean? (hint: it's in *every* folder!)

Type `ls`.
* What does `ls` do?
* Type `ls -a`. Read the manpage to find out what the _a_ switch does. What's the difference between `ls` and `ls -a`?
* _Without_ using `cd`, show all the files and directories in the root directory (remember "/"?)
* _Without_ using `cd`, show all the files and directories in the parent directory (remember ".."?)
* What do the switches `l`, `r`, and `t` do? What does the command `ls -lart` do? Why is it useful?

What does `ps` do? Try it!

## Editing text
Open the `pico` editor.

Type some text! Say hello, write your name, where you come from, what you like to do in your spare time. Write two paragraphs about yourself.

At the bottom of the screen, you'll see all the commands you can use. Sometimes you'll see `^` - this just means `ctrl`. So for example, `^O` just means `ctrl`+`o`.

Use the _WriteOut_ command to save your work (name the file with your first name), then the _Exit_ command to quit pico. You'll be right back at the command prompt.

My file is called `sam`. What happens when I type `cat sam` in the command prompt? Try that with the name of your file. Use the manpage for cat to figure out what's happening.

What happens when I type `less sam`? What's `less`? (Type `q` to escape!). Do you recognise `less`? It's how manpages are shown on the screen!

## Combining commands
Some commands can be combined together. For example, `wc` is a simple command that shows a wordcount for a file - the number of characters, lines, and words in the file.
* Type `wc` `<enter>`. Then, type a bunch of text. You're actually writing a file into wc right now! Hit enter and enter some more text. Do it some more. When you're done, hit `ctrl`+`d` to end the "file". What do the three numbers mean?
* What does `wc -l` do? Enter it as a command and then do the same - what does the one number mean?
* Remember my file called `sam`? What happens when I enter `cat sam | wc -l`? What is the "pipe" doing?
* Try it with your file. How many words are in your file? How many lines of text?
* Use `ls` and `wc` to find out how many files and directories are in your `root` directory.
* How many files and directories are in your `home` directory?
