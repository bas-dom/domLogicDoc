# 概述

冷机脉冲命令模块，用于冷机开启与停止时的脉冲命令。其中，OnOffSetting点值变化时触发逻辑，开机发出OnSettingPointName脉冲，关机发出OffSettingPointName脉冲 ，检测到OnOffStatus成功匹配后返回，可重试10次。

# 详细参数

| 序号 | 参数名称 | 参数意义 | 推荐参数 |
| :--- | :--- | :--- | :--- |
| 1 | OnOffSetting | 开关设置点名字符串 |  |
| 2 | OnOffStatus | 开关状态点名字符串 |  |
| 3 | Reserve02 | 保留 | 1 |
| 4 | Reserve03 | 保留 | 50 |
| 5 | Log | 是否打Log，1打，0不打 |  |
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



