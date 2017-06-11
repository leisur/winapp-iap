**

## STM32串口IAP的上位机工具部分使用说明

> 终于我们来到这一篇，现在我们来简单说一下上位机工具的基本配置及使用。

1. 该项目实现通过PC的串口对STM32系列MCU进行IAP。

2. 该项目包含三个部分（三套代码）：
    
    - 运行在STM32平台的Bootloader；
    - 运行在STM32平台的App(我做了两个，一个是支持usmart的重量版，另一个是很简洁的轻量版)；
    - 运行在Windows平台的上位机操作工具。

3. 本篇是属于运行在windows平台的上位机工具部分，另外两篇介绍请参阅：
    
    - [windows平台操作工具](https://github.com/havenxie/winapp-iap)
    - [STM32平台的App(usmart版)](https://github.com/havenxie/stm32-iap-bootloader)    
        或[STM32平台的App(轻量版)](https://github.com/havenxie/stm32-iap-app_lite)
	
4. 这套代码使用C#基于.net4.0开发。我用的是vs2017.

*****

## 工具使用方法：

1. 通过jlink或者其他工具将与你的硬件相对应的bootloader烧入你的片子。

2. 运行该上位机工具

3. 通过串口将硬件和PC进行连接

4. 选择对应的串口

5. 波特率选择115200

6. 打开串口

7. 选择你待升级的app固件

8. 包长度随你选

9. 点击"更新固件Update"按钮后固件将会自动烧录到你的片子。

10. 烧完之后自动运行app。

### 其他

- "读取固件Upload"按钮将会把芯片内的固件读出来（这个功能还没有做）

- "擦除固件Erase"按钮将会把App部分的固件擦除，之后运行bootloader的菜单。

- "进入IAP菜单"按钮将会软件自动复位硬件，然后运行bootloader的菜单。

- "运行App"按钮将会软件自动复位硬件，然后跳转到app部分去执行。

- "清除窗口"按钮将会把信息视窗的内容清空。

- 除了这些按钮你还可以通过在信息视窗输入相应的指令并回车以完成不同的操作，这里就不过多讲解了，你可以自己试一试。

注：bootloader部分只需要烧录一次即可，之后所有操作都通过上位机工具完成。


*****

## 版本说明：
- 用户使用master版本即可。
	

