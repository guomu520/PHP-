#libevent扩展介绍
###libevent是一个基于事件驱动的高性能网络库。支持多种 I/O 多路复用技术， epoll、 poll、 dev/poll、 select 和 kqueue 等；支持 I/O，定时器和信号等事件；注册事件优先级。libevent扩展依赖于原始的libevent库，必须先把libevent库安装。
##PHP Libevent扩展介绍：
###(1)常量
值   常量名             含义

1   EV_TIMEOUT  超过时间后事件成为激活状态

2   EV_READ     FD就绪，可以读取的时候 ，事件成为激活状态

4   EV_WRITE    FD就绪，可以写入的时候 ，事件成为激活状态

8   EV_SIGNAL   用于实现信号检测

16  EV_PERSIST  表示事件是持久的

32  EV_ET       表示底层是否支持边沿触发事件

1   EVLOOP_ONCE 如果设置了EVLOOP_ONCE，循环将等待某些事件成为激活的，执行激活的事件直到没有更多的事件可以执行，然会返回。

2   EVLOOP_NONBLOCK  如果设置了EVLOOP_NONBLOCK，循环不会等待事件被触发：循环将仅仅检测是否有事件已经就绪，可以立即触发，如果有，则执行事件的回调。



###(2)函数
event_base_free() 释放资源，这不能销毁绑定事件

event_base_loop() 处理事件，根据指定的base来处理事件循环

event_base_loopbreak() 立即取消事件循环，行为各break语句相同

event_base_loopexit() 在指定的时间后退出循环

event_base_new() 创建并且初始事件

event_base_priority_init() 设定事件的优先级

event_base_set() 关联事件到事件base

event_buffer_base_set() 关联缓存的事件到event_base

event_buffer_disable() 禁用一个缓存的事件

event_buffer_enable() 启用一个指定的缓存的事件

event_buffer_fd_set() 改变一个缓存的文件系统描述

event_buffer_free() 释放缓存事件

event_buffer_new() 建立一个新的缓存事件

event_buffer_priority_set() 缓存事件的优先级设定

event_buffer_read() 读取缓存事件中的数据

event_buffer_set_callback() 给缓存的事件设置或重置回调hansh函数

event_buffer_timeout_set() 给一个缓存的事件设定超时的读写时间

event_buffer_watermark_set 设置读写事件的水印标记

event_buffer_write() 向缓存事件中写入数据

event_add() 向指定的设置中添加一个执行事件

event_del() 从设置的事件中移除事件

event_free() 清空事件句柄

event_new() 创建一个新的事件

event_set() 准备想要在event_add中添加事件

