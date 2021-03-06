# 调用接口

## 1、初始化

调用该函数初始化广告SDK，该函数需要在[GameSDK.init\(\)](../../ji-shu-dui-jie/ke-hu-duan-dui-jie/tiao-yong-jie-kou.md#chu-shi-hua)之后调用。

函数：

```text
AdSDK.init();
```

#### 注意：为避免广告填充率不足时，游戏出现因无法请求到广告而卡界面的问题，请开发者务必监听请求广告失败的回调，并进行处理。

### 2、创建横幅广告

调用该函数创建横幅广告，支持多个banner横幅创建

函数：

`var banner=AdSDK. createBannerAd(adId,bannerAdId,position)` 

参数说明：

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>&#x53C2;&#x6570;</b>
      </th>
      <th style="text-align:left"><b>&#x542B;&#x4E49;</b>
      </th>
      <th style="text-align:left"><b>&#x7C7B;&#x578B;</b>
      </th>
      <th style="text-align:left"><b>&#x662F;&#x5426;&#x4E3A;&#x7A7A;</b>
      </th>
      <th style="text-align:left"><b>&#x5907;&#x6CE8;</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">adId</td>
      <td style="text-align:left">&#x5E7F;&#x544A;&#x5E8F;&#x53F7;ID</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x975E;&#x7A7A;</td>
      <td style="text-align:left">&#x6807;&#x8BC6;&#x5E7F;&#x544A;</td>
    </tr>
    <tr>
      <td style="text-align:left">bannerId</td>
      <td style="text-align:left">&#x5E7F;&#x544A;&#x4F4D;ID</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x975E;&#x7A7A;</td>
      <td style="text-align:left">&#x5E7F;&#x544A;&#x4F4D;ID&#xFF0C;&#x9700;&#x7533;&#x8BF7;</td>
    </tr>
    <tr>
      <td style="text-align:left">position</td>
      <td style="text-align:left">&#x5E7F;&#x544A;&#x4F4D;&#x7F6E;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x975E;&#x7A7A;</td>
      <td style="text-align:left">
        <p>1&#x3001;&#x9876;&#x90E8;&#xFF1B;2&#x3001;&#x5E95;&#x90E8;&#xFF1B;3&#x3001;&#x4E2D;</p>
        <p>&#x95F4;</p>
      </td>
    </tr>
  </tbody>
</table>### 3、展示横幅广告

横幅广告组件默认是隐藏的，调用广告实例的show函数展示横幅广告，返回值为Promise,banner广告显示操作的结果

_**建议在监听到横幅广告加载成功的回调函数中调用该函数。**_

函数：

`banner.show().then(() => console.log('banner 广告显示成功'), err => { console.log('banner 广告显示失败') })`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| 无 |  |  |  |  |

### 4、隐藏横幅广告

调用广告实例的hide函数隐藏横幅广告

函数：

`banner.hide ()`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| 无 |  |  |  |  |

### 5、销毁横幅广告

调用广告实例的destroy函数销毁横幅广告

函数：

`banner.destroy ()`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| 无 |  |  |  |  |

### 6、监听横幅广告加载成功事件

调用该函数注册回调函数，当加载广告成功时函数会执行

函数：

`banner.onLoad (func);` 

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 横幅广告加载成功回调函数 | function | 非空 | 游戏定义回调函数 |

### 7、监听横幅广告加载错误事件

调用该函数注册回调函数，当加载广告失败时函数会执行

函数：

`banner.onError (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 横幅广告加载失败回调函数 | function | 非空 | 游戏定义回调函数 |

### 8、监听横幅广告尺寸变化事件

调用该函数注册回调函数，监听广告尺寸变化事件

函数：

`banner.onResize (func)`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 横幅广告尺寸变化事件的函数回调 | function | 非空 | 游戏定义回调函数 |

### 9、取消监听横幅广告加载成功事件

调用该函数注册回调函数，取消监听广告加载成功事件

函数：

`banner.offLoad (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 横幅广告加载事件的回调函数 | function | 非空 | 游戏定义回调函数 |

### 10、取消监听横幅广告加载错误事件

调用该函数注册回调函数，取消监听广告加载错误事件

函数：

`banner.offError (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 横幅广告错误事件的回调函数 | function | 非空 | 游戏定义回调函数 |

### 11、取消监听横幅广告尺寸变化事件

调用该函数注册回调函数，取消监听广告尺寸变化事件

函数：

`banner.offResize  (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 横幅广告尺寸变化事件的回调函数 | function | 非空 | 游戏定义回调函数 |

### 12、创建插屏广告

调用该函数创建插屏广告

函数：

`var interstitialAd = AdSDK.createInterstitialAd(adId，interstitialAdId, style)`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| adId | 广告序号ID | String | 非空 | 标识广告 |
| interstitialAdId | 广告位ID | String | 非空 | 插屏广告位ID，需申请 |
| style | 展示样式 | Int | 非空 | 1、全屏；2、半屏 |

### 13、展示插屏广告

调用广告实例的show函数展示插屏广告，返回值Promise，返回广告显示操作的结果

_**建议在监听到插屏广告加载成功的回调函数中调用该函数。**_

函数：

`interstitialAd.show().then(() => console.log('interstitialAd 广告显示成功'), err => { console.log('interstitialAd 广告显示失败') })`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| 无 |  |  |  |  |

### 14、隐藏插屏广告

调用广告实例的hide函数隐藏插屏广告

函数：

`interstitialAd.hide ()；`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| 无 |  |  |  |  |

### 15、销毁插屏广告

调用广告实例的destroy函数销毁插屏广告

函数：

`interstitialAd.destroy ()；`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| 无 |  |  |  |  |

### 16、监听插屏广告加载成功事件

调用该函数注册回调函数，当加载广告成功时函数会执行

函数：

`interstitialAd.onLoad (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 插屏广告加载成功回调函数 | function | 非空 | 游戏定义回调函数 |

### 17、监听插屏广告加载错误事件

调用该函数注册回调函数，当加载广告错误时函数会执行

函数：

`interstitialAd.onError (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 插屏广告加载失败回调函数 | function | 非空 | 游戏定义回调函数 |

### 18、监听插屏广告尺寸变化事件

调用该函数注册回调函数，监听广告尺寸变化事件

函数：

`interstitialAd.onResize ( func )`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 插屏广告尺寸变化事件的函数回调 | function | 非空 | 游戏定义回调函数 |

### 19、取消插屏广告加载成功事件

调用该函数注册回调函数，取消监听广告加载成功事件

函数：

`interstitialAd.offLoad (func);`  

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 插屏广告加载成功事件的函数回调 | function | 非空 | 游戏定义回调函数 |

### 20、取消监听插屏广告加载错误事件

调用该函数注册回调函数，取消监听广告加载错误事件

函数：

`interstitialAd.offError (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 插屏广告加载错误事件的函数回调 | function | 非空 | 游戏定义回调函数 |

### 21、取消监听插屏广告尺寸变化事件

调用该函数注册回调函数，取消监听广告尺寸变化事件

函数：

`interstitialAd.offResize  (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 插屏广告尺寸变化事件的函数回调 | function | 非空 | 游戏定义回调函数 |

### 22、创建视频广告

调用该函数创建视频广告

函数：

`var videoAd=AdSDK.createRewardedVideoAd (adId，videoAdId, screenOrientation)`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| adId | 广告序号ID | String | 非空 | 标识广告 |
| videoAdId | 广告位ID | String | 非空 | 视频广告位ID，需申请 |
| screenOrientation | 展示样式 | Int | 非空 | 1、横屏；2、竖屏 |

### 23、展示视频广告

调用该函数展示视频广告，返回值Promise，视频广告显示操作的结果。

_**建议在监听到视频广告加载成功的回调函数中调用该函数。**_

函数：

`videoAd.show().then(() => console.log('videoAd 广告显示成功'), err => { console.log('videoAd 广告显示失败') })`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| adId | 广告序号ID | String | 非空 | 标识广告 |

### 24、隐藏视频广告

调用该函数隐藏视频广告

函数：

`videoAd.hide()；`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| adId | 广告序号ID | String | 非空 | 标识广告 |

### 25、监听视频广告加载成功事件

调用该函数注册回调函数，当加载广告成功函数会执行

函数：

`videoAd.onLoad (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 视频广告加载成功回调函数 | function | 非空 | 游戏定义回调函数 |

### 26、监听视频广告加载错误事件

调用该函数注册回调函数，当加载广告失败函数会执行

函数：

`videoAd.onError (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 视频广告加载失败回调函数 | function | 非空 | 游戏定义回调函数 |

### 27、监听视频广告关闭按钮点击事件

关闭视频广告时该函数执行

函数：

`videoAd.onClose (func)`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 视频广告关闭时回调该函数 | function | 非空 | 游戏定义回调函数 |

### 28、取消监听视频广告加载成功事件

调用该函数注册回调函数，取消监听视频广告加载成功事件

函数：

`videoAd.offLoad (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 视频广告加载事件的函数回调 | function | 非空 | 游戏定义回调函数 |

### 29、取消监听视频广告加载错误事件

调用该函数注册回调函数，取消监听视频广告加载错误事件

函数：

`videoAd.offError(func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 视频错误事件的回调函数 | function | 非空 | 游戏定义回调函数 |

### 30、取消监听视频广告点击关闭按钮事件

调用该函数注册回调函数，取消监听视频广告点击关闭按钮事件

函数：

`videoAd.offClose (func);`

参数说明：

| **参数** | **含义** | **类型** | **是否为空** | **备注** |
| :--- | :--- | :--- | :--- | :--- |
| func | 用户点击 关闭广告 按钮的事件的回调函数 | function | 非空 | 游戏定义回调函数 |

