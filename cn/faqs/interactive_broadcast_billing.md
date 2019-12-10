
---
title: 视频互动直播计费说明
description: 
platform: All Platforms
updatedAt: Tue Dec 10 2019 18:06:08 GMT+0800 (CST)
---
# 视频互动直播计费说明
## 服务用量统计方式




声网会按月统计你的每个 [App ID](https://console.agora.io/) 所对应项目使用的以下两种分钟数：
- [视频分钟数](#vmin)
- [音频分钟数](#amin)




### <a name="vmin"></a>视频分钟数 

如果某用户加入 RTC 频道后订阅了音视频流并且成功接收到了视频，相应时间记为视频分钟数。

我们会对同一用户同时刻订阅的多路视频流的分辨率相加计算集合分辨率，并根据集合分辨率划分视频档位分别计费：



| 视频档位    | 集合分辨率   |
| :---------- | :----------- |
| 高清（HD）  | ≤ 1280 x 720 |
| 超清（HD+） | > 1280 x 720 |





<div class="alert note"><li>集合分辨率会随着被订阅流分辨率的变化而变化。声网会实时统计对应视频分钟数，统计精度为秒。</li><li>小程序端只有高清视频分钟数。</li></div>

**计算集合分辨率**

假设用户 A 在 RTC 频道中有一共 45 分钟，始终订阅 B，C，D 三个视频流用户。A 用户订阅的 B，C，D 用户的视频分辨率如下表所示：

|                | A 订阅 B 的分辨率 | A 订阅 C 的分辨率  | A 订阅 D 的分辨率   | A 的集合分辨率       |
| -------------- | ---------- | -------- | ---------- | -------------------- |
| **前 30 分钟** | 640 x 360  | 640 x 360 | 640 x 360  | 691200 < 1280 x 720  |
| **后 15 分钟** | 640 x 360  | 240 x 180 | 1280 x 720 | 1195200 > 1280 x 720 |

可以看出：

- 前 30 分钟用户 A 的集合分辨率 = B 面积 + C 面积 + D 面积 = 691200 < 1280 x 720, 位于高清档 HD。
- 后 15 分钟用户 A 的集合分辨率 = B 面积 + C 面积 + D 面积 = 1195200 > 1280 x 720,  位于超清档 HD+。

所以，用户 A 的总费用 = 高清档单价 x 30 分钟 + 超清档单价 x 15 分钟 

> 视频分钟数的计费详见[产品计费表](#billing)。


### <a name="amin"></a>音频分钟数 

用户在 RTC 频道内的时间扣除订阅视频流的分钟数后所得剩余时间，无论是否订阅音频流都记为音频分钟数。


<div class="alert note"><li>同时订阅了多路音频流的同一用户的音频分钟数不会被叠加。</li><li>音频分钟数的定义和计算方法也适用于小程序。</li><li>音频分钟数的计费方案详见<a href="#billing">产品计费表</a>。</li></div>





## 产品计费表






| 服务<a name="billing"></a>         | 报价（元/每 1000 分钟） |
| :----------- | :---------------------- |
| 音频         | 7.00                    |
| 小程序音频   | 10.00                   |
| 高清视频 HD  | 28.00                   |
| 小程序视频   | 30.00                   |
| 超清视频 HD+ | 105.00                  |







## 每月 10000 分钟免费时长

详见：[每月一万分钟免费说明](https://docs.agora.io/cn/faq/billing_free)