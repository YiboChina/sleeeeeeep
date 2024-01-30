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
   