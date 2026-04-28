


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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NzU2NzEwMTZdfQ==
-->