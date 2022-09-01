# Git操作

## 下载并安装Git

https://git-scm.com/downloads

## 配置SSH密钥

### 检查本地计算机是否已经存在SSH key

1. 在你创建一个新的ssh key之前，先检查你的本地电脑是否已经存在一个ssh key了，在Git Bash中输入`ls -al ~/.ssh`看看是否有已经存在的ssh key



### 创建ssh key

1. 在Git Bash中输入下面的文本（替换为您的 GitHub 电子邮件地址），这将以提供的电子邮件地址为标签创建新 SSH 密钥。

```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. 提示您“Enter a file in which to save the key”时，按 Enter 键。 这将接受默认文件位置。
2. 在提示Enter passphrase (empty for no passphrase)时不输入密码，则不对SSH密钥再加密（保证你的本地计算机是安全的情况下）



### 将新的SSH密钥添加到github账户中


1. 复制你的SSH公钥

2. 在任何页面的右上角，单击您的个人资料照片，然后单击 Settings（设置）。

3. 在边栏的“Access（访问）”部分中，单击  SSH 和 GPG 密钥。

4. 点击New SSH key

5. 将复制的SSH公钥粘贴到Key字段中，点击 Add SSH key即可



### 测试SSH连接

1. 在Git Bash中输入以下内容测试SSH连接

   ```shell
   $ ssh -T git@github.com
   # Attempts to ssh to GitHub
   ```

2. 您可能会看到类似如下的警告：

   ```shell
   > The authenticity of host 'github.com (IP ADDRESS)' can't be established.
   > RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
   > Are you sure you want to continue connecting (yes/no)?
   ```

3. 验证所看到消息中的指纹是否匹配 GitHub 的公钥指纹。 如果是，则输入 yes

   以下是 GitHub 的公钥指纹：

   - `SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8` (RSA)
   - `SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM` (ECDSA)
   - `SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU` (Ed25519)

4. 验证生成的消息包含您的用户名。连接成功。

   ```shell
   > Hi username! You've successfully authenticated, but GitHub does not provide shell access.
   ```



## 利用Git在本地连接远程仓库

在你想建立repository的位置打开Git Bash Here，输入以下文本

```shell
git clone git@github.com:your_username/your_repository.git
```

![image-20220821232509944](C:\Users\54690\AppData\Roaming\Typora\typora-user-images\image-20220821232509944.png)



## 利用Git将本地端文件更新至远程端

创建一个sh脚本"update.sh"，通过记事本打开编辑，写入以下文本。每次更新时双击运行即可。当然自己在Git Bash中输入以下文本来更新，会更加灵活。

```sh
git add . //添加文件夹中所有文件
git commit -m "备注信息"  //备注本次修改了什么
git push //推送到远程端
```



## 分支操作

> 创建、重命名、查看、删除项目分支，通过 `Git` 做项目开发时，一般都是在开发分支中进行，开发完成后合并分支到主干。

1. 创建新分支
```
git branch daily/0.0.0
```
创建一个名为 `daily/0.0.0` 的日常开发分支，分支名只要不包括特殊字符即可

2. 查看当前项目分支列表
```
git branch
```


3. 删除分支
```
git branch -d daily/0.0.1
```

4. 重命名分支
```
git branch -m daily/0.0.0 daily/0.0.1
```

5. 切换到另一分支上工作
```
git checkout daily/0.0.1
```