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
#1

```

```py
#2
#编写函数:
#函数原型：def print_double(number):
#函数参数：number (整数)
#函数功能：打印从0到number之间所有的偶数[包含数字0和number]

def print_double(number):
    for i in range(0, number+1):
        if i % 2 == 0:
            print(i)


print_double(10)
```

```py
#3
#编写函数:
#函数原型：def mul(num_1,num_2):
#函数参数：num_1，num_2 (两个整数)
#函数返回值：两个数的乘积
#函数功能：计算两个数的乘积并作为返回值

def mul(num_1, num_2):
    a = num_1 * num_2
    return a

print(mul(3,4))
```

```py
#4
#编写函数：
#函数原型：def isNumber(num):
#函数参数：num (整数)
#函数返回值：bool类型变量
#函数功能：判断一个变量是否为整数，是整数返回True，

def isNumber(num):
    if type(num) == int:
        print("整型")
        return True
    else:
        return False

print(isNumber("ee"))
```

```py
#5
#编写函数：
#函数原型：def str_sum(char_num):
#函数参数：char_num (字符串类型的数字，例：”134567”)
#函数返回值：sum (整数)
#函数功能：计算字符串中的数字之和并作为返回值 例如：
#  “12345” 的和为15

def str_sum(char_num):
    sum = 0
    for i in char_num:
        sum += int(i)
    return sum
print(str_sum("123"))
```

```py
#6
#编写函数：
#函数原型：def lower_upper(li_str):
#函数参数：li_str (列表)
#函数返回值：无
#函数功能：将列表中的小写字母转换为大写字母，大写字母转换为小写字母.
#例如：[ ‘a’,‘B’，c’] 转换为 [ ‘A’ , ‘b’ , ‘C’]

# 方法一：
def lower_upper(li_str):
    for i in range(len(li_str)):
        flag = li_str[i].islower()

        if flag == True:
            li_str[i] = li_str[i].upper()
        else:
            li_str[i] = li_str[i].lower()
    return li_str

print(lower_upper(["a", "D"]))


#方法：二
# 大写字母 [65 ,90]
# 小写字母 [97 ,122]
# ord()返回字符ascii码值

def lower_upper(li_str):
    for i in range(len(li_str)):
        flag = ord(li_str[i])

         if 122 >= flag >= 97:
             li_str[i] = li_str[i].upper()
         else:
             li_str[i] = li_str[i].lower()
     return li_str

print(lower_upper(['a','D']))



# 第三种方法：
def lower_upper(a):
    b = []
    for i in range(len(a)):
        b.append(a[i-1].upper())
        b.append(a[i-1].lower())
    # print(b)
    for i in a:
        b.remove(i)
    print(b)

a = ['a', 'b', 'B']
lower_upper(a)



# 第四种方法：
def lower_upper(li_str):
    for i, val in enumerate(li_str):
        if "a" <= val <= "z":
            li_str[i] = li_str[i].upper()
        else:
            li_str[i] = li_str[i].lower()
    return li_str

print(lower_upper(['a','B']))
```

```py
#7
#编写函数：
#函数原型：def create_li(n):
#函数参数：n (空列表的个数，默认是5)
#函数返回值：包含n个空列表的大列表
#函数功能：创建一个列表，这个列表中有n个空列表(返回时二维列表，例：[ [ ],[ ],[ ],[ ],[ ] ] )
#例如：
#i = create_li()
#print( “列表li的长度为%d” % ( len( li ) ) )

def create_li(n=5):
    a = []
    for i in range(n):
        a.append([])
    return a

print(create_li())
```



