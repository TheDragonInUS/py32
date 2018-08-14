# day08

## 今日任务

1. 消化今天老师上课内容
2. 整理学习笔记\(x-mind\)
3. 完成每日作业
4. 登录博学谷-进行学习反馈
5. 和同桌讨论今天遇到的bug

# 学习目标

能够说出引用的含义  
能够说出匿名函数的定义方式  
能够说出列表推导式作用  
能够说出文件的打开和关闭函数  
能够说出文件读写数据操作  
能够说出文件拷贝的操作  
能够说出文件夹的重命名、新建、文件列表、切换目录、当前目录路径、删除的操作  
能够说出批量修改文件名的操作

## 今天作业

```py
#1 什么是引用？
#python 中的值传递一种方式，引用就是 容器 -- 物品之间  -- 对应关系（可以类比c的指针）
```

```py
#2 定义一个递归函数，做一个1-100之间地偶数和？

def ou_shu(start):

    if start > 2:
        start = start + ou_shu(start-2)

    else:
        start = 2

    return start

print(ou_shu(100))
```

```py
#3 定义一个匿名函数，产生1-100偶数和？
a = lambda x: x+a(x-2) if x> 2 else 2
```

```py
#4 使用列表推导式，产生一个1- 100 包含1- 100 之间的偶数列表？
a = [i for i in range(0, 100, 2)]
print(a)
```

```py
#5 定义一个函数，函数创建一个文件并写入“hello world” , 一定另外一个函数， 函数读取文件“hello world” 并打印出来
def hello_write():
    with open("1.txt", 'w')as f:
        f.write("hello")


def hello_read():
    with open("1.txt", 'r')as f:
        a = f.read()
        print(a)

if __name__ == '__main__':
    hello_write()
    hello_read()
```

```py
#6 根据5的例子进行改变，用户输入年龄，性别，家庭住址，通过函数把信息存到文件中，并显示“报错成功”（将你们同桌所有个人的信息）
# 录入文件
def cun_chu():
    a = {}
    a['name'] = input("name:")
    a['age'] = input("age:")
    a['gender'] = input("gender:")
    a['addr'] = input("addr:")
    
    with open("2.txt", 'w')as f:
        f.write(str(a))
cun_chu()
```



