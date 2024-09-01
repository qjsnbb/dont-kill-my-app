---
manufacturer:
-华为

---


###在部分EMUI 8、9和10设备上发布App（华为P20、华为P20 Lite、华为Mate 10……）

* *手机设置>电池>应用程序启动*然后将你的应用程序设置为“手动管理”，并确保一切都打开了。

<级班级=“img-block”>
<数字>
<百万毫克学生代表会="/assets/img/huawei/ss_huawei_app_launch_1.png">
<图>1。*手机设置>>应用程序*。此功能可能适用于所有设备，也可能不适用于所有设备。</图>
</数字>

<数字>
<百万毫克学生代表会="/assets/img/huawei/ss_huawei_app_launch_3.png">
<图>2.关闭“自动管理”</图>
</数字>

  <数字>
    <百万毫克学生代表会="/assets/img/huawei/ss_huawei_app_launch_4.png">
    <图>3。一定要启用！所有切换。</图>
  </figure>

</div>

Also for reliable background processes you may need to uninstall PowerGenie as described below.


### Startup manager

Startup manager seems to be a new kid on the block, preventing apps run automatically after the phone starts up.

* Go to Settings > All > Startup manager.

<div class="img-block">
  <figure>
    <img src="/assets/img/huawei/startup.jpg">
    <figcaption>1. *Phone settings > All > Startup manager* and allow the app.</figcaption>
  </figure>
</div>

### EMUI 9+ devices

#### Classic battery optimization

Open Settings, and search for and access Battery optimization. Touch the little inverted triangle next to Don't allow, touch All apps, locate and touch your app, and select Don't allow.

#### PowerGenie

Huawei is extremely inventive in breaking apps on their devices. In addition to all the non-standard power management measures described below, they introduced a new task killer app build right into EMUI 9 on Android Pie.


It is called <b>PowerGenie</b> and it kills all apps that are not on its whitelist. You cannot add custom apps on their pre-defined whitelist. This means there is no other way to fix proper app functionality on Huawei than uninstalling PowerGenie.



不幸的是，这是一个系统应用程序，只能完全卸载使用ADB（Android Debug Bridge）源代码：[XDA](https://forum.xda-developers.com/mate-20-pro/themes/remove-powergenie-to-allow-background-t3890409).


你需要：


1. [安装ADB](https://www.xda-developers.com/install-adb-windows-macos-linux/)在你的电脑上


2.用数据线连接手机


3.使能够[开发人员选项](https://developer.android.com/studio/debug/dev-options.html)


4.在设备上的开发人员选项中启用USB调试


5.在计算机上运行下列命令：

`adb shell pm卸载-k-user 0 com. huawei. powergenie`

`adb shell pm卸载-k-user 0 com. huawei. android. hwaps`

如果应用程序不断被杀死尝试运行`adb壳牌am stopservice`.

We did not yet have this confirmed but it is possible you can alternatively just disable PowerGenie in *Phone settings > Apps*. This setting would need to be re-applied every time you reboot your device.


<div class="caution-box">
Please still follow the steps below - Huawei phones usually have multiple powersaving mechanisms.
<br><br>
Also, you may not have PowerGenie on your device, but your apps may still get killed by another mechanism.
</div>

### EMUI 5.X and 8.X

#### Classic battery optimization

Open Settings, and search for and access Ignore battery optimization. Touch the little inverted triangle next to Allow, touch All apps, locate and touch the app, and select Allow.

### EMUI 6+ devices (and some EMUI 5 devices)

* *Phone settings > Advanced Settings > Battery manager > Power plan* set to *Performance*

* *Phone Settings > Advanced Settings > Battery Manager > Protected apps* – set your app as *Protected*

* *Phone Settings > Apps > Your app > Battery > Power-intensive prompt* [uncheck] and *Keep running after screen off* [check]

* *Phone settings > Apps > Advanced (At the bottom) > Ignore optimisations >* Press *Allowed > All apps >* Find your app on the list and set to *Allow*


### Huawei P9 Plus

* *Phone settings > Apps > Settings > Special access > Ignore battery optimisation >* select allow for your app.


### Huawei Honor 9 Lite, Huawei Mate 9 Pro

* *Phone settings > Battery > Launch* and then set your app to “Manage manually” and make sure everything is turned on.

On EMUI 4 there is no way out, sorry, but you can ask developers of your apps to implement the workaround described in <a href="#developer-solution-section">Developer section</a>
