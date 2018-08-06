# day05

## 今日任务

1. 消化今天老师上课内容
2. 整理学习笔记\(x-mind\)
3. 完成每日作业
4. 登录博学谷-进行学习反馈
5. 和同桌讨论今天遇到的bug

# 学习目标

掌握列表的增删改查  
掌握元组的基本使用  
掌握字典的增删改查

## 今天作业

1.完成下列操作  
list = \[“xiaoming”,”xiaohua”,”xiaohong”\]  
\(1\)循环遍历出列表的所有元素  
\(2\)把列表list1\[“jack”,”marry”,”tom”\]中的每个元素逐一添加到list列表中  
\(3\)查看list列表是否有“xiaohua”这个元素  
\(4\)查看list列表的长度

2.将下列两个列表合并，将合并后的列表升序并输出.  
list1 = \[1,3,4,5,7\]  
list2 = \[0,66,8,9\]

3.使用字典来存储一个人的信息\(姓名、年龄\[数字\]、学号\)，  
这些信息来自键盘的输入，储存完输出至终端.

4.有下列字典dict1,查找值为“itcast”对应的key并输出到终端.\(结果应该是输出school\)

dict1={“school”:“itcast”,“date”:2017,”address”:“beijing”}

参考答案

```
#(1)
for i in list:
 print(i)
```

```py
#(2)方法一
list1 = ["jack", "marry", "tom"]
for i in list1:
    list.append(i)
# 方法二
list.extend(list1)
print(list)

# 方法三
# 自己尝试insert()
```

```py
#（3）
if "xiaohua" in list:
    print("在")
else:
    print("不在")
```

```py
# （4）
print(len(list))
```

```py
# 2 
list1 = [1, 3, 4, 5, 7]
list2 = [0, 66, 8, 9]
list1.extend(list2)
list1.sort(reverse=False)
print(list1)
```

```
# 3
a = {}
a["name"] = input("name:")
a["age"] = input("age:")
a["ID"] = input("ID:")
print(a)

```

1. ```py
   #4
   dict1 = {'school': 'itcast', 'date': 2017, 'address': 'beijing'}
   for i in dict1.keys():
    if dict1[i] == "itcast":
        print(i)
   ```



