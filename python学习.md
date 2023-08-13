## 基础语法

### 字面量

![image-20230811083225808](/Users/kad/Library/Application Support/typora-user-images/image-20230811083225808.png)

输出的时候使用print，字符串需要加上""

### 注释

```
# 我是注释，单行注释
"""

我是多行注释

“”“

```

### 变量

```
# 变量是用来记录数据的
# 先定义后使用
he = 10
he2 = he+1
print(he)

```

### 数据类型

```
type()
num = 10
print(type(num))
# 输出num类型是number
```

### 数据类型转换

```
# 转换是应对数据多变的情况，让其为我所用
int(x)
float(x)
str(x)
print(str(xx))
```

### 标识符

```
# 你定义的一些名字是标识符
# 数字不能开头
# 大小写敏感
# 不能占用关键字
```

![image-20230811084159900](/Users/kad/Library/Application Support/typora-user-images/image-20230811084159900.png)

### 运算符

```
+
-
*
/
// 取整
% 取余
** 指数
+= 等运算符省略
```



### 定义字符串

```
# 定义有三种方式
su = 'kk'
su = "kk"
su = """kk"""
# 类型3可以当注释，被变量接收就是字符串

# 使用转义字符
\"
su = "\"kkkkk"
```

### 字符串拼接

```
# 输出带多个参数
print("kk"+"cc")
# 其他拼接
print("11"+str(11))
# 字符串可以转换后拼接

# 字符串格式化
message ="xuexi %s" %name
# 先占位%s，后面加上需要展示的变量

# %s 字符串 %d 整数 %f 浮点数
```

![image-20230811085450503](/Users/kad/Library/Application Support/typora-user-images/image-20230811085450503.png)



### 字符串精度

```
# m、 n控制宽度和精度
# %5.2f 控制宽度为5 精度为2位，浮点数
```

### 字符串格式化优雅版

```
# 字符串前面加入f标记
# 不限制数据类型，不关注精度
# format
print(f"我是{name}")
```

### 表达式的格式化

```
# 有明确结果的表达式
print(f"我的成绩是{11 * 9}")
```



### 数据输入

```
# 可以在键盘中读取输入
name = input()
print(name)
```

## 判断语句

![image-20230811090525855](/Users/kad/Library/Application Support/typora-user-images/image-20230811090525855.png)

```python
# if语句
age = 10
# 判断
if age < 18:
	print("你是小屁孩")
	
# if eles
age = 10
# 判断
if age < 18:
	print("你是小屁孩")
else:
	print("恭喜你成功进入人类副本")

#if elif else
age = 10
# 判断
if age < 18:
	print("你是小屁孩")
elif age < 15:
	print("你是小小屁孩")
elif age < 10:
	print("你是小小小屁孩")
else:
	print("恭喜你成功进入人类副本")

# 猜猜我是多少岁
age = 1
if int(input("请输入猜想的age")) == age:
	print("恭喜你猜到了")
elif int(input("请输入猜想的age")) == age:
	print("恭喜你猜到了")
elif int(input("请输入猜想的age")) == age:
	print("恭喜你猜到了")
else:	
	print("sorry,game over！")

# python可以嵌套判断语句，实现更强大的功能

```

### 循环语句

```python
# while的循环语句
num = 1
while num < 100:
	num = num + 1
# num +=1 简写
	print(num)
	
# 1加到100的while实现
num = 1
sum = 0
while num < 100:
    sum += num
    num += 1
    print(f"{sum}-----{num}")

# 猜数游戏
# random函数,生成100内的随机数
num = random.rendint(1,100)
flag = True
count = 0
while flag:
	guess_num = int(intput("请输入需要猜的数字："))
	count +=1
	if guess_num ==num:
		print("猜中了")
		flag = False
	else:
		print("你猜错了")
		if guess_num > num:
			print("你猜大了")
		else:
			print("你猜小了")
print(f"count={count}")

# while循环与乘法表
print("hell",end="")//不换行
print("\t")//制表符
    i = 1
    while i <= 9:
        j = 1
        while j <= i:
            print(f"{i}*{j}={i * j}\t",end='')
            j += 1
        i += 1
        print()
```

```python
# for循环
name = "xxkkkkkk"
for x in name:
  print(x)
# 计算a的个数
name = "aabbbbbccccc"
count = 0
for x in name:
  if x == 'a':
    count +=1
print(f"被统计的字符串有{count}个")

#range(num)生成序列
range(5) = [0,1,2,3,4]
range(num1,num2)
range(num1,num2,step)
# 变量作用域，看代码的步进
# for循环的99乘法表
for x in range(1,10):
  for y in range(1,x+1):
    print(f"{x}*{y}={x*y}\t",end="")
  print()
  
# 循环跳过
continue 中断循环
break 跳出循环
```



### 函数

```python
# python的函数，就是代码块
# 例如len()
def my_len(data):
  count += 1
  print(f"字符串{data}长度是{count}")
  
# 函数的定义
def 函数名(传入参数):
  函数体
  return 函数值

# add函数
def add(x,y):
  result = x + y
  print(f"{x}+{y}={result}")

 add(1,2)

# add函数 return版本
def add(x,y):
  result = x + y
  return result

 r = add(1,2)
print(r)

# 没有设置返回的话 返回的是none
# 函数说明文档,方便理解
def add(x,y):
  """
  :x xxx
  :y yyy
  :z zzz
  :return xxxx
  """
  result = x + y
  return result

 r = add(1,2)
print(r)


# 函数的嵌套调用
# 有a、b函数，通过b内置a，进行调用就是嵌套
def a():
  print(a)
def b():
  print(b)
  a()
b()

# 变量分局部变量和全局变量
# 局部变量只能局部使用，全局变量可以全局使用
global num=10
```

### python数据容器

```python
# 数据容器等于程序运行中数据仓库
# 有list、tuple、str、set、dict
# list的定义
sum = [1,2,3]
sum = list(1,2,3)
# list 索引从0开始
num[0] = 1
num[2] = 3
# list的index方法
num.index(1)
# 列表是否有1 ，没有truse

# 对下标重新赋值
num[2] = 100
# insert，插入方法
num.insert(1,222)
# 插入下标为1，插入222

# 追加
# append
num.append(111)
# 列表后面自动追加111

#追加更多用extend 
num.extend(1,2,3,4,5,6,1)

# 列表删除
num.del[2]
# 删除下标2的元素
num.pop(2)
# pop删除后还能返回值

# remove
num,remove(123)
# 只能删除一次，前往后

# 清空列表
num.clear()
# 什么都没有了

# count统计函数
num.count(1)
# num 有几个元素1


# 列表元素的遍历
su = [1,2,3,4,5,6]
index = 0
while index<len(su):
  qw = su[index]
  print(f"{qw}")
  index += 1

su = [1,2,3,4,5,6]
for index in su:
  print(f"{index}")
  
# tuple
# 元组是不可改变的，元组内的list可改变
(1,2,3)
su = (1,1,2)
su = tuple(1,1,1,1,1)
index()
count()
len()


# 字符串容器
su = "abcdefg"
su[0]=a
su[-1]=g
# index
su.index("c")
# 输出2
# replace
su.replace("a","c")
# 生成一个新的修改后的字符串
# spilt分割字符串
su.split(" ")
# 按照空格切分后输出一个新的list
# strip
su = " 1111"
su.sstrip()
# 字符串输出111，去除了空格
su = "1222221"
su.sstrip("12")
# 字符串输出2222，去除了首尾
# count
# len

# 序列切片
list = [1,2,3,4,5]
result = list[1:4]
# 默认步长为1，结果是输出[2,3,4]
# 从头到尾
result = list[:]
# 步长为2
result = list[::2]


# set集合，对数据去重，主要是无序
{1,2,3,4}
su = set()
# 不支持下标索引
# add
su = {1,2,3}
su.add(2)
su = {1,2,3,2}
# remove
su.remove(3)
su = {1,2}
# pop
s = su.pop()
# 随机取出元素
# 清空集合
su.clear()
# 差集
su = {1,2,3}
su2 = {2,3,4}
su3 = su.difference(su2)
# 取出来的是{1,4}
su = {1,2,3}
su2 = {2,3,4}
su.difference_update(su2)
# 消除掉了su的2，3，su2没有变化
# 合并
su = {1,2,3}
su2 = {2,3,4}
su3 = su.union(su2)
# 去重生成新的su3

# 统计元素数量
su = {1,2,3,4,5}
num = len(su)
# 遍历
su = {1,2,3}
for x in su:
  print(x)

# 把list去重
# 通过for循环添加到集合中


# 字典，键值对
{
  key:1,
  value:2,
  age,34
}
# 定义字典
su = {}
su = dict()
# 字典不能重复
# 通过键值对拿到值
kk = su["key"]
# 字典可以嵌套，学生成绩示范
{
  "王力宏":{
    "语文":100,
    "数学":88,
    "英语":77
  },"周杰伦":{
    "语文":100,
    "数学":88,
    "英语":77
  }
}
# 字典查王力宏成绩
su = q["王力宏"]["语文"]
# 字典新增
xx["可爱多"] = 5
# 更新元素
xx["可爱多"] = 4
# 删除元素
pop(key)
xx.pop("可爱多")
# 清空元素
xx.clear()
# 获取所有的key
xx.keys()

# 字典遍历
for key in xx:
  priny(f"{key}")
  print(f"xx[key]")
# len()统计字典
xx.len()
# 可以看见最大最小
max()
min()
# list() 将给定容器转换成列表
# str() 转字符串
# tuple() 转元组
# set() 转集合
# sorted(容器，[reverse=True])
```



## 函数进阶

```python
# 多个函数返回值
def xx():
  return x,y
z,c = xx()
print(z)

# 关键字传参数
形式参数 = "实际参数"

# 不定长参数
# 位置不定长
def xx(*arg):
  return arg
# 关键字不定长
def xx(**arg):
  return arg
#传入需键值对
xx(name="kk",age=33)

# 匿名函数，只能使用一次
lambda 传入参数:函数体(一行代码)

# python的文件操作
# 文件读取
# 打开文件 r 只读，w重新生成新文件，a 追加内容，无文件则会新建
f = open('python.txt','r',encoding='UTF-8')
# 读方法read()
f.read(10)
# 读取10个字节，多次调用注意会从之前调用开始
# 读取文件 readLines() 读取全部
# 读取文件 readLine() 读取一行数据，一次一行
# 文件关闭
f.close()
# 暂停程序
# time.sleep(50000)
# with open,使用完后自动关闭
with open('python.txt','r',encoding='UTF-8') as f:
  for line in f:
    printf(f"{line}")

# 文件的写入
f.write("hello world")

# 内容刷新,写入数据
f.flush()
# 或
f.close()


# 文件追加,a模式就是追加操作
f = open("python.txt","a")
f.write("keaiduo")
f.close()



```

## python 异常 模块 包

```python
# 捕获异常
try:
	可能错误的代码
  open('python.txt','r',encoding='UTF-8')
except:
  print("没有对应的文件，需要用w方式")
  open('python.txt','w',encoding='UTF-8')
  如果出现异常怎么做
else:
  print("没有异常")
finally:
  print("有无异常我都要执行")
  f.close()
# 异常具有传递性

# 模块一个python文件，可以拿来用
import 模块名
from 模块名 import 类、变量、方法
from 模块名 import *
import 模块名 as xxx
from 模块名 import 功能名 as 别名

# time 模块
import time
# 睡眠5秒钟
time.sleep(5)

# python自定义模块
# 等于文件关联
# 避免导入模块后运行，使用main变量
if __name__ == "__main__"
# 避免模块包自动运行，又可以测试功能

# __all__变量
# 控制导入的函数
__all__ = ['test_a']

# python中的包,有才算包
__init__.py
xxx.py

# 安装第三方包
pip install

```



##  数据可视化

```python
# json介绍，字典/列表
# pyecharts 百度开发的数据可视化





```



## 对象

```python
# 设计一个类
class student:
  name = none
  age = 18
  gende = 1
# 创建一个类
student()
# 对对象进行赋值
student.age = 11
student.name = "kk"

# 类的定义和使用
class student:
  name = none
  age = 18
  gende = 1
  def say(self):
    print(f"{self.name}")
    
    
# 类和对象


# 构造方法
__init__()
# 创建时自动执行
# 将传递参数自动传递给__init__
class student:
  
  def __init__(self,name,age,tel):
    self.name=name
    self.age = age
    self.tel = tel
    
    
# 内置方法
__init__ 构造方法
__str__ 字符串方法
# 类对象转变成字符串，地址编程数据
__lt__ 小于符号比较方法
# 类不能直接比较，通过lt方法对类里面属性比较
# 小于等于
__le__
# 比较运算符
__eq__ 
# == 比较


# 封装 继承 多态
# 定义私有
class phone:
  q = none
  p = none
	__qq = none
  def _pp(self):
    print("让cpu允许")
phone = phone()
# 不能输出，不会报错
phone.__qq = 8274
# 私有变量方法只能类中自己使用，即是封装


# 继承
class 类名(父类):
  kk = 10
  pass
# pass 语法不产生错误
# 复写
# 把父类方法中不满意的修改
# 调用弗雷成员
# 使用父类名.成员变量
# 使用父类名.成员变量(self)

# super(成员变量)
# super(成员方法)()

# 类型注解
ctrl+p 提示
qq : int = 111111
ss : float = 1.23
# 让pycharm知道你的类型
# 形式参数注解
def add(x:int,y:int):
  return x+y
# union注解
# 描述混合类型的字典
qq:list[union[str,int]]

# 多态，多个状态
# 使用同一个函数，传入不同，输出不同

```


## 闭包

```python
# 实现功能避免被修改，数量
def out(logo):
  
  def inn(msg):
    print(f"{logo}{msg}")
  
  return inn
fn1 = outer("黑马")
fn1("大家好")
# 输出黑马大家好 就是一个房子，谁住进去就是谁的
# 公房，谁都可以住，不过里面的东西不能改，而且程序运行公房就一直
# 需要修改加nolocal

# 装饰器
# 让代码优雅🐶


# 设计模式
# 单例模式
# 节省内存


# 工厂模式
# 根据输入可以选择类型


# 多线程 进程
import threading
pp = threading.Thread([[[[]]]])
pp.start()


# re
# match 从头匹配，匹配一个
# search 全局匹配 匹配一个
# findall 全局匹配，匹配全部


# 匹配正则
^[0-9a-zA-Z][6,10]$
# 数字和字母 6-10位

# 递归
# 自己用自己

```

