测试机环境：windows

# 需要预安装和运行的软件

1. core（安装参考coreManual）
2. Factory及调试工具
3. omsite客户端
4. 项目配置文件S3db（必须有配置策略线程中包含DemoResponse.dll
   > 仿真策略DemoResponse.dll用于仿真常见设备和阀门等的动作响应，只在仿真模式下生效

# 测试运行步骤

1. 运行调试工具，将环境配置为“仿真”而不是现场模式
2. 将s3db拷贝入core，确保是core下唯一的s3db，运行core.exe
3. 运行logicEngine.exe
4. 用Factory在策略上点击连接调试，登录127.0.0.1，开启需要调试的策略线程（右键-运行）
5. 在调试工具的策略面板的工具栏中查看策略LOG，观察是否有ERROR，根据ERROR调整配置；如果没有ERROR信息，那么观察执行结果和过程提示，是否符合预期。
6. 策略可以同时开启，也可以逐步打开。

# 注意点

1. 新建策略线程和策略后，建议重启logicEngine.exe
2. 更新策略库文件后，建议重启LogicEngine.exe
3. 修改策略配置参数后，立即会生效，不需要重启



