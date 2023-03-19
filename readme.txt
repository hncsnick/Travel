virtualenv 创建虚拟环境
主要用于在一台电脑上需要安装不同版本的python虚拟环境来做项目, virtualenv就是用来为一个项目创建一套可以隔离的Python运行环境。

1
2
3
4
pip install virtualenv

# 或者使用 pip3
pip3 install virtualenv
创建过程
创建目录
Windows系统的话, 新建一个空的文件目录, linux的话 mkdir XXX_project

创建虚拟环境
在新创建的目录中, 进入CMD终端, 执行下面命令. linux 在命令行执行


1
2
3
4
5
6
7
8
9
10
11
# 创建完全与外部packages隔离的虚拟环境 myenv, python版本可能是最新的python3.7
virtualenv --no-site-packages myenv

# 如果新的python虚拟环境也需要原来python的第三方库，可以将第三方库一起复制到新的虚拟环境
virtualenv --system-site-packages myenv

# win 指定本地已有的python3.5版本(本地已有python2.7, python3.5, python3.7的解释器)
virtualenv -p C:\Users\Administrator\AppData\Local\Programs\Python\Python35\python.exe myenv

# linux
virtualenv -p /usr/bin/python3.5 myenv
　　3.激活虚拟环境　

　　在新创建的目录中, 进入CMD终端命令, 执行下面命令, 只需要记住, 在win系统下, 激活就是还行 Scripts 下面activate 的脚本, 关闭就是执行 deactivate.bat 的脚本就OK了
1
2
3
4
5
# windows
myenv\Scripts\activate

# linux
source myenv/bin/activate
　　4.关闭虚拟环境　　

1
2
3
4
5
# Windows (记不住单词没关系 按Tab键是可以自动补全的)
myenv\Scripts\deactivate.bat

# linux
deactivate
　　5.删除虚拟环境

1
2
3
4
5
# windows
简单粗暴, 直接删除创建时生成的 myenv 的目录就好了

# linux
rm -r myenv

python manage.py db init
python manage.py db migrate
python manage.py db upgrade
python manage.py runserver