# learngit
## 如何把本地项目上传到Github  
- 第一步：在github上新建一个仓库，命名learngit。
- 第二步：复制仓库https地址。
- 第三步：使用git工具建立本地仓库，连接github远程仓库。
  1. 新建learngit文件夹，里面添加几个文件。右击learngit文件夹根目录，点击“Git Bash Here”，打开git命令行;
  2. 在命令行中，输入“git init”，使learngit文件夹加入git管理；
  3. 输入“git add .”（不要漏了“.”），将learngit文件夹全部内容添加到git；
  4. 输入“git commit -m "first commit"”（“git commit -m "提交信息"”
）；
  5. 输入“git remote add origin https://github.com/wtchen77/learngit.git”（git remote add origin 你自己的https地址），连接你的github仓库；
  6. 输入“git push -u origin master”，上传项目到Github。这里会要求输入Github的账号密码，按要求输入就可以。由于新建的远程仓库是空的，所以要加上-u这个参数，等远程仓库里面有了内容之后，下次再从本地库上传内容的时候只需下面这样就可以了：$ git push origin master  

注意：这里有个坑需要注意一下，就是在上面创建远程仓库的时候，如果你勾选了Initialize this repository with a README（创建仓库的时候自动创建一个README文件），那么你将本地仓库内容推送到远程仓库的时候就会报错，failed to push some refs to 'https://github.com/wtchen77/learngit.git' ，这是由于新创建的那个仓库里面的README文件不在本地仓库目录中，这时我们可以通过以下命令先将内容合并一下：$ git pull --rebase origin master  

## github上的版本和本地版本冲突的解决方法
1. 使用强制push的方法：
$ git push -u origin master -f
这样会使远程修改丢失，一般是不可取的，尤其是多人协作开发的时候。
2. push前先将远程repository修改pull下来
$ git pull origin master
$ git push -u origin master
3. 若不想merge远程和本地修改，可以先创建新的分支：
$ git branch [name]
然后push
$ git push -u origin [name]
