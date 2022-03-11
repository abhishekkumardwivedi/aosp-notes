### App files

* .dex  : Java to java bytecode through javac, android converts java bytecode to dalvik through dx or D8. This bytecode is wrapped into dex format. https://source.android.com/devices/tech/dalvik/dex-format.
* .odex : 
* .vdex :
* .art  :
* .oat  :

Tools:
* dex2oat     :
* dalvikvm    :
* app_process : 


### Zygote startup

* https://elinux.org/Android_Zygote_Startup    
        
Init runs /system/bin/app_process (a c++ program), and name this process as zygote.    
As in init.rc:    
    
``` service zygote /system/bin/app_process -Xzygote /system/bin --zygote --start-system-server```    
    
Usage of ```app_process``` is:    

``` Usage: app_process [java-options] cmd-dir start-class-name [options] ```    
    
app_process does ```runtime.start("com.android.internal.os.ZygoteInit", startSystemServer)```    

