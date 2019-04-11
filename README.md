# zingzing

##miniconda
#下载地址：https://docs.conda.io/en/latest/miniconda.html
#安装路径：C:\Users\Administrator\Miniconda3
#安装教程：https://mp.weixin.qq.com/s/yqyEknvYLIH5E0nMlWEDSQ?
#环境配置：PATH--C:\Users\Administrator\Miniconda3;C:\Users\Administrator\Miniconda3\Scripts;C:\Users\Administrator\Miniconda3\Library\bin
#添加conda的镜像服务器：
conda config --set show_channel_urls yes
#创建Python3.5的虚拟环境命名为course_py35：
conda create –n course_py35 python=3.5
#载入环境：
conda activate course_py35

#查看Python版本信息：python
#退出Python环境：
quit()或deactivate
#退出Python环境后用conda安装工具包：
conda install scipy
conda install pandas
#用pip安装工具包：
pip install scikit-learn
#进入环境后检查包安装是否成功
import scipy
import pandas
#退出环境后查列出软件包
conda list
#为了重复使用，把软件包信息导出
conda list --export
#找到合适的目录存储log
pip install appdirs


第一本书：Python数据科学实践指南

#Python的5个基本数据类型：none,int,float,bool,str
#对字符串a进行切片：a[1:-1:2]  从序列中位置为1 的值到倒数第一个值，以2为步长切片.切片为：a[start:end:step]
a='abcdefg'
a[1:-1:2]
#结果为：'bdf'
len(a)#确定字符串的长度

#获取键盘输入：
name=raw_input("who are you?")
print("hello"+name)

单行注释用#，多行注释用""" """
#寻找前n个质数
primes = [2] #第一个质数是2，先将2存储到质数列表primes里
i=1 #i代表一共找到了多少个质数，已经找到了质数2，所以i=1
num=3 #当前需要判断是否为质数的数字
n=10 #最多找到几个质数为止
while i < n: #通过穷举法寻找质数，判断质数的方法：当前的数字是否能被已经发现的质数整除。
    flag=1 #表示一个新的判断质数的循环开始
    for prime in primes: #把当前的num与之前找到的全部质数做取模运算
        if num % prime ==0:
            flag=0 #不是质数，中断循环
            break
    if num % prime == 1:
        primes.append(num) #将当前的质数存储到质数列表中
        i=i+1 #找到一个新的质数时自增1
    num=num+1 #每一次循环结束时自增1
    
print(primes) #打印全部结果

#定义一个计算绝对值的函数
def my_abs(num): #定义函数需要使用def关键字。my_abs即为函数的名字，括号中的num则是函数的参数
    if num <0:
        return -num
    return num
#定义一个计算最大值的函数*
    else:
    return b
#定义一个my_range函数
def my_range(start=None,stop=None,step=1):
    return range(start,stop,step)
myrange(1,10,step=2) #调用定义的函数
#定义可变数量参数的函数
def func(*args,**kwargs):#任意数量的位置参数会合并成一个元组并绑定到args，任意数量的关键字参数会合并成一个字典绑定到kwargs
    print(args, kwargs)
func(1,2,3,a=1,b=2)
def func1(x,y,z,a,b):
    print((x,y,z),{'a':a,'b':b})
元组***是由圆括号括起来的一组连续数据，如（1,2,3）。而字典是由很多组“键：值”组成的数据结构，如{‘a':1,'b':2}

#用递归的方法定义一个计算阶乘的函数
def fact(n):
    if n>1:
        return n*fact(n-1)
    else:
        return n #一般递归函数会在函数内部调用自身来实现递归式，不要忘记最后增加一个退出条件
#*递归*需要的两个部分：①1！=1②(n+1)!=(n+1)*n!.第一个*部分是递归的终止条件，第二个部分代表递归的方法

                                                     
#定义一个计算商的函数
def div(a,b):
    try:
        ret = a / b
    except ZeroDivisionError:
        print("除数不能为0")
    return ret

div(5,2)
div(1,0)

#try...except语法与if...else语法类似，如果try正确执行，就不会执行except语句。except后是需要处理的异常类型。有时候需要处理更多的异常类型
def div(a,b):
    try:
        ret=a/b
    except ZeroDvisionError:
        print("除数不能为0")
        ret=0
    except (ValueError, NameError):
        print("已知的异常")
        ret=1
    except:
        raise StandardError("未知的异常")
    finally: #funally是无论如何都会执行的语句
        print("done")
    return ret

div('a',1)
                                                     
                                                     
#高级字符串处理函数
# -*- coding: utf-8 -*- #告诉Python解释器，这个文件需要以utf-8的编码方式解码
ord("a")                                                   
chr(97)
内建的ord函数可以打印一个ASCII字符的ASCII编码；反之，chr可以将一个ASCII编码还原成ASCII字符
gbk_string.decode("utf-8")#打开文件乱码时可以尝试decode('GBK')将GBK编码的字符串转换成Unicode编码的字符串
字符串的基本操作：                                               
1.去除字符串前后的空白字符:strip()
如：' ascd\n'.strip()  
2.改变大小写：capitalize()使字符串首字母大写；lower()全部字符串小写；title()像一个英文标题一样格式化整个字符串，即将每个单词的首字母大写；upper()全部字母大写
'abcde'.capitalize()
'ABCDE'.lower()
'abcd efg'.title()
'abcde'.upper()
3.判断字符串特性：isalnum()字符串中包含字母或数字时给出T；isdigit()字符串中只包含数字时为T；startswith()、endswith()字符串以其参数为开始或结尾时返回T
'abcd123'.isalnum()
'abcde'.isdigit()
'abcde'starstwith('ab')
'abcde'endswith('d')
4.查找并替换：index()查找第一次出现的位置；replace()替换字符
'abcde'.index('cd')
'abcde'.replace('bc','fr')                                                     
5.字符串分割：split()从左侧以第一个参数为分隔符，第二个参数代表切到第几个分割符为止。rsplit()从右侧进行分割
'1,3,4,5,6,7'.split(',')
'1,2,3,4,5,6'.split(',',3)#以逗号为分割符，切到第三个分割符为止
6.字符串格式化：% 或format()
name='zingzing'
age=25
'{0} is {1} years old.'.format(name,age)
'%s is %d years old.' %(name, age) 
'{} is a girl.'.format(name)
'%s is a girl.'% name
'{0:.3} is a decimal.'.format(1/3.0)
'%.3f is a decimal.'% float(1/3.0)#%s使用字符串替换，%d使用整数替换，%f使用浮点数进行替换。“.3”则表示保留几位小数
'{first} is as {second}.'.format(first=name,second='zingzing')
'%s is as %s.'%(name,'zingzing')                                                     
     
正则表达式：从文本中提取出想要的模式的文本，或是判断文本是否符合某种规则，常用于数据清洗
.是一个元字符，代表任意字符  \.则可以只匹配点号，其中\是转义符，表示在后面的某个符号失去元字符的功能，或某个字母可以匹配更多字符
\d 匹配任何十进制数，相当于[0-9]
\D 匹配任何非数字字符，相当于[^0-9]
\s 匹配任何空白字符，相当于[\t\n\r\f\v]
\S 匹配任何非空白字符，相当于[^\t\n\r\f\v]
\w 匹配任何数字字母字符，相当于[a-zA-Z0-9_]
\W 匹配任何非字母数字字符，相当于[^a-zA-Z0-9_]
表示重复功能的元字符： 
*  表示匹配前面一个字符0到无穷多次，也叫贪婪匹配
+  表示匹配1次到无穷多次
?  表示匹配0次到1次
{} 表示前面的字符匹配几次，如：{8}表示前面的字符匹配8次，{4-8}表示前面的字符匹配4-8次。\d{8}匹配8位的数字
|  表示分歧条件的元字符，多个规则使用多个|分隔，任意一组正则表达式匹配上即可。如 "http://.*?"|"https://.*?"匹配以http://开头或以https://开头的网址
() 表示分组，如IP：192.168.0.1的正则表达式可以是：(\d{1-3}.){3}\d{1-3}   
^  表示从每一行的开始进行匹配
$  表示匹配到行尾。要匹配一整行数据可以使用：^.*$。也可以使用切割符对行进行切割，split("\n")
b  匹配单个单词。如匹配"world"这个单词可以使用\bworld\b，也可以用切割符对空格切分：split(" ")                                                     

案例： 
# ! /usr/bin/python
# -*- coding: utf-8 -*-
from __future__ import print_function
import re #导入re模块使用正则表达式

p=re.compile('"(https?://.*?)"',re.I)
with open('C:/Users/Administrator/Desktop/HackerNews.html','r',encoding = 'UTF-8') as fr:
    doc=fr.read()

for i in p.findall(doc):
    print(i) 
                                                     
re模块中常用的匹配字符串的方法：
match()  决定re是否在字符串刚开始的位置匹配
search() 扫描字符串，找到re匹配的位置
findall() 找到re匹配的所有子串，并把他们作为一个列表返回
finditer()  找到re匹配的所有子串，并把他们作为一个迭代器返回                                                     

import re
p=re.compile('[a-z]+')
m=p.match('tutorial')
m.group()#匹配到的字符串
m.start()#匹配到的字符串开始的位置
m.end()#匹配到的字符串结束的位置
m.span()#返回一个元组匹配到的字符串（开始，结束）的位置
  
容器和collections
集中基本的容器类型：元组（不可变），列表、字典、集合（可变）                                                   
1.元组：定义时使用（），分隔。对象可以是任意类型
t1=('a',1,True)
t2=('b',t1,2)=('b',('a',1,true),2) 
a,b,c=('a',t1,'c')    
                                                     
t2=('b',('a',1,True),2) 
for item in t2:
    print(item)
2.列表：定义时使用[]
l1=[1,'a',2]
l1[2]=True
l1.append('b')#在末尾追加字符，没有返回值，直接修改原表
l1.insert(0,'abc') #在列表中第一个参数为下标的位置插入第二个参数值，没有返回值，直接修改原表
l1.pop(0)#删除列表中参数为下标的位置的值，有返回值，返回值是被删除的值                                                     
print(l1+l2) :+是指将两个列表进行拼接
c=[]
c.extend(l1)
c.extend(l2)
print(c)#extend将一个列表中的每一个值都追加到另一个列表的尾部
print(la*3)  
python中的赋值都是传递引用，可以使用切片克隆的方式对列表进行“浅拷贝”,c=l1[:],
但是列表中嵌套的其他数据结构还是引用状态。为了保证所有数据都不变，可以使用deepcopy递归复制
from copy import deepcopy                                                     
c=deepcopy(l1)

列表的其他构造方式：
range(1:8)=[1,2,3,4,5,6,7]
[x*2 for x in range(1:8)]#列表解析式：将函数作用到整个列表中每一个元素上，并将结果构造成一个新的列表返回。如生成偶数数列
3.字典：通过{key:value}组成的无序结构
d={"a":1,"b":2}#直接定义字典
                                                     
d={}
for x in ["a","b","c"]:
    d[x]=1
print(d)#增量构建字典
                                                     
tuple_list=zip(["a","b","c","d"],[1]*4)#zip()函数可以将两个或多个列表按照对应项合并成元组的列表，需要注意长度不同时会按照短的进行截取
d=dict(tuple_list)
print(d)#使用dict函数构建字典

取值：d["a"]或d.get("a")#通过直接使用key来获取其中的值
for k in d:
    print(k,d[k])
for k,v in d.items():
    print(k,v)
d.keys()
d.values()
应用：将英文月份翻译为数字表达
monthNumbers={"Jan":1,"Feb":2,"Mar":3,"Apr":4,"May":5}
print("我的生日是在{May}月".format(**monthNumbers))                                                     
                                                     

编辑字典的键值对：
d["a"]=True #复制操作，如果key存在直接覆盖值，如果key不存在则创建一个新的key值
d.pop("a")#删除
d.update(d2)#合并两个字典。注意一旦有重复的key，结果字典中相应key值会被参数中的key值覆盖                                                     
                       
d={("name","age"):10,("sex","location"):20}    
                                                     
collections标准库：
1.namedtuple:具名元组：每个值都有名字的元组                                                     
from collections import namedtuple
nt=namedtuple('nt','name age loc')#第一个参数是元组的名字，它的一半要与赋值的变量一直；第二个参数是要定义的元组结构--对应的key值
ntl=nt('zingzing', '25', 'beijing')
ntl
ntl.name                                                     
2.Counter：累加器：可用作经典的word count
from collections import Counter
doc="i love u more than i can say. it's really really shocking. can u call me back?"
word_list=doc.split()#将原始的英文文本进行分词
cc=Counter(word_list)
cc
for k,v in cc.most_common():
    print(k,v)
3.defaultdict:为一个字典的值设定一个默认值                                                     
from collections import defaultdict
cl=defaultdict(list)
cl["key"]
cl["key"].append(1)
cl["key"].append(2)
cl["key"].append(3)
cl["key1"].append(4)
cl  
4.OrderedDict:保留数据被添加进字典的顺序
from collections import OrderedDict
d={}
cc=OrderedDict()
for x in ["b","a","d","c"]:
    cc[x]=1
    d[x]=1
    
for x in range(len(d)):
    print(d.keys()[x],cc.keys()[x])#第一列是普通字典，第二列是有序字典      
                                                     
                                                     
                                                     
标准库介绍：
1.math模块
①常量                                                     
import math
math.pi
math.e
print('pi:%.30f' % math.pi)    
②无穷
math.isinf()#判断值的大小是否超过python对无穷的定义
③整数转换
math.trunc():将浮点型小数点后面的数字全部截掉，只留下整数部分
math.floor():取比当前浮点型小的最近的整数
math.ceil():取比当前浮点型大的最近的整数
④绝对值
math.fabs()#计算浮点数的绝对值
         

