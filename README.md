## 备注
- havcs v3版本，配置方式发生变化，如要使用旧版本插件到[release][1]页面下载
- 使用教程[传送门][2]
- 建议HA版本 0.104.2 0.107.7
# 更新日志
- 2020-04-09
  1. 修复页面注册方法兼容问题
- 2020-04-06
  1. 增加页面get方法方便检测
  2. 去除失效的自动测试提醒
- 2020-04-05（注意：服务url以及插件配置有调整）
  1. 增加授权页面，可自定义客户端ID，调整各服务url进同一层级（/havcs/）
  2. 设备管理页面增加导出、导入、同步设备、查看插件配置信息的功能
  3. 修复若干bug
- 2020-04-01
  1. 修复页面新增按钮失效、增加新增设备简单校验
- 2020-03-30
  1. havcs v3版本，增加UI配置管理
- 2020-02-23
  1. 旧证书有问题重新进行更新，如使用app的havcs技能（连接mqtt服务器）需要重新替换本地ca.crt文件
- 2020-01-28
  1. 调整"entity_key"配置项（加密entity_id）为可选
- 2020-01-23
  1. 调整设备类型生成逻辑，优先尝试根据设备名称识别生成
- 2020-01-17
  1. 增加企业微信控制功能（测试）
  2. ca证书过期，更新证书
- 2020-01-12
  1. 修复天猫精灵名称识别总是匹配到大类的问题
  2. 修复查询指令返回属性不正确
- 2020-01-02
  1. 刷新token增加返回refresh_token值（天猫精灵要求）
- 2019-11-21
  1. 修复旧版本(0.89)mqtt初始化成功判断失效
- 2019-10-20
  1. 修复havcs_device_type不设置会导致错误、自动生成device_tpye代码出错
- 2019-10-03
  1. 修复指定device_type没有匹配相应的actions
  2. 修复叮咚生成设备信息中的话术信息可能导致的错
- 2019-09-25
  1. 重构音箱网关代码，改用独立文件配置设备信息
  2. 修复取消配置后不能正常清除config entry信息的问题
  3. 调整设备信息属性havcs_enable为havcs_visable，可以设置该设备只对指定平台可见
- 2019-09-17
  1. 修复天猫精灵获取变量信息失败导致初始化失败
- 2019-08-23
  1. HA 0.97.2版本下测试，修复一些小度音箱定时控制指令功能的bug
- 2019-08-20
  1. 小度音箱支持light、switch、inputboolean类型定时打开/关闭指令，需配合common_timer插件使用
- 2019-05-10
  1. 采用新方案，在不影响HA的token超时时间参数情况下，现在可以为token独立设置超时时间
- 2019-05-07
  1. 修复原生input_boolean打开关闭指令失效
  2. 修复token正则匹配不正确
- 2019-05-06
  1. 重新设计配置项更容易设置
  2. 优化三种模式代码逻辑
  3. 整合模式一服务网关，重新测试
  4. 优化调试日志的样式
- 2019-05-03
  1. input_boolean实体支持对调节亮度操作指令映射service（aihome_actions属性）
  2. 指令映射模式下，支持执行多条指令（设置方法有变化，请查看教程）
  2. HA 0.92.1版本测试
- 2019-04-09
  1. 增加设备配置样例（使用packages方式导入即可测试）
  2. 修复叮咚启动不同步信息bug
- 2019-04-07
  1. 精简配置项，增加模式三简略配置说明
- 2019-04-01
  1. 增加首次启动连接mqtt测试功能，如果正常INFO级别日志会显示提示信息，否则请检查appkey以及网络连接
- 2019-03-29
  1. 设备开关状态主动上报（小度音箱），可通过配置文件设置是否上报
  2. HA 0.90.2版本测试
  3. 前端页面优化，上线了密码找回功能
- 2019-03-06
  1. HA 0.88.2版本测试
- 2019-02-27
  1. input_boolean支持直接调用service指令
- 2019-02-22
  1. 增加叮咚设备更新（插件启动触发更新）
  2. 修复京东音箱、小度音箱对input_boolean类的开/关控制
  3. 天猫精灵设备配置命名风格统一
  4. 更改设备发现模式为非主动发现,使用"aihome_device"属性设置设备可被发现
  5. 传感器类设备配置属性精简
  6. 说明文档补充设备配置样例
- 2019-01-xx
  HA 0.86.4 和 HA 0.82.1，本地单机测试

## 调试Tips
1. 根据[教程][3]调整插件的调试级别查看详细的运行日志
2. 配置好插件，启动HA，观看是否有mqtt连接成功信息（app技能接入方式）
3. 授权过程，观看是否有相关的处理日志
4. 说音响指令后，观看是否有相关的处理日志
5. web页面->开发者工具->服务->havcs.reload，观看是否生成设备信息
> WARN: 如需要帮助，请提供以上步骤相对应的日志信息方便定位原因。


[1]: https://github.com/cnk700i/havcs/releases "历史版本"
[2]: https://ljr.im/articles/plugins-havcs-edible-instructions/ "【插件】HAVCS食用说明"
[3]: https://ljr.im/articles/home-assistant-novice-question-set/#3-%E8%B0%83%E8%AF%95%E5%8F%8A%E6%9F%A5%E7%9C%8B%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%97%A5%E5%BF%97 "调试及查看程序运行日志"


