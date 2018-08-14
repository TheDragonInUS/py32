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
#1创造一个文件book.txt 使用循环写入100行‘媳妇我错了’，然后进行文件备份，要求使用函数实现，函数有返回值“ok”。
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
os.chdir("/Users/python/Desktop/my_code")
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
```

```py
#4.完成学生管理系统，文件写入
```

```py
#5.定义一个类，智能手机类，要求有打电话功能，短信功能，视频功能，定义后，创建一个实例对象，添加颜色属性，尺寸。
```



