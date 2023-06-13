# usegit
使用git管理上传代码
# 下载git 初始化
+ 下载目录`https://git-scm.com/`
+ 桌面右键`Git Bash Here`
+ `ssh-keygen -t rsa` 生成秘钥 （生成的文件在用户的.shh文件内复制id——rsa.pub文件到github上）
+ `git config --global user.name {name}`  
+ `git config --global user.email {email}`
# 上传步骤  
+ 创建一个想要上传的文件，在文件夹内右键鼠标点击`Git Bash Here`
+ `git init` 管理即将新建的源代码
+ `git add .` 把当前文件夹内所有的文件和非空文件，设置为准备提交 | .可以更改为文件名称指定文件上传
+ `git commit -m "xxx"` xxx=备注 注意写备注
+ `git log` 查看历史记录
+ `git checkout HEAD {name}` 回溯一个文件到最后一次提交的版本  
+ `git clone {url}` 复制项目
