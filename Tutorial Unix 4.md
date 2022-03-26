Tutorial Unix 4: Regular expressions and grep
===============

### Question 1:
* 1. grep regular expressions
* 2. grep -E 用于显示文件中符合条件的字符 Extend 
* 3. grep -P Perl regular expresson engine
* 4. cat error.txt | grep "or"
* 5. \bthe\b
> grep -E ' the|the ' error.txt 空格

````
[user@sahara ~]$ grep -E 'the|the' error.txt 
String the as world hello your answer is correct
the world i can do now it and wo shi ni de
thearte a moive mean player ARE PERFORED
i wanthe to a world 
i wanthea to world
[user@sahara ~]$ grep -E ' the|the ' error.txt 
String the as world hello your answer is correct
the world i can do now it and wo shi ni de
i wanthe to a world 
```
