### Python是什么? 列出一些Python语言的特性。

Python是一种现代强大的解释语言，包含对象、模块、线程、异常和自动内存管理。

Guido van Rossum在1991年向全世界介绍了Python。

Python的突出特征

- 简单 & 容易：Python是简单的语言并且容易学习。
- 自由 / 开源：这意味着每个人都可以使用python并且无需购买许可证。
- 高级语言：当用Python编程时不必考虑底层的细节。
- 可移植：Python程序是与机器和平台无关的。
- 可扩展：Python程序可以和C / C++一起使用。
- 可嵌入：Python程序可以嵌入C / c++代码；还可以当作脚本语言。
- 标准库：Python标准库包含内置的编程工具。
- 内置的数据结构：包含很多数据结构如列表,数字和字典。

### 请解释如何python是如何解释执行的。

Python程序直接从源代码运行。每种类型的Python程序正在执行的代码都是必需的。
Python把程序员写的源代码转换成中间语言，然后再把中间语言转换成计算机可执行的机器语言，所以Python是解释性语言。

### Python中局部和全局变量的规则是什么？

如果一个变量是在函数外定义，那么它是隐式全局。如果变量在函数内可以被赋予新的值，则意味着它是本地的。
如果我们希望把它全局化，我们需要将其明确定义为全局的。函数内部的变量引用是隐式全局。
下面的代码片段将进一步解释它们的差异：

```python
#!/usr/bin/python
# Filename: variable_localglobal.py
def fun1(a):
    print 'a:', a
    a= 33;
    print 'local a: ', a
a = 100
fun1(a)
print 'a outside fun1:', a
def fun2():
    global b
    print 'b: ', b
    b = 33
    print 'global b:', b
b =100
fun2()
print 'b outside fun2', b
```
Output

```bash
$ python variable_localglobal.py
a: 100
local a: 33
a outside fun1: 100
b :100
global b: 33
b outside fun2: 33
```

### 请解释Python中的字典类型。

字典是Python的内置数据类型，它定义了键和值之间一对一的关系。

- 字典包括成对的键和它们的相应的值。
- 字典是由键索引。
- 字典类似于关联数组或其他语言的哈希表。

下面的例子将进一步解释 - `India`, `Angel` 和 `Cartoon` 是键，与之一一对应的值是`Bharat`, `Mother Teresa` 和 `Mickey`：

```python
>>> dict = {'India': 'Bharat', 'Angel': ‘Mother Teresa’, 'Cartoon': 'Mickey'}
>>>print dict[India]
Bharat
>>>print dict[Angel]
Mother Teresa
```

### Python中我们如何共享模块间的全局变量？

我们可以创建一个配置文件，存储要在模块或脚本间共享的整个全局变量。
通过导入配置文件，那些定义在配置文件中的全局变量将可在其他模块使用。
比如我想要`a，b，c`在模块之间共享：

``` python
#config.py:

a=0
b=0
c=0

#module1.py:

import config
config.a = 1
config.b =2
config.c=3
print “ a, b & resp. are : “ , config.a, config.b, config.c
``` 
output of module1.py will be   
1 2 3

### Python中我们如何在方法间传递可选参数或关键字参数？

在函数的参数列表中可以同时使用`*`和`**`符。把位置参数作为`tuple`，关键字参数作为`dictionary`，
然后，当调用另一个功能时可以通过使用`*`与`**`来传递参数：

```python
def fun1(a, *tup, **keywordArg):
    ...
    keywordArg['width']='23.3c'
    ...
    Fun2(a, *tup, **keywordArg)
```

### 请解释序列操作中的索引和切片

Python中有不同类型的序列 - 字符串，Unicode字符串，列表，元组，缓冲器，还有xrange对象，切片和索引是序列操作的显著特征。
索引操作允许直接访问序列（类似数组/列表索引）中的特定项，切片操作允许检索出序列的一部分。
切片操作符通过在指定的序列名后跟一对方括号，括号内包含可选的用冒号分隔的一对数字来表示，如S[startno: stopno]。
切片操作符中的`startno`表示从哪里开始切片，`stopno`表示切片将在该位置停止。
如果省略了startno，Python将在序列的开头处开始。如果省略了stopno，Python将在序列结束处停止。
下面的代码将进一步解释索引和切片操作：

```python
>>> cosmeticList =[‘lipsstick’,’facepowder’,eyeliner’,’blusher’,kajal’] 
>>> print “Slicing operation :”,cosmeticList[2:]
Slicing operation :[‘eyeliner’,’blusher’,kajal’]
>>>print “Indexing operation :”,cosmeticList[0]
“Indexing operation :lipsstick
```

### 什么是lambda形式？请解释断言？

lambda形式:

使用lambda关键字创建微小的匿名函数。
这是Python的一个非常强大的功能，它在运行时声明了一行未知的小函数。lambda用于创建新的功能的对象，然后在运行时返回它们。

lambda的一般语法为：
```python
lambda parameter(s): expression using the parameter(s)
```

比如k是lambda函数:
```python
>>> k= lambda y: y + y
>>> k(30)
60
>>> k(40)
80
``` 

断言:

Python在1.5版本中引入的内置`assert`语句用来断言某些东西是真实的。
程序员常常在函数的开始处用断言检查输入是否有效，在函数调用后用断言检查输出是否有效，程序测试结束后断言语句可以删除。
如果断言的计算结果是假的，将抛出一个`AssertionError`异常。 AssertionError异常可以用try-except来处理。

断言语句的一般语法为：
```python 
assert Expression[, Arguments]
```

### 请解释repr函数的作用。

Python可以通过利用两个函数`repr()`或`str()`将任何值转换为字符串。
str()函数返回人类可读的值的表示形式，而repr()生成可以由解释器读取的形式。
repr()返回机器可读的值的表示形式，适合于exec命令。
下面的代码片段展示repr()和str()的工作：

```python
def fun():
    y=2333.3
    x=str(y)
    z=repr(y)
    print " y :",y
    print "str(y) :",x
    print "repr(y):",z

fun()
#-------------#
#output
y : 2333.3
str(y) : 2333.3
repr(y) : 2333.3000000000002
```

### 请解释pickling和unpickling。

pickle是序列化和反序列化Python对象结构的标准模块。

pickle模块接受任何Python对象，将它转换成一个字符串表示形式，转储到一个以后可以使用的文件中（通过使用`dump()`函数），这个过程称为pickling；而unpickle是用于将存储字符串表示形式装换为原始Python对象的过程。

### Python的列表推导特点是什么？

Python在2.0中引入列表推导特性，它基于现有列表创建新列表。
它通过一个函数将每个现有列表中的元素映射成另一个列表元素。
列表推导不用`map()` , `filter()` 或 `lambda`创建列表。

### Python如何进行内存管理？

Python中的内存管理涉及包含所有的Python对象和数据结构的私有堆。解释器接管了Python中的堆，然而程序员无法访问它。
堆空间Python对象的分配由Python的内存管理器完成。 Python中的核心API提供了让程序员编写更可靠，更健壮的程序的一些工具。
Python中也有一个内置的垃圾收集器回收所有的未使用的内存。
当一个对象不再被程序引用时，它占用的堆空间就可以被释放。
垃圾回收器确定不再被程序所引用的对象，释放它们占用的内存，并使其对堆空间可用。

GC的模块定义了启用/禁用垃圾收集器的函数：
```
gc.enable() - 启用自动垃圾收集。
gc.disable() - 停用自动垃圾收集。
```

### 你如何在Python中使用高阶函数？

高阶函数接受一个或多个函数作为输入，并返回一个新的函数。有时需要使用函数作为数据。
为了使用高阶函数，我们需要导入fucntools模块。
`functools.partial()`函数通常用于高阶函数。

### 请解释Python中如何复制一个对象？

Python中存在两种复制对象的方式：浅拷贝和深拷贝。
浅拷贝复制的越少越好，而深拷贝复制一切。
如果一个对象要被复制，然后

- copy.copy(a) returns a shallow copy of a.
- copy.deepcopy(a) returns a deep copy of a.

### 怎么Python的方法或属性？

Python内置的dir()方法，对一个实例显示了实例的类及其所有基类的按字母顺序定义的实例变量以及方法和类的属性。 
因此，任何对象作为参数传递给dir()，我们可以找到该对象所有的方法和对象的类的属性。

下面的代码片段显示dir()如何工作：

```python
class Employee:
    def __init__(self,name,empCode,pay):
        self.name=name
        self.empCode=empCode
        self.pay=pay

e = Employee('name', 'empCode', 'pay')
print("dir()列出了Employee类的所有的方法和属性")
print dir(e)
-----------------------------------------------------
Output
dir()列出了Employee类的所有的方法和属性
[ '__init__', 'empCode', 'name', 'pay']
```

### How do I convert a string to a number?

Python contains several built-in functions to convert values from one data type to another data type.
The int function takes string and coverts it to an integer.

```
>>>s = "1234" # s is string
>>>i = int(s) # string converted to int
>>>print i+2
-------------------------
1236
The float function converts strings into float number.
>>>s = "1234.22" # s is string
>>>i = float(s) # string converted to float
>>>print i
-------------------------
1234.22
```
### What is a negative index in python?

Python arrays & list items can be accessed with positive or negative numbers (also known as index).
For instance our array/list is of size n, then for positive index 0 is the first index, 1 second, last index will be n-1. For negative index, -n is the first index, -(n-1) second, last negative index will be – 1.
A negative index accesses elements from the end of the list counting backwards.
An example to show negative index in python

```
>>> import array
>>> a= [1, 2, 3]
>>> print a[-3]
1
>>> print a[-2]
2
>>> print a[-1]
3
```
### How  an array in Python?

The array module contains methods for creating arrays of fixed types with homogeneous data types. Arrays are slower then list.
Array of characters, integers, floating point numbers can be created using array module.
array(typecode[, intializer])
Returns a new array whose items are constrained by typecode, and initialized from the optional initialized value. Where the typecode can be for instance ‘c’ for character value, ‘d’ for double, ‘f’ for float.



### Explain how to create a multidimensional list.

There are two ways in which Multidimensional list can be created:
By direct initializing the list as shown below to create multidimlist below

```
>>>multidimlist = [ [227, 122, 223],[222, 321, 192],[21, 122, 444]]
>>>print multidimlist[0]
>>>print multidimlist[1][2]
__________________________
Output 
[227, 122, 223]
192
```

The second approach is to create a list of the desired length first and then fill in each element with a newly created lists demonstrated below :

```
>>>list=[0]*3
>>>for i in range(3):
>>> list[i]=[0]*2
>>>for i in range (3):
>>> for j in range(2):
>>> list[i][j] = i+j
>>>print list
__________________________
Output 
[[0, 1], [1, 2], [2, 3]]
```
### Explain how to overload constructors (or methods) in Python.

`_init__ ()` is a first method defined in a class. when an instance of a class is created, python calls __init__() to initialize the attribute of the object.
Following example demonstrate further:

```
class Employee:

def __init__(self, name, empCode,pay):
self.name=name
self.empCode=empCode
self.pay=pay

e1 = Employee("Sarah",99,30000.00)

e2 = Employee("Asrar",100,60000.00)
print("Employee Details:")

print(" Name:",e1.name,"Code:", e1.empCode,"Pay:", e1.pay)
print(" Name:",e2.name,"Code:", e2.empCode,"Pay:", e2.pay)
---------------------------------------------------------------
Output

Employee Details:
(' Name:', 'Sarah', 'Code:', 99, 'Pay:', 30000.0)
(' Name:', 'Asrar', 'Code:', 100, 'Pay:', 60000.0)

```

### Desc to send mail from a Python script.

The smtplib module defines an SMTP client session object that can be used to send mail to any Internet machine.

A sample email is demonstrated below.

```
import smtplib
SERVER = smtplib.SMTP(‘smtp.server.domain’)
FROM = sender@mail.com
TO = ["user@mail.com"] # must be a list
SUBJECT = "Hello!"
TEXT = "This message was sent with Python's smtplib."
# Main message
message = """
From: Sarah Naaz < sender@mail.com >
To: CarreerRide user@mail.com
Subject: SMTP email msg
This is a test email. Acknowledge the email by responding.
""" % (FROM, ", ".join(TO), SUBJECT, TEXT)
server = smtplib.SMTP(SERVER)
server.sendmail(FROM, TO, message)
server.quit()
```



### Desc how to generate random numbers in Python.

Thee standard module random implements a random number generator.  

There are also many other in this module, such as:

```
uniform(a, b) returns a floating point number in the range [a, b].
randint(a, b)returns a random integer number in the range [a, b].
random()returns a floating point number in the range [0, 1].
```
Following code snippet show usage of all the three functions of module random:
Note: output of this code will be different evertime it is executed.

```
import random
i = random.randint(1,99)# i randomly initialized by integer between range 1 & 99
j= random.uniform(1,999)# j randomly initialized by float between range 1 & 999
k= random.random()# k randomly initialized by float between range 0 & 1
print("i :" ,i)
print("j :" ,j)
print("k :" ,k) 
__________
Output -
('i :', 64)
('j :', 701.85008797642115)
('k :', 0.18173593240301023)

Output-
('i :', 83)
('j :', 56.817584548210945)
('k :', 0.9946957743038618)
```

### How do we make python scripts executable?

Python scripts can be executed in two ways:
Suppose I want to execute script1.py
We can open the script1.py in IDE editor & run the script in the frontmost window of the python IDE by hitting the run all button.
Second way is using command prompt by making sure PATH is set appropriately directly type script name else type

```
>>>python script1.py

```

### Explain how to make Forms in python.
As python is scripting language forms processing is done by Python. We need to import cgi module to access form fields using FieldStorage class.

Every instance of class FieldStorage (for 'form') has the following attributes:

form.name: The name of the field, if specified. 
form.filename: If an FTP transaction, the client-side filename. 
form.value: The value of the field as a string. 
form.file: file object from which data can be read. 
form.type: The content type, if applicable. 
form.type_options: The options of the 'content-type' line of the HTTP request, returned as a dictionary. 
form.disposition: The field 'content-disposition'; None if unspecified. 
form.disposition_options: The options for 'content-disposition'. 
form.headers: All of the HTTP headers returned as a dictionary.

A code snippet of form handling in python:

```
import cgi

form = cgi.FieldStorage()
if not (form.has_key("name") and form.has_key("age")):
print "<H1>Name & Age not Entered</H1>"
print "Fill the Name & Age accurately."
return
print "<p>name:", form["name"].value
print "<p>Age:", form["age"].value

```

### Desc how to implement Cookies for Web python.
A cookie is an arbitrary string of characters that uniquely identify a session.

Each cookie is specific to one Web site and one user.

The Cookie module defines classes for abstracting the concept of cookies. It contains following method to creates cookie

```
Cookie.SimpleCookie([input])
Cookie.SerialCookie([input]
Cookie.SmartCookie([input])
for instance following code creates a new cookie ck-

import Cookie
ck= Cookie.SimpleCookie ( x )


```
### Desc how to use Sessions for Web python.

Sessions are the server side version of cookies. While a cookie preserves state at the client side, sessions preserves state at server side.

The session state is kept in a file or in a database at the server side. Each session is identified by a unique session id (SID). To make it possible to the client to identify himself to the server the SID must be created by the server and sent to the client whenever the client makes a request.

Session handling is done through the web.session module in the following manner:

```
import web.session session = web.session.start( option1, Option2,... )
session['myVariable'] = 'It can be requested'

```

### Desc how exceptions are handled in python.

Errors detected during execution of program are called exceptions. Exceptions can be handled using the try..except statement. 
We basically put our usual statements within the try-block and put all our error handlers in the except-block.

```
try…except demo code:
>>> while True:
try:
         x = int(raw_input("Enter no. of your choice: "))
         break
except ValueError:
         print "Oops! Not a valid number. Attempt again"

Enter no. of your choice: 12ww
Oops! Not a valid number. Attempt again
Enter no. of your choice: hi there
Oops! Not a valid number. Attempt again
Enter no. of your choice: 22
>>>


```
### What is used to create Unicode string in Python?


Unicode is a system to represent characters from all the world's different languages.
Two methods can be used to create unicode string:
unicode() method is unicode(string[, encoding, errors]), its arguments should be 8-bit strings. The first argument is converted to Unicode using the specified encoding, if encoding argument left, the ASCII encoding is used for the conversion.
encode() method is encode([encoding], [errors='strict']), which returns an 8-bit string version of the Unicode string.

### When to use list vs. tuple vs. dictionary vs. set?

List is like array, it can be used to store homogeneous as well as heterogeneous data type (It can store same data type as well as different data type). List are faster compared to array. Individual element of List data can be accessed using indexing & can be manipulated.

```
List Code Snippet:
list = ["Sarah",29,30000.00]
for i in range (3):
     print list[i]
------------------
Output
Sarah
29
30000.0
```

Tuples are similar to lists, but there data can be changed once created throught the execution of program. Individual element of Tuples can be accessed using indexing.

Tuples Code Snippet: The Days

```
days = ("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday")
print days
------------------------------
('Sunday', 'Mondays', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday')
```

Sets stores unordered values & have no index. And unlike Tuples and Lists, Sets can have no duplicate data, It is similar to Mathematical sets.

add() function can be used to add element to a set.
update() function can be used to add a group of elements to a set.
Copy() function can be used to create clone of set.
Set Code Snippet:

```

disneyLand = set (['Minnie Mouse', 'Donald Duck', 'Daisy Duck', 'Goofy'])
disneyLand.add('Pluto')
print disneyLand
-----------------------------------------------
Output
set(['Goofy', 'Daisy Duck', 'Donald Duck', 'Minnie Mouse', ’Pluto’])

Dictionary are similar to what their name is. In a dictionary, In python, the word is called a 'key', and the definition a 'value'. Dictionaries consist of pairs of keys and their corresponding values.

Dictionary Code Snippet:
>>> dict = {'India': 'Bharat', 'Angel': ‘Mother Teresa’, 'Cartoon': 'Mickey'}
>>>print dict[India]
Bharat
>>>print dict[Angel]
Mother Teresa

```

### Explain the disadvantages of python
Disadvantages of Python are:

Python isn't the best for memory intensive tasks.
Python is interpreted language & is slow compared to C/C++ or java.
Python not a great choice for a high-graphic 3d game that takes up a lot of CPU.
Python is evolving continuously, with constant evolution there is little substantial documentation available for the language.

### What are the ways to write a function using call by reference?

Arguments in python are passed as an assignment. This assignment creates an object that has no relationship between an argument name in source and target. The procedure to write the function using call by reference includes:
The tuple result can be returned to the object which called it. The example below shows it:

```
def function(a, b):
a = 'value' 
b = b + 1 
# a and b are local variables that are used to assign the new objects
return a, b 
# This is the function that is used to return the value stored in b
```

• The use of global variables allows the function to be called as reference but this is not the safe method to call any function. 
• The use of mutable (they are the classes that consists of changeable objects) objects are used to pass the function by reference. 

```
def function(a):
a[0] = 'string' 
a[1] = a[1] + 1 
# The ‘a’ array give reference to the mutable list and it changes the changes that are shared
args = ['string', 10]
func1(args)
print args[0], args[1] 
#This prints the value stored in the array of ‘a’
```

### What are the commands that are used to copy an object in Python?

The command that is used to copy an object in python includes: 
• copy.copy() function: This makes a copy of the file from source to destination. It returns a shallow copy of the parameter that is passed. 
• copy.deepcopy(): This also creates a copy of the object from source to destination. It returns a deep copy of the parameter that is passed to the function. 
The dictionary consists of all the objects and the copy() method which is used as:
newdict = olddict.copy()
The assignment statement doesn’t copy any object but it creates a binding between the target and the object that is used for the mutable items. Copy is required to keep a copy of it using the modules that is provided to give generic and shallow operations.

### What is the difference between deep and shallow copy?

• Shallow copy is used when a new instance type gets created and it keeps the values that are copied in the new instance. Whereas, deep copy is used to store the values that are already copied. 
• Shallow copy is used to copy the reference pointers just like it copies the values. These references point to the original objects and the changes made in any member of the class will also affect the original copy of it. Whereas, deep copy doesn’t copy the reference pointers to the objects. Deep copy makes the reference to an object and the new object that is pointed by some other object gets stored. The changes made in the original copy won’t affect any other copy that uses the object. 
• Shallow copy allows faster execution of the program and it depends on the size of the data that is used. Whereas, deep copy makes it slower due to making certain copies for each object that is been called.

### Write a program to find out the name of an object in python.

The object doesn’t have any name and there is no way the can be found out for objects. The assignment is used to bind a name to the value that includes the name of the object that has to be bound by a value. If the value is callable then the statements are made true and then the program followed can be used to find the reference name of an object. 


```
class try:
pass
B = A
a = B()
b = a
print b
<__main__.try instance at 0x16D07CC>
print b
```
The class consists of name and the names are invoked by using the the variable B that creates an instance for the class try. The method is to find out from all the namespaces that the object exists and then print the name of the object.

### How can the ternary operators be used in python?

The ternary operator is the operator that is used to show the conditional statements. This consists of the true or false values with a statement that has to be evaluated for it. The operator will be given as:

```
[on_true] if [expression] else [on_false]
x, y = 25, 50
big = x if x < y else y
```

This is the lowest priority operator that is used in making a decision that is based on the values of true or false. The expression gets evaluated like if x<y else y, in this case if x<y is true then the value is returned as big=x and if it is incorrect then big=y will be sent as a result.  


### How the string does get converted to a number?

• To convert the string into a number the built-in functions are used like int() constructor. It is a data type that is used like int (‘1’) ==1. 
• float() is also used to show the number in the format as float(‘1’)=1.
• The number by default are interpreted as decimal and if it is represented by int(‘0x1’) then it gives an error as ValueError. In this the int(string,base) function takes the parameter to convert string to number in this the process will be like int(‘0x1’,16)==16. If the base parameter is defined as 0 then it is indicated by an octal and 0x indicates it as hexadecimal number. 
• There is function eval() that can be used to convert string into number but it is a bit slower and present many security risks like __import__('os').system("rm -rf$HOME") - use of this will delete the home directory of the system.

### What is the function of negative index?

The sequences in python are indexed and it consists of the positive as well as negative numbers. The numbers that are positive uses ‘0’ that is uses as first index and ‘1’ as the second index and the process goes on like that. The index for the negative number starts from ‘-1’ that represents the last index in the sequence and ‘-2’ as the penultimate index and the sequence carries forward like the positive number. The negative index is used to remove any new-line spaces from the string and allow the string to except the last character that is given as S[:-1]. The negative index is also used to show the index to represent the string in correct order.

### Write a program to check whether the object is of a class or its subclass.

There is a method which is built-in to show the instances of an object that consists of many classes by providing a tuple in a table instead of individual classes. The method is given as isinstance(obj,cls) and in more details given as:

isinstance(obj, (class1, class2, ...)) that is used to check about the object’s presence in one of the classes. The built in types can also have many formats of the same function like isinstance(obj, str) or isinstance(obj, (int, long, float, complex)). 

It is not preferred to use the class instead user-defined classes are made that allow easy object-oriented style to define the behavior of the object’s class. These perform different thing that is based on the class. The function differs from one class to another class. To find out the object of the particular class the following program is used:


```
def search(obj):
if isinstance(obj, box):
# This is the code that is given for the box and write the program in the object
elif isinstance(obj, Document):
# This is the code that searches the document and writes the values in it
elif 
obj.search()
#This is the function used to search the object’s class.
```
### Why does delegation performed in Python?

Delegation is a technique that is used in object oriented programming. This is used to show the object and the behavior of the methods that are used. The class can be created to provide an implementation of the method that allows the method to be referenced. The delegate is having the parameter and the return value in an object. It also allows the methods to be passed as parameters and allow the defining of the callback methods that can be grouped together in multiple methods. These methods can be called from a single event. The example shows a class that captures the behavior of the file and converts data from lower to uppercase. 

```
class upcase:
def __init__(self, out):
self._out = out
def write(self, s):
self._outfile.write(s.upper())
def __getattr__(self, name):
return getattr(self._out, name)
```

The write() method that is used in the upcase class converts the string to the uppercase before calling another method. The delegation is being given using the self.__outfile object.

### What is the function of “self”?

“Self” is a variable that represent the instance of the object to itself. In most of the object oriented programming language, this is passed as to the methods as a hidden parameters that is defined by an object. But, in python it is declare it and pass it explicitly. It is the first argument that gets created in the instance of the class A and the parameters to the methods are passed automatically. It refers to separate instance of the variable for individual objects. This is the first argument that is used in the class instance and the “self” method is defined explicitly to all the methods that are used and present. The variables are referred as “self.xxx”. 


### How is “self” explicitly defined in a method?

“Self” is a reference variable and an instance attribute that is used instead of the local variable inside the class. The function or the variable of the self like self.x or self.meth() can be used in case the class is not known. There are no variables declared as local. It doesn’t have any syntax and it allow the reference to be passed explicity or call the method for the class that is in use. The use of writebaseclass.methodname(self, <argument list>) shows that the method of _init_() can be extended to the base class methods. This also solves the problem that is syntactic by using the assignment and the local variables. This tells a way to the interpreter the values that are to be used for the instance variables and local variables. The use of explicit self.var solves the problem mentioned above.

### What is the use of join() for a string rather than list or tuple method?

The functions and the methods that are used for the functionality uses the string module. This string module is represented as by using the join function in it:

> ", ".join(['1', '2', '4', '8', '16']) that results in "1, 2, 4, 8, 16"

The string variable that is used provide a fixed string literal to allow the names that are used to be bounded to the strings. join() is a string method that is used to provide a separator string to use the function over the sequence of the string and insert the function to an adjacent elements. The method uses any number of arguments that follow some rules that has to be put up for the sequence objects that the class defines for itself. The join is used for the string module that is used to join the string characters together as it is given in the program. The example is given as:
```
string.join(['1', '2', '4', '8', '16'], ", ")
```
### What is the process of compilation and linking in python?

The compiling and linking allows the new extensions to be compiled properly without any error and the linking can be done only when it passes the compiled procedure. If the dynamic loading is used then it depends on the style that is being provided with the system. The python interpreter can be used to provide the dynamic loading of the configuration setup files and will rebuild the interpreter. The steps that is required in this as:
• Create a file with any name and in any lanugage that is supported by the compiler of your system. For example comp.c
• Place this file in the Modules/ directory of the distribution which is getting used. 
• Add a line in the file Setup.local that is present in the Modules/ directory. 
• Run the file using spam comp.o
• After successful run of this rebuild the interpreter by using the make command on the top-level directory. 
• If the file is changed then run rebuildMakefile by using the command as ‘make Makefile’.

### What is the procedure to extract values from the object used in python?

To extract the value it requires the object type to be defined and according to the object type only the values will be fetched. The values will be extracted as:
• If the object is a tuple then PyTuple_Size() method is used that returns the length of the values and another method PyTuple_GetItem() returns the data item that is stored at a specific index. 
• If the object is a list then PyListSize() is having the same function that is defined for the tuple and PyList_GetItem() that also return the data items at a specified index.
• Strings uses PyString_Size() to return the length of the value and PyString_AsString() that return the pointer to its value. 
• To check the type of the object and the extracted values use of methods like PyString_Check(), PyTuple_Check(), PyList_Check(), etc are used.

### What are the steps required to make a script executable on Unix?

The steps that are required to make a script executable are to:

• First create a script file and write the code that has to be executed in it.
• Make the file mode as executable by making the first line starts with `#!` this is the line that python interpreter reads. 
• Set the permission for the file by using `chmod +x` file. The file uses the line that is the most important line to be used:

```
 #!/usr/local/bin/python
```

• This explains the pathname that is given to the python interpreter and it is independent of the environment programs. 
• Absolute pathname should be included so that the interpreter can interpret and execute the code accordingly. The sample code that is written:

```
#! /bin/sh
# Write your code here
exec python $0 ${1+"$@"}
# Write the function that need to be included.
```

### How does global value mutation used for thread-safety?

The global interpreter lock is used to allow the running of the thread one at a time. This is internal to the program only and used to distribute the functionality along all the virtual machines that are used. Python allows the switching between the threads to be performed by using the byte code instructions that are used to provide platform-independence. The sys.setcheckinterval() method is used that allow the switching to occur during the implementation of the program and the instruction. This provides the understanding in the field of accounting to use the byte code implementation that makes it portable to use. The atomicity can be provided such that the shared variables can be given as built-in data types.

### Write a program to read and write the binary data using python?

The module that is used to write and read the binary data is known as struct. This module allows the functionality and with it many functionalities to be used that consists of the string class. This class contains the binary data that is in the form of numbers that gets converted in python objects for use and vice versa. The program can read or write the binary data is:

```
import struct
f = open(file-name, "rb") 
# This Open() method allows the file to get opened in binary mode to make it portable for # use. 
s = f.read(8)
x, y, z = struct.unpack(">hhl", s)
```

The ‘>” is used to show the format string that allows the string to be converted in big-endian data form. For homogenous list of data the array module can be used that will allow the data to be kept more organized fashion.

### What is the process to run sub-process with pipes that connect both input and output?

The `popen2()` module is used to run the sub-process but due to some difficulty in processing like creation of deadlock that keep a process blocked that wait for the output from the child and child is waiting for the input. The dead lock occurs due to the fact that parent and child doesn’t have the synchronization and both are waiting to get the processor to provide the resources to one another. Use of popen3() method allow the reading of stdout and stderr to take place where the internal buffer increases and there is no read() takes place to share the resources. popen2() take care of the deadlock by providing the methods like wait() and waitpid() that finishes a process first and when a request comes it hands over the responsibility to the process that is waiting for the resources. The program is used to show the process and run it.

```
import popen2
fromchild, tochild = popen2.popen2("command")
tochild.write("input\n")
tochild.flush()
output = fromchild.readline()
```

### What are the different ways to generate random numbers?

Random module is the standard module that is used to generate the random number. 
The method is defined as:

```
import random
random.random()
```

The statement random.random() method return the floating point number that is in the range of [0, 1). The function generates the random float numbers. The methods that are used with the random class are the bound methods of the hidden instances. The instances of the Random can be done to show the multi-threading programs that creates different instance of individual threads. The other random generators that are used in this are:

- randrange(a, b): it chooses an integer and define the range in-between [a, b). It returns the elements by selecting it randomly from the range that is specified. It doesn’t build a range object. 
- uniform(a, b): it chooses a floating point number that is defined in the range of [a,b).Iyt returns the floating point number
- normalvariate(mean, sdev): it is used for the normal distribution where the mu is a mean and the sdev is a sigma that is used for standard deviation. 
- The Random class that is used and instantiated creates an independent multiple random number generators.

### Write a program to show the singleton pattern used in python.

Singleton patter is used to provide a mechanism that limits the number of instances that can be used by one class. It also allows the same object to be shared between many different parts of the code. This allows the global variables to be used as the actual data that is used is hidden by the singleton class interface. The singleton class interface can have only one public member and one class method Handle. Private constructors are not used to create an object that is used outside the class. The process waits for the static member function to create new instances and return the singleton object. The code that is used to call the singleton object is:

```
Singleton& Singleton::Handle() 
{
if( !psingle ) {
psingle = new Singleton;
}
return *psingle;
}
```
