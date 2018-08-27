# cocos_doudizhu
cocos creator 斗地主


tasks01:
2018-08-20 by zxf

1. 游戏代号使用ddz, 不使用doudizhu（包括这个github的名字，直接叫ddz）
2. 先增加一个头像控件，（和poker类似），之前做的不够好，可以参考 欢乐斗地主， 开发时直接使用它的资源。
3. 使用bmfont字体（cocos-creator可能不是这个名字），并在wiki下面增加一个bmfont的使用文档。
   tip: 上次下载的包里面有个xxx.fnt的文件（还有个同名的xxx.png）
4. 使用bmfont字体是做游戏内部的操作按钮(不要、出牌、抢地主、不抢、不叫、叫地主、提示)，前期可以只要三个按钮：不要、出牌、提示

task02:
2018-08-21 by zxf

1. 完善服务器游戏流程。主要是具体的游戏逻辑。
2. 简化游戏创建桌子的流程，如下：
    -2.1. 服务器启动时，直接创建出若干个桌子。
    -2.2. 客户端连接服务器后，将桌子列表下发（tbaleId,tableName,tablePlayerCount等信息）
    -2.3. 前端可以选择桌子进入。
3. 简化游戏逻辑。
    -3.1. 玩家进入桌子后，服务器判断人数。如果人数已满，广播游戏开始的信息。并发牌，同时选定一个玩家是地主。
    -3.2. 不要叫地主、抢地主、叫分等流程。发牌的同时、选地主、发底牌。
    - 3.3. 超时玩家，服务器直接给出 pass 或者 出一张最小的单牌（如果是出牌的玩家超时）
    - 3.4. 服务器当检测到某一个玩家出完了。停止桌子的所有定时器，进行结算。广播游戏结束的消息。
    3.5. 结算界面提供两个选项。“继续游戏” 、 “离开” 
4. 暂时不使用机器人。直接前端开三个页面。后面机器人可以用python加个robot server。
5. 如果进展顺利，可以周末再加个python的机器人服务。前端再加个骨骼动画。

task03:
2018-08-21 by zxf

1. 屏幕自适应
   - 1.1 确定一种自适应方案
   - 1.2 确定一个设计分辨率
2. bmfont 字体
3. 粒子动画
   - 3.1 找一个粒子动画编辑器
   - 3.2 规范化添加粒子动画的流程
4. spine动画
   - 4.1 找一个spine骨骼动画编辑器
   - 4.2 规范化骨骼动化使用流程

task04
2018-08-27 by zxf

1. 完善游戏流程。
   - 1.1 游戏结算。服务器结算玩家输赢。
   - 1.2 游戏结束的选项
      * 1.2.1 继续游戏。重新再开一局。
      * 1.2.2 退出游戏。离开游戏，回到大厅
   - 1.3 参照腾讯的经典斗地主玩法完善玩法流程（好像是有叫分）
   
2. 后续
   - 2.1 机器人，可以用是python做机器人服务
   - 2.2 数据持久化（最好mysql也可以mongo）
   - 2.3 设计货币系统
   - 2.4 充值、兑换
   - 2.5 玩家行为记录
   - 2.6 增加前端表现（粒子动画、spine动画等）
   - 2.7 后台功能。加一个后台管理网站。可以修改玩家信息（查看、修改）
   
3. 再后续
   - 3.1 机器人 完善AI
   - 3.2 增加游戏玩法。（如4人斗地主等。）
   - 3.3 前端优化。（比如人性化设计）
   - 3.4 数据分析。（比如玩家行为分析）

