[TOC]
##### 内置函数
1. chr()函数，将ASCII码转为对应字符 
e.g:   ```print(chr(97))```
2. ord()函数，查找字符对应的ASCII码
e.g:   ```print(ord('北')) ```
3. 强制类型转换
```py
num=int(num) #强制类型转换为整形
float(x) #转换为浮点型
str(x) #转换为字符串
bool(x) #转换为bool型
hex(x) #将整数转换为十六进制
oct(x) #将整数转换为八进制
bin(x) #将整数转换为二进制
```
4. len()函数，求长度
e.g:   ```print(len(keyword.kwlist)) ```
5. type()函数，返回类型
e.g:   ```print(type(a)) ```
6. id()函数，返回内存地址
e.g:   ``` print(id(a))```
7. 进制
   1. 二进制以0b或0B开头
   2. 八进制以0o或0O开头
   3. 十六进制以0x或0X开头
print出来都是十进制的
8. round(num,保留位数)函数，保留几位小数
e.g:   ```print(round(0.2+0.1,1)) ```
9. eval()函数，去掉字符串最外侧的引号并按python语句执行的方式执行去掉引号后的语句
   1.  执行运算
    ```python
    s='3.14+3'
    print(eval(s)) #6.14
    ```
    2. 与input一起获取用户输入的数值型
   
    ```python
    age=eval(input('请输入您的年龄')) #相当于int(age)，age为int型
    ``` 
    3. ```eval('print("dddd")')```相当于直接执行print操作
10. range函数,产生一个[n,m)的整数序列，不包括m
```python
for i in range(1,11):
print(i)
```
##### print函数
```py
print(value,...,sep=' ',end='\n',file=none)
# sep：分隔符，两个value之间的连接符，默认为空格
# end：结束语，默认为换行
# file：文件操作
print('Hello'+','+'World')
# 必须是字符串类型
s='HELLOWORLD'
print(s[0],s[-10]) #都是H
print('北京欢迎你'[4]) #'你'
print('北京欢迎你'[-1]) #'你'
print(s[2:7]) #LLOWO,从2开始不包括7
print(s[-8:-3]) #同上
print(s[5:]) #从5开始到结束
print('$'*4) #输出$$$$
"""
这是一个多行注释，用三个'或三个"包围均可
"""
```
##### input函数
```py
x=input('提示文字')
# 无论输入的是什么，都是字符串类型
```
##### 文件操作
```py
fp=open('note.txt','w') 
print('hello,world',file=fp)
fp.close()
```
##### 查询关键字
```python
import keyword
print(keyword.kwlist)
```
##### 变量
变量的定义可以连等``` num=number=23```,num与number的内存地址相同
##### 数据类型
1. 复数
```python
x=123+456j #虚部单位j
print(x.real) #实数部分
print(x.imag) #虚数部分
```
1. 字符串类型
   1. 多行字符串
      ```python
      info="""这是第一行
              这是第二行
           """
      # 用三个'或"引起来
      ```
   2. 转义字符
    ```
    \n 换行
    \t 制表符
    \" 双引号
    \\ 反斜线
     ```
    加r或R使转义字符失效
    ```python
    print(r'Hello\nWorld') #输出Hello\nWorld
    ```
2. bool类型
```print(False+10) ```输出10
非0的整数或小数的bool值为True
非空的字符串的bool值为True
False与None的bool值为False 
##### 运算符
|  运算符   |     运算     |                             示例                              |
| :-------: | :----------: | :-----------------------------------------------------------: |
|    //     |     整除     |                            10//3=3                            |
|    **     |    幂运算    |                            2**4=16                            |
|     %     |     取余     |                            10%3=1                             |
|     =     |   链式赋值   |                a=b=c=5,a,b,c,d='room',a='r'...                |
| a,b=10,20 | 系列解包赋值 |                           a=10,b=20                           |
|  a,b=b,a  | 交换a与b的值 |                       temp=a,a=b,b=temp                       |
|    and    |    与或且    |            都为True才为True，只要有False即为False             |
|    or     |      或      |               全为False为False，有True即为True                |
|    not    |      非      |                             取反                              |
|     &     |    按位与    |                    转为二进制后按位进行and                    |
|    \|     |    按位或    |                          按位进行or                           |
|     ^     |   按位异或   |             二进制对齐，每一位相同为零，不同为一              |
|     ~     |   按位取反   |                        0变为1，1变为0                         |
|    <<     |    左移位    |    高位溢出，低位补零，3<<4=48，相当于3*2*2*2*2，左乘右除     |
|    \>>    |    右移位    | 低位溢出，高位为零补零，为一补一，9>>2=2，相当于(9//2)//2整除 |

##### 选择结构
```python
num=eval(input('请输入您的彩票号码'))
if num==678934:
    print('恭喜中奖')
elif num==123455:
    print('50元')
else:
    print('not found 404')
# 或者
print('恭喜中奖'if num=678934 else'404')
```
##### match语句
```py
score=input('请输入成绩等级')
match score:
    case 'A':
        print('优秀')
    case 'B':
        print('ok')
    case 'C':
        print('vegetable chicken')

```

##### 循环结构
```python
1.for
for i in 'hello':
    print(i)
s=0
for i in range(1,11):
    s+=i
else:
    print('1~10的和为's)
# else在循环正常结束时执行，遇break等不执行
2.while
s=0
i=1
while i<101:
    s+=i
    i+=1
else: #正常循环结束执行，即i到101时
    print('sum=',s)
```

##### break continue pass
break：跳出循环
continue跳过本次循环的后续代码
pass执行空语句块 
e.g: if a==5:
        pass//否则空着会报错

##### 序列的操作
1. 切片操作
序列[a:b:c]
a为开始位置，默认为0
b为结束位置，不包括b，默认为结尾
c为步长，默认为1
```python
s='helloworld'
s1=s[0:5:2]
print(s1) #输出hlo
print(s[::-1]) #可以将序列逆序输出
print(s[-1:-11:-1]) #逆序输出
```
2. 相加与相乘
```python
s1='hello'
s2='world'
s=s1+s2 #s=helloworld
print('-'*40) #输出40个-
print(s1*40)
```
3. 其他操作
```python
x in s #判断x是否是s的元素，是为True，不是为False
x not in s #不是为True，是为False
len(s) #序列的长度
max(s) #序列s元素的最大值
min(s) #元素的最小值
s.index(x) #序列s中第一次出现x的位置
s.count(x) #出现x的总次数
```
##### 列表（属于序列）
1. 创建
```python
list1=['happy','every','day',98]
list2=list('helloworld')
del list2 #删除list2
list3=list(range(1,10,2))

"""
print结果为
['happy', 'every', 'day', 98]
['h', 'e', 'l', 'l', 'o', 'w', 'o', 'r', 'l', 'd']
[1, 3, 5, 7, 9]
"""
```
2. 遍历
```python
list1=['abc','def','ghi']
for item in list1:
    print(item)
for i in range(0,len(list1)):
    print(list1[i])
for index,item in enumerate(list1,start=1):
    print(index,item) 
# index为序号，item是元素，start为序号的初始值
```
3. 列表的操作
```python
lst.append(x) #在列表最后加一个元素x
lst.insert(index,x) #在列表第index位置加一个元素x
lst.clear() #清空lst中元素
lst.pop(index) #将lst中第index位置的元素取出并从列表中将其删除
lst.remove(x) #将第一个x删除
lst.reverse() #将列表元素反转
lst.copy() #拷贝所有元素并新建一个列表
lst.sort(key=None,reverse=False) #排序，参数key是排序规则，reverse为排序方式，默认升序为False，lst.sort()
sorted(iterable,key=None,reverse=False) #iterable为排序对象,字母排序先排大写，再排小写，大写的ASCII码比小写的小32
lst.sort(key=str.lower) #排序不考虑大小写
列表生成式
lst=[expression for item in range]
lst=[expression for item in range if condition]
e.g:
lst=[item for item in range(1,11)] #生成一个1到10的列表
lst=[random.randint(1,100) for _ in range(10)] #生成一个十个随机数的列表，item不用可以用_代替
lst=[item for item in range(1,11) if item%2==0] #[2, 4, 6, 8, 10]
二维列表
1.遍历
for row in lst:
    for item in row:
        print(item,end='___')
    print()
允许lst[2][2]访问
lst[0:3:2]
2.生成
lst=[[1,2,3,4,5],[6,7,8,9,10]]
lst=[[item for item in range(5)] for _ in range(4)] #4行5列
```
##### 元组
不可变数据类型，没有增删改等操作，只能索引或者遍历
```python
1.元组的创建
t=('hello',[10,20,30],40,'world')
t=tuple('helloworld') #('h', 'e', 'l', 'l', 'o', 'w', 'o', 'r', 'l', 'd')
2.元组有in，not in，max，len等操作
3.元组中只有一个元素时‘，’不能省，t=(10,)
4.删除 del t
5.访问
print(t[0:3:2])
print(t[2])
6.遍历
for item in t:
    print(item)
for i in range(len(t)):
    print(t[i])
for index,item in enumerate(t,start=11):
    print(index,':',item)
7.元组生成式
t=(item for item in range(1,4))
print(t) #无法输出
t=tuple(t) #转换为元组可以输出
———————————————————————————————
t=(item for item in range(1,4))
print(t.__next__()) #取出1
print(t.__next__()) #取出2
print(t.__next__()) #取出3，t中没有元素了
```
##### 字典
一个key对应一个value
key的值不能重复，若重复后面的key的value会将前面的value覆盖
key的值为不可变数据类型，list不能作为key {lst：10}报错
空字典，元组，列表的bool值为False，其余为True
1. 创建
```python
1.用{}创建
d={key1:value1,key2:value2,key3:value3}
2.映射创建
lst1=[10,20,30,40]
lst2=['张三','李四','王五','pet','cat'] #多出来的忽略
zipobj=zip(lst1,lst2) #直接输出会print：<zip object at 0x0000016EB720A540>
d=dict(zipobj) #转为字典,上面的是key，下面的是value
print(d) #输出{10: '张三', 20: '李四', 30: '王五', 40: 'pet'}
3.参数创建字典
d=dict(cat=10,dog=20,cow=30,room=40) #左侧是key，右侧是value
print(d) #{'cat': 10, 'dog': 20, 'cow': 30, 'room': 40}
```
2. 用法
```python
d={'cat':10,'dog':0}
print(max(d)) #dog
print(min(d)) #cat
print(len(d)) #2

```
3. 取值
```python
1.访问
d[key] or d.get(key) #print(d['cat'])
如果key不存在，d[key]会报错，d.get(key)可以指定默认值
print(d.get('Los Angeles')) #会报None
get方法可以指定默认值，d.get('Los Angeles','不存在') #会返回‘不存在’
2.遍历
for item in d.items():
    print(item)
for key,value in d.items():
    print(key,value)
```
4. 操作
```python
d={1001:'Jerry',1002:'Mike',1003:'Jenny',1004:'Jason',1005:'Bob'}
keys=d.keys() #获取所有key数据
#返回值为dict_keys([1001, 1002, 1003, 1004, 1005])结果集，无法访问其中每一个
#访问每一个值：转换为列表类型或元组类型，list(keys),tuple(keys)
d.values() #获取所有value数据
d.pop(key,default) #key存在返回对应的value，同时删除key-value对，否则获取默认值
d.popitem() #随机从字典中取出一个key-value对，结果为元组类型，同时将该key-value从字典中删除
d.clear() #清空字典中所有的键值对
d[1006]='Li Hua' #向字典中添加元素
d.items() #获取所有键值对
#直接print(d.items())输出结果集
#需要转换为list或者tuple，print(list(d.items()))
#转为list后再进行字典操作的需要在转回字典类型，d=dict(d)
合并字典 d3=d1|d2
```
5.字典的生成式
```python
d={key:value for item in range}
d={key:value for key,value in zip(lst1,lst2)}
```
##### 集合
无序的不重复的元素序列
只能储存不可变数据类型,不能存储字典,序列
1. 定义
```python
s={element1,element2,element3...}
s=set( ) #创建空集合,空集合的bool值为False
s={} #创建空字典
s=set('helloworld') #{'r', 'h', 'l', 'w', 'd', 'o', 'e'}
s=set([10,20,30]) #{10, 20, 30}
max,min,len,in,not in
```
2. 操作
```py
A={10,20,30,40,50}
B={20,40,60,80,100}
1.交集 A&B
print(A&B) #{40, 20}
2.并集 A|B
print(A|B) #{100, 40, 10, 80, 50, 20, 60, 30}
3.差集 A-B
print(A-B) #{50, 10, 30}A去掉重复的
print(B-A) #{80, 100, 60}B去掉重复的
4.补集 A^B
print(A^B) #{80, 50, 100, 10, 60, 30}
5.add(x) #添加元素
6.remove(x) #删除元素
7.clear() #清空集合中所有元素
```
3. 遍历
```python
for item in s:
    print(item)
for index,item in enumerate(s):
    print(index,':',item)
```   
4. 生成式
```python
s={i for i in range(1,11)}
```
##### 结构模式匹配
```python
data=eval(input('请输入'))
match data:
    case {'key':'value'}:
        print('dictionary')
    case [10,20]:
        print('list')
    case (10,20):
        print('tuple')
    case _:   #相当于多重if中的else
        print('else')
```
##### 同步迭代
```python
fruits=['apple','orange','pear']
numbers=(10,20,30)
for fruit,number in zip(fruits,numbers):
    match fruit,number:
        case 'apple',10:
            print('ten apples')
        case 'orange',20:
            print('twenty oranges')
#ten apples
#twenty oranges
```






