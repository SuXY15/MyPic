HesaiTech 实习工作汇报 {#Title}
==========
苏星宇 [suxingyu_intern@hesaitech.com](suxingyu_intern@hesaitech.com)
> 为期六周的实习居然也就快结束了，时间哗哗响啊～

**目录** <a name="table"></a>

[TOC]

- - - - - - - - - - 
一、软件、工具学习
----------

![](https://raw.githubusercontent.com/SuXY15/MyPic/master/tools.png)

#### (一) 编程语言
##### Python
+ 从几乎从未接触Python开始，第一天入职后即开始学习，至今仍在甚至很多年内也将继续学习的语言。体会到了脚本语言的魅力。从最开始看基础的[Python教程-廖雪峰的官方网站][1]，到慢慢找一些比较系统的资源如盛哥推荐的[简明Python教程][2]，再到看官方的`numpy/scipy`的说明文档，虽然容易在写代码时犯基础性的错误，但自己体验一遍错误的过程确实也让我受益良多。目前使用Python还是只能完成一些简单的任务，但以后还会经常用的 ：）。
##### Verilog HDL
+ 一门接触的更少的语言。以前偶有耳闻 “硬件描述语言” 的大名，但真正自己使用还是相当Excited！从最基础的`$display("Hello World!")` 到照着例程写一个计数器，到由晋哥提供的LFSR随机数生成器了解语法、写法，再到自己尝试写MersnneTwister算法的Verilog实现(虽然以失败告终...)，和结合开源代码实现的Tausworthe随机数生成器。虽然主要是模仿尝试，原创性内容很少，但也算是了解了最基本的Verilog的用法。
##### C++
+ `PandarTool`中的Qt部分主要为C++代码，了解了一些Python调用C++的基本用法，和参数变量的传递方法。另外基于个人兴趣了解了一些网络编程的内容，例程为C++代码，使用`gcc`编译(*第一次知道Linux下怎么写C代码...*)。顺便了解了一些Linux系统的基本知识，对系统/进程有所认识。

#### (二) 软件
##### SolidWorks
+ 在学校也曾学习使用过SolidWorks，也画过简单的3D打印件，但多为现成参数而非自己设计实现。就结果而言，应当是一两个小时就能设计好的简单部件，但前前后后改了四版，打了4次废件，效率有点低下。主要学习到了一点设计的技巧，如开孔拔模，立柱支撑，侧孔窄高等。
##### AltiumDesigner
+ 一直以来就想学AD，在学校时也曾下载过想自学，但无奈一没有相关练手项目，二没有任何指导，加上网上资源不齐全(官方中文文档仍在整理中)，入门颇为费劲。看了个比较简易的[Altium Designer教程——两小时快速入门][3]然后自己试着瞎画一点，看看官方有限的中文文档，糊里糊涂做了个小板子。不过也算是了解了基本的使用方法流程，等学习了电子相关知识后，一定再多加学习练习！
##### Thundbird / 为知笔记
+ 主要受Markdown激励，对支持Markdown的工具产生了巨大的好感。以及第一次尝试笔记软件，真的十分不错，感觉早接触一天，学到的东西就能多一分！还需要多多使用，多多熟悉。
> PS: 曾经用过txt记课程笔记......简直惨不忍睹orz

#### (三) 工具
##### git / Markdowm
+ 以前也用过简单的git，甚至在github上写过自己的小项目，但却是文件拖拽上传的......系统的看了看git的教程，使用git维护自己的代码后，才算是感受到了其方便性。而Markdown来源于皮哥一次看我写README毫无格式，就简单提点了一二，从此爱上Markdown，各种便利，写文档神器！
##### ssh / samba
+ 以前也想学一点ssh相关知识来着(曾经买过一个树莓派想搭一个自己的服务器)，奈何未能入门，连最简单的`ssh user@ip`也没理解，于是乎留到现在。用了ssh / scp以后，看到张姐电脑上的share文件夹可以被晋哥随意存取查看，就试着照教程用samba建了自己的共享文件夹，超级好用！感受到了Linux的便利，再也不想用U盘系列：）。
##### VTK(Visualization Toolkit)
+ 以前曾用过一点简单的OpenCV，VTK又有所不同，其特色的管道结构带来了很大的性能提升，三维显示相当优秀，不过了解并不深入，以后用到再继续学习~
##### Emacs / Sublime Text 3
+ 曾经用Ubuntu，看到网上教程要用`vim`改某个文件，我几乎必定会改用`nano`，对vim的使用有很不好的体验(vim大概对新手不友好吧......)，但想起来有同学推荐过Emacs，就试着学学，找了个大神的配置和主题，体验十分良好。虽然目前离使用一些高级命令还差得很远，但已经能满足日常的编辑需要了。至于Sublime，主要是简单好用，插件丰富，故而也很喜欢。当然，顺便也有看一点`vim`的教程，但是看到页面上有大概几百个命令，然后就......没有然后了：）。

[回到目录](#table)

- - - - - - - - - - 
二、各类脚本编写
----------
> 大多前期测试的脚本，在中期都融入到PandarTool中成为某个功能或其部分了，仅列出当前仍独立使用的脚本。

#### 1. 波形显示脚本 `waveShow.py` [输入DB] [输出PDF] <a name="waveShow"></a>
用于查看波形，生成结果为一个画有波形图的PDF文件，其中多次光强的测量结果在同一张图上以不同颜色表示，如下图：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/waveShow.png)
用法：
```bash
python waveShow.py yourPath/yourWaveData.db
```

#### 2. 波形匹配脚本 `waveAdapt.py` [独立运行] <a name="waveAdapt"></a>
用于自动调整光强以匹配波形使得峰值在指定范围内(140±5)并测量，最终生成40个图像文件，对应40个通道
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/waveAdapt.png)
图像横轴为光强(间距为5)，纵轴为对应光强下波形峰值在140±5时的测距(16次取均值)
用法：
使用PanadarTool调节设备，确定A0通道后，命令行输入
```bash
python waveAdapt.py
```

#### 3. 波形分析脚本 `waveAnalyze.py` [输入DB] [输出PDF] <a name="waveAnalyze"></a>
用于获取波形相关参数信息，生成对应分析表格，报告峰值、时长等信息，生成结果如下图：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/waveAnalyze_1.png)
点击对应通道可跳转至对应通道的测量数据：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/waveAnalyze_2.png)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/waveAnalyze_3.png)
其中，黄色实线为75，绿色点划线为所选基线，绿色实线为基线+10，红色点为峰值点(Y值与峰值相等的点)
用法：
```bash
python waveAnalyze.py yourPath/yourWaveData.db
```

#### 4. 数据插入脚本 `dataInsert.py` [输入DB] [更新DB] <a name="dataInsert"></a>
用于测量单个通道并插入指定KeyPoints数据库中(需要改写脚本内的下图对应参数变量)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/dataInsert.png)
> PS: 用于测量至一半，补测后部分；单通道更新不用此脚本

用法：
```bash
python dataInsert.py yourPath/yourKeyPointsDB.db
```
#### 5. 点云显示脚本 `pointShow.py` [输入Mat] [显示点云] <a name="pointShow"></a>
用于显示由`pointCloud.py`所采集的点云(.mat文件)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/pointShow.png)
用法：
+ 直接在含有对应 .mat 文件的路径内双击运行，或在该路径下运行 ``` python pointShow.py ```
```bash
 python pointShow.py yourPath/yourPointCloud.mat
```

#### 6. 数据显示脚本`distShow.py` [输入DB] [输出PDF] <a name="distShow"></a>
用于显示获取到的`keyPoints`数据或`distMean`数据，使用此脚本需要在同路径下有`config.cfg`文件，用于限定对应参数，详见项目内的该文件；
`mode = 1`时，处理`keyPoints`数据，所得PDF表格如下：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/distShow_1.png)
用法：
```bash
python distShow.py yourPath/yourKeyPointsDB.db
```
`mode = 0`时，处理`distMean`数据，所得PDF表格如下：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/distShow_2.png)
用法：
```bash
python distShow.py yourPath/yourDistMeanDB.db
```

#### 7. t_base获取脚本`baseGet.py` [独立运行] <a name="baseGet"></a>
用于获取`t_base`参数，保存获取的参数为`t_base.csv`，并生成相应的校准文件，同时对原始数据和比对数据绘图并保存；
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/baseGet.png)
用法：
```bash
python baseGet.py
```

#### 8. 数据串口烧写脚本`writePara.py` [输入param] [串口烧写] <a name="writePara"></a>
用于将生成的`.param`文件烧写到FPGA中，用法为：
```bash
python writePara.py yourPath/Lidar-x.param
or
python writePara.py
```



[回到目录](#table)

- - - - - - - - - -
三、PandarTool开发维护
----------
#### (一) 基本介绍
+ 文件明细如下图(部分依赖项或测试内容以灰色标注)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/PandarTool_Extra.png)
+ 其中，`smallConrtol.py`为主要接口，用于与原`PandarTool`部分对接；`replace/`文件夹内为需要替换或添加到原`PandarTool`相应路径下的文件，具体路径见`README.md`内介绍；`tools/`文件夹内主要为各个脚本和相应的测试内容。
+ 下载链接为：
    * [ssh://git@code.hesaitech.cn:10022/suxingyu/PandarTool_Extra.git][4]
    * [http://code.hesaitech.cn:10080/suxingyu/PandarTool_Extra.git][5]

#### (二) 主要功能
##### 1. 波形数据waveData获取 <a name="waveData"></a>
+ 确认A0通道后，可点击`Extra波形获取`采集相关波形参数：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/waveData.png)
+ 保存文件后，即开始测量，采集从光强10 -> 40 -> 150，每个光强下由A0 -> A19 -> B0 -> B19，每个通道测量一次数据(**1024**个点)，共计耗时约5分钟，测完后跳转至A0通道10光强。
+ 测完的波形数据可用 [waveShow.py](#waveShow) 脚本进行显示，也可用[waveAnalyze.py](#waveAnalyze)脚本进行波形分析。

##### 2. 校准数据KeyPoints获取 <a name="keyPoints"></a>
+ 确认A0通道后，先勾选`来回移动遮挡片`，再点击`Extra校准数据`，保存文件后即开始测量。
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/keyPoints.png)
+ 采集从光强10 -> 40 -> 150，每个光强下由A0 -> A19 -> B0 -> B19，每个通道采集**6144**(192*32)个点，每次切换通道后会自动打开实时显示(RealTimeChart)，每次测量从橙色框开始，测量进行到1/3(**2048**)个点时，转台左移1000，激光照射到白色方框处测量，到2/3(**4096**)个点时，转台右移2000，激光照射到黑色方框处，至该通道测量结束。共计耗时约80分钟，测完后跳转至A0通道10光强。
+ 测完的数据可用 [distShow.py](#distShow)脚本进行显示，也可使用[数据查看与修改](#extraImport)进行查看修改，可使用[单通道更新](#updateData)更新指定通道，也可用于[格式输出](#formatData)

##### 3. 校准数据DistMean获取 <a name="distMean"></a>
+ 采集过程与[KeyPoints获取](#keyPoints)基本相同，仅需在点击`Extra校准数据`前不勾选`来回移动遮挡片`即可。
+ 同样，每次切换通道后会自动打开实时显示(RealTimeChart)，但不再在中途移动转台，而仅测量打在橙色框中的数据，每个通道**256**(8*32)个点，共计耗时约10分钟，测完后跳转至A0通道10光强。
+ 测完的数据可用 [distShow.py](#distShow)脚本进行显示，可使用[单通道更新](#updateData)更新指定通道，也可用于[格式输出](#formatData)

##### 4. 数据查看与修改 <a name="extraImport"></a>
+ 勾选校准页面的`Extra数据库导入`后，点击`数据导入`即可导入测量得到的KeyPoints数据：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/extraImport_1.png)
+ 导入后可点击查看对应通道的数据如下：(导入后，在原`Extra数据库导入`处显示打开的文件名及路径)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/extraImport_2.png)
+ 其中，右上角为原始数据及计算所得关键点(红色为当前选中点)，右下角为原始数据经关键点得到的残差，数字键`1``2`可左右选择关键点，关键点坐标可调节，键盘上下左右为微调(**步长0.01**)，按住`Ctrl`上下左右为普通调(**步长0.1**)，按住`Shift`上下左右为粗调(**步长1**)。
+ `Ctrl+P`可切换为上一个通道，`Ctrl+N`可切换为下一个通道，切换至两端时，会保留当前通道不变。另外，`Ctrl+Q`可实现定点功能，在原始数据表中放置鼠标，按下`Ctrl+Q`即可将当前选中点的坐标改为当前鼠标所在点的坐标位置。

##### 5. 单通道更新 <a name="updateData"></a>
+ 当有较差数据时，可使用`Extra更新通道`按钮进行更新，且仍以`来回移动遮挡片`选框为标志区分更新KeyPoints和DistMean两种数据。方法如下：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/updateData_1.png)
    * 更新KeyPoints数据：确定A0通道后，勾选`来回移动遮挡片`，勾选`选择后移动激光器`，并选择对应要更新的通道(此处以A0为例)，再调节光强至目标档位(仅10/40/150三个档位可选，此处以10为例)，最后点击'Extra通道更新'选择对应`KeyPoints`文件，即可更新该文件内对应光强对应通道的数据。
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/updateData_2.png)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/updateData_3.png)
    * 更新DistMean数据：同上，不勾选`来回移动遮挡片`，并且在选择文件时选择`DistMean`数据文件即可

##### 6. 数据检查与格式输出 <a name="formatData"></a>
+ **数据检查**
    * 人工粗略检查并更新后，可进行数据检查，点击`Extra格式输出`，依次选择KeyPoints数据文件和DistMean数据文件，即开始数据检查，耗时约5秒。检查后，弹出窗口提示可能存在错误的通道，如图：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/formatData_1.png)
    * 且会在KeyPoints数据文件路径下生成检查报表，如图：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/formatData_2.png)
    * 对此处异常通道A7->光强1500ns，查看数据可发现，中间有明显断电，数据确实不合格。
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/formatData_3.png)
    * 此时，可选择细微调整或[更新通道](#updateData)
+ 待排查所有错误后，可进行**格式输出**
    * 点击`Extra格式输出`，待检查完毕且错误在可接受范围内时，点击`Yes`进行格式输出，约30秒输出完毕，生成6个校准文件和1个校准报表。
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/formatData_4.png)
    * 报表前部分表格内容与检查表格内容相同，后部分为每个通道对应的数据明细情况，以待进一步检查，链接模式与[波形分析](#waveAnalyze)部分相同。
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/formatData_5.png)
    * 其中，蓝色点为原始数据点，红色点为计算所得的关键点，横坐标从0到最大关键点横坐标加0.5，纵坐标为关键的点两侧偏移0.1，黄色点为DistMean数据点，黄色实线为其均值所在Y值处水平线。
+ 格式输出完毕后，会弹出窗口询问是否进行**串口烧写**(Lidarboard板上相关功能尚未匹配)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/formatData_6.png)
    * 若选择No，则不进行串口烧写
    * 若选择Yes，则将会把生成的数据通过串口烧写到上仓板，过程持续约2分钟，且烧写过程中PandarTool界面黑屏。

##### 7. 点云扫描与保存 <a name="pointCloud"></a>
+ 数据烧写完成后，即可进行点云扫描验证Lidar校准是否正确，方法为：
```bash
python pointcloud.py
```
+ 或双击脚本文件pointcloud.py也可。点云扫描完成后会弹出VTK渲染窗口，可用鼠标缩放、拖动、旋转点云查看，同时会在当前运行路径下生成对应的点云数据文件，以时间为前缀命名。该文件可用[点云查看脚本](#pointShow)复现查看。

##### 8. 程序运行信息显示 <a name="plainText"></a>
+ 本部分用于测试过程中输出相关程序信息，以供了解当前运行动态和保留操作历史以便排查错误。
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_1.png)
+ 主要信息有如下几种：
     * 确认A0通道时，提示已确认：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_2.png)
     * 开始/停止自动刷新波形/实时刷新数据时(此二者用同一张表显示，互斥)：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_3.png)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_4.png)
     * 开始测量时，提示相关信息(类型、文件名、光强、通道等)：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_5.png)
     * 测量过程中，提示相关信息(单通道时间、左移右移提示、数据总数等)：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_6.png)
     * `停止`按钮提供暂停/继续功能，此时会提示相关信息(通道，当前测数)：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_7.png)
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/plainText_8.png)

#### (三) 其他及注意事项
1. 相互冲突：
    `自动刷新波形`和`校准数据`功能占用同一个绘图表格，互相冲突，不能同时选中；且测量数据时，不推荐勾选`自动刷新波形`，一是测量时在移动通道后会开启`校准数据`的实时刷新，与`自动刷新波形`冲突，~~二是`自动刷新波形`会读取当前RadioButton选中的通道，每次测量时自动移动至该通道，与采集数据的移动通道冲突~~(此部分已优化)。
2. 软件卡顿
    软件卡顿可能有多种原因，若出现黑屏，多半为网络延时过高或某个函数采集数据时未收到上仓板数据反馈；[格式输出](#formatData)的黑屏是正常现象，无需担心。

[回到目录](#table)

- - - - - - - - - - 
四、上仓板测试用保护外壳
----------
#### (一) 3D打印外壳
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/Board_1.png)
+ 整体来说结构并不复杂，但因考虑不周还是改了好几版，浪费了一些材料，风扇安装孔是全凭感觉做的(网上没有找到相关说明)，也还能凑和用，不过目前整体的安装拆卸并不方便。
+ 比较奇怪的是，一开始设计的是上板有支撑而下板几乎空白，结构明显不合理(主要接线在板上方)，居然到第四版才发现，还是经验太不充足。

#### (二) 电源转接板
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/Board_2.png)
+ 很简单的一个小板子，只有一个电源接入和两个电源输出，但还是花了不少时间。主要难度在于从头开始，没有系统的学习，加上第一次就要自己制作元件库，还是颇为麻烦。
+ 犯了很多低级错误。边缘处三个焊盘本用作定位孔，但因为拿到没有具体参数，只能手工比对位置，结果却把位置定反；另外，因为个人疏忽，把size 和 hole 设置错了，导致收到的板子并没有安装定位孔。以及尺寸设计超范围，要正常安装上需要将板子左下角磨掉约1毫米(上图PCB视图下)。
+ 但好在也勉强能用，不至于彻底浪费。。。

[回到目录](#table)

- - - - - - - - - - 
五、Verilog 随机数生成器
----------

#### (一) Mersenne Twister随机数生成器
+ [Mersenne Twister][^Mersenne]是一个伪随机数发生算法，其最为广泛使用的MT19937可达到2^19937-1长的周期，在1<=k<=623的维度之间都可以均等分布。故而一开始尝试用此种方法写随机数生成器，用python实现了一个简易的测试如下图：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/Mersenne.png)
+ 可见其随机性还算不错，但问题在于其用到了较多的质数相乘，大型数组，对FPGA资源消耗巨大，故未继续采用。

#### (二) Tausworthe 随机数生成器
+ 简单调研了一下如AES、Hash等随机数生成算法，最终采用了Tausworthe算法，基于一个开源的[github项目][^Tausworthe]修改了一个供测试的程序如下：
![](https://raw.githubusercontent.com/SuXY15/MyPic/master/Tausworthe.png)
其中靛、黄、紫三种颜色的点来自三个种子随机生成的数据(依次覆盖，故而看上去占比不一样)，可见随机性也已足够好，故最终采用。

[回到目录](#table)

- - - - - - - - - - 
六、简要总结
----------

<font size=4>总的来说学到了很多新姿势，锻炼了自己的编程能力，同时也发现了自己的很多不足：</font>

+ <font size=3>经常安排的任务并没有妥善做完做好，完成到90%的时候就开始松懈，导致**收尾较差**;</font>
+ <font size=3>刚到时感觉一切很新鲜，干劲很足，后来慢慢**变得懒散**;</font>
+ <font size=3>有些内容可以更加完善，但因难度较大或收益较小而并**未能尽善尽美**; </font>
+ <font size=3>学习AD时，完美体现了“**欲速则不达**”，越想速成，越难以入门，最后还是一步一步看视频教程;</font>


[回到目录](#table)

[^Mersenne]: https://en.wikipedia.org/wiki/Mersenne_Twister

[^Tausworthe]: https://github.com/scottwilson46/FPGARandom

[1]: https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/
[2]: http://www.kuqin.com/abyteofpython_cn/
[3]: http://www.bilibili.com/video/av2351785/
[4]: ssh://git@code.hesaitech.cn:10022/suxingyu/PandarTool_Extra.git
[5]: http://code.hesaitech.cn:10080/suxingyu/PandarTool_Extra.git
