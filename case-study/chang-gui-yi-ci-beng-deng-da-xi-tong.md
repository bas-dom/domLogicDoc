# 前提

点名必须符合系统规范

# 标准策略清单

| 策略名 | 策略文件名 | 配置关键参数 |
| :--- | :--- | :--- |
| 能效计算策略 | StandardHomeIndex | 设备数量 |
| 一键开关机策略 | StandardOneClickStart | 设备数量、冷量 |
| 一键开机房策略 | StandardOneClickOpenChillerPlantRoom | 机组数量、系统形式 |
| 全变频优化策略 | StandardChillerPlantRoomOptimizeV1 | 优化设定高低限制 |
| 泵塔PID控制 | PIDMultiIO | KP, TI |
| 设备运行时间统计策略 | StandardRunTimeMeter | 设备数量 |
| 设备自动加减策略 | StandardChillerAddSubControl | 设备数量、冷量 |
| 冷机低负荷待机策略 | ChillerStandbyControl | 待机电流百分比条件 |
| 故障诊断策略 | DiagnosisCommon | 设备数量 |

# 计算类策略清单

| 策略名 | 策略文件名 | 配置关键参数 |
| :--- | :--- | :--- |
| 计算冷冻水温差 | MathOperation |  |
| 计算冷却水温差 | MathOperation |  |
| 计算湿球温度及焓值 | WetbulbTemp | 是否计算焓值 |

# 机房仿真策略

| 策略名 | 策略文件名 | 配置关键参数 |
| :--- | :--- | :--- |
| 仿真设备开关反馈和阀门设定反馈 | DemoSettingResponse | 上线后一定要把Enable配置为0，否则会对现场有影响 |



