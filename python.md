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
12. format函数
```python
format(value,format_spec) #将value以format——spec格式显示
print(format(3.14,'20')) #                3.14默认右对齐
print(format('hello','20')) #hello            默认左对齐
print(format('hello','#>20')) ################hello
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
# 或者三目运算符
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
##### 类
1.创建
```python
class Student(): #创建一个类，首字母必须大写
    #类属性定义在类中，方法外的变量
    school='ChongQing University'

    #初始化方法 
    def __init__(self,name,age,id):#name和age是方法的参数，局部变量作用于是__init__方法
        self.name=name
        self.age=age
        self.id=id
    #定义在类中函数为方法，自带参数self
    def show(self):
        print(f'my name is {self.name},my age is{self.age},my id is {self.id}')
    #静态方法
    @staticmethod
    def sm(): 
        print('这是一个静态方法，不能调用实例属性和实例方法')
    @classmethod
    def cm(cls):
        print('这是一个类方法，不能调用实例属性和实例方法')
stu=Student('Jason',18,'20230510') #创建一个类的对象
stu1=Student
print(stu.school) #ChongQing University
print(stu.age) #18
stu.show() #my name is Jason,my age is18,my id is 20230510
Student.sm() #这是一个静态方法，不能调用实例属性和实例方法
stu.school='BeiJing U'
print(stu.school) #BeiJing U
print(Student.school) #ChongQing University
stu.age=19
print(stu.age) #19
```
2. 动态绑定
```python
1.动态绑定属性
stu2.gender='男' #独属于2的属性
print(stu2.gender)
print(stu1.gender)
2.动态绑定方法
def gohome():
    print('I want to go home')
stu2.wenthome=gohome
stu2.wenthome() #I want to go home
```
3. 封装
```python
class Student:
    #首位双下划线
    def __init__(self,name,age,gender):
        self._name=name #单下划线_name受保护的只能本类和子类访问
        self.__age=age #双下划线__age私有，只能类本身访问
        self.gender=gender
    def _fun1():
        print('受保护，只有类本身和子类去使用')
    def __fun2():
        print('私有，只有类本身可以使用')
    def fun(self):
        self._fun1()
        self.__fun2()
        print(self.__age)
stu=Student('LM',18,'M')
#也可以访问私有形式
print(stu._Student__age)
print(dir(Student)) #给出所有属性和方法如_Student__fun2
```
4. 继承
```python
class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def show(self):
        print(f'My name is {self.name}, I am {self.age} years old')
class Student(Person):
    def __init__(self, name, age,id):
        super().__init__(name, age) #继承Person中name和age的定义
        self.id=id
#多继承调用父类的属性方法
FatherA.__init__(self,name)
FatherB.__init__(self,age) #不用super().__init__了
#子类可以重写父类中的方法，可以通过super().xxx()调用父类中被重写的方法
print(stu) #直接输出对象名，调用__str__方法，返回对象的地址，也可以重写此方法
```
5. 特殊属性
```python
obj.__dict__ #返回对象的属性字典
obj.__class__ #返回对象所属的类
class.__bases__ #返回类的父类元组 
class.__base__ #返回类的父类
class.__mro__ #返回类的层次结构
class.__subclasses__() #返回类的子类列表
```
6. 类对象拷贝
```python
1.赋值‘=’
只是形成两个变量，实际上还是指向一个对象，一个内存地址
2.浅拷贝
import copy
obj2=copy.copy(obj)
对象会被拷贝但是子对象不会被拷贝，引用同一个子对象
3.深拷贝
obj3=copy.deepcopy(obj)
对象和子对象均被拷贝
```
##### 模块
1. 导入
```python
import my_info
print(my_info.name)
my_info.info() 需要my_info.info()
from my_info import name
print(name)
from my_info import *
print(name)
info() 可以直接调用info()
import math,time,random
导入多个模块时,如果有同名函数,后导入的会将前者覆盖
```
2. 包
```python
创建包会自动生成一个__init__.py文件
import admin.my_admin as a #import 包名.模块名
a.info()
第一种导入方式,当包被导入时,__init__文件会被自动调用执行
from admin import my_admin as b
b.info()
第二次导入时不执行__init__
from 包名.模块名 import 函数/变量/*
```
3. 主程序运行
```python
if __name__ =='__main__':
    print('good')
    print('job')
#别的文件调用此文件时,此内容不会被执行
```
##### random
```python
seed(x) #初始化给定的随机数种子,默认为系统当前的时间,如果随机数种子相同产生的随机数也相同
    e.g:random.seed(10)
random() #产生一个[0.0,1.0)之间的随即小数
    e.g:print(random.random())
randint(a,b) #产生一个[a,b]之间的整数
randrange(m,n,k) #生成一个[m,n)之间步长为k的随机整数
    e.g:random.randrange(1,10,3) #[1,10),1,4,7 
uniform(a,b) #生成一个[a,b]之间的随即小数
choice(seq) #从序列中随机选择一个元素
shuffle(seq) #将序列中元素随机排列 ,返回打乱后的序列
```
##### time模块
```python
time() #获取当前时间戳
localtime(sec) #获取指定时间戳对应的本地时间的strut_time对象
ctime() #获取当前时间戳对应的易读字符串
strftime() #格式化时间,结果为字符串
strptime() #提取字符串的时间,结果为struct_time对象
sleep(sec) #休眠sec秒

e.g:
import time
now=time.time()
print(now) #1709621211.91413
obj=time.localtime()
print(obj)
#time.struct_time(tm_year=2024, tm_mon=3, tm_mday=5, tm_hour=14, tm_min=49, tm_sec=12, tm_wday=1, tm_yday=65, tm_isdst=0)
print(obj.tm_wday) #从0开始,1表示星期二
print(time.localtime(100))
#time.struct_time(tm_year=1970, tm_mon=1, tm_mday=1, tm_hour=8, tm_min=1, tm_sec=40, tm_wday=3, tm_yday=1, tm_isdst=0)
print(time.ctime())
print(time.strftime('year:%Y_month:%m_date:%d',time.localtime())) #year:2024_month:03_date:05
print(time.strptime('2049-10-1','%Y-%m-%d'))
#time.struct_time(tm_year=2049, tm_mon=10, tm_mday=1, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=4, tm_yday=274, tm_isdst=-1)
time.sleep(5)
print('我暂停了5秒')
```
|格式化字符串|日期/时间|取值范围|
|---|---|---|
|%Y|年份|0001~9999|
|%m|月份|01~12|
|%B|月名|January~December|
|%d|日期|01~31|
|%A|星期|Monday~Sunday|
|%H|小时(24h)|00~23|
|%I|小时(12h)|01~12|
|%M|分钟|00~59|
|%S|秒|00~59|
##### datetime模块
```py
datetime.datatime #表示日期时间的类
datetime.timedelta #表示时间间隔的类
datetime.date #日期的类
datetime.time #时间的类
datetime.tzinfo #表示时区的类im

import datetime
now=datetime.datetime.now()
print(now) #2024-03-05 15:11:30.758472

#可以手动创建一个datetime对象
dt2=datetime.datetime(2049,10,1)
print(dt2) #2049-10-01 00:00:00

#直接取出时分秒等用dt2.year/month/day/hour/minute/second
print(dt2.year) #2049

#可以直接比大小,越早越小

#datetime类型与字符串进行转换 可以利用strftime和strptime方法
now=datetime.datetime.now()
strnow=now.strftime('%Y----%m----%d')  
print(strnow) #2024----03----05

#两个datetime对象相减会得到一个timedelta对象
delta1=datetime.datetime(2028,10,1)-datetime.datetime(2028,5,1)
print(delta1,type(delta1)) #153 days, 0:00:00 <class 'datetime.timedelta'> 

#创建一个timedelta对象
dalta2=datetime.timedelta(10,11)
print(dalta2) #两个参数,第一个是天数,第二个是秒数
```
##### 第三方模块的安装
1. win+R打开运行窗口
2. 输入cmd(输入notepad为记事本)
3. 安装
    1. 输入pip install 模块名称
    2. 或者输入
        pip install 模块名  -i
        https://pypi.douban.com/simple--trusted-host
        pypi.douban.com
4. 卸载 输入pip uninstall 模块名称
5. 升级pip命令的语句
    python -m pip install --upgrade pip

##### requests模块(爬虫)
1. 爬取文字
```python
import requests
import re
url='http://www.weather.com.cn/weather1d/101090101.shtml#input'
#爬虫打开浏览器上的网页
respond=requests.get(url) #打开浏览器并打开网址
respond.encoding='utf-8' #设置编码格式以显示中文
# print(respond.text) #respond响应对象，html页面
city=re.findall('<span class="name">([\u4e00-\u9fa5]*)</span>',respond.text)
weather=re.findall('<span class="weather">([\u4e00-\u9fa5]*)</span>',respond.text)
temperature=re.findall('<span class="wd">(.*)</span>',respond.text)
like=re.findall('<span class="zs">([\u4e00-\u9fa5]*)</span>',respond.text)
'''
<span class="name">三亚</span>
<span class="weather">多云</span>
<span class="wd">30/21℃</span>
<span class="zs">适宜</span>
'''
print(city) #['景区', '三亚', '九寨沟', '大理', '张家界', '桂林', '青岛']
print(weather) #['天气', '多云', '阴转小雨', '晴', '多云', '多云', '多云转阴']
print(temperature) #['气温', '30/21℃', '8/2℃', '22/8℃', '12/7℃', '17/10℃', '9/-1℃']
print(like) #['旅游指数', '适宜', '适宜', '适宜', '适宜', '适宜', '一般']
lst=[]
for a,b,c,d in zip(city,weather,temperature,like):
    lst.append([a,b,c,d])
print(lst)
#[['景区', '天气', '气温', '旅游指数']
#['三亚', '多云', '30/21℃', '适宜']
#['九寨沟', '阴转小雨', '8/2℃', '适宜']
#['大理', '晴', '22/8℃', '适宜']
#['张家界', '多云', '12/7℃', '适宜']
#['桂林', '多云', '17/10℃', '适宜']
#['青岛', '多云转阴', '9/-1℃', '一般']]


#终端中用CTRL+F可以查找内容
```
2. 爬取图片
```python
import requests
a='https://www.baidu.com/img/24lianghui_3fa64faa4dd8496d4ab2a1d411a93dad.gif'
respond=requests.get(a)
with open('baidu.png','wb') as file: #保存到本地
    file.write(respond.content)
```
 ![alt text](baidu.png)

 ##### openpyxl模块(处理excel文件)
 ```python
load_workbook(filename) #打开已存在的表格,结果为工作簿对象
creat_sheet(sheetname) #创建新的sheet
workbook.sheetnames #工作簿对象的sheetnames属性,用于获取所有工作表的名称,结果为列表类型
sheet.append(lst) #向工作表中添加一行数据,新数据接在工作表已有数据的后面
workbook.save(excelname) #保存工作簿
Workbook() #创建新的工作簿对象
```
1. 写入
```python
import weather
import openpyxl
str=weather.get_html() #发请求得响应结果
lst=weather.parse_html(str) #解析数据
workbook=openpyxl.Workbook() #创建一个新的excel工作簿
sheet=workbook.create_sheet('weather') #在excel文件中创建工作表
for item in lst:
    sheet.append(item) #向工作表中添加数据
workbook.save('python实现.xlsx')
```
2. 读取
```python
import openpyxl

#打开工作表
workbook=openpyxl.load_workbook('python实现.xlsx')
#选择要操作的工作表
sheet=workbook['weather']
#表格数据时二位列表
for hang in sheet.rows:
    for item in hang:
        print(item.value) #获取单元格内容
```
##### pdfplumber(PDF读取内容)----快速办公
```python
import pdfplumber
#打开PDF文件
with pdfplumber.open('复习.pdf') as pdf:
    for i in pdf.pages:
        print(i.extract_text()) #extract_text方法提取内容
        print('-'*40,f'第{i.page_number}页','-'*40) 
```
##### Numpy模块(可以进行图像处理)----数据分析

```python
import numpy as np
import matplotlib.pyplot as plt
#读取图片
n1=plt.imread('baidu.jpg')
print(type(n1),n1)#n1是三维数组,最高维是图像的高,次一维是图像的宽,最低维为图像的[R,G,B]颜色
plt.imshow(n1)

#灰度公式
n2=np.array([0.299,0.587,0.114,0])#创建数组
#将数组n1(RGB)颜色值与数组n2(灰度公式固定值),进行点乘运算
x=np.dot(n1,n2) 
plt.imshow(x,cmap='gray')
plt.show()
```
![alt text](.vscode/Figure_1.png)

##### Pandas(数据分析,读取excel)与Matplotlib(数据可视化,方便绘制折线图等)模块
##### PyEcharts模块(数据可视化图)
##### PIL（图像处理）
##### jieba模块（实现中文分词）
##### pyinstaller模块（将源代码打包）
##### 文件操作
```python
1.打开文件(创建)
变量名=open(filename,mode,encoding) #'w'或'r'
2.操作文件
变量名.read()
变量名.write(str)
3.关闭文件
变量名.close()
```
文件模式
|打开模式|操作说明|
|---|---|
|r|只读,文件指针在文件开头,若文件不存在则异常|
|rb|以只读模式打开二进制文件,如图片|
|w|覆盖写模式,文件不存在则创建,文件存在则覆盖|
|wb|覆盖写模式写入二进制数据,文件不存在则创建,文件存在则覆盖|
|a|追加写模式|
|+|w,r,a一同使用,同时读写|
```python
file.read(size) #从文件中读取size个字符或字节，如果没有指定参数，则读取全部内容
file.readline(size) #读取一行，如果给定参数，就读取size个字符
file.readlines() #从文件中读取所有内容，结果为列表类型
file.write(s) #将字符串s写入文件
file.writelines(lst) #将内容全部为字符串的列表lst写入文件
file.seek(offset) #改变当前文件操作指针的位置，零为起始位置
```
with语句(可以自动关闭已打开的文件)
```python
with open() as file:
    pass
```
##### json模块(处理高维数据)
```python
json.dumps(obj) #将python数据类型转换为json格式,编码过程
json.loads(s) #将json格式字符串转成python数据类型,解码过程
json.dump(obj,file) #与dumps()功能相同,将转换结果存储到文件file中
json.load(file) #与loads()功能相同,从文件file中读入数据
############################################################
import json
lst=[
    {'name':'LiBai','age':1000,'score':99},
    {'name':'DuFu','age':989,'score':98},
    {'name':'BaiJuYi','age':999,'score':94}
]
s=json.dumps(lst,ensure_ascii=False,indent=4) #ensure_ascii正常显示中文,indent增加数据的缩进,美观
print(s)

```
##### os模块
```python
import os
# os.getcwd() 当前工作路径
print('当前工作路径',os.getcwd()) #当前工作路径 E:\VScode\cpp
#os.listdir() 查找所有的文件及目录
print('当前路径下所有的目录及文件',os.listdir())
print('指定路径下的目录及文件',os.listdir('E:/vscode')) #['.vscode', 'cpp', 'Microsoft VS Code', 'note.txt']
#os.mkdir() 创建目录
os.mkdir('学习') #若创建的文件夹存在,会报错
#os.makedirs() 创建多级目录
os.makedirs('./aa/bb/cc')
#os.rmdir()只能删除空目录
os.rmdir('./aa/bb/cc') #./表示当前路径
os.removedirs('./aa/bb') #删除多级目录,只能是空目录
#改变工作路径,移到别的目录下
os.chdir('path')
#os.walk()遍历目录树
for dirs,dirlst,filelst in os.walk('e:/vscode'):
    print(dirs)
    print(dirlst)
    print(filelst)
    print('-'*40)
#删除文件
os.remove('./lll.txt')
#重命名
os.rename('./modela.py','./example.py')
#获取文件信息
info=os.stat('./aa.txt')
print(info) #可以用date内置函数将时间戳转换成时间
#启动路径下文件
os.startfile('calc.exe') #打开计算器
```
