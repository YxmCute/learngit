#### 初始的配置

1. 你可以通过以下命令查看所有的配置以及它们所在的文件：因为如果是公司的电脑有可能之前的配置过的

     ```console
     $ git config --list --show-origin
     ```

     

#### 用户信息

1.     安装完 Git 之后，要做的第一件事就是设置你的用户名和邮件地址。 这一点很重要，因为每一个 Git 提交都会使用这些信息，它们会写入到你的每一次提交中，不可更改：
  
     ```console
     $ git config --global user.name  "Your name"
     $ git config --global user.email "your email"
   ```
   如果使用了 --global 选项，那么该命令只需要运行一次，因为之后无论你在该系统上做任何事情， Git 都会使用那些信息。 当你想针对特定项目使用不同的用户名称与邮件地址时，可以在那个项目目录下运行没有 --global 选项的命令来配置。
   
2.  为不同的项目配置不同的用户名和邮箱，在当前项目下时使用Git命令
      ```console
     $ git config  user.name  "Your name"
     $ git config  user.email "your email"
     ```
3. .git 中config文件中有相应的信息，如图所示
![config](pic/%E6%89%B9%E6%B3%A8%202020-07-18%20095218-1595038199872.png)