>Git 教程目录
- 安装git
- 创建ssh key、配置git
- 提交本地项目到GitHub
- 账号密码
  1. seanzq0331@163.com
  2. 1001
- 服务器解析地址：https://www.ipaddress.com/ip-lookup

# 一、安装Git
> - MAC上安装Git主要有两种方式  
首先查看电脑是否安装Git，终端输入：
git --version

# 二、生成秘钥
> - 重新生成id_rsa  
ssh-keygen -t rsa -b 4096 -C "seanzq0331@163.com"

# 三、初始化
> - 初始化仓库生成分支（master）和工作区  
  git init
>>  - 添加远程仓库
  git remote add origin git@xxx.git
>>  - 首次推送代码  
git push -u(提交并合并远程) origin master

> - 避免每次pull或者push都要输入密码  
ssh-keygen -p -P oldpass -N '' -f ~/.ssh/id_rsa

# 四、添加到缓存区
> - 添加到本地缓存区  
 git add file/dir
 git add .
 git add --all
> - 删除缓存区  
 git rm --cached “文件路径”
 git rm --f “文件路径” 真实删除

# 五、添加到分支
> -  添加文件到本地分支  
 git commit -m "info"
