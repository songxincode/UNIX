Tutorial Unix 2
=====


### Linux#!/bin/bash 脚本
这只是因为在我们常用的linux系统上默认都是执行/bin/bash来执行我们的shell脚本，<br>
但是如果有些用户使用的是csh，那么缺少第一行的“#！/bin/bash的shell脚本执行结果就可能存在语法不兼容的问题，<br>
导致结果异常或者根本不能执行。<br>
<br>
shell是一种解释性语言，他需要专门的解析器来解析然后执行，不同的脚本语言需要匹配对应的解析器才能解析执行<br>
我们linux上的shell 是bash shell，所以我们在编写一个脚本的时候需要在第一行添加”#！/bin/bash“. 这句话的意思是告诉执行器需要调用/bin/bash来执行我。


### 【Linux基础】linux下的stdin,stdout和stderr理解
https://www.cnblogs.com/badboy200800/p/11121880.html
* 使用“ 2> ”符号，将标准错误输出重定向到文件中。形式为：命令 2> 文件名

### Basic file permissions
> Exercise 1. Create the empty files "f1 f2 f3 g1 g2 g3 g4 g5" in the ~/usp2 directory. 
> View the permission settings for the files you created.

```
mkdir ~/usp2
cd ~/usp2
touch f1 f2 f3 g1 g2 g3 g4 g5
ls -l
```
```
To change the permissions of a file or files use the chmod command. There two ways to express the permissions, firstly, symbolic and secondly, numeric. We will first use the symbolic method. Using this method the characters "u,g,o,a" have the following meanings:
"u" stands for the user who owns the file.
"g" stands for the other members of the owners group.
"o" stands for all other users.
"a" stands for all users.
The permissions can be one of:
"r" read permission
"w" write permission
"x" execute permission
The characters "+,-,=" have the following meanings:
"+" adds the permission specified
"-" removes the permission specified
"=" adds the permission specified and removes any not specified
To show how all of this fits together we give some examples. In each case chmod acts on the file named "filename".
chmod u+x filename   adds execute permission for the owner of the file.
chmod u-x filename   removes execute permission for the owner of the file .
chmod u=x filename   adds execute permission and removes read and write permissions for the owner of the file.
chmod g+rx filename   adds read and execute permission for the owners group members.
chmod g-rx filename   removes read and execute permission for the owners group members.
chmod o+rx filename   adds read and execute permission for other users of the file.
chmod a+rxw filename   adds read, write and execute permission for all users of the file.
chmod a+w filename   adds write permission for all users of the file.
```
