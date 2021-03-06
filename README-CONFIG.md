# ADEasy-在线配置说明-v3

- adSwitch----------------------------------------------------------广告总开关
- ads---------------------------------------------------------------广告平台列表
   - appId---------------------------------------平台参数
   - appKey--------------------------------------平台参数
   - appToken------------------------------------平台参数
   - group---------------------------------------平台名称(见ADEasy->ADInfo.GROUP_XXX)
   - weight--------------------------------------平台权重
   - ctrl----------------------------------------控制体
      - whiteMap----------白名单列表
         - country----国家列表
         - model------手机型号列表
         - brand------手机品牌列表
         - channel----渠道列表
      - blackMap----------黑名单列表
         - country----国家列表
         - model------手机型号列表
         - brand------手机品牌列表
         - channel----渠道列表
      - appVer------------app版本范围，正数代表白名单，负数代表黑名单
      - androidVer--------Android版本范围，正数代表白名单，负数代表黑名单
   - placements----------------------------------广告位列表
      - code--------------广告位代号
      - type--------------广告位类型(video,ins,ins_video,banner,splash)
      - weight------------权重
      - ctrl--------------控制体(同上)
- parameterMap-------------------------------------------------------在线参数体
   - key1-----------------------------------------参数列表1(一个key有多个条件下的值)
      - ctrl--------------控制体(同上)
      - value-------------参数值
   - key2-----------------------------------------参数列表2(一个key有多个条件下的值)
      - ctrl--------------控制体(同上)
      - value-------------参数值
- insCtrl-------------------------------------------------------------插屏控制体
   - autoShow--------------------------------------自动显示插屏开关
   - intTime------------------------------------------显示了插屏后，N毫秒内不再显示插屏
   - offset----------------------------------------从第N关开始显示插屏
   - switch----------------------------------------显示插屏的开关
   - maxFill---------------------------------------单页面最大填充数
- videoCtrl-----------------------------------------------------------视频控制体
   - switch----------------------------------------视频开关
   - maxFill---------------------------------------单页面最大填充数
- bannerCtrl----------------------------------------------------------Banner控制体
   - switch----------------------------------------Banner开关
   - maxFill---------------------------------------单页面最大填充数
- splashCtrl----------------------------------------------------------Banner控制体
   - switch----------------------------------------Banner开关
   - maxWaitTime---------------------------------------最大等待时间   
- ctrl---------------------------------------------------------------控制体(同上)

## 示例

```
{
	"adSwitch": true,
	"ads": [
		{
			"appId": "xxxxx",
			"group": "mi",
			"weight": 1,
			"ctrl": {
				"whiteMap": [
					"country":["CN"],
					"brand":["Xiaomi"],
					"model":["Xiaomi 10"]
				],
				"blackMap": [
					"country":["JP"]
				],
				"appVer": [1,1],
				"androidVer": [-1,-1]
			},
			"placements": [
				{
					"code": "df680161af4ee6a79552cb330b0fcc8a",
					"type": "video",
					"weight": 1
				},
				{
					"code": "1e1f1a4432c4f3c7aa1f630a022d0485",
					"type": "ins",
					"weight": 1
				}
			]
		},
		{
			"group": "adMob",
			"weight": 1,
			"placements": [
				{
					"code": "ca-app-pub-3940256099942544/5224354917",
					"type": "video",
					"weight": 1
				},
				{
					"code": "ca-app-pub-3940256099942544/1033173712",
					"type": "ins",
					"weight": 1
				},
				{
					"code": "ca-app-pub-3940256099942544/6300978111",
					"type": "banner",
					"weight": 1
				}
			]
		}
	],
	"parameterMap": {
		"key1": [
			{
				"value": "在线参数1"
			}
		]
	}
}
```
