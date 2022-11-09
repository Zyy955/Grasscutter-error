# Grasscutter-error
 Grasscutter错误代码
* ## 4214-错误代码

* 以下`UserAssembly.dll`简称`UA`；`global-metadata.dat`简称`meta`。

* #### 1：元文件(补丁)未进行修补

```
错误代码4214
第一种情况：
3.1版本后需要替换
`Genshin Impact Game\YuanShen_Data\Native`
这个路径下的UserAssembly.dll
这里不教怎么替换（替换都不会，你不适合玩电脑）。
第二种情况：我非常坚信，肯定，100%替换了补丁(也就是UserAssembly.dll)，
那么请检查你的代理，不行就重启电脑，换一个代理等等。

总结：
没有替换补丁(也就是UserAssembly.dll)之前
如果你开启代理，进入客户端界面会显示4214.
替换补丁(也就是UserAssembly.dll)之后
如果你未开启代理，直接进入客户端，同样显示4214.
二者缺一不可。

还有一种情况，我替换了补丁为什么打开客户端没有反应
因为你踏马拿着C2驾照开C1的手动挡
3.1版本的客户端给你打一个7.0的补丁上去，你觉得行不行？

在不懂卸载吧。拜拜~！
```
```
2.6-3.0版本，需要修补的文件为"meta"
国服修补路径：Yuanshen_Data\Managed\Metadata\global-metadata.dat
国际服修补路径：GenshinImpact_Data\Managed\Metadata\global-metadata.dat
```
```
3.1版本开始，需要修补的文件为`UA`。
国服修补文件路径为：Yuanshen_Data\Native\UserAssembly.dll
国际服修补文件路径为：GenshinImpact_Data\Native\UserAssembly.dll
```
* 发生4214正确的做法是，先确定自己的客户端版本，从网上下载修补完成的文件进行替换，替换完成挂代理进入游戏即可。

* 例：
我的客户端版本是`国服3.1`
那我从[rainkavik网盘](https://cloud.rainkavik.com/s/zLEHx?path=%2F%E5%AE%A2%E6%88%B7%E7%AB%AF)下载`国服3.1补丁`
你可以从任意地方下载修补完成的补丁，这里只是推荐。
打开我的游戏客户端，跳转到`Yuanshen_Data\Native`路径下
把此路径下的`UserAssembly.dll`进行重命名`UserAssembly-官服.dll`(防止覆盖，玩官服需要恢复)
把下载的`UserAssembly.dll`复制到当前路径，即可完成元文件修补。
![修补完成且备份元数据布局](https://github.com/Yuer-QAQ/Grasscutter-error/blob/main/Photo/4214-2.png)

* #### 2：修补元数据后，代理劫持失败。
* 如果你修补元数据文件之后，仍然报4214，请检查你的代理，代理问题请往下看。

## 元数据(补丁)更多错误

* 1：Exception has been thrown by the target of aninvocation
![国际服客户端使用国服补丁会出现此错误，解决方法为下载正确的补丁在进行文件替换,可借鉴"4214"。](https://github.com/Yuer-QAQ/Grasscutter-error/blob/main/Photo/4214-3.png)
* 2.Failed to load il2cpp

* ![Failed to load il2cpp](https://github.com/Yuer-QAQ/Grasscutter-error/blob/main/Photo/4214-4.png)

* 本人暂未碰到此错误，据群友所说的是使用其他版本的补丁造成此错误，解决方法为下载正确的补丁在进行文件替换，可借鉴`4214`.

* ## 4206 错误
* 此错误大概率发生在服务端，服务端没有正确配置`config.json`里面的公网/局域网IP导致。
解决方法：修改`config.json`的`accessAddress`修改为公网/局域网IP。
```
"server": {
    "debugWhitelist": [],
    "debugBlacklist": [],
    "runMode": "HYBRID",
    "logCommands": true,
    "http": {
      "bindAddress": "0.0.0.0",
      "bindPort": 443,
      "accessAddress": "127.0.0.1",
//修改"127.0.0.1"为你的公网IP
```
```
    "game": {
      "bindAddress": "0.0.0.0",
      "bindPort": 22102,
      "accessAddress": "127.0.0.1",
//修改"127.0.0.1"为你的公网IP
```
## 代理问题合集

* ## 点击登录转圈然后没反应
* 代理失败或者代理没开

* ## 502 / 4301 / 无法连接服务器
* 代理失败或者代理没开

* ## 开启代理后还是登录了官服
* 代理失败或者代理没开

* ## 4201
检查是否正确安装并信任证书

* ## -9203
一般为代理问题，目前`iOS`使用小火箭会存在此问题

* ## 卡检查更新
尝试正常进游戏一次后再连代理进；检查服务端网络问题，如确实没问题请尝试重启代理端 / 更换代理端口 / 重启服务器

* ## 进门后连接超时
* 服务器开放`UDP 22102`

* ## 进门白屏
* 啥也别说，换个账号解决一切问题。

---

* ## 服务端问题合集
* ## 443端口占用
![443](https://github.com/Lost-Season/Grasscutter-error/blob/main/Photo/443.jpg)
1) 杀掉占用了`443`端口的进程
> * 打开cmd
> * netstat -aon|findstr 443
> * taskkill -f -pid **** #进程PID （可能需要管理员权限）
2) 修改`config.json`的端口
> * 找到40行左右的`"bindPort": 443,`，将443换成其它没有被占用的端口

