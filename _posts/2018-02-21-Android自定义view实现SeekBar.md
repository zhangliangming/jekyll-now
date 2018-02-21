---
 layout: post
 title: Android自定义view实现SeekBar
---
# 引言 #
该SeekBar由自定义view来实现，主要完成了普通的进度条（可修改进度条的颜色，游标颜色，二级进度条颜色等等），最后再在普通进度条的基础上实现了歌曲使用的进度条，可弹出窗口显示时间和歌词，该功能主要是在我的乐乐音乐播放器里面使用，其项目地址如下：[https://github.com/zhangliangming/HappyPlayer5.git](https://github.com/zhangliangming/HappyPlayer5.git "乐乐音乐播放器") 。
# 需求 #
- 完成SeekBar的基本功能
- 扩展弹出窗口显示歌曲时间和歌词
# 预览图 #
![](https://i.imgur.com/hjlLiTQ.png)

# 实现思路 #
- 重写view的onDraw来绘画进度条和游标
- 重写view的onTouchEvent来监听用户拖动游标或者拖动的事件
- 拖动时，弹出窗口显示时间和歌词

# 主要代码分析 #
## onDraw ##
![](https://i.imgur.com/AGLoBvW.png)


## onTouchEvent ##
![](https://i.imgur.com/1pHTCVE.png)

![](https://i.imgur.com/ja8FK5e.png)

# 源码 #
具体的代码和调用Demo，可到源码地址处查看：
[https://github.com/zhangliangming/SeekBar.git](https://github.com/zhangliangming/SeekBar.git "自定义view实现SeekBar")
# 最后 #
如果有问题，可到github上面留言。