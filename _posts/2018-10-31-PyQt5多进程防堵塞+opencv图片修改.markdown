---
layout: post
title: PyQt5多进程防堵塞+opencv修改图片
date: 2018-10-31 16:14:23 +0800
categories: technology
tags: python opencv PyQt5
img: https://github.com/Trepverterless/Trepverterless.github.io/raw/master/assets/images/posts/post181031.png
---
PyQt5多进程防堵塞+opencv修改图片

* 
{:toc}
#PyQt5多进程防堵塞
 编写pyqt5可视化程序时遇到了一个问题，就是当某个事件触发执行外部函数时，由于外部函数执行时间比较长导致长时间不再主程序内运行，致使主程序被堵塞未响应崩溃。

##解决办法
 为了解决这个问题就必须使得主程序能够在外部函数执行的情况下仍然能够执行本身。我们应把主线程与工作线程分离，以免主循环阻塞，造成程序停止响应。这时引进一个多进程便可以解决这个问题。但是有时是需要多进程的所执行的程序的结果做为下面流程的输入。这时PyQt5带的一个QThread类可以使得当线程结束时发送一个pyqtSignal信号到主界面的槽函数里。此时便可以接受信号的返回值并调用函数处理。

##实现代码

###主程序代码
<code>

	self.thread = testThread(i)   #主界面创建一个线程类
    self.thread.start()                 
    self.thread.trigger.connect(self.Stopped) #当收到返回的信号就运行Stopped（）函数
</code>
###Stoped（）函数
<code>

	def Stopped(self,i):
		print(i)
###线程函数类
<code>

	class testThread(QThread):          #线程函数
	    trigger = pyqtSignal(int)     #设置一个信号
	
	    def __init__(self,i):         #初始化方法
	        super(testThread, self).__init__()

	        self.i = i
	 
	    def __del__(self):  #删除方法
	        self.wait() 
	  
	    def run(self):      #当类被创建完成就会运行该函数下代码
	        ret = 1
	        self.trigger.emit(ret)    #代码运行后发送自定义信号

</code>

#opencv图片修改的一些问题
 这里不讲opencv图片怎么修改了，网上教程很多，也很简单，主要是调用opencv库和numpy，这里主要讲下遇到的一些问题。
##常见图片格式
###jpg
 JPEG格式：也是应用最广泛的图片格式之一，它采用一种特殊的有损压缩算法，将不易被人眼察觉的图像颜色删除，从而达到较大的压缩比(可达到2:1甚至40:1)，因为JPEG格式的文件尺寸较小，下载速度快,所以是互联网上最广泛使用的格式!
###png
 与JPG格式类似,网页中有很多图片都是这种格式，是一种无损压缩。压缩比高于GIF，支持图像透明，可以利用Alpha通道调节图像的透明度
###bmg
 Windows系统下的标准位图格式,未经过压缩，一般图像文件会比较大。在很多软件中被广泛应用.

##对于图片修改的问题
 当使用opencv修改图片后，如果图片使用jpg等有损压缩格式是会改变原来想
 要保存图片的像素点的值。使得并不是准确的你想要保存的值，而是接近那个值的一个值。比如一个图片你想要把左上角的区域的R设置成200，然后保存，采取有损压缩的格式比如jpg格式，那么这些区域很有可能设置成两百几的值，而不是准确的200。这个对于视觉上来说没有太大区别，但是如果是要对图片加解密，那么如过加密后的值被修改那么就没法解密了。所以建议保存尽量选择那些无损压缩或者无压缩的格式。