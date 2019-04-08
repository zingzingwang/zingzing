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


###第一本书：Python数据科学实践指南

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

