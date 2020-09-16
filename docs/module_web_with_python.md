# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!

  1. *Descriptive related but different database and table names*
  2. *Keywords and expressions are aligned into separate columns*
  3. *Indented new line after every logical step*
  4. *Query parameters indented to create a block like body*
  5. *Commas are at the end of the query*

#### What layers can you name in a simple web application?

[web application](https://gyires.inf.unideb.hu/GyBITT/08/ch04.html#:~:text=The%20most%20external%20of%20them,that%20is%20the%20Data%20Layer.)

1. View
2. Application service
3. Database
4. Domain

### Error handling

#### What error can occur, when an array does not have an element on the requested index?

Index error.

#### What is the “finally” block, and how would you use it?

The finally block is as the name, some code that you want to execute regardless of what happens.

#### Why should we catch special exception types?

*In general, an exception breaks the normal flow of execution and executes a pre-registered exception handler.*
*To point to using an exception handler is to keep running the code in cases which are "minor" problems from a view of the program:*
  * *to avoid a bad input that can broke the consistency of the code*,
  * *to avoid an index error with limiting the steps for the user*,
  
 *Or to prevent some mayor problem. For example, important sequences should properly given for the program. __Misspelling__ or __harmful__ injections
can be handled with exception in the case that the code can not accept just the right one.*
  
### Security

#### What is SQL injection? How to protect an application against it?

SQL Injection (SQLi) is a type of an injection attack that makes it possible to execute malicious SQL statements. Prevent SQL Injection attacks with input validation and parametrized queries with prepared statements: do not use the input directly. Also sanitizing all input e.g.: remove potential malicious code elements such as single quotes and other special characters.

#### What is XSS? How to protect an application against it?

[XSS protect](https://www.computerweekly.com/tip/Cross-site-scripting-explained-How-to-prevent-XSS-attacks)
[sql injection](https://www.acunetix.com/websitesecurity/sql-injection/#:~:text=The%20only%20sure%20way%20to,inputs%20such%20as%20login%20forms.)

Cross-site script injection. Most of all:

    * Filter input on arrival. At the point where user input is received, filter as strictly as possible based on what is expected or valid input.
    * Encode data on output. At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
    * Use appropriate response headers. To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way you intend.
    * Content Security Policy. As a last line of defense, you can use Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.
    * Whitelist Values
    * HTTP-only Cookies : meaning that cookies will be received, stored, and sent by the browser, but cannot be modified or read by JavaScript.*
    * Disallow the characters – especially `<` and `>` characters – from being rendered*

#### How to properly store passwords?

In at least hashed form. Or hashed and salted.

#### What is HTTPS?

Hypertext Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP). 
It is used for secure communication over a computer network, and is widely used on the Internet It protects against man-in-the-middle attacks.

#### What is encryption and decryption?

[encryption](https://lab.getapp.com/common-encryption-methods/)

*Encryption:<br>
The process of translating plain text data (plaintext) into something that appears to be random and meaningless (ciphertext).*

*Decryption:<br>
The process of converting ciphertext back to plaintext.*

#### What is hashing?

![hashing](https://cheapsslsecurity.com/blog/wp-content/uploads/2017/08/hashing-function.jpg)

A hash function is where a computer takes an input of any length and content (e.g. letters, numbers, and symbols) 
and uses a mathematical formula to chop it, mix it up, and produce an output of a specific length.

#### What is the difference between encryption and hashing? When would you use which?

*The key difference between encryption and hashing is that encrypted strings can be reversed back into their original decrypted form if you have the right key.*<br>

*Hashing:<br>
Ideal way to store passwords, as hashes are inherently one-way in their nature.(+ salt)*

*Encryption:<br>
Ideal for sending secure messages.*

#### What encryption methods do you know?

[encryption methods](https://lab.getapp.com/common-encryption-methods/#:~:text=Advanced%20Encryption%20Standard%20(AES)&text=Each%20round%20consists%20of%20several,rest%20and%20data%20in%20transit.)
[encryption](https://www.goodcore.co.uk/blog/types-of-encryption/)

![Symmetric](data:image/jpeg;base64,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)

1. **Symmetric encryption:** <br>
Symmetric encryption uses a single key to encrypt as well as decrypt data. The key needs to be shared with all authorized people.

![Asymmetric](https://lab.getapp.com/wp-content/uploads/2019/07/GetApp_assymetric_encryption.png)

2. **Asymmetric encryption:** <br>
Also called public key cryptography, asymmetric encryption uses two separate keys—one public (shared with everyone) and one private (known only to the key’s generator). The public key is used to encrypt the data and the private key helps to decrypt it.

#### What hashing methods do you know?

[hashing](https://www.2brightsparks.com/resources/articles/introduction-to-hashing-and-its-uses.html)

1. MD5 
2. SHA-2

#### How/where would you store sensitive data (like db password, API key, ...) of your application?

Fist I would encrypt, and after on a secured server.

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?

![stack](https://journey.code.cool/v2/media/algorithms/stack-representation.jpg?jwt=ZXlKaGJHY2lPaUpJVXpJMU5pSjkuZXlKemRXSWlPaUpuWkc5eWFUSXdNVGhBWjIxaGFXd3VZMjl0SWl3aVpXMWhhV3dpT2lKblpHOXlhVEl3TVRoQVoyMWhhV3d1WTI5dElpd2labWx5YzNST1lXMWxJam9pUk1PemNtRWlMQ0pzWVhOMFRtRnRaU0k2SWtmRG9YTnd3NkZ5SWl3aVkyOTFiblJ5ZVNJNklraFZJaXdpYkc5allYUnBiMjRpT2lKQ1ZVUWlMQ0poY0hCeklqcGJYU3dpYm1KbUlqb3hOVGszT1RFeU1UZ3dMQ0psZUhBaU9qRTJNREExTURReE9EQjkuRHZaUnAwbm5zV0taeHVEYU5EREhERGRyazZvUlBaZTlqWkVtUnlRMHAzWQ==)

Stack data structure have just one pointer, adding operation (push) or removing operation (pop) take place from the top of the list, 
for example: LIFO (Last In First Out)

![queue](https://www.studytonight.com/data-structures/images/implementation-of-queue.png)

Queue have two pointers. One for each side of the list. The front side can take a new operation (enqueue),
to remove (dequeue) an operation the pointer should use the the rear side. Principle: FIFO (First In First Out)

#### What is BubbleSort? Describe the main logic of this sorting algorithm.

![bubblesort](https://www.w3resource.com/w3r_images/bubble-short.png)

_BubbleSort is a sorting method. Starting from the first element, comparing it with the next. If the next element higher then the previous move to the next. Else swap them. And so on till the last index._

#### Explain the process of finding the maximum and minimum value in a list of numbers!

Iterate trough the list of numbers. Set the first as highest/lowest. Then comparing each next element with the firsts and replace it with the first accordingly.

#### Explain the process of calculating the average value in an array of numbers!

Adding each element value together and dividing it with the the total element count.

#### What is Big O complexity? Explain time and space complexity!

![bigO](https://miro.medium.com/max/2544/1*yiyfZodqXNwMouC0-B0Wlg.png)
[bigO](https://medium.com/@zoebai_70369/big-o-notation-time-and-space-complexity-305a1e301e35#:~:text=Big%20O%20notation%20is%20used,space%20used%20by%20an%20algorithm.)

*Big O Notation is to describe the complexity of an algorithm. How long an algorithm takes to run. It is to compare the efficiency of different approaches to a problem.*
  * How quickly the runtime grows : use Big O Notation to talk about how quickly the runtime grows.
  * Relative to the input : With Big O Notation, we use the size of the input, which we call “n”. So we can say things like the runtime grows “on the order of the size of the  - input” (O(n)) or “on the order of the square of the size of the input” (O(n²)).
  * As the input gets larger : we care more about the stuff that grows fastest as the input grows, because everything else is quickly eclipsed as n gets very large.

#### Explain the process of calculating the average value in a list of numbers!

Similar to the average counting of an array. We have to move along each nodes and adding together the values, than dividing them with the total nodes count.

### Procedural

#### How the CASE condition works in SQL?

CASE is a program-flow controlling structure, it checks the cases ,when the condition is true it goes into and execute it and never checks the cases after, if none of the cases are true , it executes what is in the else clause.

#### How the switch-case condition works in JavaScript?

*The switch statement is used to perform different actions based on different conditions.<br>
Use the switch statement to select one of many code blocks to be executed.*

#### How to achieve a switch-case-like structure in Python?

*The Pythonic way to implement switch statement is to use the powerful dictionary mappings, also known as associative arrays, that provide simple one-to-one key-value mappings.*

```Python
def switch_demo(argument):
   switcher = {
       1: "January",
       2: "February",
       3: "March",
       4: "April",
       5: "May",
       6: "June",
       7: "July",
       8: "August",
       9: "September",
       10: "October",
       11: "November",
       12: "December"
   }
   print(switcher.get(argument, "Invalid month")) # Invalid month is default if number not found
```

#### Explain variable scoping in Python!

`LEGB Rule`

*L, Local — Names assigned in any way within a function (def or lambda)),
and not declared global in that function.*

*E, Enclosing-function locals — Name in the local scope of any and
all statically enclosing functions (def or lambda), from inner to outer.*

*G, Global (module) — Names assigned at the top-level of a module file,
or by executing a global statement in a def within the file.*

*B, Built-in (Python) — Names preassigned in the built-in names module : open,range,SyntaxError,...*

*example:*
```Python
code1
class Foo:
   code2
   def spam.....
      code3
      for code4..:
       code5
       x()
```
*The for loop does not have its own namespace. In LEGB order, the scopes would be*

*L : local, in def spam (in code3, code 4, code5).*

*E : Enclosed function, any enclosing functions (if the whole example were in another def)*

*G : Global. Were there any x declared globally in the module (code1)?*

*B : Any builtin x in Python.*

*x will never be found in code2*

#### What’s the difference between const and var in JavaScript?

var is a variable, the value can be modified after all. const is a constant, the value is immutable, can't be reassigned after declaration.

#### How the list comprehension looks like in Python?

```Python
squares = []

for x in range(10):
    squares.append(x**2)
 
print(squares)
#result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# Or you can use list comprehensions to get the same result:
squares = [x**2 for x in range(10)]

print(squares)
#result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```     

#### How the “ternary expression” looks like in Python?

```Python
a = val_if_true if test else val_if_false
in action:
d = {'a': 'x', 'b': 'y', 'c': 'x'}

def has_unique_value(k):
    return d.values().count(d[k]) == 1

def keys_with_same_value_as_key(k):
    return set([key for key in d.keys() if d[key] == d[k]])

print( {d[k]:k if has_unique_value(k) else keys_with_same_value_as_key(k) for k in d.keys()} )
```

#### How the ternary expression looks like in JavaScript?

*with if/else:*

```Javascript
if (person.age >= 16) {
  person.driver = 'Yes';
} else {
  person.driver = 'No';
}
with tenary expression:
person.driver = person.age >=16 ? 'Yes' : 'No';
```
#### How to import a function from another module in Python?

```Python
from module import module_name

calling: module_name.function_name
```

#### How to import a function from another module in JavaScript?

```Javascript
import "my-module.js";
    import myModule from "my-module.js";
    import {reallyReallyLongModuleMemberName as shortName} from "my-module.js";
```

### Functional

#### What is recursion?

*Recursive in function:<br>
The function calls itself again at the end of the execution with value(s) what is/are defined by itself. Can be other meanings too, e.g.: copying or deleting a folder in a recursive way will delete/copy the sub folders too.*

#### Write a recursive function which calculates the Fibonacci numbers!

```Javascript
function fibo(limit, firstNumber, secondNumber) {
        if (limit === 0) {
            break;
        } else {
		limit -= 1;
		let nextFiboNum = firstNumber + secondNumber;
	    	console.log(nextFiboNum);
	   	firstNumber = secondNumber;
	    	secondNumber = nextFiboNum;
		fibo(limit, firstNumber, secondNumber) 
	    }
    }
```

#### How to store a function in a variable in Python?

```Python
def my_function():
    print("this is the function")

function_variable = my_function
```

#### List the ways of defining a callable logical unit in JavaScript!

* *concise method syntax:*

```Javascript
      let obj = {
              myMethod(arg1, arg2) {
                  ...
              }
          };
```

* *arrow function*

 ```Javascript
    const foo = (arg1, arg2) => {
        ...
    };
 ```

#### What is an event listener? How to attach one?

* Event listeners give functionality to the application. Trough them can be triggered a function by the user. Locating the target, attaching a listener function and in the callback handling the event with an event handler function.
    * Locating:
        * object: window or document
        * methods: getElementById ,getElementsBy[TagName, .ClassName],
* querySelector, querySelectorAll
    * Attaching:
        * method: addEventListener
        * event listener: a string named event listener type
        * event handler: a callable function
        
	example:

```Javascript
document.querySelector(".Btn").addEventListener("click", displayDate);
```

#### How to trigger an event in JavaScript?

Event listeners have a target, which they listen for. It can be triggered by:
    * mouse actions
    * keyboard actions
    * content load (or change) actions

#### What is a callback function? Tell some examples of its usage.

*A callback is a function that is to be executed after another function has finished executing — hence the name ‘call back’.
More complexly put: In JavaScript, functions are objects. Because of this, functions can take functions as arguments, and can be returned by other functions.*

```Javascript
function doHomework(subject, callback) {
 alert(`Starting my ${subject} homework.`);
 callback();
}
function alertFinished(){
 alert('Finished my homework');
}
doHomework('math', alertFinished);
```

*As you can see, we’ve passed the alertFinished function definition as an argument during our doHomework() function call!*

#### What is a Python decorator? How does it work? Tell some examples of its usage.

*A decorator takes in a function, adds some functionality and returns it.*

```Javascript
def smart_divide(func):
   def inner(a,b):
      print("I am going to divide",a,"and",b)
      if b == 0:
         print("Whoops! cannot divide")
         return

      return func(a,b)
   return inner

@smart_divide
def divide(a,b):
    return a/b
```

#### What is the difference between synchronous and asynchronous execution?

When you execute something **synchronously**, you wait for it to finish before moving on to another task. When you execute something asynchronously, you can move on to another task before it finishes.<br>
Synchronous execution means the execution happens in a single series.

`A->B->C->D`

If you are calling those routines, A will run, then finish, then B will start, then finish, then C will start, etc.<br>
With **Asynchronous** execution, you begin a routine, and let it run in the background while you start your next, then at some point, say "wait for this to finish". It's more like:<br>

`Start A->B->C->D->Wait for A to finish`

The advantage is that you can execute B, C, and or D while A is still running (in the background, on a separate thread), so you can take better advantage of your resources and have fewer "hangs" or "waits".

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?

I need a connection string and a connection object from the database provider to set a session with the database server. For phyton we can use the psycopg2 module api's to connect an application with psql database.

`Everything On One Server`:<br>
*The entire environment resides on a single server. For a typical web application, that would include the web server, application server, and database server.*

`Separate Database Server`:<br>
*The database management system (DBMS) can be separated from the rest of the environment to eliminate the resource contention between the application and the database, and to increase security.*

#### When do you use the DISTINCT keyword in SQL?

*DISTINCT clause is used in the SELECT statement to remove duplicate rows from a result set.*

#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?
  
  * *WHERE:<br>*
      *It's equal to `if` in programming languages. It's used to "filter" the data based on conditions.*
  * GROUP BY:<br>
      *The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".<br>*
      *It is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.*
  * HAVING:<br>
      *HAVING is the same as WHERE. It's needed, as WHERE can't be used in aggregate functions.*
  * ORDER BY:<br>
      *The ORDER BY keyword is used to sort the result-set in ascending or descending order.*

#### What are aggregate functions in SQL? Give 3 examples.

An aggregate function performs a calculation on a set of values, and returns a single value.
  1. **COUNT()**: *Returns the number of rows that matches a specified criterion.*
  2. **MAX()**: *Returns the highest value of the selected column.*
  3. **MIN()**: *Returns the smallest value of the selected column.*
  4. **SUM()**: *Returns the total sum of a numeric column.*
  5. **AVG()**: *Returns the average value of a numeric column.*

#### What kind of JOIN types do you know in SQL? Could you give examples?

**Inner Join:**<br>
*(returns records at the intersection of the two tables.)*
```postgresql
select first_name, last_name, order_date, order_amount
from customers c
inner join orders o
on c.customer_id = o.customer_id
```

**Left Join:**<br>
*(A left join returns all records from table A and any matching records from table B.)*
```postgresql
select first_name, last_name, order_date, order_amount
from customers c
left join orders o
on c.customer_id = o.customer_id
```

**Right Join:**<br>
*Right join is a mirror version of the left join and allows to get a list of all orders, appended with customer information.)*

**Full Join:**<br>
*Finally, for a list of all records from both tables, we can use a full join.)*

#### What are the constraints in sql?

*SQL constraints are used to specify rules for data in a table.*
**NOT NULL** - *Ensures that a column cannot have a NULL value*
**UNIQUE** - *Ensures that all values in a column are different*
**PRIMARY KEY** - *A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table*
**FOREIGN KEY** - *Uniquely identifies a row/record in another table*

#### What is a cursor in SQL? Why would you use one?

*A cursor is a temporary work area created in the system memory when a SQL statement is executed.<br> 
A cursor contains information on a select statement and the rows of data accessed by it.<br>
This temporary work area is used to store the data retrieved from the database, and manipulate this data. A cursor can hold more than one row, but can process only one row at a time. The set of rows the cursor holds is called the active set.*

#### What are database indexes? When to use?

*A database index is a data structure that improves the speed of data retrieval operations on a database table at the cost of additional writes and storage space to maintain the index data structure. Indexes are used to quickly locate data without having to search every row in a database table.*

#### What are database transactions? When to use?

*A transaction is a unit of work that you want to treat as "a whole." It has to either happen in full or not at all.<br>
A classical example is transferring money from one bank account to another. To do that you have first to withdraw the amount from the source account, and then deposit it to the destination account. The operation has to succeed in full. If you stop halfway, the money will be lost, and that is Very Bad.<br>
In modern databases transactions also do some other things - like ensure that you can't access data that another person has written halfway. But the basic idea is the same - transactions are there to ensure, that no matter what happens, the data you work with will be in a sensible state. They guarantee that there will NOT be a situation where money is withdrawn from one account, but not deposited to another.*

#### What kind of database relations do you know? How to define them?

**One-to-One:**<br>
*A row in table A can have only one matching row in table B, and vice versa.*

**One-to-Many (or Many-to-One):**<br>
*This is the most common relationship type. In this type of relationship,<br>
a row in table A can have many matching rows in table B,<br>
but a row in table B can have only one matching row in table A.<br>
(Each customer can only be assigned one city. One city can be assigned to many customers.)*

**Many-to-Many:**<br>
*A many-to-many relationship could be thought of as two one-to-many relationships,<br>
linked by an intermediary table( “cross-reference table”).<br>
(So in order to create a many-to-many relationship between the Customers table and the Products table,
we created a new table called Orders.)*

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?

```postgresql
SELECT * FROM table WHERE city = 'Miskolc';
```

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

I would create a log table and create a trigger on that will insert a row into person_log table whenever the table/s row/s get updated/deletes/added

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?

*Both HTML and XML are markup languages, which represents text data in proper format using tags. However they are used for completely different purposes.*

*Similarities between HTML and XML:*
 1. *Both are languages of web.*
 2. *Both are markup languages.*
 3. *Both are originated from SGML. "Standardized General Markup Language".*
 4. *Tags are basic building blocks of both HTML and XML documents.*
 
 *Differences between HTML and XML:*
 1. *HTML tags are predefined tags where as XML tags are user defined tags.*
 2. *HTML tags are limited number of tags where as XML tags are extensible.*
 3. *HTML tags are case insensitive where as XML tags are sensitive.*
 4. *HTML tags are meant for displaying the data but not for describing the data where as XML tags are meant for describing the data.*
 5. *HTML focuses on how data looks where as XML focuses on what data is.*

XHTML:
1. *XHTML stands for EXtensible HyperText Markup Language*
2. *XHTML is almost identical to HTML*
3. *XHTML is stricter than HTML*
4. *XHTML is HTML defined as an XML application*

#### How to include a JavaScript file in a webpage?

*Using the script tag in .html file:*
```HTML
<script type="text/javascript" src="path-to-javascript-file.js"></script>
```

#### How to include a CSS file in a webpage?

*Using the link tag in .html file:*

```HTML
<link rel="stylesheet" type="text/css" href="stylesheet.css"/>
```

#### How to select an element using its id in CSS?

*You have to use the hashtag(#) + the element id name:*

```CSS
#elementIdName {
    /*code;*/
}
```

#### How to select elements using their class in CSS?

*You have to use the dot(.) + the element class name:*

```CSS
.elementClassName {
    /*code;*/
}
```

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?

*You have to define in css file with dot classname dot classname:*

```CSS
.alpha.beta{color:red;}
/*here you can reach the beta class*/
```

#### How to select all list items in all ordered lists on the page in CSS?

*You can reach by using the ordered tag which is < ol >:*
```CSS
ol {
 /*code;*/
}
```

#### How to select elements using their attributes in CSS?

```CSS
/*We can reach differently*/y

[data-value] {
  /* Attribute exists */
}

[data-value="foo"] {
  /* Attribute has this exact value */
}

[data-value*="foo"] {
  /* Attribute value contains this value somewhere in it */
}

[data-value~="foo"] {
  /* Attribute has this value in a space-separated list somewhere */
}

[data-value^="foo"] {
  /* Attribute value starts with this */
}

[data-value|="foo"] {
  /* Attribute value starts with this in a dash-separated list */
}

[data-value$="foo"] {
  /* Attribute value ends with this */
}
```

#### What are UX and UI?

**UI:**<br>
*The "UI" in UI design stands for “user interface.” The user interface is the graphical layout of an application. It consists of the buttons users click on, the text they read, the images, sliders, text entry fields, and all the rest of the items the user interacts with. This includes screen layout, transitions, interface animations and every single micro-interaction. Any sort of visual element, interaction, or animation must all be designed.*

**UX:**<br>
*It stands for “user experience.” A user’s experience of the app is determined by how they interact with it. User experience is determined by how easy or difficult it is to interact with the user interface elements that the UI designers have created.*


#### Please list some points that an application should fulfill to have good UX.

* Fulfill the users' needs
* Have a clear stucture
* Consistency
* Understandable
* Usability

#### What is XML, XSLT, DTD?

*First we will start at the top. The VERY top. SGML stands for Standard Generalized Markup Language. Simply put, it is the very root coding of coding. HTML is an application of SGML.*

**XML** *is a simplified subset of SGML. It stands for eXtensible Markup Language.*<br>
**DTD** *stands for Document Type Declaration. It is a set of instructions that states what tags are usable and what (re)action they create. Each browser has a DTD set in it's programming set by the browser companies. This is how some tags will work in only one type of browser or version. It has the tags stated in it's DTD. XML makes it possible to create unique tag sets by applying it's own DTD. This makes the DTD more compatable with more browsers.*<br>
**XSLT** *stands for eXtensible Stylesheet Language Transformation. It is a strong verions of CSS that formats the XML page for viewing.*

#### What is the difference between HTML and XML?

 1. *HTML tags are predefined tags where as XML tags are user defined tags.*
 2. *HTML tags are limited number of tags where as XML tags are extensible.*
 3. *HTML tags are case insensitive where as XML tags are sensitive.*
 4. *HTML tags are meant for displaying the data but not for describing the data where as XML tags are meant for describing the data.*
 5. *HTML focuses on how data looks where as XML focuses on what data is.*

### Javascript

#### What is javascript?

*JS is a scripting language designed to control web page content.<br>*
  * *can update and change both HTML and CSS*
  * *can calculate, manipulate and validate data.*

#### When to use AJAX? Bring examples of its usage.

*AJAX stands for "Asynchronous Javascript and XML".<br>*
*AJAX programming is used, for exchanging data in the background without actually disturbing the user experience, and for rendering the access of data more efficiently and effectively.*
*Things That Are Good for AJAX:*
    * *Form validation (It's so much nicer when the form tells
        you as you are typing if you've filled it out wrong or not.),*
    * *Comments when a commenter hits the comment button, it's nice to see the comment appear immediately on the page.),*
    * *Login Forms,*
    * *Auto-Complete(when searching for example),*
    * *Voting and Rating (forums),*
    * *Updating With User Content,*
    * *Chat Rooms And Instant Messaging,*
    * *Lightboxes instead of pop-ups*
    
#### What is DOM and how to manipulate it from Javascript?

*DOM - Document Object Model DOM is representative displaying for the according html document, and those objects can be modified.<br>*
  * *Creating, removing or replacing an element*
  * *Modifying an element's text and/or HTML content*
  * *Getting an element content and working with it*

```Javascript
let element = document.querySelector('selector')

/* You can use it to get the element from the DOM and save
it as a variable, and manipulate it.  */


let btn = document.querySelector('button');
btn.addEventListener('click', foo);

/*Or give it a event listener for a specific  element*/


let pEle = document.createElement('p')

/*You can even create elements*/


let div = document.querySelector('div');
div.setAttribute('contentEditable', '')
/* method either adds a new attribute to an HTML element, or updates the value*/
```

#### What are events and how/why to use them in Javascript?

*Events occur when the page loads, when user interacts (clicks, hovers, changes) and myriad other times, and can be triggered manually too.*

*The addEventListener method is the most preferred way to add an event listener to window, document or any other element in the DOM,<br>
because JavaScript in the browser uses an event-driven programming model.* **Everything starts by following an event**

```Javascript
let btn = document.querySelector('button');
btn.addEventListener('click',function(event) {
  }
);
```

#### What is event bubbling/capturing? How would you use it?

*Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event.
When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.
With capturing, the event is first captured by the outermost element and propagated to the inner elements.
Event capturing:*

```
---------------| |-----------------
| element1     | |                |
|   -----------| |-----------     |
|   |element2  \ /          |     |
|   -------------------------     |
|        Event CAPTURING          |
-----------------------------------
```

*The event handler of element1 fires first, the event handler of element2 fires last.
Event bubbling:*

```
               / \
---------------| |-----------------
| element1     | |                |
|   -----------| |-----------     |
|   |element2  | |          |     |
|   -------------------------     |
|        Event BUBBLING           |
-----------------------------------
```

*The event handler of element2 fires first, the event handler of element1 fires last.*

#### What is JSON and how do we use it?

*JSON is short for JavaScript Object Notation, and is a way to store information in an organized, easy-to-access manner. In a nutshell, it gives us a human-readable collection of data that we can access in a really logical manner. JSON (in Javascript) is a string.<br>
How to use it:<br>
In short, you are forced to communicate things using key-value pairs and arrays.<br>
JSON is basically a way of communicating data to someone, with very, very specific rules.*

## Software engineering

### Version control

#### What type of branching strategy would you use?

*I would use* **Gitflow Workflow**:
  * *Code in master is deployable at all times,*
  * *When you want to start working on a new task, create a new branch off of master and give it a descriptive name,*
  * *Commit to that branch locally and regularly send your work to the same-named branch on the server,*
  * *Open a pull request when you feel your changes are ready to be merged (or even if you aren’t so sure, but would like some feedback),*
  * *After the new feature is revised and approved, you can merge it into master,*
  * *Once your changes are merged and pushed to the master, you can and should delete the branch.*

#### What would you do if you find a bug on the production code (master branch)?

*I would report it to my project manager. And he/she would tell us how/who should fix it.<br>
Alternatively, I would open a new branch, locate and fix the bug, after testing merge it back to master.*

#### How can you move changes from one branch to another in GIT?

*Make and checkout to a new branch will copy the actual state of the original branch where can be rollback or set back status. Rebase or merge bring changes from another branch into the current one.*

```git
git branch checkout <branchname>
```

#### How does a VCS help with code reviews?

 * *Modern version control systems are designed to help address problems that teams face when collaborating.*
 * *Breaking down silos and embracing more perspectives and conversations can enable you and your team to deliver better software.*

#### What is your favorite git command? Why?

git clone  It’s a new exciting beginning.

#### What does remote/local mean in Git?

`remote`  -> *Repository's server, storing the repo online.*<br>
`local`   -> *The repository's offline, local, on-disk stored version, which we make the changes on.*

### DevOps

#### Why is it good to use a package manager software?

  * *They prevent mixing incompatible files/libraries.*
  * *They establish a shared convention for managing libraries.(When new developers come onto your project, team, company, etc., they're likely to know the conventions of the package manager. This means they don't have to waste time figuring out the fine details of how libraries are managed in your code base.)*
  * *They give you a standard way of versioning and distributing your own dependencies and files that don't belong in your repository.*
  * *Some package managers provide additional features during installation.*
  * *They tend to centralize hosting and distribution.*
  * *Helps with complex dependency trees (and that can be managed downloading a dependency together with all its dependencies).*
  * *Packages contain metadata, such as the software's name, description of its purpose, version number, vendor, checksum, and a list of dependencies necessary for the software to run properly*


#### Why is it good to use a virtual environment for a project?

  * *Dependency Management: Prevent conflicts between dependencies of multiple projects.*
  * *Every project can have a single unique virtual environment with the specific packages.*

### Networks

#### What kind of HTTP status codes do you know?

* 100–199 - Informational responses
* 200–299 - Successful responses
* 300–399 - Redirects
* 400–499 - Client errors
* 500–599 - Server errors

* **418 - I'm a teapot**

#### What is a API?

*API stands for Application Programming Interface.<br>
An API, or application programming interface, is essentially a way for apps to borrow functionality and data from each other.<br>
An API is code, that allows two software programs to communicate with each other. One program can call another programs API to get access to data or functionality of the other program.<br>
An API is the messenger that takes a request, tells a system what you want to do and then returns the response back to you.*

#### What is REST API?

*A REST API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data.*

#### What is JSON? When to use?

*JSON is short for JavaScript Object Notation, and is a way to store information in an organized, easy-to-access manner. In a nutshell, it gives us a human-readable collection of data that we can access in a really logical manner. JSON (in Javascript) is a string.<br>
How to use it:<br>
In short, you are forced to communicate things using key-value pairs and arrays.<br>
JSON is basically a way of communicating data to someone, with very, very specific rules.<br>
For fast and and effective communication between server-user for example.*

#### What is TCP/IP? What layers does it define, what are they responsible for?

*Transmission Control Protocol/Internet Protocol (TCP/IP) is the language a computer uses to access the internet.<br>
It consists of a suite of protocols designed to establish a network of networks to provide a host with access to the internet.<br>
(It's like a set of rules to allow communication to each other)*

| **Layer** | **Primary function** | **Examples** |
|:-:|:-:|:-:|
| *Application* | *Do useful work* | *HTTP, SMTP, POP, Ping, FTP* |
| *Transport* | *Control the flow of information between the application program running on the client and the application program running on the server* | *TCP (reliable), UDP (not reliable)* |
| *Network* | *Route packets between networks (inter-network)* | *IP* |
| *Data link* | *Move data within a local area network* | *Ethernet, ATM, PPP* |
| *Physical* | *Define the physical characteristics of the communication hardware and medium* | *Radio, twisted pair, fiber* |

#### What’s the difference between TCP and UDP?

*TCP (Transmission Control Protocol) is connection oriented, whereas UDP (User Datagram Protocol) is connection-less.<br>
This means that TCP tracks all data sent, requiring acknowledgment for each octet (generally). UDP does not use acknowledgments at all, and is usually used for protocols where a few lost datagrams do not matter.*

| **TCP** | **UDP** |
|:-:|:-:|
| *Reliable* | *Unreliable* |
| *Connection-oriented* | *Connectionless* |
| *Segment retransmission and flow control through windowing* | *No windowing or retransmission* |
| *Segment sequencing* | *No sequencing* |
| *Acknowledge sequencing* | *No acknowledgment* |

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?

*A simple request message from a client computer consists of the following components:*<br>
  * *A request line to get a required resource, for example a request GET /content/page1.html is requesting a resource called /content/page1.html from the server.*
  * *Headers (Example – Accept-Language: EN).*
  * *An empty line.*
  * *A message body which is optional.*
  * *All the lines should end with a carriage return and line feed. The empty line should only contains carriage return and line feed without any spaces.*

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?

*A simple response from the server contains the following components:*
  * *HTTP Status Code (For example HTTP/1.1 301 Moved Permanently, means the requested resource was permanently moved and redirecting to some other resource).*
  * *Headers (Example – Content-Type: html)*
  * *An empty line.*
  * *A message body which is optional.*

#### What is DNS? How does it work?

*Domain Name Servers (DNS) are the Internet's equivalent of a phone book. They maintain a directory of domain names and translate them to Internet Protocol (IP) addresses.*

#### What is a web server?

*A Web server is a program that uses HTTP (Hypertext Transfer Protocol) to serve the files that form Web pages to users, in response to their requests, which are forwarded by their computers' HTTP clients. Dedicated computers and appliances may be referred to as Web servers as well.*

#### Explain the client-server architecture.

*Client-server architecture, architecture of a computer network in which many clients (remote processors) request and receive service from a centralized server (host computer).*<br>
*Client computers provide an interface to allow a computer user to request services of the server and to display the results the server returns.*

#### What would you use a session for?

*The purpose for `session` is to* **store data** *that you (as the web application developer) would like to have preserved across page loads.<br>
Thus, you can set flags in your login script such as *`logged_in`, *to check if the user is logged in, and on any other page check* `session['logged_in'] == true`*, instead of querying for that information.*
  * *Sessions use a cookie as a key of sorts, to associate with the data that is stored on the server side.*
  * *IDU is stored on server (i.e. server-side)*
  * *Safer (because of 1)*
  * *Expiration can not be set, session variables will be expired when users close the browser.*

#### What would you use a cookie for?

*You can save settings to cookie for the websites between visits, so its gonna remember your previous preferences.*<br>
*Cookies:*
  * *IDU is stored on web-browser (i.e. client-side)*
  * *Not very safe, since hackers can reach and get your information (because of 1)*
  * *Expiration can be set (see setcookies() for more information)*

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?

**Waterfall development methodology:**<br>
`-> Requirements -> Desing -> Implementation -> Verification -> Maintanance`<br> 
It’s a rigid linear model that consists of sequential phases (requirements, design, implementation, verification, maintenance) in which distinct goals are accomplished.<br>
Each phase must be ***100% complete before the next phase can start***, and traditionally there is no process for going back to modify the project or direction.

**Agile:**<br>
***Adaptive*** *approach which is able to respond to the changing requirements of the clients. Direct communication and feedback from customer.*

**Agile development methodology:**<br>
 * *Requirement/Features/User stories/Product Backlog*
 * *Scrum Team(with lead)*
 * *Sprint Planning(relative time)*
 * *Sprints 1-4 Weeks Duration* 
 * *Production deployment*
 * *Done Checklist*
 *(While this process other people making the desing,build it,inegrate,test the software)*
 * *Sprint Retrospective*
 * *Product review(customer input)*
 * *Potential Product Increment*

#### What are the SCRUM roles?

  1. *One of the most important things for the success of scrum is the role of the `Product Owner`, who serves as an interface between the team and other involved parties (stakeholders).*
  2. *The* `Scrum Master` *does not interfere into the decisions of the team regarding specifically the development, but rather is there for the team as an advisor. He only interferes actively when anybody of the team or any other participant of a project (Stakeholder) does not obey the rules of Scrum.*
  3. *The* `Development Team` *in Scrum a team is not just the executive organ that receives its tasks from the project leader, it rather decides self dependent, which requirements or User Stories it can accomplish in one sprint.*

#### What are the SCRUM ceremonies?

**Ceremonies**
* *Sprint Planning*
* *Sprint review*
* *Sprint retrospective*
* *Daily Scrum*

#### What are the SCRUM artifacts?

**Artifacts**
* *Increment*
* *Product backlog*
* *Sprint backlog*

#### What is the main goal of a retrospective meeting?

*This is where the Scrum Team meets ***to reflect on their previous Sprint and to figure out how to improve as a team*** by asking – what went well, what did not and what can be improved. It allows the team to focus on its overall performance and identify strategies for continuous improvement.*

#### Explain, when would you recommend to use the waterfall methodology?

*Use Waterfall when:*
  * *The project is simple,*
  * *The project is complicated, but you have the expertise to deliver it,*
  * *It is all you know and you have no support for change,*
  * *The upfront investment is not risky to make,*
  * *You focus your performance measures on delivery date and budget.*