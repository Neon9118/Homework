# 第二章节：Git和GitHub

---

- [第二章节：Git和GitHub](#第二章节git和github)
  - [一、Repository](#一repository)
    - [1.1 工作区](#11-工作区)
    - [1.2 暂存区](#12-暂存区)
    - [1.3 本地仓库](#13-本地仓库)
  - [二、Commit](#二commit)
  - [三、Branch](#三branch)
    - [3.1 Creat](#31-creat)
    - [3.2 Merge](#32-merge)
  - [四、Remote](#四remote)
    - [4.1 代理](#41-代理)
    - [4.2 用SSH代替HTTPS](#42-用ssh代替https)


---


## 一、Repository

![](https://i.ibb.co/dsjkqgr9/gitcreat.png)
*初始化仓库*

### 1.1 工作区
![](https://i.ibb.co/5WxFXVLy/gongzuo.png)
*工作区*

>U=Untracked未追踪，说明文件改了但还没管它

<br/>

### 1.2 暂存区

![](https://i.ibb.co/5XQg9yvd/zancun.png)
*暂存区*

<br/>

### 1.3 本地仓库

![](https://i.ibb.co/zVtRQxJF/bendicangku.png)
>蓝色是指文件已经存到本地仓库中，紫色是指已经push到远程仓库
*本地仓库*

<br/>


---

## 二、Commit
![](https://i.ibb.co/qYbG1TmZ/gitcommit.png)
*commit*
>在提交时要简单描述，提交的标题不能是空

每次提交后会生成唯一的commit ID。可以通过`git log`命令获取

![](https://i.ibb.co/dwJCdH1y/gitlog.png)
*唯一的commit ID*
<br/>

---

## 三、Branch

### 3.1 Creat
因为模块的不确定性，担心加入后程序出错，可以创建新分支。待调试稳定后，合并分支加入程序。

![](https://i.ibb.co/mCrDHc5X/gitbranch.png)
*创建分支*

### 3.2 Merge

![](https://i.ibb.co/394VKpxS/gitmerge.png)
*合并分支*

---

## 四、Remote
>使用GitHub实现

### 4.1 代理
一开始我并没有设置ssh，而是用Microsoft Store 中的Watttoolkit 设置的代理，但一直push失败

![](https://i.ibb.co/ZRLYHgLW/ssh1.png)
*代理连接失败*

### 4.2 用SSH代替HTTPS

SSH（Secure Shell） = 安全远程连接协议
>用密钥代替密码，安全地连远程服务器。

- **生成ssh公钥**

![](https://i.ibb.co/jkMz53t9/remote1.png)
*ssh密钥*

<br/>

- **在GitHub里添加New SSH Key**

![](https://i.ibb.co/vvLjGLyg/remote2.png)
*创建远程连接*
<br/>

- **回VS Code 终端测试**
![alt text](https://i.ibb.co/QFvwC3gD/remote3.png)
*测试*

<br/>

- **push到远程仓库**
![](https://i.ibb.co/4qxdwdy/remote4.png)
*上传GitHub*


>SSH走22端口，这样就可以不经过代理，直接连GitHub
>以后日常操作就三步：`git add .`,`git commit -m "说明"`,`git push`
>全程不需要代理。