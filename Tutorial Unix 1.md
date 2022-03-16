Tutorial Unix 1
======

### 1.Getting help, using the man pages.

```
man man
man pwd
```

- f 向前翻页
- b 向后翻页


### 2.Simple file system commands
> You can find out your current working directory 
```
pwd
```
> change directory command
```
cd
```
> You can make a new directory by using the mkdir command along with a name for the new directory.
```
mkdir xxx (directory name)
```

> Exercise 1. Having done the above steps what is your current working directory ?
- Solution: pwd

### 3.Path types
> An absolute path
> A relative path
```
"." for the current working directory.
".." for the parent directory of a directory.
"~" for the current users home directory.
```

### 4.Listing the files in a directory
> To list the files in the current working directory type
```
ls
``` 

> The ls command can list the files in directories other than the current working directory. 打开文件or文件夹
```
ls /usr (file name)
```

### 5.Removing directories
> To remove a file or directory and its contents use the rm command with the -r option. 没有-r没法删除文件夹
```
rm -r xxx
```

### 6.Creating empty test files
> To create one or more empty files you can use the touch command. 
```
touch f1 f2 f3
```

### 7.Copying and moving files
> To copy one or more files to a directory use the cp command. 
```
cp f1 f2 sub2/
cp f1 f2 sub2/
cp f1 f2 /home/sub2/
```
> To move (or rename) a file or directory use the mv command. 
```
mv f1 new1
```
### 8.Shortcuts to save typing
> 用↑pageup↓pagedown来循环浏览命令历史记录To cycle through the command history use the up arrow key <br>
> tab key ↹ 来补全

### 9.File name globbing 通配符
>  *，?，[ and ]  are meta-characters because they have meaning above the normal set of characters.
```
*   matches all normal file names.
f*   matches all file names starting with "f".
get123*   matches file names starting with "get123".
*txt   matches all normal file names ending in "txt".
f?   matches all normal files with two character names starting in "f".
f??get*txt   matches all files names starting with "f" followed by any two characters followed by "get" followed by any number of characters followed by "txt".
```
```
[1-3]*   matches all file names starting with "1","2" or "3" followed by zero or more characters.
[2-4][a-c]   matches all file names starting with "2" "3" or "4" followed by "a", "b" or "c".
*[A-Z]   matches file names ending in an upper case character.
[0-9]*txt*   matches file names starting with a digit and containing "txt".
f[0-9][0-9]?   matches all files with four character names starting in "f" followed by two digits.
[1-3]*[4-5]   matches all file names starting with "1", "2" or "3" and ending in "4" or "5".

```
### 10.Seeing the files matching a file name glob
> To see the files matched by a file name glob use the echo command. For example
>> echo命令是我们常用的一个命令,它的主要作用功能是在屏幕上显示文字,也可以直接在文件中写入要写的内容,具体如下
```
Exercise 8. Create the following empty files: "g1", "g2", "g3", "g4", "g5", "f1", "f2", "f3" in the directory "~/usp1/q8/sub". <br>
From this directory copy all the files starting with "g" to the parent of the parent directory "~/usp1q8/q8a/q8b/sub".

Solution

The following steps are one way of achieving the required result.
First, create the required directories .
mkdir ~/usp1q8
mkdir ~/usp1q8/q8a/
mkdir ~/usp1q8/q8a/q8b/
mkdir ~/usp1q8/q8a/q8b/sub
Next, cd to the required directory and create the required files.
cd ~/usp1q8/q8a/q8b/sub
touch g1 g2 g3 g4 g5 f1 f2 f3

Confirm you have created the files.
ls

Do the copy.
cp g* ../../

Finally, confirm it worked.
ls ../../
```




