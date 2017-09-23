# 概述

统计策略主要用于：  
  计算主页各种指标和其他能耗统计信息\r\n\

1.计算运行设备台数：根据设备的OnOff点位计算运行台数，输入：ChOnOff01等，输出为：Number\_ChRunning等；\r\n\  
2.计算设备组功率：根据设备的Power点位计算设备的组功率，输入：ChPower01等，输出为ChGroupPower等及RealtimeTotalPower（总功率）；\r\n\  
3.计算设备组总用电量：根据设备的PowerTotal点位计算设备的组功率，输入：ChPowerTotal01等，输出为ChGroupPowerTotal等及ChillerRoomGroupPowerTotal（总用电量）；\r\n\  
4.计算系统输出冷量：根据系统的供回水温度及流量计算实时输入冷量（RealtimeLoad）；存在二次泵点位时读取SecChWTempReturn01，SecChWTempSupply01，SecChWFlow01；不存在时读取PriChWTempReturn01，PriChWTempSupply01，PriChWFlow01；\r\n\  
5.计算系统能效比：根据功率和冷量计算能效比；输入：RealtimeLoad，RealtimeTotalPower；输出RealtimeEfficiency（kW/RT），RealtimeEfficiencyCOP（kW/kW）；\r\n\  
6.计算冷机平均电流百分比：根据冷机ChOnOff和ChAMPS计算平均电流百分比，输出：AverageLoad01；\r\n\  
7.计算累计冷量、累计用电量、机房平均效率：并带有清零功能。当HomeIndexReset为1时，对上述参数进行清零；\r\n\  
输入：RealtimeLoad，ChillerRoomGroupPowerTotal，HomeIndexReset；输出：CoolingCapacityTotal，PowerConsumptionTotal，EfficiencyTotal\r\n\  
计算输出:\r\n\  
总电量：ChillerRoomGroupPowerTotal，\r\n\  
总冷量：CoolingCapacityTotal，\r\n\  
累计总效率：EfficiencyTotal,\r\n\  
8.计算参数的昨今对比：该功能需要参数10选择是否开启；计算用电量，负荷，平均负荷，平均干球，平均湿球的今日值及与昨日同期的对比值（%）；\r\n\  
IndexCompareAverageRealtimeLoad，IndexCompareAverageOutdoorTdbin，IndexCompareAverageOutdoorWetTemp，\r\n\  
IndexPowerTotalToday，IndexPowerTotalDelta，IndexLoadToday，IndexLoadDelta，IndexAverageLoadToday，IndexAverageLoadDelta，IndexAverageTdbToday，IndexAverageTdbDelta，IndexAverageTwbToday，IndexAverageTwbDelta\r\n\  
9.计算冷机冷却水进出口平均温度：输入：ChEnterCondTemp01、ChLeaveCondTemp01、ChOnOff01等。输出:ChEnterCondAverageTemp,ChLeaveCondAverageTemp\r\n\  
10.计算节能效果：根据手输的12个月的节能率计算平均节能率，并计算因此节省的标煤及CO2排放；输入：PowerSavingRate01等，PowerConsumptionTotal；输出PowerSavingRateAve，PowerSavingTotal，CoalSavingTotal，Co2SavingTotal\r\n\  
11.计算负荷：一般项目为1个末端，如果有多个冷冻水末端，则填入具体数量，冷冻水负荷将多末端负荷进行累加；输入：PriChWTempReturn01,PriChWTempSupply01,PriChWFlow01（二次泵台数大于零时计算根据二次冷冻水点位计算）等,输出：RealtimeLoad\r\n\

# 参数配置

|  |  |  |
| :--- | :--- | :--- |
|输入参数1 | :选择是否显示Log，0=不打log，1=打log  |  |  
| 输入参数2 | 选择本项目所使用的流量单位，流量单位会影响到冷量计算以及效率计算，0=立方米每小时，1=升每秒||
| 输入参数3-9 | 选择本项目的设备台数，如无则填零 |  |  
| 输入参数10 | 选择是否进行部分参数的昨今对比 |  |  
| 输入参数11 | 选择需要计算的末端数量 |  |  
|  |  |  |  
|  |  |  |

# 计算原理

## ChillerRoomGroupPowerTotal（机房累积总耗电量）

累积总耗电量是从电表零点时刻开始的机房的用电量（包括冷机、冷冻泵、冷却泵、冷却塔）。

单位：度电（kWh）

计算方法：每个设备的电表数据的累积量之和。

## CoolingCapacityTotal（机房累积总冷量）

累积总冷量是从某一个时刻起（这个时刻可以通过Reset点进行复位，复位后就从零重新累积），系统的输出冷量对时间的积分值。

单位：冷吨时（tonh）

计算方法：制冷出力\*时间，不断积分累加：

```
制冷出力计算方法：由系统冷冻水流量和总管温差计算
特殊处理：
1. 温差为负时不累加
2. 冷冻泵不运行时不累加
```

## EfficiencyTotal（机房实时效率）

机房实时效率是在某一个时刻的机房效率指标

单位：kw/ton

计算方法：当前制冷出力/当前机房总功率（冷机、冷冻泵、冷却泵、冷却塔）









