# usegit
使用git管理上传代码
# 下载git 初始化
+ 下载目录`https://git-scm.com/`
+ 桌面右键`Git Bash Here`
+ `ssh-keygen -t rsa` 生成秘钥 （生成的文件在用户的.shh文件内复制id——rsa.pub文件到github上）
+ `git config --global user.name {name}`  
+ `git config --global user.email {email}`
# 上传步骤  

+ `git branch` 查看当前分支
+ `git switch {main}` 切换分支
+ ### 创建一个想要上传的文件，在文件夹内右键鼠标点击`Git Bash Here`
+ `git init` 管理即将新建的源代码
+ `git add .` 把当前文件夹内所有的文件和非空文件，设置为准备提交 | .可以更改为文件名称指定文件上传
+ `git commit -m "xxx"` xxx=备注 注意写备注,（每次有文件修改需要运行，然后上传）
+ 
+ `git remote add origin {****.git}` （****.git为所建立的项目的地址)
+ `git push -u origin {main分支名}` 代码上传github默认是main不是master
+ `git log` 查看历史记录
+ `git checkout HEAD {name}` 回溯一个文件到最后一次提交的版本  
+ `git clone {url}` 复制项目


# 遇到错误
1. 错误：fatal: remote error:The unauthenticated git protocol on port 9418 is no longer supported.  


原因：现在已经不支持"git://github.com..............."这样以git开头了，必须使用"http://github......."

但我相信有很多人是因为http开头不成功所以换了git的（我就是.......cry）,所以你可能会遇到接下来这个问题。

2. 错误：fatal: unable to access 'https://github.com/..........git/': The requested URL returned error: 403  


尝试方法：

（1）git config --global http.sslVerify true 没用

（2）git config --global http.proxy http://127.0.0.1:1080

         git config --global --unset http.proxy
没用

原因：（根据我后来解决的方法推测）后来觉得可能是由于其他错误导致的这个错误，因为还有一句报错是：见第三条错误。

3.错误：remote: Write access to repository not granted.  


解决办法：重新在github网站上申请一个personal access token，具体申请方法可以百度，然后一定要勾选repo这个选项！！！有效期可以随意，我直接设置了永不失效。

然后再次clone,又出问题了，这次先让我输入了自己的用户名和密码，结果报错为：见第四条错误。

4.错误：fatal: Authentication failed for 'https://github.com/...............git/'  


解决办法：打开github网站，退出登录（sign out），然后再在弹出的sign in窗口里输入自己的personal access token，然后就可以成功clone了！！

