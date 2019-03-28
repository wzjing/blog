# Android Api changes

## Android Doze App Standby(>=23) [Doc](https://developer.android.com/training/monitoring-device-state/doze-standby.html)
>Android Wake Machanism(安卓休眠机制)

Android常用耗电硬件

* AP (Application Processor >50mA)

* Bp (Baseband Processor 5mA)

* LCD (>100mA)

* WIFI (100mA)

在深度休眠状态下，AP LCD WIFI均处于休眠状态下，开发者可以通过持有一个wake_lock的锁来实现阻止app进入深度休眠。

>JobScheduler

 API21及以上，Android系统提供了JobScheduler来进行任务的调度。JopScheduler可以让开发者把一些需要特殊需求的任务移动到恰当的时机执行，比如把高密度的网络访问任务推迟到有Wifi网络时执行，把高耗电的任务推迟到充电状态或电量充足时执行。目前支持的设置有：NetworkType BatteryNotLow Charging DeviceIdle StorageNotLow等条件设置。使用方法：

 1. 继承JobService并在JobService中添加相关操作

 1. 使用JobInfo.Builder构建执行条件

 1. 最后使用JobScheduler添加计划任务。

>Doze Mode

当手机进入锁屏状态一定时间后，如果检测到手机没有大幅运动（如置于桌面，几乎没有移动），手机将进入低耗电模式，点亮屏幕或充电时会立即退出该模式。在深度休眠状态，所有的后台服务、Wake_lock、JobScheduler以及AlertManager等都会失效（Alert可以使用setAndAllowWhileIdle()和 setExactAndAllowWhileIdle()避开此模式的限制），申请REQUEST_IGNORE_BATTERY_OPTIMIZATIONS权限进入电池优化白名单，但也仅能保留Partial_Wake_Lock。进入低耗电模式后，每个一段时间会有一个30s长的“维护窗口”，应用可以在这个30s内执行一些必要的后台操作，开始时每隔30min进入一次维护窗口，之后时间会逐渐增长。过程：
> 锁屏-[30min]->大幅运动检测[1min]-[30min]->Doze模式-[30min]->维护-[>30min]->维护-[>50min]->维护 .....