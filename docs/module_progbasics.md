# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list data structure? Name some methods of it!
collection which is ordered, changeable, allows duplicate members
https://www.programiz.com/python-programming/methods/list

#### What is the difference between a list and a set?
A set is a collection which is unordered and unindexed, and doesnt allow duplicates.
list vs set:  duplication, order,index

#### What is the purpose and methods of a map data structure?
map(function, iterable, ...)
A map (also known as dictionary or associative array) is not a data structure. It is an abstract data type: an interface that specifies what operations can be performed, but not how these operations are implemented.A map stores a collection of (key,value) pairs, such that each possible key appears at most once in the collection. The operations supported by a map are to store a new (key,value) pair, or to look up the value that is associated with a certain key.

def calculateSquare(n):
  return n*n

numbers = (1, 2, 3, 4)
result = map(calculateSquare, numbers)
print(result)

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
xn = xn−1 + xn−2
https://www.mathsisfun.com/numbers/fibonacci-sequence.html
https://www.geeksforgeeks.org/python-program-for-program-for-fibonacci-numbers-2/
def Fibonacci(n):
    if n<0:
        print("Incorrect input")
    elif n==0:
        return 0
    elif n==1:
        return 1
    else:
        return Fibonacci(n-1)+Fibonacci(n-2)

#### How do you find a max value in a list if you can’t use any built-in functions?
in-sort method
print the last element  in a list

def find_max():
    lst = [1, 9, 7, 3, - 2]
    max = 0
    for i in lst:
        if i > max:
            max = i
    return max

#### How do you find the average of values in a list if you can’t use any built-in functions?
add elements to eachother
count them with a variable
add  divide them by a variable

def find_avg():
    lst = [1, 9, 7, 3, - 2]
    count = 0
    sum = 0
    for i in lst:
        count += 1
        sum = sum  + i
    avg = sum/count
    return avg

#### What do we call an *in-place* sort?
An in-place sorting algorithm uses constant extra space for producing the output (modifies the given list only). It sorts the list only by modifying the order of the elements within the list.

#### Explain an algorithm which sorts a list!
https://www.tutorialspoint.com/python_data_structure/python_sorting_algorithms.htm
- Bubble sort, sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. The algorithm, which is a comparison sort, is named for the way smaller or larger elements "bubble" to the top of the list.
- stalin sort

### Programming paradigms - procedural

#### What is the call stack?
https://dev.to/theoutlander/implementing-the-stack-data-structure-in-javascript-4164
pic

#### What is “Stack overflow”?
error type
In software, a stack overflow occurs if the call stack pointer exceeds the stack bound. The call stack may consist of a limited amount of address space, often determined at the start of the program. The size of the call stack depends on many factors, including the programming language, machine architecture, multi-threading, and amount of available memory. When a program attempts to use more space than is available on the call stack (that is, when it attempts to access memory beyond the call stack's bounds, which is essentially a buffer overflow), the stack is said to overflow, typically resulting in a program crash.
fe: recursive function never quit

#### What are the main parts of a function?
def random(arg1, arg2): # function signature(function name,paramater list)
    multiply = arg1+ arg2 # function body
    return multiply

### Programming languages - Python  

#### How do you use a dictionary in Python?

#### What does it mean that an object is immutable in Python?
These are of in-built types like int, float, bool, string, unicode, tuple. In simple words, an immutable object can't be changed after it is created.

#### What is conditional expression in Python?
Ternary operators also known as conditional expressions are operators that evaluate something based on a condition being true or false.

#### What are different types of arguments in Python?
http://www.trytoprogram.com/python-programming/python-function-arguments/
Default Arguments: def sum(a=4, b=2):
Keyword Arguments: def print_name(name1, name2): print_name(name2 = 'John',name1 = 'Gary')
Variable-length Arguments: def display(*name, **address): display('john','Mary','Nina',John='LA',Mary='NY',Nina='DC')

#### What is variable shadowing? (context: variable scope)
In computer programming, variable shadowing occurs when a variable declared within a certain scope (decision block, method, or inner class) has the same name as a variable declared in an outer scope. At the level of identifiers (names, rather than variables), this is known as name masking.

(t's defined as when a variable "hides" another variable with the same name. So, when variable shadowing occurs, there are two or more variables with the same name, and their definitions are dependent on their scope (meaning their values may be different depending upon scope).)

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
https://www.geeksforgeeks.org/scope-resolution-in-python-legb-rule/

#### If you need to access the iterator variable after a for loop, how would you do it in Python?
#### What type of elements can a list contain in Python?
#### What is slice operator in Python and how to use?
https://www.w3schools.com/python/ref_func_slice.asp
list:  listname[0:2] [:4] [1:-1] [:]

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
#### What is the purpose of the in and not in membership operators in Python?
#### What does the + operator mean when used with strings in Python?
#### Explain f strings in Python?
#### Name 4 iterable types in Python!
list, strings, tuple,  dictonory

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
#### Does the order of the function definitions matter in Python? Why?
#### What does unpacking mean in Python?
https://towardsdatascience.com/python-basics-iteration-and-looping-6ca63b30835c

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
print, debugger, rubberduck

#### What does step over, step into and step out mean while using the debugger?
step  over:
step into:
step out:

#### How can you start to debug a program from a certain line using the debugger?
breakpoints

### Version control (Git)

#### What are the advantages of using a version control system?
tracking, backup
#### What is the difference between the working directory, the staging area and the repository in git?
http://archaeogeek.github.io/foss4gukdontbeafraid/git/stages.html
#### What are remote repositories in git?
#### Why does a merge conflict occur?
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
#### What does it mean atomic commits and descriptive commit messages?
Atomic commits, in short, are what they sound like: atomic. I feel like there’s basically three features a commit needs to have to be atomic:
1. Every commit pertains to one fix or feature
2. Don't break the build on any commit
3. purpose is clear from commit msges and description (descriptive commit messages?)

#### What’s the difference between git and GitHub?
Git is a distributed version control tool that can manage a development project's source code history, while GitHub is a cloud based platform built around the Git tool.

## Software design

### Clean code

#### What does clean code mean?
https://learn.code.cool/full-stack/#/../pages/general/clean-code
https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29

#### What steps do we usually do during a clean code refactoring?
Bad naming
Badly formatted code
Repeated code
Long method
Wrong comment usage
Dead code

### Error handling

#### What is exception handling?
An exception is an error that happens during execution of a program. When that
error occurs, Python generate an exception that can be handled, which avoids your
program to crash.

#### What are the basics of exception handling in Python?
https://www.pythonforbeginners.com/error-handling/exception-handling-in-python
The error handling is done through the use of exceptions that are caught in try
blocks and handled in except blocks. If an error is encountered, a try block
code execution is stopped and transferred down to the except block.

In addition to using an except block after the try block, you can also use the
finally block.

The code in the finally block will be executed regardless of whether an exception
occurs.

#### In which case should we catch an exception? Why?  # FIXME
Exceptions are convenient in many ways for handling errors and special conditions
in a program. When you think that you have a code which can produce an error then
you can use exception handling.

#### What can/should we do with an exception in the ‘except’ block? # FIXME
printing, quitting

#### What does the else and finally statement do in a try-except block in Python?
else block will be executed only if the code inside the try block doesn’t generate an exception.

finally block code is always executed, whether the program executed properly or it raised an exception.

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?
The goal of the retrospective is for the team members to discuss among themselves about
how the work went during the last sprint so that better ways can be found to meet the project's goals.

## Programming environment

### Unix (Unix stands for Uniplexed Information and Computer Systems)

#### What is UNIX and what is Linux?
https://www.guru99.com/difference-unix-vs-linux.html

#### What do we call the shell in Linux?
The shell is the command interpretor in an operating system such as Unix or GNU/Linux, it is a program that executes other programs. It provides a computer user an interface to the Unix/GNU Linux system so that the user can run different commands or utilities/tools with some input data.

#### What does root means in a Linux environment?
root is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user and the superuser.

#### How do you access your personal files in Linux?
home/username in terminal

#### How can you install an application in Linux?
sudo apt install <deb name>

#### What is package management in Linux, what are repositories? # TODO: repos
https://www.linode.com/docs/tools-reference/linux-package-management/
A package manager or package-management system is a collection of software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner.

The Debian package management system, based on a tool called dpkg with the very popular apt system, is a powerful, popular, and useful method of package management.

#### How do you navigate in the filesystem with the command line?
PWD — FIND YOUR “PRESENT WORKING DIRECTORY”
LS — SEE THE FILES IN YOUR CURRENT DIRECTORY
CD — CHANGE YOUR CURRENT DIRECTORY
    To navigate into the root directory, use "cd /"
    To navigate to your home directory, use "cd" or "cd ~"
    To navigate up one directory level, use "cd .."
    To navigate to the previous directory (or back), use "cd -"

#### What does the following commands do: mkdir, rm, cat, cp, touch?
https://www.softwaretestinghelp.com/unix-file-system-commands/
mkdir: Make directory
rm: Remove files and directories
cat: Concatenate files and print to stdout.
cp: Copy files
touch: Create a new file or update its timestamp.
#### How can you look up what does a command do in Linux if you have no internet connection?
commandname -help or commandname -h
#### What does the following commands do: head, tail, more, less?
https://linuxfrombeginning.wordpress.com/2008/09/19/linux/
head: displays the first ten lines of a file, unless otherwise stated.
tail: display the last part of the file
more: to view a text file one page at a time, press spacebar to go to the next page
less: is much the same as more command except
#### How do you download a file from internet using the terminal?
sudo apt install curl
curl –O [URL]
$ curl –o [filename] [URL] # save with diffrent filename
curl -O [URL1] -O [URL2]
or
sudo apt-get install wget
wget [URL]
wget -O [filename] [URL]
wget –i [filename.txt]
