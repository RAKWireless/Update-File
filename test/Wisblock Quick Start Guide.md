---
typora-copy-images-to: assets
---

# Wisblock Quick Start Guide

[TOC]



## 1. Introduction

Wisblock is an amazing product built by RAK company for IoT industry. It can build circuits like building blocks quickly to realize your idea, and through high-speed connectors and fasteners interconnection, it can directly compose the reliable industrial products.

Wisblock consists of Wisbase board, Wiscore board, and WisIO board.

RAK5005-O is the Wisbase board which can be connected with Wiscore and WisIO through the connector of the board, and provides direct databus interconnection. Wisbase module also integrates the power supply circuit to realize low power battery power supply. In order to facilitate users, Wisbase has reserved USB ports, indicator lights, keys and extended IO interfaces.

RAK4631 is the Wiscore board which consists of nRF52840 and SX1262. It supports LoRa and BLE functions, and supply a rich resource MCU so that you can program it if you want.

Wisblock is not only functional testability product in product development verification stage, but also industrial products oriented to mass production. It uses a high-speed connector to ensure the integrity of the signal. At the same time, it is equipped with fastening screw, which can be used in vibration environment. And Wisblock can be used reliably in various civil and industrial scenarios through rigorous reliability tests.

Wisblock uses a compact stacked hardware design, which integrates various computing, connecting and sensor circuits in the size of 60*30mm. The compact size makes it easy for users to build in various customized housings to achieve complete products. RAK also have a series of housings for Wisblock modules, which can meet the requirements of various protection levels.

## 2. Safety information

Please read the following items carefully so that Wisblock can be used safely.

### 2.1 Hardware

1) Please use Wisblock according to its hardware specification, including the power supply, the temperature of using, the battery, and so on.

2) Don't submerge Wisblock in liquids, and don't place Wisblock where water can reach.

3) Don't power Wisblock using other power sources which RAK hasn't suggested.



### 2.2 Software

1)  There is already a bootloader in every Wisblock core board MCU when you receive the device, so that you needn't to flash the bootloader again. Normally, you only need to use it directly or upload new code into it through Arduino IDE. If you accidentally erase the bootloader, please contact with us on RAK forum: forum.rakwireless.com.

2) Please don't unplug any hardware connector when you are uploading code into it, otherwise Wisblock may become unresponsive.



## 3. Hardware Setup

### 3.1 Base Board --- RAK5005-O

RAK5005-O is the Wisblock base board which can connect with the core board and other sensor boards through some slots. RAK5005-O has an USB interface which connect with the core MCU's USB pins so that you can use Arduino IDE to upload and debug it directly.

![image-20200630170056520](assets/image-20200630170056520.png)

Please note: as you see, there are 6 slots on RAK5005-O, "CPU SLOT" is used for the core board which has the main MCU, "IO SLOT" is used for IO extension, for example, RS485 board, 4~20mA/0~5V board, Wi-Fi board, Cellular board. "SLOT A", "SLOT B", "SLOT C", and "SLOT D" are used to connect with I2C board, while "SLOT A" can be used for GPS board too.

You can have a look at the



### 3.2 Core board --- RAK4631

RAK4631 is the core board of Wisblock, because the MCU stay on this board.

<img src="assets/image-20200630171353822.png" alt="image-20200702164625941" style="zoom:50%;" />



![image-20200702164625941](assets/image-20200702164625941.png)

RAK4631 consists of a nRF52840 MCU and a SX1262 LoRa chip mainly. The final Arduino  code will be uploaded into nRF52840 actually. This core board supports BLE and LoRa features. You can connect it with RAK5005-O base board with slot, and program it through the USB interface on RAK5005-O through Arduino IDE.

![RAK5005 connect RAK4631](assets\RAK5005 connect RAK4631.PNG)



### 3.3 Sensor Boards

#### 3.3.1 Temperature & Humidity sensor board --- RAK1901

RAK1901 is a Temperature & Humidity sensor board with an I2C interface, which means it can be connected with RAK5005-O through the I2C slot (SLOT A/B/C/D).

<img src="assets\image-20200702110638518.png" alt="image-20200702110638518" style="zoom: 50%;" />

More information about RAK1901, please have a look at the following link:

> **(RAK1901 introduction document link)**



#### 3.3.2 Pressure sensor board --- RAK1902

RAK1902 is a pressure sensor board with an I2C interface, which means it can be connected with RAK5005-O through the I2C slot (SLOT A/B/C/D).

<img src="assets\RAK1902.PNG" alt="RAK1902" style="zoom:50%;" />

More information about RAK1902, please have a look at the following link:

> **(RAK1902 introduction document link)**



#### 3.3.3 Optical sensor board --- RAK1903

RAK1903 is an optical sensor board with an I2C interface, which means it can be connected with RAK5005-O through the I2C slot (SLOT A/B/C/D).

<img src="assets\RAK1903.PNG" alt="RAK1903" style="zoom:50%;" />

More information about RAK1903, please have a look at the following link:

> **(RAK1903 introduction document link)**



#### 3.3.4 3-axis acceleration sensor board --- RAK1904

RAK1904 is a 3-axis acceleration sensor board with an I2C interface, which means it can be connected with RAK5005-O through the I2C slot (SLOT A/B/C/D).

<img src="assets\RAK1904.PNG" alt="RAK1904" style="zoom:50%;" />

More information about RAK1904, please have a look at the following link:

> **(RAK1904 introduction document link)**



#### 3.3.5 Environment sensor board --- RAK1906

RAK1906 is an environment sensor board with I2C interface, which means it can be connected with RAK5005-O through the I2C slot (SLOT A/B/C/D).

<img src="assets\RAK1906.PNG" alt="RAK1906" style="zoom:50%;" />

More information about RAK1906, please have a look at the following link:

> **(RAK1906 introduction document link)**



#### 3.3.6 GPS board --- RAK1910

RAK1910 is a GPS board with UART interface, which means it can only be connected with RAK5005-O through SLOT A.

<img src="assets\RAK1910-1.PNG" alt="RAK1910-1" style="zoom:50%;" />                                                                                                    <img src=".\assets\RAK1910-2.PNG" alt="RAK1910-2" style="zoom:50%;" /> 



![image-20200702160832581](assets/image-20200702160832581.png)

More information about RAK1910, please have a look at the following link:

> **(RAK1910 introduction document link)**



#### 3.3.7 WiFi board --- RAK2305

RAK2305 is a WiFi board which is ESP32 module actually, and it can only be connected with RAK5005-O through the IO SLOT.

<img src="assets\RAK2305-1.PNG" alt="RAK2305-1" style="zoom:50%;" />         <img src=".\assets\RAK2305-2.PNG" alt="RAK2305-2" style="zoom:50%;" /> 



![image-20200702161818627](assets/image-20200702161818627.png)

More information about RAK2305, please have a look at the following link:

> **(RAK2305 introduction document link)**



#### 3.3.8 Cellular board --- RAK5860

RAK5860 is a cellular board which uses Quectel BG77 module actually, and it can only be connected with RAK5005-O through IO SLOT.

<img src="assets\RAK5860.PNG" alt="RAK5860" style="zoom:50%;" />   <img src="assets\RAK5860-1.PNG" alt="RAK5860-1" style="zoom:50%;" />  



![image-20200702162227112](assets/image-20200702162227112.png)

More information about RAK5860, please have a look at the following link:

> **(RAK5860 introduction document link)**



#### 3.3.9 4~20mA board --- RAK5801

RAK5801 is an IO board which can connect with any 4~20mA sensors. This board can only be connected with RAK5005-O through IO SLOT.

<img src="assets\RAK5801.PNG" alt="RAK5801" style="zoom:50%;" />

More information about RAK5801, please have a look at the following link:

> **(RAK5801 introduction document link)**



#### 3.3.10 0~5V board --- RAK5811

RAK5811 is an IO board which can connect with any 0~5V sensors. This board can only be connected with RAK5005-O through IO SLOT.

<img src="assets\RAK5811.PNG" alt="RAK5811" style="zoom:50%;" />

More information about RAK5811, please have a look at the following link:

> **(RAK5811 introduction document link)**



#### 3.3.11 RS485 board --- RAK5802

RAK5802 is an IO board which can connect with any RS485 sensors. This board can only be connected with RAK5005-O through IO SLOT.

<img src="assets\RAK5802.PNG" alt="RAK5802" style="zoom:50%;" />

More information about RAK5802, please have a look at the following link:

> **(RAK5802 introduction document link)**



#### 3.3.12 Sensor conversion board --- RAK1920

RAK1920 is a sensor conversion board which can connect with any Microbus, Grove, or Qwiic sensors. This board can only be connected with RAK5005-O through IO SLOT.

<img src="assets\RAK1920.PNG" alt="RAK1920" style="zoom:50%;" />

More information about RAK1920, please have a look at the following link:

> **(RAK1920 introduction document link)**



#### 3.3.13 IO extension board --- RAK5804

RAK5804 is an IO extension board which is used to extent more IO interface, and it can only be connected with RAK5005-O through IO SLOT.

<img src="assets\RAK5804.PNG" alt="RAK5804" style="zoom:50%;" />

More information about RAK5804, please have a look at the following link:

> **(RAK5804 introduction document link)**



#### 3.3.14 OLED --- RAK1921





### 3.4 Antennas





### 3.5 Battery

Please use the battery which RAK suggest, and connect the battery with RAK5005-O as follow:

![image-20200702193814577](assets/image-20200702193814577.png)



### 3.6 Enclosure





## 4. Arduino IDE Download and Installation

You should use Arduino IDE for Wisblock coding and programming.

Please download the Arduino IDE on the Arduino official website:

https://www.arduino.cc/en/Main/Software 

You can see the current version of Arduino IDE is V1.8.13, and there are several versions for Windows, Linux, and Mac OS X.

![image-20200703115901208](assets/image-20200703115901208.png)

Just download the correct version of Arduino IDE from here.



### 4.1 Install in Windows

Now, let's install the Arduino IDE, which you just download, on a Windows PC.

![image-20200703115937421](assets/image-20200703115937421.png)

"I Agree"

![image-20200703115958670](assets/image-20200703115958670.png)

"Next"

![image-20200703120015822](assets/image-20200703120015822.png)

"Install"

![image-20200703120034198](assets/image-20200703120034198.png)

After 100% progress, Arduino IDE has been installed successfully.

![image-20200703120054258](assets/image-20200703120054258.png)



### 4.2 Install in Linux

In Linux, there is no install process actually, just a process of uncompression, then you can open Arduino IDE successfully.



### 4.3 Install in Mac OS X

In Mac OS X, it is almost same with Linux, there is no install process actually, just a process of uncompression, then you can open Arduino IDE successfully.



### 4.4 Open Arduino IDE

![image-20200703120123062](assets/image-20200703120123062.png)

As you see, Arduino IDE has mainly 5 parts:

1) IDE option menu

You can configure some general parameters such as the serial port, the board information, the libraries, the edit parameters, and so on.

2) Operating buttons

You can verify/compile source code, upload the compiled code into Wisblock, open a new Arduino IDE window, open an exist application, or save the current application. 

![image-20200703120140901](assets/image-20200703120140901.png)



3) Code area

You can edit the source code which will be compiled and uploaded into Wisblock later in this area.

4) State area

5) Output message area

You can see the output message in this area, no matter failed information and success information.



## 5. Configuration On Arduino IDE

Once Arduino IDE has been installed successfully, and you've understood the mainly parts of Arduino IDE, we can do some configuration changes on Arduino IDE so that it can be adapted to Wisblock.

We use https://github.com/adafruit/Adafruit_nRF52_Arduino and do as below:

- Open Arduino IDE

- Go into Preferences

  ![image-20200702170623007](assets/image-20200702170623007.png)

- Add https://www.adafruit.com/package_adafruit_index.json as an 'Additional Board Manager URL'

  ![image-20200702170822034](assets/image-20200702170822034.png)

- Restart the Arduino IDE

- Open the Boards Manager from the Tools -> Board menu

  ![image-20200702171102982](assets/image-20200702171102982.png)

- Search and install "Adafruit nRF52" as the following image shows, and install it. It is the BSP actually.

  ![image-20200702171813125](assets/image-20200702171813125.png)

- Once the BSP is installed, select 'Nordic nRF52840DK(PCA10056)' from Tools -> Board -> Adafruit nRF52 Boards, which will update your system config to use the right compiler and settings for the nRF52840.

  ![image-20200702173222325](assets/image-20200702173222325.png)

- Replace the pin map in Adafruit library with RAK header. You can download the RAK header file from https://bitbucket.org/Fomi-RAK/wisblock-rak4630-development/src/master/bsp/variants.h , and copy it to the following folder instead of the original header file:

  - macOS : `~/Library/Arduino15/packages/adafruit/hardware/nrf52/0.20.1/variants/pca10056/`
  - Linux : `~/.arduino15/packages/adafruit/hardware/nrf52/0.20.1/variants/pca10056/`
  - Windows: `%APPDATA%\Local\Arduino15\packages\adafruit\hardware\nrf52\0.20.1\variants\pca10056\`

  OK, we've configured Arduino IDE correctly and install the BSP successfully!

## 6. Load Examples

RAK has supplied many examples source code on Github for Wisblock:

https://bitbucket.org/Fomi-RAK/wisblock-rak4630-development/src/master/examples/

![image-20200703122036065](assets/image-20200703122036065.png)

  

![image-20200703122058277](assets/image-20200703122058277.png)![image-20200703122125471](assets/image-20200703122125471.png) ![image-20200703122250989](assets/image-20200703122250989.png)

You can use Wisblock directly or make their customized code according to these examples source code. What you need to do is just to load one of these examples into Arduino IDE by opening a .ino file in RAK examples, in this document, we use "ble_proximity_sensing.ino":

![image-20200702191428103](assets/image-20200702191428103.png)

Now, we can compile it directly according to the section 7, or do some customized code before compiling it If you want.

About customization code, you can have a look at the section 9 for more details.



## 7. Compiling Project

The compiling process is very easy, what you need to do is just to click the Verify/Compile button on Arduino IDE:

![image-20200703120229579](assets/image-20200703120229579.png)

Then it will start to compile:

![image-20200702191717737](assets/image-20200702191717737.png)

After compiling successfully, you can see some information in the output message area, and the state is "Done compiling":

![image-20200702191352945](assets/image-20200702191352945.png)

Now, you can connect your Wisblock hardware with your PC, and upload the code into it.

## 8. Uploading to Wisblock

Before uploading, please make sure that your Wisblock hardware has been connected with your PC correctly, and your PC has recognized Wisblock hardware successfully. If it is, you can select the port now as the following image shows:

![image-20200702192336842](assets/image-20200702192336842.png)

Then click the "Upload" button to start it:

![image-20200703120245093](assets/image-20200703120245093.png)

After uploading successfully, you can see some information as the following image shows in the output message area:

![image-20200702192430475](assets/image-20200702192430475.png)

Great! That means you've uploaded the code into Wisblock successfully.

Now, enjoy you Wisblock and have an amazing play time!



## 9. Customized Code

As you know, RAK has supplied some examples source code for reference so that you can learn some code level method about how to do an application for Wisblock. Meanwhile, RAK has supplied a set of tutorials too, which has introduced the ability of Wisblock software and shown the development process of these RAK examples so that you can understand better about how to do some customized code.

All of these tutorials can be found here:

https://bitbucket.org/Fomi-RAK/wisblock-rak4630-development/src/master/doc/