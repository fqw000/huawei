# huawei
使用LM Ultimate修改默认launcher（使用小黑屋或者adb冻结华为桌面，安装第三方launcher）可实现重启自动运行第三方launcher

# 华为/荣耀 HMS系手机安装GMS及googleplay
<pre> 


开动前准备工装：
1.确保手机无谷歌残留。打开应用管理（显示系统程序），搜索google，如有，卸载。（提示：部分需要在设备管理器里解除相应的激活后卸载，以免卸载异常。）
2.下载文件包，包括google系及谷歌服务助手恢复文件。（助手功能已残，这里仅使用其激活功能。）所有文件已上传阿里云,需要在华为应用商店才能彻底卸载。
      //-   huawei.zip: 备份文件，用于安装谷歌服务助手便于激活
      //-   0.apk: MicroG-Huawei fix eloygomezTV 0.2.12.203315-dirty (com.google.android.gms version:203315025)
      //-   1.apk: google服务框架 10 (com.google.android.gsf version:29)
      //-   2.apk: googleplay服务 17.8.57 (com.google.android.gms version:17857037)
      //-   3.apk: googleplay商店 19.5.13-all[0][pr]303545793 (com.android.vending version:81951300)
      //-   4.apk: google帐户管理程序 4.4.4-1227136 (com.google.android.gsf.login version:19)
      //-   5.apk: googleplay服务 20.24.14[120408-319035315] (com.google.android.gms version:202414033)

3.自备梯子。
4.关闭应用分身
5.关闭google账号的两部验证



开动步骤：
严格按照步骤走！
1.解压缩文件包。
使用自带文件管理工具解压，解压缩路径修改为 我的手机  ！！！！，解压后的文件夹内的Huawei.zip解压到默认路径，不要动！
异常处理：解压路径不对会导致下一步操作找不到 从内部存储恢复 选项！！！

2.使用备份恢复功能安装谷歌服务助手。
a.调整系统时间为2020年5月（必要，否则出现异常！）
b.使用备份和恢复功能，点击右上角找到 从内部存储恢复 ，如果没有这个选项： 合适上一步文件解压路径是否完全正确！从新进入备份和恢复选项。
c.选择备份文件打开，勾选应用+数据。
异常处理：华为升级了备份软件，新版修正了部分功能，很多教程是告诉你pc端adb卸载掉com.huawei.Backup，然后安装旧版本的备份软件，没有错，但是失效了，华为做了修正，安装旧版后系统会提示你版本低不能使用备份和恢复功能，可以使用Hisuite恢复备份，但是打开谷歌服务助手会出现 网络链接异常 的提示。主要是只恢复了应用，没有能恢复数据。
d.打开谷歌服务助手-激活，提示始终允许确认
e.恢复系统时间

### 从这里开始一下操作要全程挂梯子，包括过程中重启手机后。
3.开始安装。
1.安装0.apk
安装后打开登录google账号
异常处理：此处要把使用的账号都登录了，如果有多个账号的话。之后就不能再添加了！！

2.依次安装1.apk 、3.apk 、4.apk
3.卸载MicroG
4.安装2.apk
异常处理：安装后通知栏会不停的出现错误通知，不要管，安装后要等这个报错出现。
5.打开play商店，这里应该是已经可以运行了，然后关闭play商店后台
6.打开应用管理（显示系统程序），搜索google：
*paly-强制停止
*谷歌账户管理程序-强制停止-删除数据
*谷歌服务框架-强制停止-清空缓存-删除数据
*重启手机
7.安装2.apk,之后直接重启手机
8.打开play商店，确认运行后关闭后台
9.应用程序管理找到play服务-删除所有数据-确定-强行停止（如果没显示灰色，多点击几次，务必确认按钮变灰色）-卸载
10.安装5.apk，重启手机
11.测试play商店是否正常运行，功能是否正常
12.如异常，回滚以上步骤后重来！！
13.卸载无关程序：谷歌账户管理、谷歌服务助手。
</pre>
### 此时安装的play商店虽能正常运行，但是play保护机制认证还是会显示设备未通过认证，毕竟华为是官方没有合作关系不允许认证的，一般不影响使用，但部分软件版权要求较高，会验证是否通过认证，否则不开放下载。
解决方案：利用GSF设备注册功能来认证（www.google.com/android/uncertified/），主要是提交设备的GSF码来自行认证，adb可以查GSF码，简单点就用DeviceId软件来读取，然后再也没提交注册会提示成功。
GSF（google service framework）

注册成功后，杀死play后台，清空数据，再打开，刷新即可。一般会有稍微延迟才能读取到，多试几次。
至此，完成google 全家桶部署。




