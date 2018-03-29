# KNESP8266LED-IOS
### ************************************************************
### 调试程序
#### IOS版本:https://github.com/kn00/KNESP8266LED-IOS
#### Android版本:https://github.com/kn00/KNESP8266LED-Android
#### 模块芯片程序:https://github.com/kn00/KNESP8266LED-Arduino
### ************************************************************

#### ESP8266模块调试Demo IOS端
#### 主要功能：
#### 1.SmartConfig 一键配网，让模块连上Wi-Fi路由。
#### 2.Socket  APP通过局域网与模块连接，实现本地控制。
#### 3.MQTT  APP与模块通过MQTT服务器，实现远程控制。




##### Socket通信：

##### 实现方法：
##### //客户端socket
##### 
#####
##### @property (nonatomic) GCDAsyncSocket *clinetSocket;

      //1、初始化
      self.clinetSocket = [[GCDAsyncSocket alloc] initWithDelegate:self delegateQueue:dispatch_get_main_queue()];
      
      //2.开始连接
      ipAddress = KNIP;
        port = KNIPPORT;
        [SVProgressHUD showWithStatus:@"正在连接"];
        NSError *err;
        [self.clinetSocket connectToHost:ipAddress onPort:port withTimeout:10.0f error:&err];


