# linux-

grep -C 5 'false' catalina.out 显示文件里匹配false那行以及上下5行
grep -B 5 'false' catalina.out 显示false及前5行
grep -A 5 'false' catalina.out 显示false及后5行

 Linux里如何查找文件内容

Linux查找文件内容的常用命令方法。  

从文件内容查找匹配指定字符串的行：

$ grep "被查找的字符串" 文件名
例子：在当前目录里第一级文件夹中寻找包含指定字符串的.in文件
grep "thermcontact" */*.in

从文件内容查找与正则表达式匹配的行：
$ grep –e “正则表达式” 文件名

查找时不区分大小写：
$ grep –i "被查找的字符串" 文件名

查找匹配的行数：
$ grep -c "被查找的字符串" 文件名


从文件内容查找不匹配指定字符串的行：
$ grep –v "被查找的字符串" 文件名


从根目录开始查找所有扩展名为.log的文本文件，并找出包含”ERROR”的行
find / -type f -name "*.log" | xargs grep "ERROR"
例子：从当前目录开始查找所有扩展名为.in的文本文件，并找出包含”thermcontact”的行
find . -name "*.in" | xargs grep "thermcontact"
