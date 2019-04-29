### git使用
   - git init 初始化 git 仓库
   - git status 查看状态，查看你当前 git 仓库的一些状态。
   - git add 文件名 或者 .(提交修改过的所有文件)   提交到暂存区
   - git commit -m '里面不能为空,描述此次修改信息' 提交到 Git仓库
   - git branch:  
      - branch 即分支的意思，分支的概念很重要，尤其是团队协作的时候，假设两个人都在做同一个项目，这个时候分支就是保证两人能协同合作的最大利器了。举个例子，A, B俩人都在做同一个项目，但是不同的模块，这个时候A新建了一个分支叫a， B新建了一个分支叫b，这样A、B做的所有代码改动都各自在各自的分支，互不影响，等到俩人都把各自的模块都做完了，最后再统一把分支合并起来。
      
      
### 连接github
- 有 http 和 ssh 
- 在github新建数据库后 复制第五行代码
- 链接github后提交git push origin master


### ssh 需要配置ssh keys
- 大多数 Git 服务器都会选择使用 SSH 公钥来进行授权。系统中的每个用户都必须提供一个公钥用于授权，没有的话就要生成一个。生成公钥的过程在所有操作系统上都差不多。首先你要确认一下本机是否已经有一个公钥。
   
#### 配置ssh keys
- 先输入$ cd ~/.ssh   $ ls 命令查看是否有SSH 公钥看一下有没有id_rsa和id_rsa.pub(或者是id_dsa和id_dsa.pub之类成对的文件)，有 .pub 后缀的文件就是公钥，另一个文件则是密钥。

- 如果没有(没有试过,我的有.pub后缀的文件)
	输入$ ssh-keygen -t rsa -C "你的邮箱地址" 命令  然后按回车出现 Your public key has been saved in /home/you/.ssh/id_rsa.pub.The key fingerprint is: # 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db 你的邮箱地址代表秘钥生成
    
- 有.pub后缀的文件直接输入,没有输入命令生成后输入$ cat ~/.ssh/id_rsa.pub 命令获得公钥 复制 

- 返回GitHub 点击setting > ssh and GPS keys > New SSH key 将复制的公钥粘贴到Key里 title自己取名字然后点击add key

- 完成后输入$ ssh -T git@github.com 命令验证是否可以正常工作   Hi xxx! You've successfully authenticated, but GitHub does not # provide shell access.表示设置成功

