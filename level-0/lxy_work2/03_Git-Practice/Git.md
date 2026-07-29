# 第三部分：Git和GitHub

---


## 一、Repository

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/gitcreat.png)
*初始化仓库*

### 1.1 工作区
![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/gongzuo.png)

>U=Untracked未追踪，说明文件改了但还没管它

<br/>

### 1.2 暂存区

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/zancun.png)
<br/>

### 1.3 本地仓库

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/bendicangku.png)

>蓝色是指文件已经存到本地仓库中，紫色是指已经push到远程仓库

<br/>


## 二、Commit
![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/gitcommit.png)
>在提交时要简单描述，提交的标题不能是空

每次提交后会生成唯一的commit ID。可以通过`git log`命令获取

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/gitlog.png)
<br/>

## 三、Branch

### 3.1 Creat
因为模块的不确定性，担心加入后程序出错，可以创建新分支。待调试稳定后，合并分支加入程序。

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/gitbranch.png)

### 3.2 Merge

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/gitmerge.png)

---

## 四、Remote
>使用GitHub实现

### 4.1 代理
一开始我并没有设置ssh，而是用Microsoft Store 中的Watttoolkit 设置的代理，但一直push失败

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/ssh1.png)

### 4.2 用SSH代替HTTPS

SSH（Secure Shell） = 安全远程连接协议
>用密钥代替密码，安全地连远程服务器。

- **生成ssh公钥**

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/remote1.png)

<br/>

- **在GitHub里添加New SSH Key**

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/remote2.png)
<br/>

- **回VS Code 终端测试**
![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/remote3.png)

<br/>

- **push到远程仓库**
![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/04_picture/remote4.png)

>SSH走22端口，这样就可以不经过代理，直接连GitHub
>以后日常操作就三步：`git add .`,`git commit -m "说明"`,`git push`
>全程不需要代理。