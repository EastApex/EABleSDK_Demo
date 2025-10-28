
 
 ## Disclaimer
 EastApex Smart Wearable Device SDK iOS
 Disclaimer

 All services provided by EastApex (Guangzhou) Technology Co., Ltd. are designed to assist customers in accelerating the development of products. Any procedures, documents, test results, solutions, support and other materials and information provided during the service process are For reference only, the customer has the right not to use or modify it by himself. The company does not provide any guarantee of completeness, reliability, etc. If any special, incidental or indirect loss is caused during the customer’s use for any reason, this The company does not take any responsibility.
 
 ### Introduction
 The document describes the interface definition and calling instructions between the EA iOS SDK and the device, and is only for the reference and discussion of the smart wearable solution implementers in business cooperation.
 
 The SDK supports all functions of EA devices and integrates multiple Bluetooth chip platforms. Developers are requested to develop corresponding functions according to the functions of the device (such as the function requirement table given by the project manager).

 For example, it supports steps, sleep, heart rate, blood pressure, blood oxygen, body fat, body temperature, ECG, respiration rate, various exercises and so on. For more functions and the latest code, please see the SDK code.

 SDK supports system 13.0 or above, bitcode, current SDK dynamic library compilation environment: OC + Swift.

 For iOS10 and above, a Bluetooth permission statement is required. Info.plist adds the following key: and the corresponding description statement.

 <key>NSBluetoothPeripheralUsageDescription</key>
 <key>NSBluetoothAlwaysUsageDescription</key>

 ---
 Xcode project configuration:

1.Cocopods Pod file addition:

The following are optional SDKs. You can use them as needed

1.1 Supports all EA watches
 `pod 'EABleSDK',        :git => 'https://github.com/EastApex/EABleSDK.git'`

1.2 If you only need to support hisilicon chips, please use the following libraries
 `https://github.com/EastApex/EAHisBleSDK.git`

1.3 If only the Jerry 707 chip is needed, please use the following library
 `pod 'EAJLBleSDK',        :git => 'https://github.com/EastApex/EAJLBleSDK.git'`
 
 
 Then `pod install`

 If not updated to the latest. Use the following command

 `pod update --no-repo-update`

 2.After `Pod install`

 #### Objective-C
 In AppDelegate.m
 ````
 #import <EABluetooth/EABluetooth.h>
 - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    
      // Permissions must be added
      // NSBluetoothAlwaysUsageDescription
      // NSBluetoothPeripheralUsageDescription
      // Please set the error when packing
      // bitcode is set to NO
      // excluded architectures add armv7
     
     // Initialize SDK
     EABleConfig *config = [EABleConfig getDefaultConfig];
     config.debug = YES;
     [[EABleManager defaultManager] setBleConfig:config];
     return YES;
 }
 ````
 #### Swift
 In AppDelegate.swift
 ````
 import EABluetooth

     func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
         // Override point for customization after application launch.
         
         // Permissions must be added
         // NSBluetoothAlwaysUsageDescription
         // NSBluetoothPeripheralUsageDescription
         // Please set the error when packing
         // bitcode is set to NO
         // excluded architectures add armv7
         
         let config = EABleConfig.getDefault();
         config.debug = true;
         let bleManager = EABleManager.default()
         bleManager.bleConfig = config;
         return true
     }
 ````
 
 
 
 ## 免责声明
 东芯泰合（广州）科技有限公司所提供的所有服务内容旨在协助客户加速产品的研发进度，在服务过程中所提供的任何程序、文档、测试结果、方案、支持等资料和信息，都仅供参考，客户有权不使用或自行参考修改，本公司不提供任何的完整性、可靠性等保证，若在客户使用过程中因任何原因造成的特别的、偶然的或间接的损失，本公司不承担任何责任。

 ### 引言
 文档描述EA iOS SDK 与设备的接口定义和调用说明，仅供商务合作的智能穿戴方案实施方参考与讨论。
 
 SDK支持EA设备所有功能，集合了多个蓝牙芯片平台，请开发者根据设备具备的功能(如项目经理给的功能需求表)来开发相应的功能。

 比如支持步数、睡眠、心率、血压、血氧、体脂、体温、心电、呼吸率，多种锻炼运动等等。更多的功能与最新的代码，请看SDK代码。

 SDK支持 系统13.0 以上、bitcode，当前SDK动态库编译环境：OC + Swift。

 iOS10 以上系统，需要蓝牙权限声明。Info.plist添加如下key：和对应的描述声明。

 <key>NSBluetoothPeripheralUsageDescription</key>
 <key>NSBluetoothAlwaysUsageDescription</key>

 ---
 1.Cocopods Pod 文件添加：
 以下为可选SDK，按需使用即可
 1.1 支持所有EA手表
 `pod 'EABleSDK',        :git => 'https://github.com/EastApex/EABleSDK.git'`

 1.2 如果只需要支持海思芯片，请使用如下库
  `https://github.com/EastApex/EAHisBleSDK.git`

 1.3 如果只需要杰里707芯片，请使用如下库
  `pod 'EAJLBleSDK',        :git => 'https://github.com/EastApex/EAJLBleSDK.git'`
  

 然后 `pod install`

 如果没有更新到最新的话。使用下面的命令

 `pod update --no-repo-update`


 2.Pod install 后，
 #### Objective-C
 在AppDelegate.m
 ```
 #import <EABluetooth/EABluetooth.h>
 - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

     
      // 必须 添加 权限
      // NSBluetoothAlwaysUsageDescription
      // NSBluetoothPeripheralUsageDescription
      // 打包时 报错请设置
      // bitcode 设为 NO
      // excluded architectures 添加 armv7
      
     // 初始化SDK
     EABleConfig *config = [EABleConfig getDefaultConfig];
     config.debug = 1;
     [[EABleManager defaultManager] setBleConfig:config];
     return YES;
 }
 ```
 ####  Swift
 在 AppDelegate.swift
 ```
 import EABluetooth

     func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
         // Override point for customization after application launch.
         
         // 必须 添加 权限
         // NSBluetoothAlwaysUsageDescription
         // NSBluetoothPeripheralUsageDescription
         // 打包时 报错请设置
         // bitcode 设为 NO
         // excluded architectures 添加 armv7
          
         let config = EABleConfig.getDefault();
         config.debug = true;
         let bleManager = EABleManager.default()
         bleManager.bleConfig = config;
     }
 ```






