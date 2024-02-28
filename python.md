[TOC]
##### 内置函数
1. chr()函数，将ASCII码转为对应字符 
e.g:   ```print(chr(97))```
2. ord()函数，查找字符对应的ASCII码
e.g:   ```print(ord('北')) ```
3. 强制类型转换
```py
num=int(num) #强制类型转换为整形,小数直接去掉
float(x) #转换为浮点型
str(x) #转换为字符串
bool(x) #转换为bool型
hex(x) #将整数转换为十六进制
oct(x) #将整数转换为八进制
bin(x) #将整数转换为二进制
bool(x) #获取指定对象的bool值
list(sequence) #将序列转化成列表类型
tuple(sequence) #将序列转化为元组类型
set(sequence) #将序列转化为集合类型 
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
11. 数学函数
```python
abs(x) #绝对值
divmod(x,y) #获取x与y的商和余数
max(sequence) #sequence中的最大值
min(sequence) #sequence中的最小值
sum(iter) #对可迭代对象进行求和运算,可以直接放入一个列表等    
pow(x,y) #获取x的y次幂
round(x,d) #x保留d位小数,结果四舍五入,只有一个参数为保留整数,四舍五入,第二个参数为-1对个位四舍五入等
```

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
##### 字符串
1. 操作
```python
string.lower() #全部转换为小写
string.upper() #全部转换为大写
string.split(sep=None) #将string字符串按照分隔符sep分隔，结果为列表类型
    e.g: s='ChenYibo@qq.com'
         a=s.split(sep='@')
         print(a) #['ChenYibo', 'qq.com'],a[0]=ChenYibo
string.count(sub) #统计sub字符串出现的次数
string.find(sub) #查询sub字符串是否存在，不存在结果为-1，存在返回首次出现的索引
string.index(sub) #与find相同，但不存在程序报错
string.startswith(s) #查询字符串是否以子串s开头
string.endswith(s) #是否以s结尾 
string.replace(old,new,替换次数) #使用new替换字符串中所有的old字符串
string.center(width,fillchar) #字符串在指定的宽度范围内居中，可以使用fillchar填充
string.join(iter) #将string插入到iter的每个字符之间
string.strip(chars) #从字符串中去掉左侧和右侧chars中列出的字符串，与chars顺序无关,只要包含就去掉
s.strip() #去除左右空格
string.lstrip(chars) #去掉左侧chars
string.rstrip(chars) #去掉右侧chars
```
2. 格式化字符串
```python
1.%占位
name='Li Ming' #一般字符串和整数等不能直接连接，需要用%占位符
age=18
score=99.9
print('年龄：%s，年龄：%d，成绩：%.1f' % (name,age,score)) # %1.f可以控制保留几位小数
2.f-string
print(f'姓名：{name}，年龄{age}，成绩{score}')
3.（.format）方法
print('姓名：{0}，年龄：{1}，成绩：{2}'.format(name,age,score))
————————————————————————————————————————————————————————————————————————————————————
{序号:填充 对齐方式 宽度 , .精度 类型}
:引导符
填充：用于填充单个字符
对齐方式：<左对齐，>右对齐，^居中对齐
宽度：字符串输出宽度
,：数字的千位分隔符，只适用于整数和浮点数
.精度：浮点数小数部分精度或字符串最大输出长度
类型：整数类型：b二进制、d十进制、o八进制、x（X）十六进制
      浮点数类型：e（E）、f、%
s='helloworld'
print('输出：{0:·^20}'.format(s)) #输出：·····helloworld·····
a=987654321.98237643
print('输出：{0:,}'.format(a)) #输出：987,654,321.9823765
print('输出：{0:.2f}   {1:.2}'.format(a,s)) #输出：987654321.98   he
num=123
print('输出：{0:b},{0:d},{0:o},{0:x}'.format(num)) #输出：1111011,123,173,7b
floatnum=13.14521111111
print('输出：{0:.2f},{0:.2e},{0:.3%}'.format(floatnum)) #输出：13.15,1.31e+01,1314.521%
```
3. 字符串拼接
```python
1.+加号
2.str.join()
print(''.join(['hello','world'])) #helloworld
print('&&'.join(['a','b','c','d'])) #a&&b&&c&&d
3.直接拼接
print('hello''world') #helloworld
4.格式化字符串拼接
s1='good'
s2='luck'
print('{0}{1}'.format(s1,s2)) #goodluck
print(f'{s1}{s2}') #goodluck
print('%s%s'%(s1,s2)) #goodluck
```
4. 字符串去重
```python
s='aaabbbcccddd'
s_new1=''
for item in s:
    if item not in s_new1:
        s_new1+=item
print(s_new1) #abcd

s_new2=''
for i in range(len(s)):
    if s[i] not in s_new2:
        s_new2+=s[i]
print(s_new2) #abcd

s_new3=set(s)
print(s_new3) #{'c', 'a', 'b', 'd'}
list3=list(s_new3)
list3.sort(key=s.index)
print(''.join(list3)) #abcd
```
##### 编码解码
```python
编码string.encode(encoding='utf-8',errors='strict/ignore/replace')
解码string.decode(encoding='utf-8',errors='strict/ignore/replace') #编码和解码需要用相同的encoding
s='中国梦'
encodes=s.encode('utf-8','strict')
print(encodes) #b'\xe4\xb8\xad\xe5\x9b\xbd\xe6\xa2\xa6'
decodes=encodes.decode('utf-8','strict')
print(decodes) #中国梦
print(b'\xe4\xb8\xad\xe5\x9b\xbd\xe6\xa2\xa6'.decode('utf-8',errors='strict')) #中国梦
```
##### 数据的验证
```python
str.isdigit() #所有字符都是十进制的阿拉伯数字
str.isnumeric() #所有字符都是数字，可以是一，二、壹，贰，罗马数字等，0b1010二进制不行
str.isalpha() #所有字符都是字母（包括中文字符）
str.isalnum() #所有字符都是数字或字母，包括中文字符
str.islower() #都是小写
str.isupper() #都是大写，中文既是大写又是小写
str.istitle() #所有字符都首字母大写 "Hello"：True，"HelloWorld"：Wrong，"Hello World"：True
str.isspace() #所有字符都是空白字符(\n,\t,' '等)
```
##### 正则表达式
1. 元字符
具有特殊意义的专用字符，例如"^"和"$"分别表示匹配的开始和结束

| 元字符 |           说明           |    example    |          result           |
| :----: | :----------------------: | :-----------: | :-----------------------: |
|   .    |   匹配任意字符（除\n）   | 'p\nytho\tn'  |   p、y、t、h、o、\t、n    |
|   \w   |  匹配字母、数字、下划线  | 'python\n123' | p、y、t、h、o、n、1、2、3 |
|   \W   | 匹配非字母、数字、下划线 | 'python\n123' |            \n             |
|   \s   |     匹配任意空白字符     | 'python\t123' |            \t             |
|   \S   |    匹配任意非空白字符    | 'python\t123' | p、y、t、h、o、n、1、2、3 |
|   \d   |     匹配任意十进制数     | 'python\t123' |          1、2、3          |
2. 限定符
用于限定匹配次数

| 限定符 |              说明              |   example   |                result                |
| :----: | :----------------------------: | :---------: | :----------------------------------: |
|   ?    |     匹配前面的字符0次或1次     |   colou?r   |        可以匹配color或colour         |
|   +    |    匹配前面的字符1次或多次     |   colou+r   |      可以匹配colour或colouu...r      |
|   *    |    匹配前面的字符0次或多次     |   colou*r   |      可以匹配color或colouu...r       |
|  {n}   |       匹配前面的字符n次        |  colou{2}r  |           可以匹配colouur            |
|  {n,}  |     匹配前面的字符最少n次      | colou{2,}r  |     可以匹配colouur或colouuu...r     |
| {n,m}  | 匹配前面的字符最小n次，最多m次 | colou{2,4}r | 可以匹配colouur或colouuur或colouuuur |
3. 其他字符

|  其他字符  |         说明         |  example   |             result             |
| :--------: | :------------------: | :--------: | :----------------------------: |
| 区间字符[] | 匹配[]中所指定的字符 | [.?!][0-9] | [匹配标点符号点、问号、感叹号][匹配0、1、2、3、4……9]|
|排除字符^|匹配不在[]中指定的字符|[^0-9]|匹配除0-9的字符|
|选择字符\||用于匹配 \| 左右的任意字符|\d{18}\|\d{15}|匹配十五位或十八位身份证|
|转义字符|同python中的转义字符|\ .|将.作为普通字符使用|
|[\u4e00-\u9fa5]|匹配任意一个汉字|||
|分组()|改变限定符的作用|six\|fourth和(six\|four)th|匹配six,fourth和匹配sixth,fourth|
##### re模块
内置模块，用于实现python中的正则表达操作
```python
re.match(pattern,string,flags=0) #用于从字符串的开始位置进行匹配，如果起始位置匹配成功结果为Match对象，否则为None
re.search(pattern,string,flags=0) #用于在整个字符串中搜索第一个匹配的值，如果匹配成功，结果为Match对象，否则为None
re.findall(pattern,string,flags=0) #用于在整个字符串中搜索所有符合正则表达式的值，结果为列表
re.sub(pattern,repl,string,count,flags=0) #用于实现对字符串中指定子串的替换,string为子字符串，repl为新的字符串
re.split(pattern,string,maxsplit,flags=0) #与字符串中的split功能相同，分隔字符串，maxsplit为分割线的数量
import re
pattern='\d\.\d+' #模式字符串
s='123.3456 python 1.32'
match=re.match(pattern,s,re.I) #re.I为忽略大小写
print(match) #None
search=re.search(pattern,s,flags=0)
print(search) #<re.Match object; span=(2, 8), match='3.3456'>
print('start:',search.start())
print('end:',search.end())
print('区间:',search.span())
print('待匹配字符串:',search.string)
print('匹配数据:',search.group()) #输出匹配的内容,不会输出<re......>
"""
start: 2
end: 8
区间: (2, 8)
待匹配字符串: 123.3456 python 1.32
匹配数据: 3.3456
"""
findall=re.findall(pattern,s,flags=0)
print(findall) #['3.3456', '1.32']
sub=re.sub(pattern,'00000',s,flags=0)
print(sub) #1200000 python 00000
split=re.split(pattern,s,1,flags=0)
print(split) #['12', ' python 1.32']
``` 
##### 异常处理
```python
try :
    可能会异常的代码
except 异常类型A:
    异常处理代码(报错后执行的代码)
except 异常类型B:
    异常处理代码(报错后执行的代码)
e.g:
try:
    a=float(input('第一个数'))
    b=float(input('第二个数'))
    print(a/b)
except ZeroDivisionError:
    print('除数为零')
except ValueError:
    print('请输入整数')
except BaseException:
    print('未知异常')
————————————————————————————
try:
    可能异常的代码
except 异常类型:
    异常处理代码(报错后执行的代码)
else:
    没有异常要执行的代码
finally:
    无论是否产生异常都要执行的代码 #例:print('程序执行结束')
————————————————————————————
raise [Exception类型(异常描述信息)]
e.g:
try:
    gender=input('请输入您的性别')
    if gender!='男' and gender!='女':
        raise Exception('性别只能是男或女')
    else:
        print(gender)
except Exception as e:
    print(e)
—————————————————————————————
常见的异常类型
ZeroDivisionError 除数为零
IndexError 索引超出范围
KeyError 字典取值时key不存在
NameError 使用一个没有声明的变量
SyntaxError Python中的语法错误
ValueError 传入的值错误
AttributeError 属性或方法不存在的异常
TypeError 类型不合适
IndentationError 不正确的缩进
```
##### 函数
1. 定义
```python
def 函数名称(参数列表):
    函数体
    return 返回值列表 #可以没有
```
2. 传参
    1. 位置传参:位置个数均相等
    2. 关键字传参:在函数调用时对实参进行赋值,但在进行参数传递时要求名称必须与函数定义的形参名称相同
       def happy_birthday(name,age)
       happy_birthday(age=18,name='陈'),顺序可以不一样
    3. 既有位置传参又有关键字传参时,位置传参在前,关键字传参在后
    4. 形参中既有默认值参数又有位置参数，默认值参数放最后
3. 可变参数
    1. 个数可变的位置参数
        在参数前加一个*，函数调用时可接收任意个数的实际参数，并放到一个元组中
        ```python
        def fun(*para):
            print(type(para)) #<class 'tuple'>
            for item in para:
                print(item)
        fun(10,20,30,40)
        fun(*[10,20,30,40]) #在调用时，参数前加一颗星，可以将调用的列表解包
        ```

    2. 个数可变的关键字参数
        在参数前加两个*，在函数调用时可接收任意多个“参数=值”形式的参数，并放到一个字典中
        ```python
        def fun2(**para):
            print(type(para)) #<class 'dict'>
            for keys,items in para.items()
            print(keys,'::::',items)
        fun2(name='Jason',age=18,Idcard=20230510)
        """
        name :::: Jason
        age :::: 18
        Idcard :::: 20230510
        """
        d={'name':'Jason','age':18}
        fun2(**d) #不可以直接传一个字典，但可以用**将字典解包
        ```
4. return多个返回值
```python
def allsum(num):
    sum=0
    odd_sum=0
    even_sum=0
    for i in range(1,num+1):
        if i%2==0:
            even_sum+=i
        else:
            odd_sum+=i
        sum+=i
    return sum,odd_sum,even_sum
print(type(allsum(10))) #<class 'tuple'>
print(allsum(10)) #(55, 25, 30)
a,b,c=allsum(10) 
print(a,b,c) #55 25 30 解包赋值
```
5. 全局变量
    函数外部定义的变量或函数内部用global修饰的变量
    global全局变量的声明和赋值必须分开进行
6. 匿名函数
只能使用一次，一般在函数体只有一句或一个返回值时使用
```python
result=lambda 参数列表:表达式
e.g:
1.
s=lambda a,b: a+b
print(s(10,20))
2.
lst=[10,20,30,40]
for item in range(1,len(lst)+1):
    result=lambda a:lst[a-1]
    print(result(item)) #与for循环遍历一样
3.
grade=[{'name':'LiMing','score':95},{'name':'Jack','score':98},{''name':'Mike','score':87},{'name':'Jone','score':93}]
grade.sort(key=lambda x: x.get('score'))
print(grade) #[{'name': 'Mike', 'score': 87}, {'name': 'Jone', 'score': 93}, {'name': 'LiMing', 'score': 95}, {'name': 'Jack', 'score': 98}] 
```
7. 递归函数
```python
def fac(n):
    result=1
    if n>1: 
        return n*fac(n-1)
    else:
        return 1
print(fac(3))   
```
##### 迭代器函数
```python
lst=[12,34,57,32,78,37]
1.sorted(iter) #对可迭代对象进行排序
    sort_lst=sorted(lst) #[12, 32, 34, 37, 57, 78]
2.reversed(sequence) #反转序列生成新的迭代器对象
    reversed_lst=reversed(lst)
    print(type(reversed_lst)) #<class 'list_reverseiterator'>
    print(list(reversed_lst)) #[37, 78, 32, 57, 34, 12]
3.zip(iter1,iter2) #将iter1与iter2打包成元组并返回一个可迭代的zip对象
    e.g:[('a',10),('b',20),('c',30)]
4.enumerate(iter) #根据iter对象创建一个enumerate对象
    enum=enumerate(lst,start=1)
    print(type(enum)) #<class 'enumerate'>
    print(list(enum)) #[(1, 12), (2, 34), (3, 57), (4, 32), (5, 78), (6, 37)]
5.all(iter) #判断可迭代对象中所有的元素的bool值是否都为True
    print(all(lst)) #True
6.any(iter) #判断可迭代对象中所有的元素的bool值是否有一个为True
7.next(iter) #获取迭代器的下一个元素 
    reversed_lst=reversed(lst)
    print(next(reversed_lst)) #37
    print(next(reversed_lst)) #78
8.filter(function,iter) #通过指定条件过滤序列并返回一个迭代器对象
    def fun(num):
        return num%2==0
    lst1=filter(fun,lst)
    print(list(lst1)) #[12, 34, 32, 78]
9.map(function,iter) #通过函数function对可迭代对象操作返回一个迭代器对象
    lst2=['hello','hi','good']
    def fun(str):
        return str.upper()
    lst3=map(fun,lst2)
    print(list(lst3)) #['HELLO', 'HI', 'GOOD']
```






        
        

















