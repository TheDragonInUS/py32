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
* 能够说\_\__str\_\_\_的作用
* 能够说\_\__del\_\_\_的作用
* 能够说出继承的特点
* 掌握单继承的含义
* 掌握多继承的含义
* 掌握子类重写父类方法的方式
* 掌握子类调用父类方法的方法
* 掌握多层继承的含义
* 了解super\(\)的作用

## 今天作业

```py
#1 定一个人类，可以跑，跳，投，说话动作，有身高，体重，性别吗，属性，
class People(object):
    """
        人类
    """
    def __init__(self, height, high, gender):
        self.height = height
        self.high__ = high
        self.gender = gender

    def run(self):
        print("runing")

    def cast(self):
        print("casting")

    def speak(self):
        print("speaking")


liming = People(12, 21, 12)
print(liming.height)
```

```py
#2 在1题基础上，创建学生类，学生有分数，性别，学号，可以实现，打印学生类的显示“day day up”


class People(object):
    """
        人类
    """

    def __init__(self, height, high, gender):
        self.height = height
        self.high__ = high
        self.gender = gender

    def run(self):
        print("runing")

    def cast(self):
        print("casting")

    def speak(self):
        print("speaking")


class Student(People):
    def __init__(self, score_, number, height, high, gender):
        self.score_ = score_
        self.number = number

        # super().__init__(height, high, gender)
        # 或者使用
        People.__init__(self, height, high, gender)

    def __str__(self):
        return "day day up"


a = Student(3.6, 130803050, 140, 150, "男")
print(a.score_)
print(a.number)
print(a.height)
print(a.high__)
print(a.gender)
```

```py
#3 定义一个学生类，属性为姓名，性别，分数，定义一个save方法，可以保存把对象的属性保存到信息文件中，打印对对象的时候可以把学生的
#基本信息打印出来

class Student(object):

    def __init__(self, name__, score_, gender, file_path):
        self.name__ = name__
        self.score_ = score_
        self.gender = gender
        self.info_path = file_path

    def save(self):
        with open(self.info_path, 'w') as f:
            con = str(self.score_) + " " + str(self.name__) + " " + str(self.gender)
            f.write(con)
            print("ok")

    def __str__(self):
        with open(self.info_path, 'r') as f:
            con = f.read()
            return con


a = Student('1', 12, '男', "./info.txt")
a.save()
print(a)
```

```py
#4.将学生管理系统使用类实现

#  4.将学生管理系统使用类实现

"""
学生管理系统文件版v1.0
"""


class System(object):

    def __init__(self):
        self.a = {}  # 信息全局字典
        self.file_path = ''

    def stu_dict_(self):
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


    def stu_print(self):
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

    def stu_chose(self):
        """
        用户输入文件选项，执行相应操作
        :return:
        """
        chose = int(input("请输入选项:"))
        if chose == 1:

            #  添加学生信息
            f = self.stu_dict_()
            self.stu_add(f)

        elif chose == 2:

            #  删除学生信息
            self.stu_del()

        elif chose == 3:

            #  3:修改学生
            self.stu_modify()

        elif chose == 4:

            # 4: 查询学生
            self.stu_find()

        elif chose == 5:

            # 5:显示所有学生
            self.stu_show()

        elif chose == 6:

            # 6:保存数据
            self.stu_save(self.file_path)

        elif chose == 7:

            # 7 退出程序
            self.stu_exit()

    def stu_add(self, key_value):
        """
        将用户输入后返回的列表进行添加大字典中，全局字典
        :param key_value: 用户信息列表
        :return: 返回
        """
        self.a[key_value[0]] = key_value[1]

        return "ok"

    def stu_del(self):
        """
        删除信息
        :return:
        """
        key = input("who's info do you want to del? \n "
                    "please input name : ")
        self.a.pop(key)
        return "del %s success" % key

    def stu_modify(self):
        """
        修改信息
        :return:
        """
        key = input("who's info do you want to modify? \n "
                    "please input name : ")
        f = self.stu_dict_()
        self.a[key] = f[1]

        return "modify  %s success" % key

    def stu_find(self):
        """
        查询
        :return:
        """
        key = input("who's info do you want to search? \n "
                    "please input name : ")

        print(self.a[key])

        return "search  %s success" % key

    def stu_show(self):
        """
        显示所有学生
        :return:
        """
        print(self.a)

        return "show all  success"

    def stu_exit(self):
        """
        结束程序
        :return:
        """
        import sys
        sys.exit()

    def stu_save(self, file_path):
        """
        保存系统全局的学生信息
        :return:
        """
        with open(file_path, 'w') as f:
            f.write(str(self.a))

    def stu_load(self, file_path):
        """
        加载文件信息，返回文件内容
        :param file_path: 文件路径
        :return: 返回文件内容
        """
        with open(file_path, 'r') as f:
            file_cont = f.read()
            return file_cont

    def stu_co_p(self, file_cont):
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

    def file_exit(self, file_path):
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

    def stu_init(self, path):
        """
        进行系统的初始化
        :param path: 文件基本路径
        :return: 返回函数
        """
        # global file_path  # 声明去全局
        self.file_path = path  # 传参修改全局
        flag = self.file_exit(self.file_path)  # 判断文件是否存在
        if not flag:  # 不存在创建文件
            self.stu_save(self.file_path)
        file_con = self.stu_load(self.file_path)  # 存在的读取文件内容，
        a = self.stu_co_p(file_con)  # 还原给a全局信息字典

        print(a)  # 查看全局 a 信息字典，加载情况


if __name__ == '__main__':
    """
    1. 判断文件是否存在
       1- 文件 不存在  创建文件内容
       2- 文件 存在    加载文件内容
    2. 判断文件内容是否有有效
    """
    bb = System()
    bb.stu_init("./info.txt")
    while True:
        bb.stu_print()
        bb.stu_chose()
```

```py
#5. 发散思维自己设计一个类要求使用--str -- 函数 - del --，和多层继承


```



