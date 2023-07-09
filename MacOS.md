### Mac上“磁盘工具”中可用的文件系统格式
* Apple文件系统(APFS): macOS 10.13或后续版本使用的文件系统。
* Mac OS扩展: macOS 10.12或之前版本使用的文件系统。
* MS-DOS(FAT)和ExFAT: 与Windows兼容的文件系统。

#### 1. Apple文件系统(APFS)
Apple文件系统(APFS)是运行macOS 10.13或后续版本的Mac电脑所使用的默认文件系统，它具有强加密、空间共享、磁盘快照、快速目录大小统计等特性，以及改进的文件系统基础。虽然APFS最适合与新款Mac电脑中的所用的闪存/SSD储存，它也可以与使用传统硬盘驱动器(HDD)和外置直连储存设备的低版本系统配合使用。macOS 10.13或后续版本支持APFS用与可引导启动的宗卷和数据宗卷。


APFS allocates disk space within a container (partition) on demand. When a single APFS container has multiple volumns, the container's free space is shared and is automatically allocated to any of the individual volumes as needed. If desired, you can specify reserve and quota sizes for each volume. Each volume uses only part of the overall conainer, so the available space is the total size of the container, minus the size of all the volumes in the container. 

APFS按照需求分配容器(分区)中的磁盘空间。单个APFS容器包含多个宗卷时，容器的可用空间会共享，并且会自动按需分配到任意单独的宗卷。如果需要，你可以指定每个宗卷的保留大小和配额大小。每个宗卷仅仅使用整体容器的一部分，这样一来，可用空间即容器的总大小减去该容器中所有宗卷的大小。

![](/images/DiskUtility.Container.png)
* Container `Container disk4` contains two volumes, `Seagate8TB` and `TimeMachine`.

**Reference**
* [Disk Utility User Guide](https://support.apple.com/guide/disk-utility/file-system-formats-dsku19ed921c/mac)
* [磁盘工具使用手册](https://support.apple.com/zh-cn/guide/disk-utility/dsku19ed921c/mac)