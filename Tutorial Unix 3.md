Tutorial Unix 3
=====

### 1.Redirection 重定向
> typically utilizing the Standard Output (STDOUT) file descriptor. 
> Error messages, are also printed on the screen by default but by utilizing the Standard Error (STERR) file descriptor. 

```
ls file1 file2 > dut.txt 2>&1
错误和正确都在一个文件

ls file1 file2 2> error.txt 1>filelist.txt
错误error.txt 正确 filelist.txt
```

### 2.piping
> 可以使用管道符号“|”。前面的例子可以用|符号更正如下：
* 这次我们可以从第1行开始读取文件。
* 提示：使用箭头上下滚动或使用空格键滚动整页。要退出，请使用CTRL+C。
```
cat numout.txt | less
可以上下
也可以b和f，前后一页
```
```
less < numout.txt

```
### 3.Using a cut command
```
Cut的-d选项表示公共列分隔符，-f选项表示列号：

cat file1 | cut -d : -f 2
root:x:0:0:Super-User:/:/sbin/sh
daemon:x:1:1::/:
bin:x:2:2::/usr/bin:

以:为分隔符，2表示第二列
```
* prnt number 加上行数
```
[user@sahara ~]$ cat file1 | cut -d : -f 1 | nl
     1root
     2daemon
     3bin
```

* 不用cat的方法
```
[user@sahara ~]$ cut -d : -f 1 file1 | nl
     1root
     2daemon
     3bin
```
* 如果要输出，> userlist

### 4.Programming language AWK
> AWK 是一种处理文本文件的语言,是一个强大的文本分析工具。
```
[user@sahara ~]$ cat who | awk '{print $1 $6}'
hjoseph(john-q-public)
saxinst(dhcp-13-094)
lubos(103.44.70.201)
```

加上format，格式输出
```
[user@sahara ~]$ cat who | awk '{ print "User "$1" is logged from "$6}'
User hjoseph is logged from (john-q-public)
User saxinst is logged from (dhcp-13-094)
User lubos is logged from (103.44.70.201)
```



### 5.Bash quotes, quotations and escape characters

> "\" 转义 
```
charlie$ date=14062009
charlie$ echo $date
14062009
charlie$ echo \$date
$date
```
> Single Quotes
```
单引号会保留其文字的值，加上转义符escape character就会消除特殊含义
```

> Double Quotes

```
1 charlie$ echo "$date"
2 14062009
3 charlie$ echo "\$date"
4 $date
5 charlie$ echo "\ $date"
6 \ 14062009
7 charlie$ echo "it's \"easy\""
8 it's "easy"
9 charlie$ echo "`date`"
10 Sun Jun 14 08:36:37 EST 2009

我们仍然可以使用日期变量（第2行）。
当“\”后跟“$”符号（第3行）时，它将保留其特殊含义（第4行）。
反斜杠后跟空格或任何其他缺乏特殊含义的字符（第5行）将产生文字反斜杠字符（第6行）。
双引号中间的一个引号（第7行）将由shell逐字读取（第8行）。
双引号（第9行）之间的反勾（`）将导致命令外壳展开，并执行日期命令（第10行）。
```

### 6.Arithmetic Expansion算术展开
> $(( expression ))
```
1 charlie$ echo $(( 5 - 2 ))
2 3
3 charlie$ echo “$date”
4 14062009
5 charlie$ echo $(( $date - 2 ))
6 14062007
7 charlie$ echo $((( $date - 2 ) * 3))
8 42186021
```






