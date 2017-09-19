# 控制策略配置与调试指南

控制策略是dom系统的重要一环，通过Factory软件可以添加、配置、启动策略，从而进行策略测试和调试。

本文档介绍dom系统提供的各类系统策略，实际工程项目中将根据实际工程要求来配置和启动相关策略。

目前dom系统常用的策略有几大类：

## Math数学类

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

## 无人值守机房策略类

| 策略标识 | 策略用途描述 |
| :--- | :--- |
| StandardChillerStandby | 待机 |
| OneClickStartChillerPlantRoom | 一键开机房 |
| OneClickStartChiller | 一键开机 |
| StandardChillerAddSubControl | 加减机 |



> 更新策略方法：在Factory中右键策略线程-更新库文件即可。



