# 概述

一键开关机策略，用于冷机的一键开机、一键关机。

1、点击一键开机按钮，策略会检查对应设备的Enable和AutoMode两个量，皆为可用时逐个开启冷机阀门，冷却塔（开启总台数的40%），冷却泵，一次泵及冷机。

2、点击一键关机按钮，策略会顺序关闭所有运行的冷机，冷却塔，冷却泵，冷冻泵，冷机阀门。其中，检查到设备不可用、或者开启关闭失败时，会退出一键开机一键关机。

3、开启和关闭失败时，考虑到设备的反应延迟，策略会重新发出命令，重试次数可在策略中配置，默认为3次。

每个设备操作后会等待一定时间，等待时间可在策略中配置，默认为20000ms；

点取消按钮后，策略会在执行完当前的设备操作结束后退出一键开机或者一键关机。

# 详细参数

| 序号 | 参数名称 | 参数意义 | 备注 |
| :--- | :--- | :--- | :--- |
| 1 | m\_nChNum | 冷机台数 |  |
| 2 | m\_nCTNum | 冷却塔台数 |  |
| 3 | m\_nCWPNum | 冷却泵台数 |  |
| 4 | m\_nPriChWPNum | 一次泵台数 |  |
| 5 | m\_nSecChWPNum | 二次泵台数 |  |
| 6 | Ch\_List、                              CT\_List、                             CWP\_List、                         PriChWP\_List、                   SecChWP\_List | 机型1起始编号，机型2起始编号，···机型n起始编号 | 当系统选择公管时才生效，举例：1、2冷机为大机，3为小机。小机对应水泵4、5，那么3冷机，4、5水泵都属于系统2，所以冷机填1,3，水泵填1,4，逗号必须是半角。冷却塔暂不检查，可忽略 |
| 7 | m\_nChRetryNum | 冷机开关状态检查重试次数 | 监测到开关机失败后重试的次数 |
| 8 | m\_bValveCheck | 检查阀门=1，不检查阀门=0 | 表示是否要检查阀门状态 |
| 9 | System\_type | 1=共管，2=一一对应 | 水系统形式 |
| 10 | TimeLag | 等待时间，毫秒 | 默认为20000ms |
| 11 | CTStartPercent | 冷却塔开启频率 | 已无效 |
| 12 | Override | 1=工频加机，0=不工频加机 |  |
| 13 | PriChWPRunningTime | 一键关机一次泵继续运行的时间，单位：min | 配点名 |
| 14 | ChSystemLag | 一键开机后系统稳定运行多久后可进入优化，单位：min |  |
| 15 | CTStartFreqSetting | 冷却塔开启平率设置，0：优化，20-50：指定频率开启 | 0：根据室外干球温度自动计算频率 |
| 16 | ChCheckTimeLag | 冷机开关检测时间，ms | 60000 |
| 17 | ChWaitingTimeLag | 冷机开启后等待时间，ms | 10000 |
| 18 | PriChWPCheckTimeLag | 一次泵开关检测时间，ms | 10000 |
| 19 | PriChWPWaitingTimeLag | 一次泵开启后等待时间，ms | 10000 |
| 20 | CWPCheckTimeLag | 冷却泵开关检测时间，ms | 10000 |
| 21 | CWPWaitingTimeLag | 冷却泵开启后等待时间，ms | 10000 |
| 22 | CTCheckTimeLag | 冷却塔开关检测时间，ms | 10000 |
| 23 | CTWaitingTimeLag | 冷却塔开启后等待时间，ms | 10000 |
| 24 | ValveCheckTimeLag | 冷机阀门开关检测时间，ms | 20000 |
| 25 | ValveChWaitingTimeLag | 冷机阀门开启后等待时间，ms | 20000 |
| 26 | m\_nCTRetryNum | 冷却塔开关机状态检测重试次数 | 10 |
| 27 | m\_nCWPRetryNum | 冷却泵开关机状态检测重试次数 | 10 |
| 28 | m\_nPriChWPRetryNum | 冷冻泵开关机状态检测重试次数 | 10 |
| 29 | m\_nValveRetryNum | 阀门开关状态检测重试次数 | 10 |
| 30 | OneClickClose | 一键关机点 |  |
| 31 | OneClickCancel | 一键关机取消 |  |
| 32 | OneClickHint | 一键开关机信息提示点 |  |
| 33 | enableCondition | 一键开关机条件点，0：不可执行，1：可执行 |  |
| 34 | m\_nChStartNum | 冷机编号开始点，与设备命名编号一致 |  |
| 35 | PIDEnableCT | 冷却塔PID使能点 |  |
| 36 | PIDEnableCWP | 冷却泵PID使能点 |  |
| 37 | PIDEnablePriChWP | 冷冻泵PID使能点 |  |
| 38 | SystemControlStatus | 状态点 |  |
| 39 | LogEnable | 调试LOG开启 |  |
| 40 | ValveOnOffSettingPointName | 调试LOG开启 |  |
| 41 | ValveOnOffPointName | 调试LOG是否开启 |  |
| 42 | FCEnable | FC是否在系统中 |  |
| 43 | OneClickFreeCoolStart | FC系统一键开点名 |  |
| 44 | FCHXChWValvePoint | 板交冷冻阀开关点前缀，不含OnOff之类 |  |
| 45 | FCHXCWValvePoint | 板交冷却阀开关点前缀 |  |
| 46 | FCChWPNoList | FC系统冷冻泵编号 |  |
| 47 | FCCWPNoList | FC系统冷却泵编号 |  |
| 48 | FreeCoolingValveCount | FC系统分支数量 |  |
| 49 | FCFriendChillers | 与FC系统公用辅助设备的冷机清单，逗号分割 |  |
| 50 |  |  |  |
| 51 |  |  |  |
| 52 |  |  |  |
| 53 |  |  |  |
| 54 |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
| 3049 | Reserve03 | 保留 |  |
| 31 | Log | 是否打Log，1打，0不打 |  |
| 6 | OnSettingPointName | 开命令输出脉冲点名字符串 |  |
| 7 | OffSettingPointName | 关命令输出脉冲点名字符串 |  |

# 举例

以开启与关闭某项目\#3螺杆机为例。

1、设置Log为1，开启日志；

2、将开命令与关命令的点名ChOnSetting03、ChOffSetting03添加到实时曲线参数中；

3、将开关设置点名ChOnOffSetting03点值设为1，观察有上升沿发送脉冲，且开关状态点名ChOnOffStatus点值变成1，3\#冷机开启；当将开关设置点名ChOnOffSetting03点值设为0，观察有下降沿发送脉冲，且开关状态点名ChOnOffStatus点值也变成0，3\#冷机关闭。

# 测试记录

| 日期 | 测试发现问题 | 解决结果 |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |



