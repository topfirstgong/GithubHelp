# 在Visual Studio Code中搭建Git环境
<br></br>
## 1、设置全局变量
在本地创建一个文件夹，进入文件夹后，鼠标右键打开` Git Bush Here `  
接下来会打开Git，在命令行中输入以下文本：  
` git config --global user.name "your name"  `  
` git config --global user.email "your@email.com" `
<br></br>
## 2、登陆GitHub，创建SSHkey
在命令行中输入` ssh-keygen -t rsa -C "your@email.com" `
然后连续3次按Enter，完成以上操作后，会在本地用户目录下生成` .ssh `
文件夹，里面包含` id_rsa `和` id_rsa.pub `两个文件。然后使用编辑器打
开` id_rsa.pub `，复制文件中的所用内容
<br></br>
回到Github，点击用户头像，打开Settings。在选项卡中选择` SSH and GPG keys `，然后
点击` New SSH key `，将之前所复制的所用内容粘贴至文本框中，点击` And SSH key `
<br></br>
返回Git，在命令行中输入` ssh -T git@github.com `，最后在命令行中输入` yes `，经过以上步骤，我们便完成了本地和GitHub的通信配置
<br></br>
## 3、克隆仓库
在仓库中点击` Code `，在` HTTPS `选项卡中复制仓库的HTTPS地址。返回Git，在命令行中输入` git clone "Your Repository HTTPS" `  
(警告：在实际操作过程中，必须将命令中的引号去掉！)
<br></br>
## 在Visual Studio Code中提交文件
使用Visual Studio Code打开克隆到本地的仓库，然后创建一个名为` Test.md `的Markdown文件，在文件中输入` ## Picture :
[The picture](https://images.pexels.com/photos/417054/pexels-photo-417054.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1) `  
保存文件，然后在Visual Studio Code中点击` 源代码管理 `，再点击上方的提交，也就是上方的` ✔ `，在弹出来的对话框中输入` Test.md `  
按Enter，便可完成提交

<br></br>

<br></br>

本文所参考的教程：  
[GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)  
[知乎](https://zhuanlan.zhihu.com/p/31417255#:~:text=%E5%9C%A8VScode%E4%B8%8A%E9%85%8D%E7%BD%AEGit%201%20%E3%80%81%E8%AE%BE%E7%BD%AE%E5%85%A8%E5%B1%80%E5%8F%98%E9%87%8F%202,%E3%80%81%E7%99%BB%E9%99%86GitHub%EF%BC%8C%E5%88%9B%E5%BB%BASSHkey..%20...%203%20%E3%80%81%E5%85%8B%E9%9A%86%E4%BB%93%E5%BA%93)
