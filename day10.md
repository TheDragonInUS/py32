# day10

## 今日任务

1. 消化今天老师上课内容
2. 整理学习笔记\(x-mind\)
3. 完成每日作业
4. 登录博学谷-进行学习反馈
5. 和同桌讨论今天遇到的bug

# 学习目标

* 掌握对象添加对象属性和获取对象属性
* 了解出init的作用
* 掌握有参数的init的作用
* 能够说\_\__str\_\__的作用
* 能够说\_\__del\_\__的作用
* 能够说出继承的特点
* 掌握单继承的含义
* 掌握多继承的含义
* 掌握子类重写父类方法的方式
* 掌握子类调用父类方法的方法
* 掌握多层继承的含义
* 了解super\(\)的作用

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
略
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



