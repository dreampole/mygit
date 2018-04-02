1、安装(linux使用命令，win下载安装包)
sudo apt-get install git

2、设置
$ git config --global user.name "mh2000"
$ git config --global user.email "youremail@example.com"

3、建立git仓库文件夹
进入建立好准备作为git仓库的文件夹执行
git init
命令

4、把文件添加到仓库并提交
添加：git add readme.txt(添加整个目录： git add .)
提交：git commit -m "说明文字"

5、连接github
（1）、终端中创建SSH Key:ssh-keygen -t rsa -C "youremail@example.com"（linux）
       管理员身份打开git-bash.exe创建SSH Key:ssh-keygen -t rsa -C "youremail@example.com"（win）	
成功后可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人
（2）、登陆GitHub，打开“Account settings”，“SSH Keys”页面：“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。
（3）、在github上创建一个新的仓库： 通过“Create a new repo”按钮，创建一个新的仓库；在Repository name填入mygit，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库。
（4）、在本地的mygit仓库下运行命令把本地仓库与github的mygit关联，然后，把本地仓库的内容推送到GitHub仓库
关联：git remote add origin git@github.com:dreampole/mygit.git
首次提交：git push -u origin master
提交：git push origin master
（5）、克隆远程库到本地
git clone git@github.com:dreampole/mygit.git

6、连接gitee
（1）、在本地库上使用命令git remote add把它和码云的远程库关联：
git remote add origin git@gitee.com:dreampole/mygit.git
提示：git remote rm origin 说明本地库已经关联了一个远程库
（2）、查看远程库信息
git remote -v
（3）、修改已关联的远程库的标识名称
首先删除已关联的origin远程库：git remote rm origin
重新关联github远程库标识名修改为github ： git remote add github git@github.com:dreampole/mygit.git
再关联gitee远程库标识名为gitee ： git remote add gitee git@gitee.com:dreampole/mygit.git
再次运行git remote -v查看远程库信息，得到的结果是：
gitee	git@gitee.com:dreampole/mygit.git (fetch)
gitee	git@gitee.com:dreampole/mygit.git (push)
github	git@github.com:dreampole/mygit.git (fetch)
github	git@github.com:dreampole/mygit.git (push)
说明两个远程库都已经关联成功
（4）、提交
git push github master
git push gitee master
（5）、本地库同步远程库
git pull github master
git pull gitee master






