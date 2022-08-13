# git使用知识点

参考链接：[菜鸟教程](https://www.runoob.com/git/git-install-setup.html)

在git中，本地文件称为工作区，在本地还有暂存区和本地库。add用于将本地文件加入暂存区，以便于对文件的改动进行追踪。commit用于将暂存区中的文件与记录加入到本地库，push用于将本地库同步到远程库。

根据上述说明，有以下规则：

- 若要删除远程库的文件，前提是本地库与远程库已经建立了文件上的连接，然后删除本地库中的文件，再同步到远程库即可删除。
- 删除本地库中的文件，缓存区的记录也会被删除，**也不能再监控后续变化**。
- 每次修改文件过后，应该先使用add加入到缓存区，再使用commit加入到本地库，再使用push加入到远程库
- 

## 信息配置与查看

### 用户信息配置

```
git config --global user.name "user" //用户名
git config --global user.email xx@xx.com //用户邮箱
```

### 配置信息查看

```
git config --list //可以查看所有信息，包括用户名等
```

## git的使用

### 从本地创建仓库

打开本子文件夹后，可以在其下创建一个仓库。

```
git init
```

也可以在git bash中直接指定文件夹。

```
gti init newrepository
```

### 添加文件到暂存区

添加文件到暂存区，以进行版本控制。

```
git add xx.x
```

### 清除暂存区文件

如果要从缓存区中删除，则使用以下操作，需要注意：**缓存区中的文件是可以删除的，且不会影响本地库已经commit的文件**。

```
//删除某文件
git rm --cached <filename>
//删除文件夹
git rm --cached -r <directory>
//清空缓存区
git rm -r --cached 
```

如果需要查看暂存区。

```
git ls-files
```

### 添加文件到本地库

```
git commit -m "说明"
```

### 删除本地与暂存区文件

如果要删除本地的文件，可以使用下面的命令，需要注意，**本地的文件会被删除！**

```
git rm <filename>
```

### 推送到github

以下命令可以将你的 [branch] 分支推送成为 [alias] 远程仓库上的 [branch] 分支。需要注意：commit是"记录对暂存区的更改"，是将本地修改过的文件提交到暂存区中；而push是"更新远程引用和相关对象"，是将暂存区中的最新信息发送给远程库。

```
git push [alias] [branch]
```

示例如下：

```
git add test.txt //添加文件到暂存区
git commit -m "添加到本地库"
git push origin main  //推送到 Github
```

### 创建密匙

```
cd ~/.ssh //挂载目录
ls //查看密匙是否存在
ssh-keygen -t rsa -C "xxx@xxx.com" //生成密匙
cat id_rsa.pub //获取密匙
```

### 从github拷贝项目

可以不指定目录。

```
git clone <repo> <directory>
```
