# Linux

## 1. Linux概述-CentOS 7
#### 创建
### touch 创建新的空文件
> touch f1.txt
### mkdir 创建目录
- 在当前目录中建立bin和bin下的os_1目录，权限设置为文件主可读、写、执行，同组用户可读和执行，其他用户无权访问
> mkdir -p-m 750 bin/os_1
#### 查看
### cat 连接文件并打印到标准输出设备上 
> cat f1.txt 输出 f1.txt 的内容到终端
-
> cat f1.txt f2.txt 输出 f1.txt f2.txt 的内容到终端 
-
> cat f1.txt f2.txt > f3.txt  输出 f1.txt f2.txt 的内容f3.txt 
-
> cat > f3.txt 在终端中直接写一个新文件/重写并输出到 f3.txt 回车 加 crtl+d 退出
-
> cat m1 m2 > file （将文件m1和m2合并后放入文件file中）
-
    -n或--number：从1开始对所有输出的行数编号；
    -b或--number-nonblank：和-n相似，只不过对于空白行不编号；
    -s或--squeeze-blank：当遇到有连续两行以上的空白行，就代换为一行的空白行；
    -A：显示不可打印字符，行尾显示“$”；
    -e：等价于"-vE"选项；
    -t：等价于"-vT"选项；
### more 显示文件内容，每次显示一屏
- 显示文件file的内容，但在显示之前先清屏，并且在屏幕的最下方显示完核的百分比。
> more -dc file
- 显示文件file的内容，每10行显示一次，而且在显示之前先清屏。
> more -c -10 file
-
    说明：该命令显示文本文件的内容，一次显示一屏，满屏后停下来，可按如下键继续。
    （1）Space键 ：默认显示文本的下一屏内容。
    （2）Enter键：默认显示文本的下一行内容。
    （3）d键或CTRL+D：向下显示文本半屏，默认为11行。
    （4）b键或CTRL+B：默认显示文本的上一屏内容。
    （5）q or Q or INTERRUPT键：退出more命令。
- 
    -num：指定一个整数，表示一屏显示多少行。
    -d：在每屏底部显示提示信息，包括当前显示的百分比，按键提示等。
    -c或 –p：不滚屏，在显示下一屏之前先清屏。
    +num：从行号num开始显示。
    +/pattern：定义一字符串，在文件中查找该字符串，从该字符串后开始显示。
### less 分屏上下翻页浏览文件内容,允许用户向前或向后浏览文件
### head 显示指定文件的开头若干行，默认显示头10行
> head -v -20 f1.txt 将f1.txt的文件名和前20行输出到终端
### tail 在屏幕上显示指定文件的末尾若干行
> tail file #（显示文件file的最后10行）
-
> tail -n +20 file #（显示文件file的内容，从第20行至文件末尾）
-
> tail -c 10 file #（显示文件file的最后10个字符）
-
> tail -25 mail.log # 显示 mail.log 最后的 25 行
-
> tail -f mail.log # 等同于--follow=descriptor，根据文件描述符进行追踪，当文件改名或被删除，追踪停止
-
> tail -F mail.log # 等同于--follow=name  --retry，根据文件名进行追踪，并保持重试，即该文件被删除或改名后，如果再次创建相同的文件名，会继续追踪
### pwd 显示当前工作目录
#### 删除 p 上一级 r 下几级 i inform
### rmdir 用来删除空目录 
    -p或--parents：删除指定目录后，若该目录的上层目录已变成空目录，则将其一并删除；
- 下面命令等价于 rmdir a/b/c, rmdir a/b, rmdir a
> rmdir -p a/b/c
### rm 删除给定的文件和目录
- 删除当前目录下除隐含文件外的所有文件和子目录 -f 表示强制删除即不提示
> rm -rf *
### mv 对文件或目录重新命名，或者将文件从一个目录移到另一个目录中。
- 将目录/usr/men中的所有文件移到当前目录（用.表示）中：
> mv /usr/men/* .

- 移动多个文件
> mv file_2.txt file_3.txt file_4.txt /home/office/

- 移动目录
> mv directory_1/ /home/office/

- 重命名文件或目录
> mv file_1.txt file_2.txt # 将文件file_1.txt改名为file_2.txt

- 重命名目录
> mv directory_1/ directory_2/

- 打印移动信息
> mv -v *.txt /home/office

- 提示是否覆盖文件
> mv -i file_1.txt /home/office

- 源文件比目标文件新时才执行更新
> mv -uv *.txt /home/office

- 不要覆盖任何已存在的文件
> mv -vn *.txt /home/office

- 复制时创建备份
> mv -bv *.txt /home/office

- 无条件覆盖已经存在的文件
> mv -f *.txt /home/office
### cp change path 将源文件或目录复制到目标文件或目录中
> cp 源文件 目标文件
- 源文件：制定源文件列表。默认情况下，cp命令不能复制目录，如果要复制目录，则必须使用-R选项；
- 目标文件：指定目标文件。当“源文件”为多个文件时，要求“目标文件”为指定的目录。
#### 
### chmod change mode 变更文件或目录的权限

| 2进制 | 8进制 
| :-: | :-: |
| 000|1|
| 001|2|
| 010|3|
| 011|4|
| 100|5|
| 101|6|
| 110|7|
    u符号代表当前用户。
    g符号代表和当前用户在同一个组的用户，以下简称组用户。
    o符号代表其他用户。
    a符号代表所有用户。
    r符号代表读权限以及八进制数4。
    w符号代表写权限以及八进制数2。
    x符号代表执行权限以及八进制数1。顾文件夹
    X符号代表如果目标文件是可执行文件或目录，可给其设置可执行权限。
    s符号代表设置权限suid和sgid，使用权限组合u+s设定文件的用户的ID位，g+s设置组用户ID位。
    t符号代表只有目录或文件的所有者才可以删除目录下的文件。
    +符号代表添加目标用户相应的权限。
    -符号代表删除目标用户相应的权限。
    =符号代表添加目标用户相应的权限，删除未提到的权限。

- 添加组用户的写权限。
> chmod g+w ./test.log

- 删除其他用户的所有权限。
> chmod o= ./test.log

- 使得所有用户都没有写权限。
> chmod a-w ./test.log

- 当前用户具有所有权限，组用户有读写权限，其他用户只有读权限。
> chmod u=rwx, g=rw, o=r ./test.log

- 等价的八进制数表示：
> chmod 754 ./test.log

- 将目录以及目录下的文件都设置为所有用户拥有读写权限。
- 注意，使用'-R'选项一定要保留当前用户的执行和读取权限，否则会报错！
> chmod -R a=rw ./testdir/
### tar 
    tar格式（该格式仅仅打包，不压缩）
    打包：tar -cvf [目标文件名].tar [原文件名/目录名]
    解包：tar -xvf [原文件名].tar
    注：c参数代表create（创建），x参数代表extract（解包），v参数代表verbose（详细信息），f参数代表filename（文件名），所以f后必须接文件名。

    tar.gz格式
    方式一：利用前面已经打包好的tar文件，直接用压缩命令。

    压缩：gzip [原文件名].tar
    解压：gunzip [原文件名].tar.gz

    方式二：一次性打包并压缩、解压并解包

    打包并压缩： tar -zcvf [目标文件名].tar.gz [原文件名/目录名]
    解压并解包： tar -zxvf [原文件名].tar.gz
    注：z代表用gzip算法来压缩/解压。

    tar.bz2格式
    方式一：利用已经打包好的tar文件，直接执行压缩命令：

    压缩：bzip2 [原文件名].tar
    解压：bunzip2 [原文件名].tar.bz2
    方式二：一次性打包并压缩、解压并解包

    打包并压缩： tar -jcvf [目标文件名].tar.bz2 [原文件名/目录名]
    解压并解包： tar -jxvf [原文件名].tar.bz2
    注：小写j代表用bzip2算法来压缩/解压。

## 2. 文件操作命令详解

## 3. 用户与组管理

## 4. 破解 root 密码

## 5. VMware 虚拟机及 CentOS 7

## 6. 高级权限
### UMASK
### SUID / SGID => Set User ID /Set Group ID
### STICK
### ACL
## 7. RPM 软件包及 YUM 软件仓库的使用技巧
## 8. Crontab 定时任务
## 9. FS Management 
## 10. swap 交换分区的管理
## 11. LVM 逻辑卷分区
## 12. 网络环境配置 
## 13. 压缩与解压缩命令的使用技巧
## 14. autos 自动挂载
## 15 使用问题
> 在window下使用 ssh 出现 WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! 
>>解决办法 => ssh-keygen -R 服务器端的ip地址