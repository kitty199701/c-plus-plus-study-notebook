# linux常用操作

## 目录操作

1. 进入某个目录

   绝对路径：

   ```
   cd /usr/bin
   ```

   返回上一级目录：

   ```
   cd ..
   ```

   

2. 展示当前目录下的所有文件：

   ```
   ls
   ```

   把所有后缀为cc的文件列出来：

   ```
   ls *.cc
   ```

   不要分栏地列出所有文件（因为ls默认会分成两栏展示文件）

   ```
   ls -1
   ```

   

3. 



## 文件操作

1. 复制文件

   ```
   //复制到当前目录并换个名字
   copy xx.txt xxx.txt
   cp xx.txt xxx.txt
   //复制到当前目录的子目录
   cp xx.txt dir/xxx.txt
   //复制到绝对路径
   cp xx.txt /dir/xxx.txt
   ```

2. 移动文件

   ```
   Move xx.txt /home 
   mv xx.txt /home 
   ```

3. 删除文件

   ```
   
   ```

4. 重命名文件

   ```
   sudo apt install rename 
   rename 's/wifi/lifi/' *wifi-*.h 
   rename 's/wifi/lifi/' *wifi-*.cc 
   ```

   

5. 



## 安装卸载软件

1. 安装软件 - 安装deb包

   ```
   sudo dpkg -i xxx.deb
   ```

2. 卸载软件

   ```
   sudo dpkg -r xxx.deb
   ```

3. 直接从apt安装

   ```
   sudo apt install xxx
   ```

4. 对于下载的二进制文件

   ```
   # 添加执行权限
   chmod +x clash
   # 运行以初始化
   Clash ./clash
   ```

   

5. 

## 其他

1. 执行shell脚本

   ```
   bash update.sh
   ```

2. 在一个目录中的所有文本中搜索关键词

   ```
   grep -r "keyword" /home/repos/ 
   ```

   当指定要查找的是目录而非文件时，必须使用这项参数`--recursive (-r)`

   在当前目录下查找

   ```
   grep -r -i "keyword" ./
   ```

   在当前目录的某个子目录下查找 

   ```
   grep -r -i "keyword" ./examples 
   ```

   grep命令中的-w选项，以及其中正则表达式的\b, \< \>都可以全字区配（整字匹配）.那它们有什么区别呢？

   先要明确**“全字匹配”**的含义。“全字匹配”是指匹配的部分**两边**没有word constituent(字母、数字和下划线)，而不是要求匹配的部分全部由word constituent组成。

   -i, --ignore-case         ignore case distinctions in patterns and data忽略大小写
         --no-ignore-case      do not ignore case distinctions (default)默认是不忽略大小写的

   ```
   grep -r -w "Linked_Increases" ./
   ```

   

3. 

   