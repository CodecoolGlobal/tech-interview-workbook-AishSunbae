# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list data structure? Name some methods of it!

[source](https://www.programiz.com/python-programming/methods/list)

collection which is ordered, changeable, allows duplicate members

#### What is the difference between a list and a set?

A set is a collection which is unordered and unindexed, and doesnt allow duplicates.
list vs set:  duplication, order,index

#### What is the purpose and methods of a map data structure?

map(function, iterable, ...)

A map (also known as dictionary or associative array) is not a data structure. It is an abstract data type: an interface that specifies what operations can be performed, but not how these operations are implemented.A map stores a collection of (key,value) pairs, such that each possible key appears at most once in the collection. The operations supported by a map are to store a new (key,value) pair, or to look up the value that is associated with a certain key.

```def calculateSquare(n):
  return n*n

numbers = (1, 2, 3, 4)
result = map(calculateSquare, numbers)
print(result)
```

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.

[source](https://www.mathsisfun.com/numbers/fibonacci-sequence.html)
[source](https://www.geeksforgeeks.org/python-program-for-program-for-fibonacci-numbers-2/)

*xn = xn−1 + xn−2*

```def Fibonacci(n):
    if n<0:
        print("Incorrect input")
    elif n==0:
        return 0
    elif n==1:
        return 1
    else:
        return Fibonacci(n-1)+Fibonacci(n-2)
```

#### How do you find a max value in a list if you can’t use any built-in functions?

1. in-sort method
2. print the last element  in a list

```def find_max():
    lst = [1, 9, 7, 3, - 2]
    max = 0
    for i in lst:
        if i > max:
            max = i
    return max
```

#### How do you find the average of values in a list if you can’t use any built-in functions?

1. add elements to eachother
2. count them with a variable
3. add  divide them by a variable

```def find_avg():
    lst = [1, 9, 7, 3, - 2]
    count = 0
    sum = 0
    for i in lst:
        count += 1
        sum = sum  + i
    avg = sum/count
    return avg
```

#### What do we call an *in-place* sort?

*An in-place sorting algorithm uses constant extra space for producing the output (modifies the given list only).
It sorts the list only by modifying the order of the elements within the list.*

#### Explain an algorithm which sorts a list!

[source](https://www.tutorialspoint.com/python_data_structure/python_sorting_algorithms.htm)

1. **Bubble sort:** *sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. The algorithm, which is a comparison sort, is named for the way smaller or larger elements "bubble" to the top of the list.*
2. **stalin sort:** *remove every element what is not in order (for fun)*

### Programming paradigms - procedural

#### What is the call stack?

![pic](https://res.cloudinary.com/practicaldev/image/fetch/s--s1Qbl8Gf--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/mwcwre09s12vqa3gvl7a.png)

#### What is “Stack overflow”?

error type

*In software, a stack overflow occurs if the call stack pointer exceeds the stack bound. The call stack may consist of a limited amount of address space, often determined at the start of the program. The size of the call stack depends on many factors, including the programming language, machine architecture, multi-threading, and amount of available memory. When a program attempts to use more space than is available on the call stack (that is, when it attempts to access memory beyond the call stack's bounds, which is essentially a buffer overflow), the stack is said to overflow, typically resulting in a program crash.
fe: recursive function never quit*

#### What are the main parts of a function?

```def random(arg1, arg2): # function signature(function name,paramater list)
    multiply = arg1+ arg2 # function body
    return multiply
```

### Programming languages - Python  

#### How do you use a dictionary in Python?

#### What does it mean that an object is immutable in Python?

*These are of in-built types like int, float, bool, string, unicode, tuple.
An immutable object can't be changed after it is created.*

#### What is conditional expression in Python?

*Ternary operators also known as conditional expressions are operators that evaluate something based on a condition being true or false.*

#### What are different types of arguments in Python?

[source](http://www.trytoprogram.com/python-programming/python-function-arguments/)

1. **Default Arguments:** *def sum(a=4, b=2):*
2. **Keyword Arguments:** *def print_name(name1, name2): print_name(name2 = 'John',name1 = 'Gary')*
3. **Variable-length Arguments:** *def display(*name, **address): display('john','Mary','Nina',John='LA',Mary='NY',Nina='DC')*

#### What is variable shadowing? (context: variable scope)

*In computer programming, variable shadowing occurs when a variable declared within a certain scope (decision block, method, or inner class) has the same name as a variable declared in an outer scope. At the level of identifiers (names, rather than variables), this is known as name masking.*

*(t's defined as when a variable "hides" another variable with the same name. So, when variable shadowing occurs, there are two or more variables with the same name, and their definitions are dependent on their scope (meaning their values may be different depending upon scope).)*

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?

[source](https://www.quora.com/In-Python-why-cant-you-remove-elements-from-a-list-with-a-for-loop-but-you-can-with-a-while-loop)

**IndexError: list index out of range**

* When we delete an item from the list, we are destructively shortening the list, but the range stays the same. Thus, the length of the range is no longer equal to the length of the list, in fact it is greater. Thus, at some point  i  exceeds the count of the list and so we get an index out of range error.*

#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?

[source](https://www.geeksforgeeks.org/scope-resolution-in-python-legb-rule/)

*In Python, the LEGB rule is used to decide the order in which the namespaces are to be searched for scope resolution.
The scopes are listed below in terms of hierarchy(highest to lowest/narrowest to broadest):*

1. Local(L): Defined inside function/class
2. Enclosed(E): Defined inside enclosing functions(Nested function concept)
3. Global(G): Defined at the uppermost level
4. Built-in(B): Reserved names in Python builtin modules

#### If you need to access the iterator variable after a for loop, how would you do it in Python?  #TODO

[source](https://realpython.com/python-for-loop/)

#### What type of elements can a list contain in Python?

Each item in a python list can be of any data type.
*fe: string, numbers, list, tuple, dict*

#### What is slice operator in Python and how to use?

[source](https://www.w3schools.com/python/ref_func_slice.asp)

*The slice() function returns a slice object.*

```slice(start, end, step)
```

*list slicing:*
list:  listname[0:2] [:4] [1:-1] [:]

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?

[source](https://www.tutorialgateway.org/python-program-to-perform-arithmetic-operations-on-lists/)

```NumList1 = [10, 20, 30]
NumList2 = [5, 2, 3]
add = []
sub = []
multi = []
div = []
mod = []
expo = []

for j in range(3):
    add.append( NumList1[j] + NumList2[j])
    sub.append( NumList1[j] - NumList2[j])
    multi.append( NumList1[j] * NumList2[j])
    div.append( NumList1[j] / NumList2[j])
    mod.append( NumList1[j] % NumList2[j])
    expo.append( NumList1[j] ** NumList2[j])

print("\nThe List Items after Addition =  ", add)
print("The List Items after Subtraction =  ", sub)
print("The List Items after Multiplication =  ", multi)
print("The List Items after Division =  ", div)
print("The List Items after Modulus =  ", mod)
print("The List Items after Exponent =  ", expo)

output:
The List Items after Addition =   [15, 22, 33]
The List Items after Subtraction =   [5, 18, 27]
The List Items after Multiplication =   [50, 40, 90]
The List Items after Division =   [2.0, 10.0, 10.0]
The List Items after Modulus =   [0, 0, 0]
The List Items after Exponent =   [100000, 400, 27000]
```

#### What is the purpose of the in and not in membership operators in Python?

[source](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)

*Membership operators are operators used to validate the membership of a value. It test for membership in a sequence, such as strings, lists, or tuples.*

**in operator :** *The ‘in’ operator is used to check if a value exists in a sequence or not. Evaluates to true if it finds a variable in the specified sequence and false otherwise.
‘not in’ operator: Evaluates to true if it does not finds a variable in the specified sequence and false otherwise.*

#### What does the + operator mean when used with strings in Python?

to explicitly concatenate the strings

*fe: "spam" + "eggs"
    spameggs*

#### Explain f strings in Python?

[source](https://realpython.com/python-f-strings/)

#### Name 4 iterable types in Python!

1. list
2. strings
3. tuple
4. dictonory

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?

[source](https://www.geeksforgeeks.org/python-list-comprehensions-vs-generator-expressions/)

#### Does the order of the function definitions matter in Python? Why?

*Really a python source code is a list of instructions from top of file to bottom. Instructions are executed in order.*

#### What does unpacking mean in Python?

[source](https://stackabuse.com/unpacking-in-python-beyond-parallel-assignment/)

*Unpacking in Python refers to an operation that consists of assigning an iterable of values to a tuple (or list ) of variables in a single assignment statement. As a complement, the term packing can be used when we collect several values in a single variable using the iterable unpacking operator.*


#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

*If there is no return statement (or just a return without an argument), an implicit return None is added to the end of a function.*

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?

1. print
2. debugger
3. rubberduck

#### What does step over, step into and step out mean while using the debugger?

1. step  over:  skip functions
2. step into: by default the debugger skips over managed properties and fields, but the Step Into Specific command allows you to override this behavior.
3. step out: to step out the specific

#### How can you start to debug a program from a certain line using the debugger? #TODO

*breakpoints*

### Version control (Git)

#### What are the advantages of using a version control system?

[source](https://www.git-tower.com/learn/git/ebook/en/command-line/basics/why-use-version-control)

1. Collaboration
2. Storing Versions (Properly)
3. Restoring Previous Versions
4. Understanding What Happened (commits)
5. Backup

#### What is the difference between the working directory, the staging area and the repository in git?

[source](http://archaeogeek.github.io/foss4gukdontbeafraid/git/stages.html)

#### What are remote repositories in git?

[source](https://www.git-tower.com/learn/git/ebook/en/command-line/remote-repositories/introduction)

*About 90% of version control related work happens in the local repository: staging, committing, viewing the status or the log/history, etc. Moreover, if you're the only person working on your project, chances are you'll never need to set up a remote repository.*

*Only when it comes to sharing data with your teammates, a remote repo comes into play. Think of it like a "file server" that you use to exchange data with your colleagues.*

#### Why does a merge conflict occur?

[source](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
[source](https://dzone.com/articles/merge-conflict-everything-you-need-to-know)

1. Merge incoming changes from remote branch to the local branch
2. Merge outgoing changes from local branch to the remote branch
3. Merge changes in one local branch to another local branch
4. Merge changes in one remote branch to another remote branch

#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?

1. mv - move file to that repo
2. git add - add to repo
3. git commit
4. git push

#### What does it mean atomic commits and descriptive commit messages?

Atomic commits, in short, are what they sound like: atomic. I feel like there’s basically three features a commit needs to have to be atomic:

1. Every commit pertains to one fix or feature
2. Don't break the build on any commit
3. purpose is clear from commit msges and description (descriptive commit messages?)

#### What’s the difference between git and GitHub?

*Git is a distributed version control tool that can manage a development project's source code history, while GitHub is a cloud based platform built around the Git tool.*

## Software design

### Clean code

#### What does clean code mean?

[source](https://learn.code.cool/full-stack/#/../pages/general/clean-code)
[source](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)

*Code is clean if it can be understood easily – by everyone on the team. Clean code can be read and enhanced by a developer other than its original author. With understandability comes readability, changeability, extensibility and maintainability.*

#### What steps do we usually do during a clean code refactoring?

1. Bad naming
2. Badly formatted code
3. Repeated code
4. Long method
5. Wrong comment usage
6. Dead code

### Error handling

#### What is exception handling?

*An exception is an error that happens during execution of a program. When that
error occurs, Python generate an exception that can be handled, which avoids your
program to crash.*

#### What are the basics of exception handling in Python?

[source](https://www.pythonforbeginners.com/error-handling/exception-handling-in-python)

*The error handling is done through the use of exceptions that are caught in try
blocks and handled in except blocks. If an error is encountered, a try block
code execution is stopped and transferred down to the except block.*

*In addition to using an except block after the try block, you can also use the
finally block.*

*The code in the finally block will be executed regardless of whether an exception
occurs.*

#### In which case should we catch an exception? Why?  #FIXME

*Exceptions are convenient in many ways for handling errors and special conditions
in a program. When you think that you have a code which can produce an error then
you can use exception handling.*

#### What can/should we do with an exception in the ‘except’ block? #FIXME

1. printing
2. quitting

#### What does the else and finally statement do in a try-except block in Python?

**else block** *will be executed only if the code inside the try block doesn’t generate an exception.*

**finally block** *code is always executed, whether the program executed properly or it raised an exception.
*
## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

*The goal of the retrospective is for the team members to discuss among themselves about
how the work went during the last sprint so that better ways can be found to meet the project's goals.*

## Programming environment

### Unix (Unix stands for Uniplexed Information and Computer Systems)

#### What is UNIX and what is Linux?

[source](https://www.guru99.com/difference-unix-vs-linux.html)

#### What do we call the shell in Linux?

*The shell is the command interpretor in an operating system such as Unix or GNU/Linux, it is a program that executes other programs. It provides a computer user an interface to the Unix/GNU Linux system so that the user can run different commands or utilities/tools with some input data.*

#### What does root means in a Linux environment?

*root is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user and the superuser.*

#### How do you access your personal files in Linux?

*home/username in terminal*

#### How can you install an application in Linux?

*sudo apt install <deb name>*

#### What is package management in Linux, what are repositories? #FIXME

[source](https://www.linode.com/docs/tools-reference/linux-package-management/)

*A package manager or package-management system is a collection of software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner.*

*The Debian package management system, based on a tool called dpkg with the very popular apt system, is a powerful, popular, and useful method of package management.*

#### How do you navigate in the filesystem with the command line?

1. **PWD:** *find your “present working directory”*
2. **LS:** *see the files in your current directory*
3. **CD:** *change your current directory*
    1. *To navigate into the root directory, use* **cd /**
    2. *To navigate to your home directory, use* **cd** or **cd ~**
    3. *To navigate up one directory level, use* **cd ..**
    4. *To navigate to the previous directory (or back),* **use cd -**

#### What does the following commands do: mkdir, rm, cat, cp, touch?

[source](https://www.softwaretestinghelp.com/unix-file-system-commands/)

1. **mkdir:** *Make directory*
2. **rm:** *Remove files and directories*
3. **cat:** *Concatenate files and print to stdout.*
4. **cp:** *Copy files*
5. **touch:** *Create a new file or update its timestamp.*

#### How can you look up what does a command do in Linux if you have no internet connection?

*<commandname> -help or <commandname> -h*

#### What does the following commands do: head, tail, more, less?

[source](https://linuxfrombeginning.wordpress.com/2008/09/19/linux/)

1. **head:** *displays the first ten lines of a file, unless otherwise stated.*
2. **tail:** *display the last part of the file*
3. **more:** *to view a text file one page at a time, press spacebar to go to the next page*
4. **less:** *is much the same as more command except*

#### How do you download a file from internet using the terminal?

1. **with curl:**
    1. *sudo apt install curl*
    2. *curl –O [URL]*
    3. *curl –o [filename] [URL] # save with diffrent filename*
    4. *curl -O [URL1] -O [URL2]*
2. **with wget**
    1. *sudo apt-get install wget*
    2. *wget [URL]*
    3. *wget -O [filename] [URL]*
    4. *wget –i [filename.txt]*
