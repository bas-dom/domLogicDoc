# 配置前提

确保标准点名规范中冷机相关点位齐全，特别是：（\*\*表示冷机编号，两位，比如01、02……）

ChEnabled\*\*， 不但要有，而且必须值为1（启用）才能使得该冷机可用

ChErr\*\*， 不但要有，而且必须值为0（非报警状态）才能使得该冷机可用

ChAutoMode\*\*， 不但要有，而且必须值为1（远程）才能使得该冷机可用

ChOnOff\*\*

ChMotorRunHour\*\*

如果系统配置了阀门，需要根据标准点名规范配置：

ChEvaValveOnOffSetting\*\*、ChConValveOnOffSetting\*\*

# 策略开启和LOG开启

调试时确保一键开机房策略打开，同时 一键开机策略打开（这里的打开是指策略线程上点击运行）。

同时策略参数中的Enable设置为1\(const\)，LogEnable设置为1\(const\)

# 策略流程与调试

`一键开机房策略`会在收到开机房指令（OneClickStartRoom=1）后决策开什么机组，这里假设是选择了2号机组，然后会将OneClickStart02点设置为1，然后交由`一键开机策略`执行。

调试时，先调试一键开机策略，将OneClickStart01设置为1，然后观察系统是否能开机正常，查看一键开机策略的LOG是否有ERROR。

一键开机策略正确无误后，再调试一键开机房策略，测试选机是否正常，指令是否能输出到OneClickStart\*\*。

# 常见问题



StandardOneClickStart策略不可用

> 策略配置的enableCondition参数，检查是否点位存在，或者是否配置为了1\(Const\)

strPriChWPList参数不合法

>



