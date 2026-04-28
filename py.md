# python语法
##  函数
### 函数的多返回值
``` python
def test_return():
    return 1,2;
x,y=test_return();
```
### 函数的多种传参方式
#### 
分类：
-位置参数
-关键字参数
-缺省参数
-不定长参数

一.位置参数
``` python
def func(name,age):
    print(f"您的名字是{name},您的年龄是{age}")
    
func('Joe',20)
```
二.关键字参数
函数调用时通过 key=value 的形式传递参数
``` python
def func(name,age):
    print(f"您的名字是{name},您的年龄是{age}")

#关键字传参
func(name="Joe",age=20)
#可以改变参数顺序
func(age=20,name="Joe")
#可以和位置参数混用，此时必须按顺序
func(name="Joe",20)
```
三.缺省参数（默认参数）
位置参数必须出现在缺省参数前
``` python
def func(name,age,gender='男'):
    print(f"名字是{name}, 年龄是{age},性别是{gender}")

func('Joe',20)
func('lily',18,'女')
```
四.不定长传递
#####  1.位置传递
``` python
def func(*args):
    print(args)

func('Tom')
func('Tom',18)
#所有传递的参数都会被args变量收集，根据传进参数的位置合并为一个元组
```
##### 2.关键字传递
``` python
def func(**kwargs):
    print(kwarg)

func(name='Tom',age=18)
#所有的key=value都会被kwargs接收并组成字典
```
### 匿名函数
#### 一 .函数作为参数传递
``` python
def test_func(compute):
    result=compute(1,2)
    print(result)

def compute(x,y):
    return x+y

test_func(compute) #结果是3
   ```
 二.lambda函数
 lambda定义的匿名函数无名称，只能临时使用一次
  语法： lambda 传入参数: 函数体   (只能写一行)
  ``` python
  def test_func(compute):
    result=compute(1,2)
    print(result)

test_func(lambda x,y : x+y)   #结果是3
```
## python的文件操作
### 一.文件编码
编码技术：翻译的规则，记录了如何将内容翻译成二进制，如UTF-8
### 二.文件读取操作
####
1.open()打开函数
语法：open(name,mode,encoding)
``` python
f=open("python.txt",'r',encoding="UTF-8")
#r：只读  
#w：只写，如果文件存在，删除原有内容从头写，不存在则创建一个
#a: 追加，文件存在则在后面加内容，不存在创建并写入
```
2.read()方法
语法： 文件对象.read(num) 
num表示读取的长度，单位：字节，默认全读取

3.readlines() 方法
按照行的方式一次读取文件内容，返回一个列表

4.readline() 方法
一次读取一行的数据

5.for循环读取
``` python
for line in open("python.txt","r"):
    print(line)
```
6.close()关闭文件
``` python
f=open("python.txt","r")
f.close()
```
7.with open语法:文件自动关闭
``` python
with open("python.txt",'r',encoding="UTF-8") as f:
    for line in f:
        print(line)
```
### 三.文件的写入
####
``` python
#打开文件
f=open("python.txt","w")
#写入
f.write("Hello World")   #写入缓存区，还未真正写入文件
f.flush()  #内容刷新
```
### 四.文件的追加
####
``` python
#打开文件
f=open("python.txt","a")
#写入
f.write("Hello World")   #写入缓存区，还未真正写入文件
f.flush()  #内容刷新
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMjk3ODM5NzQsLTEyODQ1Mjk1ODIsLT
E0NzU2NzEwMTZdfQ==
-->