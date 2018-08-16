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


```

```py
#4.将学生管理系统使用类实现
```

```py
#5. 发散思维自己设计一个类要求使用--str -- 函数 - del --，和多层继承
```



