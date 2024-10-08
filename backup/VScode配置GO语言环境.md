# VScode简单配置GO语言开发环境
## 一. Go语言安装
**下载安装**

官方下载地址: <br /> https://golang.google.cn/doc/install

![image](https://github.com/user-attachments/assets/e61d0b50-350f-4e05-b35e-18784698f628)


这里我是windows系统， 所以选择windows，点击download ，进入 下面的页面<br />

![image](https://github.com/user-attachments/assets/bccc6ecf-9573-41d7-a4c7-67e5ca7d4821)

点击Microsoft Windows下面的链接可以直接下载最新版本的windows安装包。当然如果想下载之前的版本或者压缩包可以自己往下找。

安装过程非常简单，没有什么需要特别注意的地方，建议大家在非C盘单独建一个文件夹，专门用来放开发使用的工具。

安装完成后，打开命令行输入`go env`查看是否安装成功<br />

![image](https://github.com/user-attachments/assets/9ec604cc-e707-4bca-a255-9c2755fb3656)

如果输出是像上图这样，证明安装成功

**配置代理**

go的很多依赖包是放在外网上的，不配置代理的话下载安装可能会有一些问题，所以我们需要配置一下代理<br />
在设置中搜索"环境变量"，选择"编辑系统环境变量"<br />
![image](https://github.com/user-attachments/assets/004960e5-dc65-41eb-9b7d-a0669c7d6609)

点击环境变量<br />

![image](https://github.com/user-attachments/assets/45a6f6f6-aa95-4cc2-88f7-3fe07c0c1a44)

在系统变量一栏点击新建<br />

![image](https://github.com/user-attachments/assets/94b5557c-7bf0-45ed-8c14-2871b81dd3b0)

分别新建下面这两个变量

![image](https://github.com/user-attachments/assets/ffb85fcf-0269-4546-b43f-28c99fbd0608)
![image](https://github.com/user-attachments/assets/6bc6e007-9078-44cd-be4e-917fc0f05abe)

> 注意需要逐个点击确定以保证创建成功

接下来再新打开一个命令行窗口，输入`go env`<br />
![image](https://github.com/user-attachments/assets/90e62806-5faa-4e8b-bed3-7b171d4c2698)
![image](https://github.com/user-attachments/assets/af43dd99-5deb-48e7-9a38-bf32499e8dc9)


如果这两行输出一致，表示代理配置成功

## 二. VScode配置

首先在扩展中搜索安装Go插件, 第一个就是
![image](https://github.com/user-attachments/assets/a44bb163-f630-45df-bbb9-e9c289db6119)

然后创建一个go的项目， 创建一个目录即可
![image](https://github.com/user-attachments/assets/78107c7a-10f5-40e9-bb7f-6b28769cd160)

在VScode中打开命令行窗口，输入下面的命令创建go模块:<br />
`go mod init 包的名字`<br />
点击回车后会生成一个go.mod的文件， 里面包含对项目的说明
![image](https://github.com/user-attachments/assets/abe3edf2-79b5-410a-8c57-8bdd876ef42d)


很多时候项目都会在github上有相应的库，那么我们就可以将包的名字命名为`github.com/你的github用户名/项目名字`<br />


以我创建的目录为例, 在命令行输入命令
![image](https://github.com/user-attachments/assets/81bf3bd8-ff2d-41c7-bc93-5bcc336f4971)

生成一个go.mod文件
![image](https://github.com/user-attachments/assets/0ff69775-8eaa-428a-872a-437ea62015a3)

现在我们便可以在这个目录下创建go文件<br />
![image](https://github.com/user-attachments/assets/eec80415-9d80-482f-acb3-e0815c351625)

运行<br />
![image](https://github.com/user-attachments/assets/347c7d61-d0ce-4a13-a69e-e601f81e159a)

可以看到go文件正确编译并输出结果
> 这里由于我之前已经安装过所需要的工具，所以没有弹出提示。但是在首次运行的时候VScode可能会出现一些问题，根据它的提示安装对应的工具就可以


**小结:** 之前配置go环境的时候用的是老的配置gopath的方法，当时我实在是有点迷，没有搞明白。后面发现了这个方法，感觉真的方便很多