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

### 请解释python是如何解释执行的？

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

### 请解释Python中的字典类型？

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

### 请解释序列操作中的索引和切片？

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

### 请解释repr函数的作用？

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

### 请解释pickling和unpickling？

pickle是序列化和反序列化Python对象结构的标准模块。

pickle模块接受任何Python对象，将它转换成一个字符串表示形式，转储到一个以后可以使用的文件中（通过使用`dump()`函数），这个过程称为pickling；而unpickle是用于将存储字符串表示形式装换为原始Python对象的过程。

### Python的列表推导特点是什么？

Python在2.0中引入列表推导特性，它基于现有列表创建新列表。
它通过一个函数将每个现有列表中的元素映射成另一个列表元素。
列表推导不用`map()` , `filter()` 或 `lambda`创建列表。

### Python中如何进行内存管理？

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

### Python中如何使用高阶函数？

高阶函数接受一个或多个函数作为输入，并返回一个新的函数。有时需要使用函数作为数据。
为了使用高阶函数，我们需要导入fucntools模块。
`functools.partial()`函数通常用于高阶函数。

### 请解释Python中如何复制一个对象？

Python中存在两种复制对象的方式：浅拷贝和深拷贝。
浅拷贝复制的越少越好，而深拷贝复制一切。
如果一个对象要被复制，然后

- copy.copy(a) returns a shallow copy of a.
- copy.deepcopy(a) returns a deep copy of a.

### 怎么查看Python的方法或属性？

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

### 如何将字符串转换为数字？

Python中包含几个内置函数将值从一种数据类型转换为另一种数据类型。
int函数接受字符串，将其转换为整数。

```python
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

### Python中负索引是什么？

Python中阵列和列表项可以使用正数或负数（也称为索引）来访问。
比如我们的数组/列表的大小为n，则正索引0是第一个索引，1是第二个，最后的索引为n-1。
对于负指数，-n是第一索引， - （N-1）是第二个，最后负指数将是 - 1。
负数索引从列表中最后一个元素倒序访问。

下面是python负索引的一个例子

```python
>>> import array
>>> a= [1, 2, 3]
>>> print a[-3]
1
>>> print a[-2]
2
>>> print a[-1]
3
```

### 请介绍Python中数组类型？

数组模块包含用于创建固定的类型与同质的数据类型的数组方法。数组比列表要慢。
可以使用数组模块来创建字符，整数，浮点数的数组。

`array(typecode[, intializer])`
返回一个新的数组，其元素数据类型受typecode类型限制，并可从可选初始化值初始化数组。
其中typecode可以是'c'表示字符型，'d'表示double型，'f'表示浮点型。

### 请解释如何创建一个多维列表？

有两种创建多维列表的方法：

1. 第一种通过如下所示直接初始化的方式创建：

    ```python
    >>>multidimlist = [ [227, 122, 223],[222, 321, 192],[21, 122, 444]]
    >>>print multidimlist[0]
    >>>print multidimlist[1][2]
    __________________________
    Output 
    [227, 122, 223]
    192
    ```
2. 第二种是先创建指定长度的列表，然后给该列表的每个元素赋值一个新的列表，如下所示：

    ```python
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

### 请解释Python中如何重载构造函数（或方法）？

`_init__ ()` 是类中定义的第一个方法，当一个类的实例被创建时，python调用__init__()方法实例化该对象的属性。

下面的例子进一步说明：

```python
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

### 请介绍如何用Python脚本发送邮件？

smtplib模块定义了一个SMTP客户端会话对象，可用于将邮件发送到任何互联网设备。

下面的示例演示发送电子邮件：

```python
import smtplib
SERVER = smtplib.SMTP("smtp.server.domain")
FROM = "sender@mail.com"
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

### 请说明Python中如何生成的随机数？

标准模块random实现了一个随机数发生器。

在该模块中也有许多其他方法，如：

```python
uniform(a, b) #returns a floating point number in the range [a, b].
randint(a, b) #returns a random integer number in the range [a, b].
random() #returns a floating point number in the range [0, 1].
```

下面的代码段展示了random模块三种函数的用法：

Note：这段代码的输出将在每次执行时会有所不同。

```python
import random
i = random.randint(1,99) # i randomly initialized by integer between range 1 & 99
j= random.uniform(1,999) # j randomly initialized by float between range 1 & 999
k= random.random() # k randomly initialized by float between range 0 & 1
print("i :" ,i)
print("j :" ,j)
print("k :" ,k) 

---------------------------------------------------------------
Output -
('i :', 64)
('j :', 701.85008797642115)
('k :', 0.18173593240301023)

Output-
('i :', 83)
('j :', 56.817584548210945)
('k :', 0.9946957743038618)
```

### 如何让Python脚本执行？

Python脚本可以用两种方式执行：

假设我想执行script1.py
1. 我们可以在IDE编辑器中打开script1.py，然后通过点击在Python IDE中的最前面的窗口的运行所有按钮运行脚本。
2. 第二种方法是使用命令提示符，确保路径设置适当,直接输入脚本名和其他参数
    ```bash
    >>>python script1.py
    ```

### 请解释Python中如何创建表单？

Python作为脚本语言，表单处理已经由Python完成。我们只需要导入cgi模块，通过FieldStorage类来访问表单域。

FieldStorage类的每个实例（“表单”）都包含以下属性：
* form.name: The name of the field, if specified. 
* form.filename: If an FTP transaction, the client-side filename. 
* form.value: The value of the field as a string. 
* form.file: file object from which data can be read.
* form.type: The content type, if applicable. 
* form.type_options: The options of the 'content-type' line of the HTTP request, returned as a dictionary. 
* form.disposition: The field 'content-disposition'; None if unspecified. 
* form.disposition_options: The options for 'content-disposition'. 
* form.headers: All of the HTTP headers returned as a dictionary.

Python中表单处理的代码片段：

```python
import cgi

form = cgi.FieldStorage()
if not (form.has_key("name") and form.has_key("age")):
    print "<H1>Name & Age not Entered</H1>"
    print "Fill the Name & Age accurately."
    return
print "<p>name:", form["name"].value
print "<p>Age:", form["age"].value
```

### 请说明python Web中如何实现Cookies？

Cookie是字符唯一地标识会话的任意字符串。每一个cookie是特定于一个网站和一个用户。

Cookie模块定义为抽象的Cookie概念类。它包含以下方法来创建的cookie：

```python
Cookie.SimpleCookie([input])
Cookie.SerialCookie([input]
Cookie.SmartCookie([input])

#for instance following code creates a new cookie ck
import Cookie
ck= Cookie.SimpleCookie ( x )
```

### 请说明python Web中如何使用sessions？

sessions是cookie的服务器端版本。cookie在客户端保存状态，然而sessions在服务器端的保存状态。

会话状态保存在服务器端的一个文件中或数据库中。每个会话都由一个唯一的会话ID（SID）标识。为了使人们有可能在客户端来识别他自己，客户机每发送一个请求，SID都必须由服务器创建然后发送到客户端。

会话处理是通过以下列方式的web.session模块完成：
```python
import web.session
session = web.session.start( option1, Option2,... )
session['myVariable'] = 'It can be requested'
```

### 请解释在Python中如何处理异常？

执行程序的过程中检测到的错误被称为异常。异常可以通过try..except语句来处理。 
我们基本上把我们平时的语句在try块内，并把我们的错误处理放在except块内。

```python
#try…except demo code:
while True:
    try:
        x = int(raw_input("Enter no. of your choice: "))
        break
    except ValueError:
        print "Oops! Not a valid number. Attempt again"

---------------------------------------
#Output:
Enter no. of your choice: 12ww
Oops! Not a valid number. Attempt again
Enter no. of your choice: hi there
Oops! Not a valid number. Attempt again
Enter no. of your choice: 22
```

### Python中怎样创建Unicode字符串？

Unicode是一个体系，用字符来表示世界上所有的不同的语言。

有两种方法可用于创建unicode字符串：
1. unicode(string[, encoding, errors])，它的参数应该是8位的字符串，第一个参数用指定的编码转换成Unicode，如果没有指定编码参数，则使用ASCII编码来进行转换。
2. encode([encoding], [errors='strict'])，它返回一个8位的Unicode字符串。

### 什么时候使用list、tuple、dictionary、set？

列表像数组，它可以被用来存储同质以及异构数据类型（它可以存储相同的数据类型以及不同数据类型）。列表比数组快。列表数据的各个元素，都可以使用索引来访问并且可被操纵。

```python
#List Code Snippet:
list = ["Sarah",29,30000.00]
for i in range (3):
     print list[i]
----------------------------
Output
Sarah
29
30000.0
```

元组和列表相似，但是它的数据一旦创建，在程序的执行过程就不能改变。元组的各个元素，可以使用索引来访问。

元组代码段：The Days
```python
days = ("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday")
print days
------------------------------
('Sunday', 'Mondays', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday')
```

集合存储无序值并且没有索引。不像元组和列表，集合不可能有重复的数据，它类似于数学集合。

* add() function can be used to add element to a set.
* update() function can be used to add a group of elements to a set.
* Copy() function can be used to create clone of set.

集合代码段：
```python
disneyLand = set (['Minnie Mouse', 'Donald Duck', 'Daisy Duck', 'Goofy'])
disneyLand.add('Pluto')
print disneyLand
-----------------------------------------------
Output
set(['Goofy', 'Daisy Duck', 'Donald Duck', 'Minnie Mouse', ’Pluto’])
```

字典可存储任意类型对象，如其他容器模型。字典由键和对应值成对组成。

字典代码段：
```python
>>>dict = {'India': 'Bharat', 'Angel': ‘Mother Teresa’, 'Cartoon': 'Mickey'}
>>>print dict[India]
Bharat
>>>print dict[Angel]
Mother Teresa
```

### 请介绍下Python的缺点

Python的缺点有：
1. Python不太适合内存密集型任务；
2. Python是解释性语言，因此相比c/c++或者java会慢一些；
3. Python不是占用大量CPU的3D高质量图形游戏的最好的选择；
4. Python正在不断发展，随着它不断的发展，可用的语言相关的文档还很少。 

### 怎么编写按引用方式调用的函数？

Python中参数是分配的。这种分配将创建一个对象，它在源参数名称和目标参数名称之间没有任何关系。
该函数的返回值可以是元组。

下面是例子说明：

```python
def function(a, b):
    a = 'value' 
    b = b + 1 
    # a and b are local variables that are used to assign the new objects
    return a, b 
    # This is the function that is used to return the value stored in b
```

• 使用全局变量允许函数被当作引用来调用，但用这种方式调用任何函数是不安全的。
• 使用可变（它们包含可变对象的类）对象所使用的引用传递函数。

```python
def function(a):
    a[0] = 'string' 
    a[1] = a[1] + 1 
    # The ‘a’ array give reference to the mutable list and it changes the changes that are shared
    args = ['string', 10]
    func1(args)
    print args[0], args[1] 
    #This prints the value stored in the array of ‘a’
```

### Python中使用什么命令拷贝对象？

Python中用来拷贝对象的命令有： 
• copy.copy() 函数: 从源文件到目标文件的拷贝，它返回传递参数的浅拷贝。 
• copy.deepcopy(): 同样是从源文件到目标文件的拷贝，不过它返回传递参数的深拷贝。

### 深拷贝和浅拷贝的区别？

* 浅拷贝用于创建一个新的实例类型，并且确保被复制到新实例中的值保持不变。而深拷贝用于存储那些已被复制的值。
* 浅拷贝来拷贝引用指针，就像它拷贝了值一样。这些引用指向原来的对象，在类的任何成员中所做的更改也会影响它的原件。然而，深拷贝不拷贝对象的引用指针。
深拷贝引用一个对象，并且指向一些其他对象的存储新的对象。对原副本所做的更改不会影响使用对象的其他副本。 
* 浅拷贝允许更快的程序执行的，它依赖于所使用的数据的大小。然而，深拷贝使得它更慢，因为调用每个对象时会使用明确的副本。

### Python中如何使用三元运算符？

三元运算符是用于显示条件语句的操作符。它由真或假值与已为它进行计算一条语句。操作符如下：

```python
# [on_true] if [expression] else [on_false]
x, y = 25, 50
big = x if x < y else y
```

这是在判断真假值时所用的最低优先级的操作符。表达式计算如 if x<y else y，在这种情况下，如果x<y为真，那么返回值big= X，如果为假，big=y将作为返回值。  

### 如何将字符串装换为数字？

* 内置函数int()可用于将字符串装换为数字，它的用法为`int('1') == 1`。
* float() 同样可以将字符串装换为数字，格式为`float(‘1’)==1`.
* 数字默认被解释为十进制。如果表示为 int('0x1') ，那么它将抛出一个ValueError错误。
int(string,base) 函数将字符串参数转换为数字，在这个过程中表示形式如：int(‘0x1’,16)==16,
如果参数base设为0，则表示转换为8进制数，0x表示装换为16进制数。 
* eval()函数可以将字符串转换成数字，但是相对较慢并且还有点安全隐患，比如`__import__('os').system("rm -rf$HOME")`，使用该方法将会删除系统home目录下的所有文件。

### 什么是负索引？

Python中的序列具有索引，它包括正索引和负索引。
正数‘0’表示第一个索引，‘1’表示第二个，以此类推。
负数索引从‘-1’开始，它表示序列中的最后一个元素，‘-2’表示倒数第二个索引，以此类推。
负索引用于从字符串中删除的任何新行的空格，允许将字符串的最后一个字符除去，如S[:-1]。
负索引也用来表示正确的字符串顺序。

### 编写一个程序来检查对象是否是一个类或者它的子类。

存在一个内置方法，通过表中的元组而不是单独的类来显示的对象实例由许多类组成，
这个方法就是isinstance(obj,cls)，更多细节如下：

`isinstance(obj, (class1, class2, ...))` 用来检测对象是否存在于其中的一个类中，
这个内置方法有许多格式，比如：`isinstance(obj, str)` or `isinstance(obj, (int, long, float, complex))`。

这些执行是基于类的不同的事情。该功能从一类到另一个类会有所不同。下面解释程序使用的特定类的对象：

```python
def search(obj):
    if isinstance(obj, box):
        # This is the code that is given for the box and write the program in the object
    elif isinstance(obj, Document):
        # This is the code that searches the document and writes the values in it
    elif
    obj.search()
    #This is the function used to search the object’s class.
```

### Python中委托是是什么？

委托是一个用于面向对象编程的技术。这是用来表明目的和所使用的方法的行为。类可以创建，以提供允许该方法中引用的方法的实现。该委托具有参数和对象的返回值。它也允许方法作为参数传递，并允许其可以组合在一起，在多个方法回调方法中定义。
这些方法可以从一个单一的事件调用。

这个例子定义了一个类，捕捉文件的行为，将数据从小写转换为大写。

```python
class upcase:
    def __init__(self, out):
        self._out = out
        
    def write(self, s):
        self._outfile.write(s.upper())
        
    def __getattr__(self, name):
        return getattr(self._out, name)
```

upcase类中的write()方法在调用另一个方法之前，将字符串转换为大写。使用self.__outfile表示委托。

### 方法中的self参数是什么？

`self`是表示对象的实例本身的变量。在大多数面向对象编程语言中，这是通过作为该对象定义方法的隐藏参数。但是，python中它是需要声明并且明确传递的。它是类A创建实例时的第一个参数并且自动传递给方法。
它指向为单个对象的各自的实例。它是类实例的第一个参数，并且`self`方法被明确地定义为所有所使用和当前的方法。变量表示为`self.xxx`. 

### 如何在方法中明确的定义“self”？

`self`是引用变量和实例属性，它被用来代替在类内的局部变量。
`self`的方法或变量，如self.x或self.meth()即使在不知道是什么类的情况下也可以使用。
没有声明局部变量，它不具有任何语法和它允许为正在使用的类显式传递引用或调用方法。
`writebaseclass.methodname(self, <argument list>)`的使用表明`__init__()`方法可以延伸到基类方法。
这也解决了通过使用分配和局部变量语法的问题。这也提供了一种实例变量和局部变量交互的方法。显式使用self.var的解决了上述问题。

### What is the use of join() for a string rather than list or tuple method?

所使用的功能的函数和方法使用字符串模块。该字符串模块通过使用join函数来表示：

```python
", ".join(['1', '2', '4', '8', '16']) #that results in "1, 2, 4, 8, 16"
```

所使用的字符串变量提供一个固定的字符串，以允许用于有界字符串的名称。
join()是用于提供一个分隔字符串使用的函数在字符串的序列，并插入函数到相邻元素的字符串函数。
该方法使用任意数量的遵循一些已经被定义在序列对象自身上的规则的参数。
string模块中的join函数用于将程序中已经给出的字符串连接在一起。
 
下面是例子:

```python
string.join(['1', '2', '4', '8', '16'], ", ")
```

### Python中编译和链接的过程？

编译和链接允许新的扩展被正确编译，且只有当它经过编译的过程后连接才完成。如果使用动态加载，它将依赖于正被提供的系统的样式。
Python解释器可用于提供配置设置文件的动态加载并重建解释。

以下为必须的步骤：
* 创建具有任何名称和所支持的系统的编译器的任何语言的文件。例如comp.c
* 把这个文件习惯性放在分配的Modules/目录中。
* 在Modules/目录中的Setup.local文件添加一行。
* 通过`spam comp.o`运行文件
* 此次运行成功后，可以通过在顶级目录执行make命令重新解释。
* 如果文件被改变，那么通过使用'make Makefile'命令运行rebuildMakefile。

### 从Python中使用的对象提取值流程是什么？

为了提取它的值，它要求对象类型必须定义，只根据对象类型将可以获取到值。
值的提取如下：
* 如果对象是一个元组，PyTuple_Size()方法用来返回的值的长度，另一方法PyTuple_GetItem()返回存储在一个特定的索引的数据项。 
* 如果对象是一个列表，PyListSize()和元组中的一样，PyList_GetItem()也返回特定索引处的数据项。
* 字符串使用PyString_Size()返回其值的长度，PyString_AsString()返回指向该值的指针。 
* PyString_Check()，PyTuple_Check()，PyList_Check(）等被用来检查对象的类型和所提取的值。

### Unix中执行脚本需要哪些步骤？

使脚本可执行所需要的步骤有：

* 首先创建一个脚本文件，在它里面写入被执行的代码。
* 通过使第一行以`#!`开始使文件可执行，这是Python解释器可读取的行。
* 通过使用'chmod + x`来设置该文件的权限，下面是该文件将要使用的最重要一行：
    ```
    #!/usr/local/bin/python
    ```
* 这一行说明了Python解释器的路径，它是独立于环境的程序。
* 使用绝对路径来确保解释器解释和执行相应的代码。示例代码如下：
    ```python
    #! /bin/sh
    # Write your code here
    exec python $0 ${1+"$@"}
    # Write the function that need to be included.
    ```

### 如何使用线程安全全局值？

全局解释锁被用来同一运行时间一次只允许一个线程。这是内部的唯一的用于为所有所使用的虚拟机分配功能的程序。Python允许通过使用用于提供平台独立性的字节代码指令执行的线程之间的切换。
sys.setcheckinterval()方法允许程序和指令在执行过程中切换。这让使用字节代码执行并使得它使用便携易于理解。这种原子性使得共享变量可以作为内置的数据类型。

### 请用python写一个读写二进制数据的程序

用来读写二进制数据的模块是struct，此类包含二进制数据，被转换为数字的形式在Python对象使用，反之亦然。

下面是读写二进制数据的程序：

```python
import struct
f = open(filename, "rb") 
# This Open() method allows the file to get opened in binary mode to make it portable for # use. 
s = f.read(8)
x, y, z = struct.unpack(">hhl", s)
```

“>”是用来显示格式字符串，这个模块允许功能和它的许多功能被字符串类使用。它允许在高位优先要转换的字符串数据的形式。
对于同质的列表数据，可以使用数组模块，允许数据以更有条理的方式保存。

### 连接输入和输出管道运行子进程的进程是什么？

`popen2()`模块用于运行该子过程，但由于一些处理困难像创建一个死锁，保持一个进程阻塞，等待子进程的输出，而子进程又等待输入。
死锁的发生是由于父和子不具有同步并且都等待获得处理器提供彼此的资源。
使用popen3()方法，允许读取输出和错误来代替内部缓冲区，也没有代替共享的资源的读取方法。
popen2()通过提供像wait()和waitpid()方法来接管死锁，首先结束一个进程，当一个请求到达时，它移交职责给等待资源的进程。
该程序用于显示进程并运行它。

```python
import popen2
fromchild, tochild = popen2.popen2("command")
tochild.write("input\n")
tochild.flush()
output = fromchild.readline()
```

### 有哪些不同的方式来产生随机数？

Random模块是用于产生随机数的标准模块。
该方法被定义为：

```python
import random
random.random()
```

random.random()方法返回在[0，1）的范围内的浮点数。该函数生成随机浮点数，所使用的随机类的方法是隐藏的实例的结合的方法。Random实例可以用来表明多线程程序通过单线程可以创建不同的实例。

其他随机数生成器的使用：

- randrange(a, b): 它选择一个整数，定义该范围在[a，b）两者之间。它返回由从所指定的范围内选择它随机的元素。它不创建一个range对象。
- uniform(a, b): 它选择在[a, b) 范围内的浮点数。
- normalvariate(mean, sdev): 它被用于正常分布，其中mu是一个平均值和sdev是用于标准偏差的Σ。
- Random类被用来创建一个独立的多个随机数生成器。

### 用python编写一个程序并且使用Singleton模式。

Singleton模式用于限制一个类的实例的数量。它也允许在代码的许多不同部分之间共享相同的对象。
这允许使用的全局变量，它是用于实际的数据被隐藏在单个类接口。单例类的接口只能有一个公共的成员和一个类的方法句柄。
私有构造函数不是用来创建所使用的类之外的对象。这个进程等待静态成员函数来创建新实例并返回单独的对象。

用于调用singleton对象的代码：

```c++
Singleton& Singleton::Handle() 
{
    if( !psingle ) {
        psingle = new Singleton;
    }
    return *psingle;
}
```
