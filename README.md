# MetaSweeper-v3.1.0_beta —— project with 8 modes of minesweeper, third generation minesweeper video player and high performance algorithm toolbox

# 元扫雷v3.1.0_beta —— 包含8种模式的扫雷项目、第三代扫雷录像播放器及高性能算法工具箱

[![SolvableMinesweeper](https://img.shields.io/badge/SolvableMinesweeper-v2.2.5-brightgreen.svg)](https://github.com/eee555/Solvable-Minesweeper)

## 简介(Introduction)

元扫雷v3.1.0_beta是由热爱扫雷的玩家开发的扫雷游戏。这个项目并非简单重复已有的工作，而是集中了一批扫雷游戏的现代化设计。

优势：

+ 内部集成了**三大判雷引擎+集成的局面状态机+概率计算引擎+光学局面识别（Optical Board Recognition，OBR）引擎**，具备性能优势。

+ 采用Python/PyQt5及Rust编写，模块间相互配合、融为一体，兼顾**开发效率、内存安全与执行速度**。游戏界面与算法高度分离，自研的工具箱同样开源，且遵循更为宽松的MIT协议，通过pip install ms_toollib命令即可安装。

+ 游戏模式方面，具有**全部6种无猜扫雷模式+标准+win7**，弱可猜、强可猜的模式都是绝无仅有的。

+ 外观上它只是一款普通的标准扫雷，但它能通过按住ctrl并滚动滚轮任意**调整大小**，能调整窗口的**透明度**。这是罕见的。

+ 按下“空格”计算局面中每一格是雷的概率。这是罕见的。

+ 按下“ctrl+空格”能**截屏识别**计算其他扫雷中每一格是雷的概率。这是绝无仅有的。

+ 其装载的录像播放器可以分析录像的高层抽象特征，并实时展示游戏局面中每一格是雷的概率。这是绝无仅有的。能够播放avf、rmv、mvf、evf四种主流格式的录像。这是罕见的。

+ 能够计算3BV/s、STNB、RQP等指标并展示，能够自定义公式。这是罕见的。

+ 完备的局面筛选功能，按用户配置来筛选。这是罕见的。

+ 对变速齿轮的防御能力。

目前属于漫长的开发阶段中，约1~3月更新一个版本，欢迎提issue、star、pull request、fork。

MetaSweeper v3.1.0_beta is a minesweeper game developed by players who love minesweeper. Rather than simply repeating existing work, the project brought together a collection of modern designs for minesweeper games. Internal integration of three mine-detection engine + probability calculation engine + Optical Board Recognition (OBR) engine, with all six no guess mode + standard + Win7. Written in Python/PyQt5 and Rust, it gives consideration to development speed, memory safety and execution speed. Different from Arbiter's emphasis on checking cheating, FreeSweeper's emphasis on statistics, Minesweeper X's small, MetaSweeper developers hope to produce a highly intelligent Minesweeper. It looks like a normal standard minesweeper, but it can be resized by holding Down CTRL and scrolling through the wheel, it can adjust the transparency of the window, it can calculate the probability of whether each cell being a mine, and it can calculate the probability of whether each cell being a mine for other minesweeper by screen shot. The video player can analyze high-level abstract features of the video and show the probability of whether each cell being a mine in real time. In terms of gameplay, the weak guess and strong guess modes are unique and the only minesweeper with its own tutorial. For high play, it is also professional, able to calculate 3BV/s, STNB, RQP metrics and display. In addition, it doesn't bother the player, no window pops up when the player doesn't open it, and any window can be quickly closed by pressing the space bar.

### 开发计划

+ 使用教程（有些老旧）：[https://mp.weixin.qq.com/s/gh9Oxtv9eHaPTUMTDwX-fg](https://mp.weixin.qq.com/s/gh9Oxtv9eHaPTUMTDwX-fg)
+ 更全面的文档（施工中）：
+ 算法工具箱地址：[https://github.com/eee555/ms_toollib](https://github.com/eee555/ms_toollib)
+ 算法工具箱文档：[https://docs.rs/ms_toollib](https://docs.rs/ms_toollib)

## 安装
建议在`Windows 10`下运行本游戏，其它操作系统未经测试，可能出现意想不到的问题。

### 通过网盘安装(推荐)
在下面的[下载链接](#下载链接)中找到最新的版本，然后下载，解压，直接运行`main.exe`文件（如果警告请点击“仍然运行”），开箱即用。

### 通过Github Actions安装(最安全)
在[Github Actions](https://github.com/eee555/Solvable-Minesweeper/actions)找到构建成功的最近一次提交，点击更新内容，在Artifacts页面可以找到打包好的文件，后面步骤同上。这个方法可以体验最新功能，能保证软件绿色安全无毒，但未发布的版本都不能保证稳定性。

### 从源码安装(不推荐)
在编译之前，请确保自己拥有：
*   Python >=3.7
*   会用Powershell或者其它命令行工具的能力

以下为安装步骤：
*   克隆这个仓库到本地
```sh
    git clone https://github.com/eee555/Solvable-Minesweeper.git
```

*   方案一：从pypi.org安装Python依赖（安装ms_toollib的release版本，简单但不一定成功，因为底层api可能有调整。如果不成功，需要往前翻到合适的版本，或直接联系作者）
```sh
    pip install -r requirements.txt # Windows
    pip3 install -r requirements.txt # *nix
```

*   方案二：从github安装Python依赖（安装ms_toollib的nightly版本，复杂但一定成功。复杂之处在于需要安装rust工具链）
```sh
    git clone https://github.com/eee555/ms_toollib.git
    cd ms_toollib\python_package
    cargo build --release
    将ms_toollib\python_package\target\release下的ms_toollib.dll重命名为ms_toollib.pyd，复制到Solvable-Minesweeper\src下
    安装requirements.txt中除ms_toollib外剩余的依赖
```

*   运行程序，大功告成了~
```sh
    py -3 src/main.py # Windows
    python3 src/main.py # *nix
```

## 实现原理

（还没写，计划弄出3.5以后回头来写）

## 贡献

[CONTRIBUTING.md](https://github.com/eee555/Solvable-Minesweeper/blob/master/CONTRIBUTING.md)

## 荣誉
被收录于Awesome Rust Repositories: 
[https://twitter.com/RustRepos/status/1636837781765799940](https://twitter.com/RustRepos/status/1636837781765799940)

## 下载链接

### 正式版v3.1.1：
修复了8个bug。现在能够播放mvf录像。提高了对变速齿轮的防御能力。
链接：[https://wwwl.lanzouw.com/itjCR0p24hdc](https://wwwl.lanzouw.com/itjCR0p24hdc)

### 测试版v3.1.0_beta：
修复了若干bug。增添了游戏时的计数器，其表达式支持任意python语法。游戏结束后，可以自动保存.evf录像。现在能够播放avf、rmv、evf三种录像。无猜埋雷可以支持任意雷数。  
链接：[https://wwwl.lanzouw.com/imdWO0joyzra](https://wwwl.lanzouw.com/imdWO0joyzra)

### 正式版v3.0.2：
修复了3个特别影响游戏体验的bug。  
链接：[https://wwb.lanzouw.com/iuhs904cfj0b](https://wwb.lanzouw.com/iuhs904cfj0b)

### 正式版v3.0.1：
修复了两个bug。现在可以将元扫雷设置为arbiter的avf文件的默认打开方式。  
链接：[https://wwb.lanzouw.com/iHaNm02ane7c](https://wwb.lanzouw.com/iHaNm02ane7c)

### 正式版v3.0：
修复了一些bug。黑猫扫雷更名为元扫雷（MetaSweeper）。首次装载第三代录像播放器，能够播放avf录像。分析出并报告抽象的录像事件。录像播放时，按下空格键可以实时地展示每格是雷的概率。  
链接：[https://wwb.lanzouw.com/i8ypL026p1za](https://wwb.lanzouw.com/i8ypL026p1za)

### 正式版v2.4.2：
软件整体重构。修复了若干bug。ui界面开始采用矢量贴图。游戏开始前，按住ctrl并滚动滚轮可以缩放界面；对雷数滚动滚轮可以调整雷数。预告：即将升级到3.0，从3.0开始，黑猫扫雷将更名为元扫雷（Meta Sweeper）。  
链接：[https://wwb.lanzouw.com/i3Bpc01vfsab](https://wwb.lanzouw.com/i3Bpc01vfsab)

### 正式版v2.4.1：
修复了若干bug。部分优化的ui界面。光学局面识别引擎开始支持自定义局面。  
链接：[https://wwe.lanzoui.com/i5Sswsq0uva](https://wwe.lanzoui.com/i5Sswsq0uva)

### 正式版v2.3.1：
修复了若干bug。  
链接：[https://wwe.lanzoui.com/ifH4Cryp3aj](https://wwe.lanzoui.com/ifH4Cryp3aj)

### 正式版v2.3：
修复了若干bug。现在可以设置自动重开、自动弹窗、结束后标雷。按住空格键可以计算每格是雷的概率。组合键“Ctrl+空格”可以通过截图+光学局面识别（Optical Board Recognition，OBR）计算每格是雷的概率。  
链接：[https://wwe.lanzoui.com/i2axoq686kb](https://wwe.lanzoui.com/i2axoq686kb)

### 测试版v2.2.6-alpha：
修复了若干bug。算法优化：(16,16,72)无猜局面埋雷速度提高200%。新功能：快捷键4、5、6可以快速设置三种不同的自定义的自定义模式。对自定义模式的优化，提高了稳定性。对局面刷新的优化。  
链接：[https://wwe.lanzoui.com/igPFFo7mwxi](https://wwe.lanzous.com/igPFFo7mwxi)

### 正式版v2.2.5：
算法优化：高级无猜局面埋雷速度达到约252局/秒。修复了上一个版本的严重bug。  
链接：[https://wws.lanzoui.com/iS3wImv2y5e](https://wws.lanzous.com/iS3wImv2y5e)  

### 正式版v2.2：
算法优化：高级埋雷速度达到37525局/秒，相当于Arbiter的三倍左右，高级无猜局面埋雷速度15.7局/秒。游戏结束按空格可以显示实力指标的极坐标图。删去了一些无用的功能。  
链接：[https://wws.lanzoui.com/iq9Ocm8zdtc](https://wws.lanzous.com/iq9Ocm8zdtc)


