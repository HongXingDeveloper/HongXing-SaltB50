
### 注意：此机器人由Nonebot框架，Nonebot-plugin-maimaiDX，Gensokyo，LLonebot，QQ官方接口构成（该项目较为复杂，请酌情使用）

<div align="center">
<img src="https://github.com/user-attachments/assets/fd09a031-736e-4569-91e1-8776966c8b4a" width="200">
</div>

# HongXing Salt B50(原 HX-SaltBot)

<p style="text-align:center"><del>主打一个能跑就行的机器人</del></p> 

<a href='./LICENSE'>
    

**前提准备：Python≥3.9 官网地址：https://www.python.org/downloads/**

------------------------------------------------------------------
## 1. 下载并安装Python:

看到这四个红色箭头了吗？那个就是下载Python的安装包！
          <div align="center">
          <img src="https://github.com/user-attachments/assets/9f857c24-3a0b-409a-827e-fb2633ab548f" width="500">
          </div>
          <p style="font-size:9px;" align="center"><del>当然你可能会遇到网速过慢的情况</del></h5>
          <div align="center">
          <img src="https://github.com/user-attachments/assets/c93e5d75-629e-4dbe-bdf2-64b9879b3441" width="500">
          </div>
     **如图，您只需点击<big> Install Now和下面的Add python.exe to PATH 即可（三个箭头）**
         <div align="center">
         <img src="https://github.com/user-attachments/assets/af535e54-0914-46cb-82ed-cbc1659bd02c" width="500">
         </div>
         <center>**安装完只需点击 close 即可，这样Python的下载与安装过程就准备好了**</center>

## 2. 安装Nonebot:

根据NoneBot官方文档：https://nonebot.dev/docs/quick-start 得知 
 
 **先确保您的Python版本≥3.9**
 
 **先卸载可能存在的NoneBot v1 代码如下**
           
    pip uninstall nonebot

### 安装pipx和脚手架（正解）

**（1）安装pipx**
    
    python -m pip install --user pipx
    python -m pipx ensurepath

**如果在此步骤的输出中出现了“open a new terminal”或者“re-login”字样，那么请关闭当前终端并重新打开一个新的终端。**

**（2）安装脚手架x2**

    pipx install nb-cli

**或者是**

    pip install nb-cli

### 注：`pip install nb-cli`是作者实验出来的，具体请看NoneBot官方文档

**安装完成后，你可以在命令行使用 `nb` 命令来使用脚手架。如果出现无法找到命令的情况（例如出现“Command not found”字样），请参考 [pipx 文档](https://pypa.github.io/pipx/) 检查你的环境变量。**


## 创建项目

使用脚手架来创建一个项目：

    nb create

**这一指令将会执行创建项目的流程，你将会看到一些询问：（请根据以下选择来部署）**

 ### 1. 项目模板

    `[?] 选择一个要使用的模板: bootstrap (初学者或用户)`

 ### 2. 项目名称

    `[?] 项目名称: awesome-bot`

**这里我们以 `awesome-bot` 为例，作为项目名称。你可以根据自己的需要来命名。**
    
### 3.其他选项 请注意，多选项使用  空格 选中或取消， 回车 确认。

    [?] 要使用哪些驱动器? FastAPI (FastAPI 驱动器)
    [?] 要使用哪些适配器? Console (基于终端的交互式适配器)
    [?] 立即安装依赖? (Y/n) Yes
    [?] 创建虚拟环境? (Y/n) Yes

**这里我们选择了创建虚拟环境，nb-cli 在之后的操作中将会自动使用这个虚拟环境。如果你不需要自动创建虚拟环境或者已经创建了其他虚拟环境，nb-cli 将会安装依赖至当前激活的 Python 虚拟环境。**

### 4.选择内置插件

    [?] 要使用哪些内置插件? echo

这里我们选择 `echo `插件作为示例。这是一个简单的复读回显插件，可以用于测试你的机器人是否正常运行。

## 运行项目

在项目创建完成后，你可以在**项目目录**中使用以下命令来运行项目：
    nb run

你现在应该已经运行起来了你的第一个 NoneBot 项目了！请注意，生成的项目中使用了 `FastAPI` 驱动器和 `Console` 适配器，你之后可以自行修改配置或安装其他适配器。

## 尝试使用

在项目运行起来后，`Console` 适配器会在你的终端启动交互模式，你可以直接在输入框中输入 `/echo hello world` 来测试你的机器人是否正常运行。

**若没有显示，很可能是`Console`适配器未装上 请输入**
    
    nb adapter install nonebot-adapter-console

---------------------------------------------------------------------------
## 下载Gensokyo，Nonebot-plugin-maimaidx，LLonebot （进阶）

**此过程为：Nonebot-plugin-maimaidx接入Nonebot Nonebot接入LLonebot LLonebot WS反代接入Gensokyo Gensokyo接入QQ官方接口**

### 1.LLOneBot接入：

根据LLOneBot给出的官方文档 https://llonebot.github.io/zh-CN/guide/getting-started 得知

**Windows一键安装方案**

https://github.com/super1207/install_llob/releases 下载 exe，双击运行即可，之后打开 QQ 的设置，看到了 `LLOneBot` 就代表安装成功了。**QQ版本不要选太老，建议9.9.15 28260**

**对接NoneBot**

**（1）配置NoneBot**

这里假设你已经安装了Onebot适配器

然后启用NoneBot，可以看到NoneBot输出的端口号，如`8080`

**(2)配置LLOneBot**

<div align="center">

<img src="https://llonebot.github.io/assets/llonebot-nonebot-rws-setting.DTJGh4Lz.png" width="500">

</div>

在 `LLOneBot` 配置页面添加反向 WS 地址，地址为 `ws://127.0.0.1:8080/onebot/v11/ws`, 这里的 `8080` 是 NoneBot 输出的端口号，`/onebot/v11/ws` 是 NoneBot onebot 适配器默认的路径

    
    

    
         






















