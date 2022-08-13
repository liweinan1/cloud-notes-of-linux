# git使用知识点

参考链接：[菜鸟教程](https://www.runoob.com/git/git-install-setup.html)

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

### 添加需要版本控制的文件

添加文件到暂存区。

```
git add xx.x
```

提交暂存区到本地仓库。

```
git commit -m "说明"
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

### 推送数据到远程仓库

以上命令将你的 [branch] 分支推送成为 [alias] 远程仓库上的 [branch] 分支。

```
git push [alias] [branch]
```

示例如下：

```
git add test.txt //添加文件到暂存区
git commit -m "添加到远程"
git push origin main    # 推送到 Github
```

