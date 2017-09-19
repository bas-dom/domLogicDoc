# 控制策略配置与调试指南

控制策略是dom系统的重要一环，通过Factory软件可以添加、配置、启动策略，从而进行策略测试和调试。

本文档介绍dom系统提供的各类系统策略，实际工程项目中将根据实际工程要求来配置和启动相关策略。

目前dom系统常用的策略有几大类：

## Math数学计算

| 策略标识 | 策略用途描述 |
| :--- | :--- |
| MathAnd | 条件与策略 |
| MathOperation | 加减乘除求反等数学操作 |
| MathIF | 条件策略 |
| MathOneToMul | 单输入分至多输出的扩容策略 |
| MathChange | 当值发生变化时产生输出 |
| MathLinearModification | 线性修正 |
| MathScale | 数值变比放大或缩小 |
| MathMaxMinAvg | 求最大最小或平均的统计策略 |

## 机房标准化计算

| 策略标识 | 策略用途描述 |
| :--- | :--- |
| WetbulbTemp |  根据干球温度和相对湿度计算湿球及焓值|
| StandardHomeIndex |  计算机房效率、功率、运行台数、运行时间统计|




# 设备驱动 #
| 策略标识 | 策略用途描述 |
| :--- | :--- |
| CTToFanCommandAndFeedback |  冷却塔风扇分组为塔的统一反馈和指令设置分发|
|EquipDriverSchneiderVSD| 施耐德变频器modbus直连上位机时的设备驱动| 
|EquipDriverABBVSD| ABB变频器modbus直连上位机时的设备驱动| 
|EquipDriverSimenseVSD| 西门子变频器modbus直连上位机时的设备驱动| 
|EquipDriverYorkYK| 约克离心机modbus直连上位机时的设备驱动| 
|EquipDriverCarrier19XR| 开利19XR离心机modbus直连上位机时的设备驱动| 
|EquipDriverTraneCentrifugal| 特灵三级离心机modbus直连上位机时的设备驱动| 








## 无人值守机房策略

| 策略标识 | 策略用途描述 |
| :--- | :--- |
| StandardChillerStandby | 待机 |
| OneClickStartChillerPlantRoom | 一键开机房 |
| OneClickStartChiller | 一键开机 |
| StandardChillerAddSubControl | 加减机 |



# 诊断

| 策略标识 | 策略用途描述 |
| :--- | :--- |
| DiagnosisCommon | 常规诊断 |
| DiagnosisAHU | AHU诊断 |






# 优化控制

| 策略标识 | 策略用途描述 |
| :--- | :--- |
| StandardChillerPlantRoomOptimizeV1 | 机房优化(V1引擎) |






# 仿真工具

| 策略标识	 | 策略用途描述 |
| :--- | :--- |
| DemoResponse | 仿真机房的开关响应 |



> 更新策略方法：在Factory中右键策略线程-更新库文件即可。



