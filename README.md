# Grasscutter-error
 Grasscutter错误代码
* ## 4214-错误代码

* 以下`UserAssembly.dll`简称`UA`；`global-metadata.dat`简称`meta`。

* #### 1：元文件未进行修补

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
![修补完成且备份元数据布局](https://github.com/Yuer-QAQ/Grasscutter-error/tree/main/Photo/4214-2.png)

* #### 2：修补元数据后，代理劫持失败。
* 如果你修补元数据文件之后，仍然报4214，请检查你的代理，代理问题请往下看。

* #### Exception has been thrown by the target of aninvocation
* 国际服客户端使用国服补丁会出现此错误，解决方法请看`4214`
![Exception has been thrown by the target of aninvocation](https://github.com/Yuer-QAQ/Grasscutter-error/tree/main/Photo/4214-3.png)

* ## 4206 错误
此类错误大多数情况为代理未正确配置，可尝试

* ### 仔细检查代理端 / 服务端所有配置

* ### 重启代理端 / 重启服务器

* ### 开启代理后运行游戏，检查服务端和代理的日志，如果代理中

没有`mihoyo.com`/`hoyoverse.com`子域的请求或者没刷新任何日志，则为客户端代理配置错误

有`mihoyo.com`/`hoyoverse.com`子域的请求，但报`TLS handshake failed`，则为客户端未安装对应服务端的证书，或服务端不能连接到相应域名

有`mihoyo.com`/`hoyoverse.com`子域的请求，但报拒绝连接等错误，可能是服务端网络问题导致无法连接米哈游服务器

如果代理没有报错，则应为服务端问题，检查服务端配置或者更新服务端

* ### 如仍无法解决，可尝试以下操作：

关闭代理正常启动游戏检查更新完后再次开代理进入游戏

修改`config.json`中`server.http.accessAddress`为`dispatchcnglobal.yuanshen.com`

另外，据经验此问题可能是服务器问题，尝试更换

* ## 登陆账号提示网络错误 / 网络超时
确认配置无误可尝试修改`config.json`中`server.http.accessAddress`为`dispatchcnglobal.yuanshen.com`然后进一遍游戏，如果能进去，就可以将此配置还原

* ## 点击登录转圈然后没反应
如果点击后服务端日志有成功登录的提示，关掉登录窗口即可进入游戏 (手机版特供 bug)
如无，请检查服务端代理是否正确运行，是否假死 (尝试重启)

* ## 502 / 4301 / 无法连接服务器
绝对是你没正确配置，自行检查

* ## 登陆后检查更新失败
如果代理日志中有`mihoyo.com`/`hoyoverse.com`子域的请求，但报拒绝连接等错误，可能是服务端网络问题导致无法连接米哈游服务器

* ## 开启代理后还是登录了官服
有其他代理冲突；服务端没有正确运行

* ## 4201
检查是否正确安装并信任证书

* ## -9203
一般为代理问题，已知 iOS 使用小火箭会存在此问题

* ## 卡检查更新
尝试正常进游戏一次后再连代理进；检查服务端网络问题，如确实没问题请尝试重启代理端 / 更换代理端口 / 重启服务器

* ## 进门后连接超时
放通 UDP 22102 。。。或者你眼瞎只改了一个 ip。。。

* ## 进门白屏
你乱改数据库改出问题了，或者服务端系统有什么大病不兼容 Java

先摆了，明天再写，打王者去了。
