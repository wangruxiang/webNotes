git小乌龟（Tortoisegit）使用教程
==============================
### 下载[git](https://git-scm.com/downloads)之后一定要下载TortoiseGit:[git小乌龟](https://tortoisegit.org/download/)
1. Tortoisegit安装（傻瓜式安装）
    - git安装/git小乌龟安装/中文语言包安装可参考：[Tortoisegit安装](https://www.cnblogs.com/xuanwotianming153/p/8504762.html)  
2. 上述安装完成后，Tortoisegit设置成中文
    - 右键→tortogit→setting，把language项改为中文，点击确定就可以了；如下图所示：
    ![language1](img\language1.jpg)  
    ![language2](img\language2.jpg) 
3. 然后就是一些基本操作了呢：  
    - 本地新建一个文件夹，名字可以随便命名  
    ![gitPic1](img\git1.webp)
    - 点击进入文件夹内，然后右键创建版本库  
    ![gitPic2](img\git2.webp)
    - 不勾选，直接确定  
    ![gitPic3](img\git3.webp)
    - 右键选择设置  
    ![gitPic4](img\git4.webp)
    - 填入你注册的时候用的用户名和邮箱  
    ![gitPic5](img\git5.webp)
    - 点击右侧的远端  
    ![gitPic6](img\git6.webp)
    - 将github上面的那串复制的地址写入url以及推送url里面，先点击添加/保存，跳出的框不用做任何修改，直接确定  
    ![gitPic7](img\git7.webp)  
    ![gitPic8](img\git8.webp)
    - 点击确定以后会弹出一个框，让你进行身份认证，你只需要将你之前注册的用户名密码重新输入一遍，然后小乌龟就开始抛投了，抛投完成以后，显示成功之后，点击关闭即可，现在，你的本地仓库就已经建好了  
    ![gitPic9](img\git9.webp)  
4. 可以通过拉取获得项目最新的成果。**<u>如果是多人协作的话，最好先拉取再提交</u>**
    - ![gitPic10](img\git10.webp)
5. 以后有什么需要更新的，只需要**先提交**，**再同步**即可，需要注意的是，<u>提交只是提交到本地版本库，并非提交到远程版本服务器，所以，你要想在远程版本服务器上看到你最新的修改，你还需要同步</u>
    - ![gitPic11](img\git11.webp)
6. 同步点击推送即可，一定要先提交再同步
    - ![gitPic12](img\git12.webp)






