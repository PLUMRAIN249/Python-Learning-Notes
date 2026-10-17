# Python基础系统讲义

第1—29课｜原理讲解 · 完整代码 · 执行分析 · 易错点

学习定位：从零基础到面向对象、迭代器、生成器、装饰器，并在第29课完成知识复盘。每一课的代码都是可独立运行的示例。

编排说明：早期部分课程的原始逐课标题未完整保留，因此第1—20课按实际已学主题重新编排；第21—29课与近期学习主线衔接。第26课作为已学文件知识的进阶复习；第28课完整补入“带参数的函数装饰器”。这是一份系统复习讲义，不表示第29课已经在对话中完成。

# 课程目录

第01课　Python入门、运行环境与print

第02课　变量、数据类型与type

第03课　输入、类型转换与字符串运算

第04课　运算符与表达式

第05课　条件分支if、elif、else

第06课　for循环与range

第07课　while循环、break与continue

第08课　列表基础：创建、索引、切片

第09课　列表方法、排序与遍历

第10课　字符串索引、切片与常用方法

第11课　元组与集合

第12课　字典基础与增删改查

第13课　嵌套容器与综合数据处理

第14课　函数定义、参数与return

第15课　函数参数进阶：默认值与关键字

第16课　变量作用域与可变对象

第17课　递归函数

第18课　列表推导式与简洁数据处理

第19课　文件读写与with open

第20课　JSON、CSV与路径管理

第21课　异常处理try、except、else、finally、raise

第22课　模块、import与标准库

第23课　函数进阶：*args、**kwargs与lambda

第24课　类与对象：self、实例属性与类属性

第25课　继承、super、重写与多态

第26课　文件操作进阶：数据持久化与健壮性

第27课　迭代器与生成器：iter、next、yield

第28课　装饰器：闭包、@语法、参数与返回值

第29课　基础复盘：调试、测试、环境与综合练习

# 第01课｜Python入门、运行环境与print

## 1. 基本原理

Python是解释型语言，源代码通常保存为.py文件，由解释器逐句执行。PyCharm用于编辑、运行与调试；脚本从上到下执行。print()负责把数据输出到控制台；#表示单行注释。

## 2. 完整可运行代码

```python
print("你好，Python")
print("第一行", "第二部分")
# 计算并输出
print(2 + 3)
print("Python", "基础", sep="-")
```

## 3. 逐步执行与深入理解

从上到下依次执行四个print；sep只控制同一次print的多个参数之间的分隔符。

## 4. 易错点与检查

不要把中文引号当作代码引号；文件编码建议UTF-8。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第02课｜变量、数据类型与type

## 1. 基本原理

变量是指向对象的名字，赋值用=，比较用==。常见类型：int整数、float浮点数、str字符串、bool布尔值。Python变量无需预先声明类型，重新赋值可绑定不同类型。

## 2. 完整可运行代码

```python
name = "小明"
age = 20
height = 1.81
is_student = True
print(name, age, height, is_student)
print(type(age), type(height))
age = "二十"
print(type(age))
```

## 3. 逐步执行与深入理解

第一次age绑定整数20，之后重新绑定字符串；type反映当前对象类型，而非变量永久类型。

## 4. 易错点与检查

True/False首字母大写；变量名不能以数字开头。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第03课｜输入、类型转换与字符串运算

## 1. 基本原理

input()得到的永远是字符串。数值运算前要用int()或float()转换。str()把数值转为文本；字符串可用+拼接、*重复。

## 2. 完整可运行代码

```python
name = input("商品名：")
price = float(input("单价："))
count = int(input("数量："))
total = price * count
print(f"{name} × {count} = {total:.2f}元")
print("ab" * 3)
```

## 3. 逐步执行与深入理解

input读入字符串；float和int转换后才能进行数值乘法；f字符串把变量嵌入文本，:.2f显示两位小数。

## 4. 易错点与检查

int("3.5")会报错；"5"+"2"得到"52"而不是7。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第04课｜运算符与表达式

## 1. 基本原理

算术运算包括+、-、*、/、//、%、**；/得到浮点商，//向下取整，%求余。比较运算得到布尔值；and/or/not用于组合条件。

## 2. 完整可运行代码

```python
a, b = 17, 5
print(a / b)
print(a // b)
print(a % b)
print(a ** 2)
print(a > 10 and b < 10)
print(not (a == b))
```

## 3. 逐步执行与深入理解

17//5为3，17%5为2；**表示幂；and要求两个条件都真，not取反。

## 4. 易错点与检查

//对负数向负无穷取整，不是简单地去掉小数。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第05课｜条件分支if、elif、else

## 1. 基本原理

条件语句按顺序测试分支，只执行第一个成立的分支。冒号引出代码块，缩进决定归属；可使用比较运算与逻辑运算。

## 2. 完整可运行代码

```python
score = int(input("分数："))
if score < 0 or score > 100:
    print("输入无效")
elif score >= 90:
    print("优秀")
elif score >= 60:
    print("及格")
else:
    print("不及格")
```

## 3. 逐步执行与深入理解

先排除非法分数，再按由高到低的区间判定；满足某个分支后不再检查后续分支。

## 4. 易错点与检查

if后要写冒号；缩进通常用4个空格。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第06课｜for循环与range

## 1. 基本原理

for遍历可迭代对象。range(n)产生0到n-1；range(start,stop,step)不包含stop。循环变量每轮取下一个值。

## 2. 完整可运行代码

```python
n = int(input("请输入n："))
total = 0
for i in range(1, n + 1):
    if i % 2 == 1:
        total += i
print("奇数和：", total)
for x in range(2, 11, 2):
    print(x, end=" ")
```

## 3. 逐步执行与深入理解

range(1,n+1)才包含n；i%2==1判奇数；total在循环外初始化，在循环内累加。

## 4. 易错点与检查

range右端不包含；不要把total初始化放在循环体内。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第07课｜while循环、break与continue

## 1. 基本原理

while在条件为真时反复执行；必须保证循环状态有机会改变。break立即退出当前循环，continue跳过本轮余下语句。

## 2. 完整可运行代码

```python
i = 0
while i < 8:
    i += 1
    if i == 3:
        continue
    if i == 7:
        break
    print(i)
print("循环结束")
```

## 3. 逐步执行与深入理解

i先递增；3被跳过，7触发break，因此只输出1、2、4、5、6。

## 4. 易错点与检查

continue前要注意更新计数器，否则可能死循环。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第08课｜列表基础：创建、索引、切片

## 1. 基本原理

列表是有序、可变序列，可保存不同类型元素。索引从0开始，负索引从末尾算；切片[start:stop:step]不含stop，返回新列表。

## 2. 完整可运行代码

```python
scores = [80, 90, 75, 100]
print(scores[0], scores[-1])
print(scores[1:3])
scores[2] = 85
print(len(scores), max(scores), min(scores))
print(scores)
```

## 3. 逐步执行与深入理解

scores[1:3]取下标1和2；赋值修改第三个元素；len、max、min是内置函数，不必导入库。

## 4. 易错点与检查

索引越界会触发IndexError；切片越界通常不会报错。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第09课｜列表方法、排序与遍历

## 1. 基本原理

append添加一个元素，extend添加多个元素，insert按位置插入；pop删除并返回元素，remove按值删除。sort原地排序，sorted返回新列表。

## 2. 完整可运行代码

```python
nums = [4, 1, 3]
nums.append(2)
nums.insert(0, 9)
removed = nums.pop(0)
nums.sort()
print("删除：", removed)
for index, value in enumerate(nums):
    print(index, value)
print(sum(nums) / len(nums))
```

## 3. 逐步执行与深入理解

append得到[4,1,3,2]；插入9再pop删去9；sort后为[1,2,3,4]；enumerate同时给索引和值。

## 4. 易错点与检查

list.sort()返回None；不要写nums=nums.sort()。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第10课｜字符串索引、切片与常用方法

## 1. 基本原理

字符串是不可变序列。可以索引、切片、遍历，但不能直接改某个字符。常用strip、lower、upper、replace、split、join、find。

## 2. 完整可运行代码

```python
text = "  Python,C,Java  "
clean = text.strip()
langs = clean.split(",")
print(langs)
print(" | ".join(langs))
print(clean.lower())
print(clean.replace("Java", "Go"))
print(clean.find("C"))
```

## 3. 逐步执行与深入理解

strip去两端空格；split按逗号拆列表；join用分隔符拼接；这些方法返回新字符串，不改原字符串。

## 4. 易错点与检查

find找不到返回-1；字符串不能像列表那样修改下标位置。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第11课｜元组与集合

## 1. 基本原理

元组tuple是有序、通常不可变的序列；集合set元素不重复、无固定索引，适合去重与成员判断。集合支持并集|、交集&、差集-。

## 2. 完整可运行代码

```python
point = (3, 5)
print(point[0])
nums = [1, 2, 2, 3, 3]
a = set(nums)
b = {3, 4, 5}
print(sorted(a))
print(sorted(a | b))
print(sorted(a & b))
print(sorted(a - b))
```

## 3. 逐步执行与深入理解

set(nums)去掉重复；sorted让展示结果有序；|并集、&交集、-差集。

## 4. 易错点与检查

单元素元组写成(3,)；空集合要用set()，{}是字典。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第12课｜字典基础与增删改查

## 1. 基本原理

字典以键值对存储数据，键必须可哈希；常用字符串作键。通过dict[key]读取或赋值；get提供默认值，避免不存在的键引发KeyError。

## 2. 完整可运行代码

```python
student = {"name": "张三", "score": 88}
student["score"] = 92
student["age"] = 20
print(student.get("class", "未分班"))
for key, value in student.items():
    print(key, value)
del student["age"]
print(student)
```

## 3. 逐步执行与深入理解

给已有键赋值是修改，新键赋值是新增；items遍历键和值；del删除键。

## 4. 易错点与检查

字典不是按数字下标访问；访问不存在的键优先考虑get。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第13课｜嵌套容器与综合数据处理

## 1. 基本原理

列表里可以放字典，字典里也能放列表。真实程序常用“记录列表”保存多条结构化数据；遍历时用字段读取和聚合计算。

## 2. 完整可运行代码

```python
students = [
    {"name": "张三", "score": 85},
    {"name": "李四", "score": 92},
    {"name": "王五", "score": 78},
]
total = 0
for s in students:
    total += s["score"]
best = max(students, key=lambda s: s["score"])
print("平均分：", total / len(students))
print("最高分：", best["name"], best["score"])
```

## 3. 逐步执行与深入理解

每个字典是一名学生；for逐条求和；max的key参数告诉Python按score比较，而不是直接比较字典。

## 4. 易错点与检查

列表为空时除以len会出现ZeroDivisionError，应先检查是否为空。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第14课｜函数定义、参数与return

## 1. 基本原理

def定义可复用函数。形参接收调用者传入的实参；return返回结果并立即结束本次函数调用。没有显式return时返回None。

## 2. 完整可运行代码

```python
def get_grade(score):
    if not 0 <= score <= 100:
        return "无效"
    if score >= 90:
        return "优秀"
    if score >= 60:
        return "及格"
    return "不及格"
for s in [95, 72, 45, 110]:
    print(s, get_grade(s))
```

## 3. 逐步执行与深入理解

调用get_grade后按分数选择return；一旦执行return，函数余下代码不执行。

## 4. 易错点与检查

print是输出，不等于return；不要把函数名与变量名混用。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第15课｜函数参数进阶：默认值与关键字

## 1. 基本原理

位置参数按顺序匹配，关键字参数按名字匹配。默认参数允许调用时省略；可用多个return值组成元组。可变默认值可能跨调用共享，通常用None作为默认。

## 2. 完整可运行代码

```python
def checkout(price, count=1, discount=1.0):
    if price < 0 or count < 0:
        raise ValueError("价格和数量不能为负")
    total = price * count * discount
    return total, count
amount, quantity = checkout(50, count=3, discount=0.8)
print(amount, quantity)
print(checkout(20))
```

## 3. 逐步执行与深入理解

count与discount有默认值；调用时用关键字显式指定；返回两个值时可直接解包。

## 4. 易错点与检查

不要把可变列表或字典直接当默认参数，除非有意共享状态。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第16课｜变量作用域与可变对象

## 1. 基本原理

函数内赋值的名字通常是局部变量；外部定义的是全局名字。参数传递的是对象引用：修改可变对象内容可能影响调用方，重新绑定形参通常不会。

## 2. 完整可运行代码

```python
def modify(items, n):
    items.append(99)
    n = n + 1
    print("函数内部：", items, n)
a = [1, 2]
b = 10
modify(a, b)
print("函数外部：", a, b)
```

## 3. 逐步执行与深入理解

append直接修改同一个列表对象，外部a会变化；n=n+1创建新整数并让局部n指向它，外部b仍为10。

## 4. 易错点与检查

不要简单把Python参数传递理解为C语言式传值或传地址。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第17课｜递归函数

## 1. 基本原理

递归是函数直接或间接调用自身。必须有终止条件；每层调用有独立局部变量，返回时按调用栈逆序回退。适合分治、树遍历等问题。

## 2. 完整可运行代码

```python
def factorial(n):
    if n < 0:
        raise ValueError("n不能为负")
    if n == 0:
        return 1
    return n * factorial(n - 1)
for i in range(6):
    print(i, factorial(i))
```

## 3. 逐步执行与深入理解

factorial(4)=4*factorial(3)，逐层展开到factorial(0)=1，再逐层返回；没有终止条件会无限递归直至报错。

## 4. 易错点与检查

递归不一定比循环高效；层数太深会触发RecursionError。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第18课｜列表推导式与简洁数据处理

## 1. 基本原理

列表推导式是创建列表的表达式写法：[表达式 for 变量 in 可迭代对象 if 条件]。先遍历、再筛选、再计算结果；适合简洁映射和过滤。

## 2. 完整可运行代码

```python
nums = [1, 2, 3, 4, 5, 6]
evens = [x for x in nums if x % 2 == 0]
squares = [x * x for x in evens]
print(evens)
print(squares)
records = [("张三", 90), ("李四", 75)]
passed = [name for name, score in records if score >= 80]
print(passed)
```

## 3. 逐步执行与深入理解

evens筛选偶数得到[2,4,6]；squares计算平方得到[4,16,36]；最后按分数筛选姓名。

## 4. 易错点与检查

过长或多层嵌套的推导式可读性差，改用普通for循环。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第19课｜文件读写与with open

## 1. 基本原理

文件是持久化数据的常见方式。open指定路径、模式与编码；r读取、w覆盖写入、a追加。with确保离开代码块时自动关闭文件。

## 2. 完整可运行代码

```python
from pathlib import Path
path = Path("notes.txt")
with path.open("w", encoding="utf-8") as f:
    f.write("Python学习\n")
    f.write("文件操作\n")
with path.open("a", encoding="utf-8") as f:
    f.write("追加一行\n")
with path.open("r", encoding="utf-8") as f:
    for line in f:
        print(line.strip())
```

## 3. 逐步执行与深入理解

先w新建并覆盖文件，a在末尾追加，r逐行读取；strip去除行尾换行。

## 4. 易错点与检查

w会覆盖旧内容；中文文件建议显式encoding="utf-8"。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第20课｜JSON、CSV与路径管理

## 1. 基本原理

JSON适合存储列表、字典等结构化数据；CSV适合二维表格。pathlib.Path用于跨平台管理路径。json.dump/load用于文件读写；CSV写入建议newline=""。

## 2. 完整可运行代码

```python
import json
import csv
from pathlib import Path
records = [{"name": "张三", "score": 90}, {"name": "李四", "score": 85}]
path = Path("students.json")
with path.open("w", encoding="utf-8") as f:
    json.dump(records, f, ensure_ascii=False, indent=2)
with path.open("r", encoding="utf-8") as f:
    loaded = json.load(f)
with open("students.csv", "w", encoding="utf-8-sig", newline="") as f:
    writer = csv.DictWriter(f, fieldnames=["name", "score"])
    writer.writeheader()
    writer.writerows(loaded)
print(loaded)
```

## 3. 逐步执行与深入理解

dump把Python对象序列化为JSON，load还原；DictWriter写入表头和记录；utf-8-sig便于部分表格软件识别中文。

## 4. 易错点与检查

JSON不直接支持任意自定义对象；路径相对当前工作目录。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第21课｜异常处理try、except、else、finally、raise

## 1. 基本原理

异常是运行时错误的信号。try包围可能失败的代码；except捕获指定异常；else仅在没有异常时运行；finally总会在离开结构时尝试执行；raise主动抛异常。

## 2. 完整可运行代码

```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("除数不能为0")
    return a / b
for text in ["2", "0", "abc"]:
    try:
        n = int(text)
        result = divide(10, n)
    except (ValueError, ZeroDivisionError) as e:
        print("错误：", e)
    else:
        print("结果：", result)
    finally:
        print("本轮结束")
```

## 3. 逐步执行与深入理解

"2"成功执行else；"0"触发除零异常；"abc"在int转换时触发ValueError；finally每轮都执行。

## 4. 易错点与检查

优先捕获具体异常，避免裸except掩盖程序缺陷。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第22课｜模块、import与标准库

## 1. 基本原理

模块是可导入的Python代码文件。import module后用module.name访问；from module import name可直接使用；as提供别名。标准库math、random等无需额外安装。

## 2. 完整可运行代码

```python
import math
import random as rnd
from statistics import mean
nums = [2, 4, 6, 8]
print(math.sqrt(81))
print(math.ceil(3.2))
print(math.factorial(5))
print(mean(nums))
print(rnd.randint(1, 6))
print(rnd.choice(["红", "蓝", "绿"]))
```

## 3. 逐步执行与深入理解

math.sqrt求平方根，ceil向上取整，factorial求阶乘；random结果每次可能不同；mean计算均值。

## 4. 易错点与检查

不要把自己的脚本命名为random.py或math.py，以免遮蔽标准库。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第23课｜函数进阶：*args、**kwargs与lambda

## 1. 基本原理

*args把多余位置参数收集为元组；**kwargs把多余关键字参数收集为字典。lambda创建只含单个表达式的匿名函数，表达式结果自动返回。

## 2. 完整可运行代码

```python
def report(title, *scores, **info):
    print("标题：", title)
    print("分数：", scores)
    print("附加信息：", info)
    return sum(scores) / len(scores) if scores else 0
avg = report("考试", 80, 90, 100, teacher="王老师")
print("平均分：", avg)
products = [("鼠标", 59), ("键盘", 199), ("耳机", 129)]
products.sort(key=lambda item: item[1])
print(products)
```

## 3. 逐步执行与深入理解

80、90、100进入scores元组；teacher进入info字典；lambda item:item[1]使商品按价格排序。

## 4. 易错点与检查

lambda适合短表达式；复杂逻辑使用def更清晰。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第24课｜类与对象：self、实例属性与类属性

## 1. 基本原理

class定义类，调用类创建对象。__init__负责初始化；self是当前实例，self.name等是实例属性。直接写在类体中的属性通常是类属性，可被实例共享访问；实例同名赋值会遮蔽类属性。

## 2. 完整可运行代码

```python
class Student:
    school = "吉林大学"
    def __init__(self, name, score):
        self.name = name
        self.score = score
    def show(self):
        print(self.name, self.score, self.school)
s1 = Student("张三", 90)
s2 = Student("李四", 85)
s1.school = "其他学校"
Student.school = "新校名"
s1.show()
s2.show()
```

## 3. 逐步执行与深入理解

s1.school建立实例同名属性；修改Student.school只影响没有同名实例属性的查找结果；show通过self读取当前对象。

## 4. 易错点与检查

self不是关键字，但约定必须这样命名；不要混淆s1.show与s1.show()。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第25课｜继承、super、重写与多态

## 1. 基本原理

子类通过class Child(Parent)继承父类功能。super()可调用父类初始化方法；子类定义同名方法即重写。多态指相同调用接口作用于不同对象时产生不同结果。

## 2. 完整可运行代码

```python
class Animal:
    def __init__(self, name):
        self.name = name
    def speak(self):
        return "动物发声"
class Dog(Animal):
    def speak(self):
        return self.name + "：汪汪"
class Cat(Animal):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age
    def speak(self):
        return self.name + "：喵喵"
for animal in [Animal("动物"), Dog("小白"), Cat("小黑", 2)]:
    print(animal.speak())
```

## 3. 逐步执行与深入理解

Dog继承Animal的__init__；Cat使用super初始化name再设置age；循环只调用speak，结果由实际对象类型决定。

## 4. 易错点与检查

重写后优先执行子类方法；继承不是复制源代码。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第26课｜文件操作进阶：数据持久化与健壮性

## 1. 基本原理

前面已学基本文件操作，这一课作为进阶巩固：使用Path.exists判断文件是否存在，读取时捕获JSON解析错误，并在写入时保持编码一致。

## 2. 完整可运行代码

```python
import json
from pathlib import Path
path = Path("counter.json")
try:
    if path.exists():
        with path.open("r", encoding="utf-8") as f:
            data = json.load(f)
    else:
        data = {"count": 0}
except (OSError, json.JSONDecodeError):
    data = {"count": 0}
data["count"] += 1
with path.open("w", encoding="utf-8") as f:
    json.dump(data, f, ensure_ascii=False, indent=2)
print("运行次数：", data["count"])
```

## 3. 逐步执行与深入理解

首次运行无文件时从0开始；后续读取旧count并加1；文件损坏时恢复初始值。

## 4. 易错点与检查

这是本次按29课重组的复习进阶部分；覆盖写入前要考虑备份或原子写入。

## 5. 本课动手任务

在不照抄的情况下重新敲一遍代码；至少修改一个输入、增加一个功能，并解释运行结果为什么变化。

# 第27课｜迭代器与生成器：iter、next、yield

## 1. 基本原理

可迭代对象能通过iter()取得迭代器；迭代器用next()逐个取值并记录进度，耗尽时触发StopIteration。包含yield的函数调用后返回生成器，执行时在yield处暂停。

## 2. 完整可运行代码

```python
def countdown(n):
    while n > 0:
        print("准备产生：", n)
        yield n
        n -= 1
g = countdown(3)
print(next(g))
print(next(g))
print("剩余：")
for x in g:
    print(x)
a = [5, 10]
it1, it2 = iter(a), iter(a)
print(next(it1), next(it2))
```

## 3. 逐步执行与深入理解

生成器创建时函数体尚未执行；第一次next产生3，第二次产生2；for接着消费剩余的1。it1与it2进度独立。

## 4. 易错点与检查

next(g)耗尽后会报StopIteration；for会自动处理迭代结束。

## 5. 本课动手任务

把countdown改为从1递增到n，分别使用next和for读取，解释为什么不能从头重复消费同一个生成器。

# 第28课｜装饰器：闭包、@语法、参数与返回值

## 1. 基本原理

函数可以作为参数和返回值。装饰器接收函数并返回包装函数；@deco等价于func=deco(func)。装饰有参数的函数时，包装器通常接收*args和**kwargs，并返回原函数结果；functools.wraps保留函数元数据。

## 2. 完整可运行代码

```python
from functools import wraps
def log_call(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        print("开始调用：", func.__name__)
        result = func(*args, **kwargs)
        print("调用结束")
        return result
    return wrapper
@log_call
def add(a, b):
    return a + b
@log_call
def greet(name, punctuation="！"):
    return "你好，" + name + punctuation
print(add(3, 5))
print(greet("小明", punctuation="!"))
```

## 3. 逐步执行与深入理解

定义函数时@log_call把add替换为wrapper；调用add(3,5)时参数进入args，原函数返回8，再由wrapper返回；greet的关键字参数进入kwargs。

## 4. 易错点与检查

不能只调用func而忘记return，否则原函数结果会丢失；@wraps用于保留名称和文档等元数据。

## 5. 本课动手任务

在log_call装饰器里增加异常日志：发生异常时打印异常类型，然后重新抛出；验证原函数返回值未丢失。

# 第29课｜基础复盘：调试、测试、环境与综合练习

## 1. 基本原理

第29课定位为复盘与查漏补缺：用断点/print定位错误，用assert做简单断言，理解pip安装第三方包与venv隔离环境；把函数、容器、异常、类结合到可运行小程序。

## 2. 完整可运行代码

```python
class GradeBook:
    def __init__(self):
        self.scores = {}
    def add(self, name, score):
        if not 0 <= score <= 100:
            raise ValueError("分数必须在0到100之间")
        self.scores[name] = score
    def average(self):
        return sum(self.scores.values()) / len(self.scores) if self.scores else 0
    def top_student(self):
        if not self.scores:
            return None
        return max(self.scores, key=self.scores.get)
book = GradeBook()
book.add("张三", 88)
book.add("李四", 95)
assert book.average() == 91.5
print("平均分：", book.average())
print("最高分：", book.top_student())
```

## 3. 逐步执行与深入理解

GradeBook用字典保存成绩；add验证输入；average处理空数据；top_student通过key比较成绩；assert检查期望结果。

## 4. 易错点与检查

assert适合开发期检查，不宜代替面向用户的输入校验；venv和pip是环境工具，不是Python语法。

## 5. 本课动手任务

为GradeBook增加删除学生、按姓名查询和JSON保存/读取，并为无效分数写两条测试。

