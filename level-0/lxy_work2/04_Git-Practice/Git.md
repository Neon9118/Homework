# 第三部分：Git和GitHub

---


## 一、Repository

![](https://i.ibb.co/dsjkqgr9/gitcreat.png)
*初始化仓库*

### 1.1 工作区
![](https://i.ibb.co/5WxFXVLy/gongzuo.png)

>U=Untracked未追踪，说明文件改了但还没管它

<br/>

### 1.2 暂存区

![](https://i.ibb.co/5XQg9yvd/zancun.png)

<br/>

### 1.3 本地仓库

![](https://i.ibb.co/zVtRQxJF/bendicangku.png)
>蓝色是指文件已经存到本地仓库中，紫色是指已经push到远程仓库

<br/>


## 二、Commit
![](https://i.ibb.co/qYbG1TmZ/gitcommit.png)
>在提交时要简单描述，提交的标题不能是空

每次提交后会生成唯一的commit ID。可以通过`git log`命令获取

![](https://i.ibb.co/dwJCdH1y/gitlog.png)
<br/>

## 三、Branch

### 3.1 Creat
因为模块的不确定性，担心加入后程序出错，可以创建新分支。待调试稳定后，合并分支加入程序。

![](https://i.ibb.co/mCrDHc5X/gitbranch.png)

### 3.2 Merge

![](https://i.ibb.co/394VKpxS/gitmerge.png)
---

## 四、Remote
>使用GitHub实现

### 4.1 代理
一开始我并没有设置ssh，而是用Microsoft Store 中的Watttoolkit 设置的代理，但一直push失败

![](https://i.ibb.co/ZRLYHgLW/ssh1.png)

### 4.2 用SSH代替HTTPS

SSH（Secure Shell） = 安全远程连接协议
>用密钥代替密码，安全地连远程服务器。

- **生成ssh公钥**

![](https://i.ibb.co/jkMz53t9/remote1.png)

<br/>

- **在GitHub里添加New SSH Key**

![](https://i.ibb.co/vvLjGLyg/remote2.png)
<br/>

- **回VS Code 终端测试**
![alt text](https://i.ibb.co/QFvwC3gD/remote3.png)

<br/>

- **push到远程仓库**
![](https://i.ibb.co/4qxdwdy/remote4.png)


>SSH走22端口，这样就可以不经过代理，直接连GitHub
>以后日常操作就三步：`git add .`,`git commit -m "说明"`,`git push`
>全程不需要代理。