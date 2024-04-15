
## 第二章 变量和简单数据类型

‍

### 变量的命名和使用注意事项：

* 慎用小写字母l和大写字母O,因为容易被看错成数字
* 变量名中，最好避免使用大写字母

‍

变量错误通常意味着两种情况：

1. 要么是使用变量前忘记赋值
2. 要么就是输入变量名字的时候拼写不正确

‍

在做p23页的动手练习的时候，发现vscode的shift + enter运行代码会报错，需要放到命令行里面去运行才正常，额，先随着它吧。

‍

### 数字

使用数字的时候，就要注意适当时候使用`str()`​避免类型错误

拼接的字符串的时候需要`str()`​

‍

## 第三章 列表简介

### 修改、添加、删除元素

修改：指定好序列位置，然后直接赋值替换

```python
motorcycles = ["honda","yamaha","suzuki"]

motorcycles[0] = "ducati"
print(motorcycles)

["ducati","yamaha","suzuki"]
```

‍

添加：

从列表末尾添加 `append( )`​ 

```python
motorcycles = ["honda","yamaha","suzuki"]
motorcycles.append("ducati") #从列表末尾添加
print(motorcycles)

["honda","yamaha","suzuki","ducati"]
```

从任意位置添加`insert( )`​

```python
motorcycles = ["honda","yamaha","suzuki"]
motorcycles.insert(1,"ducati")
print(motorcycles)

["honda","ducati","yamaha","suzuki"]
```

‍

删除：

* 使用del语句删除元素（需要知道具体的位置（序列））  
  删除后**无法再访问**

```python
motorcycles = ['honda', 'yamaha', 'suzuki'] 
del motorcycles[1]
print(motorcycles)

["honda","suzuki"]
```

‍

* 使用方法`pop()`​删除元素  **（默认删除尾，也可指定索引）**   
  方法pop删除之后，单独删除的那个元素还可以再拿来使用的

```python
motorcycles = ['honda', 'yamaha', 'suzuki']  
popped_motorcycle = motorcycles.pop() 
print(motorcycles)
print(popped_motorcycle)

['honda', 'yamaha' ]
suzuki


# 下面是指定索引的用法
motorcycles = ['honda', 'yamaha', 'suzuki'] 
first_owned = motorcycles.pop(0)
print(motorcycles)
print(first_owned)

['yamaha', 'suzuki'] 
honda
```

* 根据值删除元素，使用方法`remove()`​（知道值不知道位置）

```python
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati'] 
print(motorcycles) 
 
['honda', 'yamaha', 'suzuki', 'ducati']

motorcycles.remove('ducati') 
print(motorcycles)
['honda', 'yamaha', 'suzuki']
```

使用`remove()`​删除元素后，也和`pop()`​一样，可以接着使用它的值  
并且，方法`remove()`​要注意的是：**它只删除第一个指定的值，并不是批量删除！**

‍

### 组织列表

**方法**​`sort()`​以字母排序，对列表进行永久性排序；  
还可以反向排序`sort(reverse=True)`​

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
['audi', 'bmw', 'subaru', 'toyota'] #永久更改

cars.sort(reverse=True)
print(cars)
['toyota', 'subaru', 'bmw', 'audi'] # 使用颠倒后，变成倒序
```

‍

使用**函数**​`sorted()`​对列表进行临时排序  
反向排序的话操作是一样的

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print(sorted(cars))
['audi', 'bmw', 'subaru', 'toyota']

print(cars)
['bmw', 'audi', 'toyota', 'subaru']
```

使用方法`reserve()`​可以倒着打印列表，并且还可以在颠倒回来

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.reserve()
print(cars)
['bmw', 'audi', 'toyota', 'subaru']
```

使用函数`len()`​可快速获取列表的长度

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
len(cars)
4
```

‍

## 第四章 操作列表

### for循环

for循环要注意那个冒号`:`​ ，以及缩进关系：  
缩进了表示从属于上面那个，不缩进就是单独的了。缩进很重要！

### 数值列表

函数`range()`​

```python
for value in range(1,6):
	print(value)
1
2
3
4
5
# 他会少打印一个,也就是输出结果不包含括号内的第二个值
```

创建数字列表：思路是使用`list()`​将这些数字转换为列表：

```python
numbers = list(range(1,6))
print(numbers)
```

并且`range()`​可以指定步长：

```python
even_numbers = list(range(2,11,2))
print(even_numbers)
```

找最大最小和求和的函数：

```python
digits = [1,2,3,4,5,6]
min(digits)
max(digits)
sum(digits)
```

‍

### 列表的一部分：切片

```python
players = ["charles","martina","michael","florence","eli"]
print(players[0:3])
```

‍

### 复制列表

```python
my_foods = ["pizza","falafel","carrot cake"]
frind_foods = my_foods[:]
# 这里相当于创建了一个副本

frind_foods = my_foods
# 这里不能这样用，因为两个列表的数据互通了
```

```python
print(pizzas[2:5]) #中间三个元素

```

我贼容易把冒号打成逗号

‍

### 元组

元组跟列表的区别就是不能修改，需要重新赋值才能修改

‍

### 设置代码格式

缩进：建议每级缩进使用4个空格；可以使用制表符键，但记得一定要设置成空格，而不是插入制表符。

行长：

* 建议每行不超过80字符
* 建议注释的行长不超过72字符

学习期间就不用考虑了，怎么开心怎么来

‍

## 第五章 if语句

简单示例：

```python
cars =["audi","bmw","subaru","toyota"]

for car in cars:
	if car == "bmw":
		print(car.upper())
	else:
		print(car.title())

------
Audi
BMW
Subaru
Toyota
```

‍

每条if语句的核心都是一个值为True或False的表达式，这种表达式被成为条件测试。

‍

### 条件测试

大多数条件测试都是要将一个“变量”的当前值同特定值进行比较

```python
>>> car = 'bmw'
>>> car == 'bmw'
------
true
```

一个等号是陈述，相当于赋值  
两个等号相当于【发问】

‍

### 检查是否相等时不考虑大小写：

大小写会影响相等，但是如果你不用考虑大小写的话，可以用函数`lower()`​进行比较，例子：

```python
car == "Audi"
car.lower() == "andi"
# 这里用函数转换为小写，但是没有改变原来的赋值
```

应用的场景：书上说是确保用户名独一无二，但我感觉平时验证码也是，不用区分大小写一般来说，只需要确认是否输入正确与否。

‍

### 检查是否不相等

这里会用到一个符号：`!=`​ 其中，叹号表示【不】的意思，就是**不相等**的写法,例子：

```python
text = "wodiu"
if text != "666":
	print("hahaha")
```

**编写的大多数条件表达式都是用来检查两个值是否相等**

‍

### 比较数字

条件语句中可以包含【小于、小于等于、大于、大于等于】

‍

<br />

### 检查多个条件

使用and 和 or 来进行检验

```python
age_0 = 1
age_1 = 2
(age_0 >= 1) and (age_1 > 2)

age_0 >=1 or age_1 > 3
```

‍

### 检查特定值是否在列表中

场景：检查用户是否已经注册过

使用关键字`in`​ ， 例子：

```python
friend = ["lxy","tyz","jyt"]
"lxy" in friend
True

"hfd" in frined
False
```

‍

### if语句

if 语句的核心前面已经提到了，是true或者false，也就是符合了就执行后面所进的，不符合就略过。因此缩进的值需要注意。

![](https://s2.loli.net/2023/11/24/dTEjvy23gMH8cLs.png)​

我们可以看到上面的例子，就是第一个不符合，但是第二个符号，因此便运行了第二个elif后面的缩进。  
这段代码可以优化，优化之后需要更改描述语句就不需要更改三次了：

![](https://s2.loli.net/2023/11/24/mjXgUdVbABa9pYy.png)​

‍

if语句如果需要使用多个的话形式是不一样的：

只用一个的话就只需要一个if  
使用两个的话需要if else  
使用三个或者多个的话就是if 不定量个elif 结尾一个else

省略else代码块  
原来else和elif是有区别的：

> else是一条包罗万象的语句，只要不满足任何if或elif中的条件测试，其中的代码就会执行，  
> 这可能会引入无效甚至恶意的数据。如果知道最终要测试的条件，应考虑使用一个elif代码块来  
> 代替else代码块。这样，你就可以肯定，仅当满足相应的条件时，你的代码才会执行。

只要前面的不满足,else就会执行，而elif只有当条件满足的时候才会执行。

‍

### 测试多个条件：

if-elif-else结构只适合只有一个条件满足的情况，但如果需要多个条件呢？  
那就使用一系列简单的if语句

> 总之，如果你只想执行一个代码块，就使用if-elif-else结构；如果要运行多个代码块，就  
> 使用一系列独立的if语句。

‍

## 第六章 字典

### 什么是键值对？

例子：

```python
alien_0 = {'color':'green','points':5}
print(alien_0['color']) # 访问字典中的值
# 如何添加键值对？
alien_0['x_position'] = 0

# 如何修改键值对？
alien_0['x_position'] = 1
```

‍

### 如何删除键值对？

```python
alien_0 = {'color':'green','points':5}

del alien_0['points']
```

‍

### 遍历字典

Python支持对字典遍历。  
因此有多种遍历字典的方式：可遍历字典的所有键—值对、键或值。

#### 遍历所有的键值对：

```python
user_0 = { 
    'username': 'efermi', 
    'first': 'enrico', 
    'last': 'fermi', 
    } 
 
for key, value in user_0.items(): 
    print("\nKey: " + key) 
    print("Value: " + value)
```

例子中，声明了两个变量，第二部分包含了字典名+方法`items()`​

注意，返回的时候顺序会变，python只关心键值的对应关系，不关注返回顺序

‍

#### 遍历所有的键：

只需要"键"的时候，使用方法`keys()`​  
书上的例子在使用keys的时候演示了两种用法：

* 指定一个列表，然后把keys的这个列表放进去for循环来匹配if语句
* keys实际上可以返回一个列表，它包含了字典中的所有键，所以可以看你需要检验的值是否在这个列表里

‍

#### 按顺序遍历字典中的所有键：

一般情况下是不需要的，但是你要按顺序遍历也不是问题。

使用`for`​循环加上函数`sorted()`​来获得特定顺序排列副本  
​`sorted()`​是按照字母顺序排序哦。

‍

#### 遍历字典中的所有值：

我们使用方法`values()`​

使用for循环可以遍历出所有的值，但是如果我们要剔除重合的部分呢？

那就使用集合（set）

```python
favorite_languages = { 
    'jen': 'python', 
    'sarah': 'c', 
    'edward': 'ruby', 
    'phil': 'python', 
    } 
 
print("The following languages have been mentioned:") 
for language in set(favorite_languages.values()): 
     print(language.title())
```

‍

#### 习题错误：

```python
or vocabulary,connotation in program_vocabulary.items():
    print(vocabulary + ": " + connotation )

counter_rivers = {
    'Yellow River':'china',
    'the Ganges River':'india',
    'Amazon':'peru',
}
# 傻逼了，我就说运行一直报错，忘记打逗号了
for river,through in counter_rivers.items():
    print("The " + river + " runs through " + through )
```

‍

### 嵌套

什么是嵌套？  
有时候，需要将一系列字典存储在列表中，或将列表作为值存储在字典中，这称为嵌套。

‍

## 第七章 用户输入和while循环

### 使用`int()`​​来获取数值输入

使用`input()`​后，填入里面的数字是作为字符串，如果要将其作为数值使用的话，需用使用`int()`​

```python
height = input("How tall are you, in inches? ")
height = int(height) #这里就把用户输入的数值转换为了可以进行比较的数字啦

if height >= 36:
	print("\nYou're tall enough to ride")
else:
	print("\nYou'll be able to rede when you're a little older.")
```

‍

### 求模运算符

求模运算符（%）是一个很有用的工具，它将两个数相除并返回余数

教材中的用法是用来判断奇偶

‍

### while循环

可以使用while循环让用户选择何时退出

关于 += 1的理解：

```python
current_number += 1
(current_number = current_number + 1)
```

‍

关于prompt += 这个的理解

```python
prompt = "If you tell us who you are, we can personalize the messages you see."
prompt += "\nWhat is your first name? "
# 意思就是在原来的基础上加上后面的这串字符
------
------
If you tell us who you are, we can personalize the messages you see.  
What is your first name? 
```

‍

使用标志

在要求很多条件都满足才继续运行的程序中，可定义一个变量，用于判断整个程序是否处于活动状态。这个变量被称为标志​

‍

break语句可以立刻退出循环

‍

循环中使用continue：要返回到循环开头，并根据条件测试结果决定是否继续执行循环，可使用continue语句

‍

注意：在做练习的时候，我发现了我的一个易错点:`我在这里经常犯错的就是忘记把票价作为字符串显示`​

‍

‍

字典：

```python
# 创建一个空字典
my_dict = {}

# 将值存入字典
my_dict["key1"] = "value1"
my_dict["key2"] = "value2"
my_dict["key3"] = "value3"

print(my_dict)

{'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}
```

‍

## 第八章 函数

### 位置实参

就是你定义好形参之后，实参的排列位置按照形参的位置给定

‍

### 关键字实参

```python
def describe_pet(animal_type, pet_name): 
    """显示宠物的信息""" 
    print("\nI have a " + animal_type + ".") 
    print("My " + animal_type + "'s name is " + pet_name.title() + ".") 
   
describe_pet(animal_type='hamster', pet_name='harry')
```

关键字实参就不用考虑位置啦

‍

### 默认值

默认值设定后，依然不影响形参的位置特性，所以，要么排序，要么给关键字

‍

### 实参可选

设定可选实参的默认值为空字符串

‍

python将非空字符串解读为True

‍

### 杂乱备注：

每次提示用户输入时，都应提供退出途径。

‍

在函数中对这个列表所作的任何修改都是永久性的

‍

编写函数时，如果你发现它执行的任务太多，请尝试将这些代码划分到两个函数中。别忘了，总是可以在一个函数中调用另一个函数，这有助于将复杂的任务划分成一系列的步骤。

‍

### 禁止函数修改列表

有时候，需要禁止函数修改列表。

为解决这个问题，可向函数传递列表的副本而不是原件；这样函数所做的任何修改都只影响副本，而丝毫不影响原件。

但除非有充分的理由需要传递副本，否则还是应该将原始列表传递给函数，因为让函数使用现成列表可避免花时间和内存创建副本，从而提高效率，在处理大型列表时尤其如此。

‍

### 传递任意数量的实参

`*toppings`​

将收到的值封装进元组，[元组](siyuan://blocks/20231121234250-lo0nq0p)是不可以修改的

‍

### 结合使用位置实参和任意数量实参

如果要让函数接受不同类型的实参，必须在函数定义中将接纳任意数量实参的形参放在最后。

```python
def make_pizza(size, *toppings):
```

‍

### 使用任意数量的关键字实参

```python
def build_profile(first, last, **user_info):
```

需要接受任意数量的实参，但预先不知道传递给函数的会是什么样的信息。

将函数编写成能够接受任意数量的键—值对

‍

### 将函数存贮在模块中

使用`import`​语句存入

函数的优点之一是，使用它们可将代码块与主程序分离。

你还可以更进一步，将函数存储在被称为模块的独立文件中，再将模块导入到主程序中。import语句允许在当前运行的程序文件中使用模块中的代码。

‍

导入特定的函数：

```python
from module_name import function_name
from module_name import function_0, function_1, function_2
```

‍

如果导入的函数与现有程序冲突可使用`as`​给函数取个外号

```python
from pizza import make_pizza as mp
```

‍

使用`as`​给模块指定别名：

```python
import pizza as p
```

‍

导入模块中的所有函数：使用`*`​号

```python
from pizza import *
```

‍

### 做题记录：

在这里发现了一个问题，就是我把模块的作业新建了一个内层的文件夹，然后`import`​模块的时候无法正常运行，我把他们全部提取到上层的文件夹之后，可以正常`import`​了，什么原因？

‍

‍

## 第九章 类

根据类来创建对象被称为实例化

在Python中，首字母大写的名称指的是类。

类中的函数称为方法

通过实例访问的变量称为属性。

方法__init__()并未显式地包含return语句，但Python自动返回一个表示这条小狗的实例。

我们通常可以认为首字母大写的名称（如Dog）指的是类，而小写的名称（如my_dog）指的是根据类创建的实例。

‍

**注意：初始的init前后需要使用双下划线！！！**

‍

修改属性的值（3种方法）：

1. 直接修改
2. 通过方法修改
3. 通过方法对属性递增

‍

继承：子类继承父类，并且还可以定义自己的属性和方法。

‍今天终于完成了python从入门到实践的学习，后面两章实在是没耐心看了，开始做点新手项目玩一玩试试，积攒一点兴趣吧。
2024.1.24 23:00 end.

<!-- ##{"timestamp":1701011243}## -->
‍