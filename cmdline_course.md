---
layout: default
---

## Week 1
### Introduction to Command Line Environments

The first week was basically just an introduction to the command line, like changing directories, basic commands, and so on. There was nothing new for me here, as I use the command line daily for both work and personal projects.

Example code:
```bash
cat README.md
```
This will print the contents of the ```README.md``` file.
## Week 2
### Navigating a UNIX System

The second week delved a little further into the file system, like creating, moving and deleting directories. Also basic compression commands and file permissions were covered. Again, nothing new for me here, as these are daily tasks.

Example code:
```bash
mkdir test
mv test test2
rm test2
```
Create directory ```test```, rename (ie. move) it to ```test2```, and then delete it. 

## Week 3
### Basic Corpus Processing

Third week was about text processing tools. We covered different character encoding systems and conversion between them. Piping and redirection was also used. I was not very familiar with th euse of ```tr```, as I've tended to write Python or NodeJS scripts to handle these kinds of problems. 

Commands covered:

|Command(s)|Description|
|---|---|
|```head```, ```tail```|Print the first/last lines of a file|
|```tr```|Transform text|
|```wget```, ```curl```|Download files|
|```grep```, ```egrep```|Search for patterns|
|```cut```|Extract columns from text|
|```wc```|Count lines, words, and characters|

Example code:
```bash
head -n 5 README.md > README.md.head
```
Print the first 5 lines of the ```README.md``` file and save it to ```README.md.head```.
## Week 4

### Advanced Corpus Processing

Fourth week expanded on the previous week. Topics included more elaborate text processing pipelines and the use of ```sed``` to transform text files using regular expressions. I learned a few nifty tricks here, mainly how to customize the usage of the basic commands such as ```sort```, ```uniq``` and so on.

Example code:
```bash
cat README.md | tr -s '\n\r\t ' '\n' | sort | uniq -c | sort -nr > README.md.freq
```
Convert ```README.md``` to one word per line, remove all whitespace, sort the words, count the number of times each words occurs, and then sort the results in descending order. Output the results to ```README.md.freq```.

## Week 5
### Scripting and Configuration Files

Fifth week covered the use of scripts to run commands and how to use configuration files to customize the shell. There was not much new stuff for me, as this is what I do almost daily, but writing the ```bash``` script to create comparative forms was pretty fun.

Example code:

```bash
#!/bin/bash
if [ $# -eq 0 ]
then
    echo "Usage: $0 <inputfile> [outputfile]"
    exit 1
fi

RESULT=$(cat $1 | tr -s '\n\r\t ' '\n' | tr '[:upper:]' '[:lower:]' | sort | uniq -c | sort -nr)

if [ -z $2 ]
then
    echo "$RESULT"
else
    echo "$RESULT" > $2
fi
```

This script takes two arguments, the first is the name of the file to be processed, and the optional second is the name of the output file. The script will read the file, convert it to lower case, convert it to single word per line, and count the occurrences of each word. It then stores the words in descending order to a temporary variable. Finally, if the output file argument is specified, the result is output to that file; otherwise the result is output to standard output. If no arguments are given, the script will print a helpful usage message and exit with an error code.

## Week 6
### Installing and Running Programs

Sixth week was about installing programs and packages with package managers like ```apt``` and ```pip```. Also, root user rights with ```sudo``` was covered, as well as Python virtual environments. Another part of this week's curriculum was the use of the ```make``` tool and the ```Makefile``` file. The use of ```Makefile``` to build corpus processing scripts was pretty novel to me, as I've mainly used it with C and C++ projects. Other than that, it was pretty smooth sailing, although ```bllipparser``` installation failed like it seemed to do for other people on the course.

Example code:

```python
from guess_language import guess_language

print(guess_language("Hello, world!"))
```

This Python program will import the ```guess_language``` module and use it to guess the language of a given string.
## Week 7
### Version Control
## Week 8
### Building Webpages using GitHub Pages