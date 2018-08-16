# day09

## 今日任务

1. 消化今天老师上课内容
2. 整理学习笔记\(x-mind\)
3. 完成每日作业
4. 登录博学谷-进行学习反馈
5. 和同桌讨论今天遇到的bug

# 学习目标

* 掌握文件读写数据操作
* 掌握文件拷贝的操作
* 掌握文件夹的重命名、新建、文件列表、切换目录、当前目录路径、删除的操作
* 掌握批量修改文件名的操作
* 掌握学生管理系统实现数据保存的操作
* 掌握类和对象的关系
* 掌握类的定义
* 掌握给对象添加对象属性和获取对象属性

## 今天作业

```py
#1创造一个文件book.txt 使用循环写入100行‘hello world’，然后进行文件备份，要求使用函数实现，函数有返回值“ok”。
def han_t(f):
    """
    循环写入文件
    :param f: 文件对象
    :return: 返回ok状态
    """
    for i in range(1, 101):
        f.write("%d hello world\n" % i)
    return "ok"


def copy_file(file_path, copy_file_path):
    """
     复制文件路径
     :param file_path: 原文件路径
     :param copy_file_path: 复制文件路径
     :return: 信息"copy is over"
     """
    with open(file_path, 'r') as fa:
        with open(copy_file_path, 'a')as fb:
            while True:
                fa_con = fa.readline()
                if fa_con == '':
                    print("copy is over")
                    return "copy is over"
                fb.write(fa_con)


if __name__ == '__main__':
    with open('./book.txt', 'w') as f:
        han_t(f)
    copy_file('./book.txt', './book_copy.txt')
```

```py
#2，将函数改良，添加额外功能，要求可以在桌面my_code文件夹文件中创建100个.txt文件，并在每个文件中写入100行“hello world”
# 创建完成后将文件的名字和路径，保存在My_code文件夹下的hello.txt文件中.

import os

def han_t(f):
    """
    循环写入文件
    :param f: 文件对象
    :return: 返回ok状态
    """
    for i in range(1, 101):
        f.write("%d hello world\n" % i)
    return "ok"


os.chdir("/Users/python/Desktop/")
if 'my_code' not in os.listdir():
    os.mkdir('my_code')
os.chdir("/Users/python/Desktop/my_code") #  这个路径改成你自己的路径
for i in range(0, 100):
    file_name = str(i) + ".txt"
    with open(file_name, 'w') as f:
        han_t(f)
        with open("hello.txt", 'a') as f_h:
            con = file_name + ' ' + os.getcwd() + '\n'
            f_h.write(con)


print(os.listdir())
```

```py
#3. 删除文件夹my_code中的文件，并将删除动作记录在hello.log文件中


import os


def tiqu_shu(f):
    con = f.readline()
    print(con)
    if con == '':
        print("over")
        return 'over'
    con = con.split("\n")
    con = con[0]
    return con


def rm_han(file_path):
    os.remove(file_path)
    import time
    time_w = time.ctime()
    info = "已经删除" + file_path + ' ' + time_w + '\n'
    return info


def log_han(info):
    with open("./hello.log", 'a') as f:
        f.write(info)
    return "ok"


if __name__ == '__main__':
    with open("/Users/python/Desktop/my_code/hello.txt", 'r') as f:
        while True:
            con = tiqu_shu(f)
            if con == 'over':
                break
            info = rm_han(con)
            log_han(info)
```

```py
#4.完成学生管理系统，文件写入
"""
学生管理系统文件版v1.0
"""

a = {}  # 信息全局字典
file_path = ''


def stu_dict_():
    """
    用户输入name,age,qq，返回列表[name, {"name":name, "age":age, "qq__": qq}]
    :return:
    """
    dic_a = {}
    name = input("name:")
    age_ = input(" age:")
    qq__ = input(" qq :")

    dic_a["name"] = name
    dic_a["age_"] = age_
    dic_a["qq__"] = qq__
    f = []
    f.insert(0, name)
    f.insert(1, dic_a)
    return f


def stu_print():
    """
    文件管理系统选项
    :return:
    """
    print("---------------------------")
    print("      学生管理系统 V1.0")
    print(" 1:添加学生")
    print(" 2:删除学生")
    print(" 3:修改学生")
    print(" 4:查询学生")
    print(" 5:显示所有学生")
    print(" 6:保存数据")
    print(" 7:退出系统")
    print("---------------------------")


def stu_chose():
    """
    用户输入文件选项，执行相应操作
    :return:
    """
    chose = int(input("请输入选项:"))
    if chose == 1:

        #  添加学生信息
        f = stu_dict_()
        stu_add(f)

    elif chose == 2:

        #  删除学生信息
        stu_del()

    elif chose == 3:

        #  3:修改学生
        stu_modify()

    elif chose == 4:

        # 4: 查询学生
        stu_find()

    elif chose == 5:

        # 5:显示所有学生
        stu_show()

    elif chose == 6:

        # 6:保存数据
        stu_save(file_path)

    elif chose == 7:

        # 7 退出程序
        stu_exit()


def stu_add(key_value):
    """
    将用户输入后返回的列表进行添加大字典中，全局字典
    :param key_value: 用户信息列表
    :return: 返回
    """
    a[key_value[0]] = key_value[1]

    return "ok"


def stu_del():
    """
    删除信息
    :return:
    """
    key = input("who's info do you want to del? \n "
                "please input name : ")
    a.pop(key)
    return "del %s success" % key


def stu_modify():
    """
    修改信息
    :return:
    """
    key = input("who's info do you want to modify? \n "
                "please input name : ")
    f = stu_dict_()
    a[key] = f[1]

    return "modify  %s success" % key


def stu_find():
    """
    查询
    :return:
    """
    key = input("who's info do you want to search? \n "
                "please input name : ")

    print(a[key])

    return "search  %s success" % key


def stu_show():
    """
    显示所有学生
    :return:
    """
    print(a)

    return "show all  success"


def stu_exit():
    """
    结束程序
    :return:
    """
    import sys
    sys.exit()


def stu_save(file_path):
    """
    保存系统全局的学生信息
    :return:
    """
    with open(file_path, 'w') as f:
        f.write(str(a))


def stu_load(file_path):
    """
    加载文件信息，返回文件内容
    :param file_path: 文件路径
    :return: 返回文件内容
    """
    with open(file_path, 'r') as f:
        file_cont = f.read()
        return file_cont


def stu_co_p(file_cont):
    """
    验证文件内容是否正确，还原给a全局
    :param file_cont: 文件内容
    :return: a 全局信息字典
    """
    if file_cont == '':
        print("文件内容为空")
        return
    a = eval(file_cont)
    return a


def file_exit(file_path):
    """
    判断文件是不是存在
    :param file_path:
    :return:
    """
    import os
    flag = os.path.exists(file_path)
    if flag:
        print("文件已经存在")
        return flag
    print("文件需要创建")
    return flag


def stu_init(path):
    """
    进行系统的初始化
    :param path: 文件基本路径
    :return: 返回函数
    """
    global file_path  # 声明去全局
    file_path = path  # 传参修改全局
    flag = file_exit(file_path)  # 判断文件是否存在
    if not flag:  # 不存在创建文件
        stu_save(file_path)
    file_con = stu_load(file_path)  # 存在的读取文件内容，
    a = stu_co_p(file_con)  # 还原给a全局信息字典

    print(a)  # 查看全局 a 信息字典，加载情况


if __name__ == '__main__':
    """
    1. 判断文件是否存在
       1- 文件 不存在  创建文件内容
       2- 文件 存在    加载文件内容
    2. 判断文件内容是否有有效
    """

    stu_init("./info.txt")
    while True:
        stu_print()
        stu_chose()
```

```py
#5.定义一个类，智能手机类，要求有打电话功能，短信功能，视频功能，定义后，创建一个实例对象，添加颜色属性，尺寸。

class Phone(object):

    def call(self):
        print("this is call ")

    def send_message(self):
        print("this is send_message ")

    def video(self):
        print("this is video ")


iphone = Phone()
iphone.call()
iphone.send_message()
iphone.video()

iphone.col = "red"
iphone.size = 5.5

print(iphone.col)
print(iphone.size)
```

第四题程序总览![](/assets/学生管理系统.png)

