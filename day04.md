# day04

## 今日任务

1. 消化今天老师上课内容
2. 整理学习笔记\(x-mind\)
3. 完成每日作业
4. 登录博学谷-进行学习反馈
5. 和同桌讨论今天遇到的bug

# 学习目标

掌握字符串的基本操作

## 今天作业

1. 现有字符串： str1 = '1234567890'，根据题目要求完成以下题目：

（1）截取字符串的第一位到第三位的字符

（2）截取字符串最后三位的字符

（3）截取字符串的全部字符

2.将下列字符串中所有的数字相加，相加完毕的结果输出至终端.  
   str = “10@20@30@4@6”

3.输出字符串str1中所有的偶数.

str1 = “1234567890”

## 参考答案

1.

```py
str1 = '1234567890'
print(str1[0:2])

print(str1[7:])
print(str1[-3:])

print(str1[:])
print(str1[0:10])
print(str1)
```

2.

```py
#方法一：
a = str1.split("@")
print(a)
sum1 = 0
for i in a:
    sum1 += int(i)
print(sum1)

#方法二：
a = int(str1[0:2])
b = int(str1[3:5])
c = int(str1[6:8])
d = int(str1[9:10])
e = int(str1[11:12])
print(a + b + c + d + e)
```

3.

```py

str1 = '1234567890'
for i in str1:
	i = int(i)
	if i % 2 == 0 and i != 0:
		print(i)
```

4.



```py
list = ['xiaoming', 'xiaohua', 'xiaohong']
for i in list:
	print(i)


list = ['xiaoming', 'xiaohua', 'xiaohong']
list1 = ['jack', 'marry', 'tom']
for i in list1:
	list.append(i)
print(list)

if 'xiaohua' in ['xiaoming', 'xiaohua', 'xiaohong']:
	print("yes")
else:
	print("no")
#


print(len(['xiaoming', 'xiaohua', 'xiaohong']))
```



