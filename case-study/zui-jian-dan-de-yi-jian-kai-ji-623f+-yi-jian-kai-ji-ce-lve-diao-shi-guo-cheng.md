# 配置前提

确保标准点名规范中冷机相关点位齐全，特别是：（\*\*表示冷机编号，两位，比如01、02……）

ChEnabled\*\*， 不但要有，而且必须值为1（启用）才能使得该冷机可用

ChErr\*\*， 不但要有，而且必须值为0（非报警状态）才能使得该冷机可用

ChAutoMode\*\*， 不但要有，而且必须值为1（远程）才能使得该冷机可用

ChOnOff\*\*

ChMotorRunHour\*\*



如果系统配置了阀门，需要根据标准点名规范配置：

ChEvaValveOnOffSetting\*\*、ChConValveOnOffSetting\*\*




