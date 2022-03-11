# some_undergraduate_thesis
都三月了 毕设才新建文件夹，做得完吗，很难的啦（赶工目标：活过中期）

之前说的是 中期答辩的时候，在搭好的云游戏实验环境上完成用户标注ROI的功能。。。第三周的时候应该把基本的云游戏功能实现出来。。。

我们现在就要求，能在一台windows电脑上作为游戏主机，然后它连到局域网内，在另一台电脑上，在浏览器上通过网页形式，可以看到游戏主机的桌面，且可以在浏览器里上面进行鼠标和键盘操作，传到游戏主机上。

核心使用的两个开源库：

ffmpeg（主要解决编码？）

WebRTC（主要解决传输？）

nodejs/react?(主要解决搭网站框架？）

你已经会写了，开始爆肝吧！（？？？）

https://blog.csdn.net/zego_0616/article/details/117997726

从 Windows 8 开始，微软引入了一套新技术叫 Desktop Duplication API，应用程序可以通过这套 API 请求桌面的图形数据。由于 Desktop Duplication API 是通过 DirectX Graphics Infrastructure（以下简称 DXGI）来提供桌面图像的，竞争的是 GPU 流水线资源，所以 CPU 占用率很低，采集性能非常高。

由于这套能力整合在 DirextX 中提供，所以与大部分 DirectX 接口的使用方式基本一致，其流程概括如下图。

todo: 学习DirectX中的windows桌面图像获取API？仅用于抓取全屏

use windows desktop duplication API(https://docs.microsoft.com/en-us/windows/win32/direct3ddxgi/desktop-dup-api)
Windows 8 disables standard Windows 2000 Display Driver Model (XDDM) mirror drivers and offers the desktop duplication API instead. The desktop duplication API provides remote access to a desktop image for collaboration scenarios. Apps can use the desktop duplication API to access frame-by-frame updates to the desktop. Because apps receive updates to the desktop image in a DXGI surface, the apps can use the full power of the GPU to process the image updates.

DXGI provides a surface that contains a current desktop image through the new IDXGIOutputDuplication::AcquireNextFrame method. The format of the desktop image is always DXGI_FORMAT_B8G8R8A8_UNORM no matter what the current display mode is. Along with this surface, these IDXGIOutputDuplication methods return the indicated types of info that help you determine which pixels within the surface you need to process:


todo：学习WebRTC API，了解如何将desktop dup api得到的每秒若干帧的图像流需要用什么格式转发到WebRTC的输入端
todo：搭建WebRTC demo，了解如何将这台机器上webRTC输入端的画面转发到另一台机器；搭建局域网测试环境


