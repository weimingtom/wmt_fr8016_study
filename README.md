# wmt_fr8016_study
My freqchip study

## FR8016HA  
* https://www.freqchip.com/fr801xh  
* https://gitee.com/freqchip/FR801xH-SDK  
* dev_v1_use_white_hongmi_write_wav_success.rar
* 红米传输  
```
我把FR8016HA开发板的声音播放跑通了，
（1）烧录程序：不能用gitee最新版，要用旧资料的代码（会导致屏幕花屏，但功能正常）
（2）需要用特定的安卓手机才能正常蓝牙传输wav文件，我用的是红米4A，安卓6，
安卓是gitee上的SBC最新版
（3）我接的喇叭是8Ω0.5W圆形喇叭（8R），带公头杜邦线（需面包板），原版没有，需要自备
（4）按K1数次，然后按K2播放
```

## FR8008XP  
* https://www.freqchip.com/fr800x  
* https://gitee.com/freqchip/fr8000  
* https://gitee.com/http1520/fr8000_lvgl_watch_240x280  
* 240x280 (需要自己接面包板): fr8000_lvgl_watch_240x280-master_v1_run_success.rar  
```
GND<-->GND (right bottom 3)   
VCC<-->VBAT (left bottom 3)   
SCL<-->PB0 (right top 1)   
SDA<-->PB2 (left top 2)   
RES<-->PB4 (left top 3)   
DC<-->PB3 (right top 2)   
CS<-->PB1 (left top 1)    
BLK<-->NC  
```
* 400屏幕 (官方售卖的1.6寸ips圆形屏转接板和扩展板, 400*400分辨率, st77903), fr800x_lvgl_prj_20220903_dev_ver.rar
* 400x400: fr800x_lvgl_prj_20220903_dev_ver_v1_st77903_not_good.rar  
* 400x400, all.bin: fr800x_lvgl_prj_20220903_dev_ver_v2_no_random_screen.7z  
https://gitee.com/http1520/file_hander_tools.git  
和UI.bin合并成all.bin然后烧录到flash (用bin打包工具合并到0x200000）    
然后可以只烧录ble_simple_peripheral.bin（写到0x0）  
https://gitee.com/http1520/lvgl_knob_open_demo  
```
!!! not sure  
GND<-->GND (right bottom 3)   
VCC<-->VBAT (left bottom 3)   
SCL<-->PB0 (right top 1)   
SDA<-->PB2 (left top 2)   
RES<-->PD5 (left top 5)   
DC<-->PB3 (right top 2)   
CS<-->PA5 (right bottom 4)    
BLK<-->NC  
```
```
我终于跑通了富芮坤FR8008XP开发板和400分辨率圆形屏的用法，烧录效果如下。这里有几个问题
（1）如果直接烧录，图片会花屏，那是因为图片都是通过Flash映射的内存地址去读的，
需要用工具写入0x200000处，或者用工具合并成一个bin文件，
烧录一次后下次就无需烧录0x200000的图片了
（2）示例代码和这个屏幕的驱动代码不在gitee上，但有提供一个示例工程代码，
我这里把原本的首页的字改了
```

## FR5082DM (named FR5086D, but not), not good, need Xplorer, but I don't have it.      
* https://www.freqchip.com/fr508x  
* https://gitee.com/freqchip/fr5080-dsp  
* https://gitee.com/freqchip/fr5080  

## 8000烧录器, 每次烧录需要重启, fr8000_config.exe  
* https://gitee.com/freqchip/fr8000/tree/master/tools

## 8010烧录器和安卓传输文件的apk, FR8010H_Download_Tool.exe  
* https://gitee.com/freqchip/FR801xH-SDK/tree/master/tools
* Fr8010loadsbc_v1.2.apk  

## 烧写UI.bin, FreqChip_Download.exe  
* https://gitee.com/http1520/lvgl_knob_open_demo
* https://gitee.com/http1520/lvgl_knob_open_demo/tree/master/freq_download
* freq_download.rar

## 合并all.bin, bin_packet_tools.exe  
* https://gitee.com/http1520/file_hander_tools  
