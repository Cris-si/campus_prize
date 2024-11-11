# 本项目为实时抽奖系统
> + 用户可以创建抽奖活动，设置基本的抽奖规则（如参与人数、奖品数量等）。
> + 抽奖用户可以便捷加入抽奖活动，并实时显示抽奖结果。
> + 所有用户可以查看抽奖结果。
> + 可以自定义奖项与奖品数量，用户抽奖时根据现有奖项随机抽取。
> + 点击按钮即可下载Excel表格，记录了抽奖顺序、昵称以及奖项。
> + 支持分享抽奖活动链接，便于用户通过链接或二维码直接参与活动。（**经过测试如果使用http协议会使一件复制链接以及二维码显示失败。所以如果您由于一些情况无法使用https协议，失败后仍能进行手动的链接复制**）
>
## 演示界面：http://110.41.14.172/
>
快照：
>

<img src="/Snapshot1.png" width="50%">

>

<img src="/Snapshot2.png" width="50%">

>
<img src="/Snapshot3.png" width="50%">

>
<img src="/Snapshot4.png" width="50%">

>

>

>


----
***Ciallo～(∠・ω< )⌒★***

----
# ***HOW TO USE***
----
## For Windows
1. **你只需要确保python的正确安装。**
*`` win+R 输入cmd 回车 在命令提示行输入``*

  
> ```
>python --version
> ```
+ 若显示为
> ```
> Python 3.xx.x
> ```
即代表python正确安装。

2. **一键安装依赖**
+ 在文件根目录鼠标右键 在终端中打开。
> ```
>pip install -r requirements.txt
> ```

3. **然后在命令提示行中输入**
> ```
>python -m http.server 8000
> ```
+ 在浏览器中输入`127.0.0.1:8000`
右键点击文件`server.py`即可开启后端服务

##### 现在前后端均已运行 你可以测试并根据自己需要修改代码

## For Linux
1. **首先你需要确保python的安装。**
> ```
>sudo apt update
>sudo apt install python3 python3-pip
> ```
2. **一键安装依赖**
> ```
>pip install -r requirements.txt
> ```
3. **运行flask应用（需要在项目根目录内）**
> ```
>python3 server.py
> ```

----
## For server
1. **首先你需要手动修改 `index.html` `templates/lottery.html` 中的ip地址。**

即将原文的`127.0.0.1`改为您服务器的公网ip地址。

**~~是的。因为我是弱鸡。所以只能写出这样丑陋的代码。~~**

2. **请保证您的服务器环境均已配置好；若有疑问请参考上文配置环境。**
>

3. **启动flask应用（若非小白请直接跳过下一步）**
> ```
>python3 server.py
> ```
3.5 **如果您是新手 即您的服务器未以任何一种方式配置为web服务器 那么我将告诉你配置httpd的方式**
> ```
>yum install git
>yum install httpd
>systemctl start httpd
> ```


+ 现在httpd已经配置完毕。您需要将文件传至服务器，推荐安装`WinCSP`软件，百度搜索即可安装，在此不多赘述。
>

+ 安装好WinCSP后，将本项目复制到/var/www/html目录下，终端输入
> ```
>cd /var/www/html
>python3 server.py
> ```
+ 至此 后端服务已经启动。前端界面应该也能通过您服务器的公网ip查看。（**如果有问题请检查云服务器厂商的防火墙**与**服务器本身的防火墙**）
>
4. **现在你或许需要`nohup`命令使得server.py在关闭终端后在后台运行。**
> ```
>cd /var/www/html
>nohup python3 server.py &
> ```

5. **至此 你应该实现了本项目在服务器的部署。并且关闭ssh连接后后端应用仍能在后台运行。您现在应该可以通过您的公网ip地址访问并且功能正常。**

----
