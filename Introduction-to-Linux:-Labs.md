# ![Introduction to Linux: Labs](../blob/master/assets/img/logo-128.png?raw=true)

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
* At the bottom of the screen, you'll see all the commands you can use. Sometimes you'll see `^` - this just means `ctrl`. So for example, `^O` just means `ctrl`+`o`.
* Use the _WriteOut_ command to save your work (name the file with your first name), then the _Exit_ command to quit pico. You'll be right back at the command prompt.
* My file is called `sam`. What happens when I type `cat sam` in the command prompt? Try that with the name of your file. Use the manpage for cat to figure out what's happening.
* What happens when I type `less sam`? What's `less`? (Type `q` to escape!). Do you recognise `less`? It's how manpages are shown on the screen!
* What happens when I type `head -1 sam`? What about `tail -1 sam`?

## Advanced commands
* `whoami` prints out your user ID!
* `ps aux` prints details of every process running on your machine.
* `grep` searches the input for lines matching a certain pattern. For example, `grep cheese sam` prints out all the lines in the file called _sam_ that contain the exact word "cheese".
* Grep is very powerful. `grep ^I sam` prints out all the lines in the file _sam_ that _start with_ the character "I".
* What do you think `grep UK$ sam` does?
* You can use the backticks (\`) to execute a command and pass its output to the outer command. This sounds complex but it's really simple. If I type `grep \`whoami\` sam`, the `whoami` command is executed first. That returns "sam". That output is then substituted into the command, so `grep sam sam` is executed. See? Easy!

## Combining commands
Some commands can be combined together. For example, `wc` is a simple command that shows a wordcount for a file - the number of characters, lines, and words in the file.
* Type `wc` `<enter>`. Then, type a bunch of text. You're actually writing a file into wc right now! Hit enter and enter some more text. Do it some more. When you're done, hit `ctrl`+`d` to end the "file". What do the three numbers mean?
* What does `wc -l` do? Enter it as a command and then do the same - what does the one number mean?
* Remember my file called `sam`? What happens when I enter `cat sam | wc -l`? What is the "pipe" doing?
* Try it with your file. How many words are in your file? How many lines of text?
* Use `ls` and `wc` to find out how many files and directories are in your `root` directory.
* How many files and directories are in your `home` directory?
* Enter `ls > files`. Then enter `cat files`. What happened? What is `files`? What does `>` do?
* Enter `wc -l < files`. What does the number mean?
* `tee` is very useful. Before passing its input through to its output, it also writes the input to a file. 

## Variables
You can save information in the shell using environment variables. Type the following:

    message="hello, my name is sam"
    echo $message

Make sure to leave no spaces around the `=`, and remember the `$` before "message" - this is the name of the variable. They can be used by processes that you write, and contain useful information that the shell uses. We'll see more variables when we come to use Heroku next week.

## Success and Failure
As well as having an input and an output, each process returns either zero or a non-zero number, notifying the shell that it either succeeded (0) or it failed (1-255). The different numbers can be used as error codes - for example 1 might mean that a file could not be read, etc.

The special variable `$?` contains the status code of the _last_ command that ran. How can you read the value of `$?`?

The simple commands `true` and `false` set status codes of `0` and `1` respectively. Run them and then print out the value of `$?`.



## Building pipelines
Linux commands are based on the philosophy of doing one job, and combining simple tasks into complex operations using `|`, `<`, and `>`.

The good thing about building pipelines is that you can build all the bits separately, and then combine them at the end. Let's work through one together: save a list of all the running process that are owned by me.
* Firstly, what command do we use to print out all the running processes? What does the output mean?
* Next, how can I find out the ID of the current user?
* Next, how can I filter the output of the processes command?
* Great! Now let's combine all those.
  * Firstly, list the processes.
  * Pass the output of that to our filter command. This should also get the current userid.
  * Finally, output the results of the filter to a file. 

Work in groups to build pipelines to do the following:
* Write a file called _everything_ which contains all the files and directories in your home directory, *and* a file called _directories_ which contains just the directories.
  * HINT: You'll need to understand the output of `ls -la`.
  * HINT: You'll need to use a `grep` pattern
  * HINT: You'll need to use `tee` once.

* Find out what `watch -n1 "ls -lart /"` does. Try it out - then it `ctrl`+`c` to exit. Write a similar pipeline to show the _one_ most recently edited file in your home directory every second. Open another terminal window and use the `echo` and `>` command to create a new file, and check that your pipeline's output changed.

