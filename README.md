
>[!NOTE]
>此机器人由NoneBot框架，nonebot-plugin-maimaidx，Gensokyo，LLOneBot，QQ官方接口构成（该项目较为复杂，请酌情使用）

<div align="center">
<img src="https://github.com/user-attachments/assets/fd09a031-736e-4569-91e1-8776966c8b4a" width="200">
</div>

# HongXing Salt B50(原 HX-Salt Bot)

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

**NoneBot官方文档：https://nonebot.dev/docs/quick-start** 
 
 **先确保您的Python版本≥3.9**
 
 **先卸载可能存在的NoneBot v1 代码如下**
           
    pip uninstall nonebot

### 安装pipx和脚手架（正解）

**（1）安装pipx**
    
    python -m pip install --user pipx
    python -m pipx ensurepath

>[!WARNING]
>如果在此步骤的输出中出现了“open a new terminal”或者“re-login”字样，那么请关闭当前终端并重新打开一个新的终端。

**（2）安装脚手架x2**

    pipx install nb-cli

**安装完成后，你可以在命令行使用 `nb` 命令来使用脚手架。如果出现无法找到命令的情况（例如出现“Command not found”字样），请参考 [pipx 文档](https://pypa.github.io/pipx/) 检查你的环境变量。**


## 创建项目

使用脚手架来创建一个项目：

    nb create

**这一指令将会执行创建项目的流程，你将会看到一些询问：（请根据以下选择来部署）**

 ### 1. 项目模板

     [?] 选择一个要使用的模板: bootstrap (初学者或用户)

 ### 2. 项目名称

     [?] 项目名称: awesome-bot

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

你现在应该已经运行起来了你的第一个 NoneBot 项目了！

---------------------------------------------------------------------------
## 下载Gensokyo，Nonebot-plugin-maimaidx，LLonebot （进阶）

**此过程为：Nonebot-plugin-maimaidx接入Nonebot Nonebot接入LLonebot LLonebot WS反代接入Gensokyo Gensokyo接入QQ官方接口**

## 1.LLOneBot接入：

**LLOneBot的官方文档 https://llonebot.github.io/zh-CN/guide/getting-started**

**Windows一键安装方案**

https://github.com/super1207/install_llob/releases 下载 exe，双击运行即可，之后打开 QQ 的设置，看到了`LLOneBot`就代表安装成功了。**QQ版本不要选太老，建议9.9.15 28260。如需降级请前往https://www.wandoujia.com/apps/566489/history**

**对接NoneBot**

**(1)配置NoneBot**

这里假设你已经安装了Onebot适配器

然后启用NoneBot，可以看到NoneBot输出的端口号，如`8080`

**(2)配置LLOneBot**

<div align="center">

<img src="https://llonebot.github.io/assets/llonebot-nonebot-rws-setting.DTJGh4Lz.png" width="500">

</div>

在**LLOneBot**配置页面添加反向 WS 地址，地址为`ws://127.0.0.1:8080/onebot/v11/ws`, 这里的`8080`是 NoneBot 输出的端口号,`/onebot/v11/ws`是 NoneBot onebot 适配器默认的路径

>[!NOTE]
>记得 LLOneBot 配置的 token 需要和 NoneBot 配置的一致

## 目前你的NoneBot与LLOneBot是接入的，先不要急着接入Gensokyo，让我们安装nonebot-plugin-maimaidx

## 部署 nonebot-plugin-maimaidx

**nonebot-plugin-maimaidx的官方文档：https://github.com/Yuri-YuzuChaN/nonebot-plugin-maimaidx**

## 安装

1.安装`nonebot-plugin-maimaidx`

   - 使用 `nb-cli` 安装
        ``` python
        nb plugin install nonebot-plugin-maimaidx
        ```

   - 使用 `pip` 安装
        ``` python
        pip install nonebot-plugin-maimaidx  ```
   
2. 安装 `PhantomJS`，前往 https://phantomjs.org/download.html 下载对应平台支持

> [!WARNING]
> 未配置 `PhantomJS` 支持的Bot，在使用 `ginfo` 指令时会被强制关闭 Bot 进程

## 配置
   
1. 下载静态资源文件，将该压缩文件解压，且解压完为文件夹 `static`

    - [私人云盘](https://share.yuzuchan.moe/d/aria/Resource.zip?sign=LOqwqDVm95dYnkEDYKX2E-VGj0xc_JxrsFnuR1BcvtI=:0)
    - [onedrive](https://yuzuai-my.sharepoint.com/:u:/g/personal/yuzuchan_yuzuai_onmicrosoft_com/EaS3jPYdMwxGiU3V_V64nRIBk6QA5Gdhs2TkJQ2bLssxbw?e=Mm6cWY)

2. 在 `.env` 文件中配置静态文件绝对路径 `MAIMAIDXPATH`

    ``` dotenv
    MAIMAIDXPATH=path.to.static

    # 例如 windows 平台，非 "管理员模式" 运行Bot尽量避免存放在C盘
    MAIMAIDXPATH=D:\bot\static
    # 例如 linux 平台
    MAIMAIDXPATH=/root/static
    ```

3. 在 `.env` 文件夹中配置 `MAIMAIDXTOKEN`
   
    ``` dotenv
    # 如果没有 `diving-fish 查分器` 的开发者 `Token`，请直接留空
    MAIMAIDXTOKEN=
    # 如果有请填入 `Token`
    MAIMAIDXTOKEN=MAIMAITOKEN
    ```

> [!NOTE]
> 安装完插件需要使用定数表或完成表指令时，需私聊Bot使用 `更新定数表` 和 `更新完成表` 进行生成

> [!NOTE]
> 插件带有别名更新推送功能，如果不需要请私聊Bot使用 `全局关闭别名推送` 指令关闭所有群组推送

## 指令

<div align="center">
<img src="https://raw.githubusercontent.com/Yuri-YuzuChaN/nonebot-plugin-maimaidx/master/nonebot_plugin_maimaidx/maimaidxhelp.png" width="500">
</div>

## 顺便说一下：如果插件/框架开发者认为我抄袭了可以联系我)

## 当然这个插件只对OneBot有用，反而在QQ官方就歇菜了，所以需要接入Gensokyo来模拟OneBot

**省流：有点BUG但不多**

**接入的思路在https://github.com/Yuri-YuzuChaN/nonebot-plugin-maimaidx/issues/53**

## 部署并接入Gensokyo （感觉像个中转站）

**Gensokyo官方文档https://github.com/Hoshinonyaruko/Gensokyo**





    

    
         






















