# Grasscutter-error
 Grasscutter错误代码
* ## 4214-错误代码

* 最常见的错误代码，此错误代码有两种情况引起。

* ### 第一种：“UserAssembly.dll”未进行修补。
需要注意的是，在3.1版本之前，用户需要修改的是“global-metadata.dat”。
而3.1版本开始，已经改成修改“UserAssembly.dll”，俗称“UA”。
* 解决方法为：按照以下路径，替换“UserAssembly.dll”。
```
国服替换文件路径为：Yuanshen_Data\Native\UserAssembly.dll
国际服替换文件路径为：GenshinImpact_Data\Native\UserAssembly.dll
历史版本替换文件路径为：GenshinImpact_Data\Managed\Metadata\global-metadata.dat
```
* 需要注意的是，每一个服务器的每一个版本都对应着不同的UserAssembly.dll。请不要混合使用补丁，如果不懂怎么区分客户端是什么版本，请往下看。
* 更换文件之前推荐重命名原文件(UserAssembly.dll)，进行备份。
* ### 第二种：修补完成UA后，代理劫持失败。
* `因为代理劫持失败有时候不会报4214，会报网络繁忙（502），所以这里通用一个解决方法。`
* 代理失败的原因真的非常非常多，请容我慢慢道来。(请使用MHY代理转向)
1. 填写错误IP端口，正确的填写方式是



* 客户端版本区别方式：



先摆了，明天再写，打王者去了。