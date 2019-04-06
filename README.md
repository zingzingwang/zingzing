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
