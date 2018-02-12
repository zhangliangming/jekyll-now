---
 layout: post
 title: Android右滑关闭Activity界面功能-自定义控件实现
---
# 引言 #
Android右滑关闭Activity界面功能，网上已经有好多优秀的开源代码和项目，不过大部分都是结合ViewDragHelper来实现的，这里要讨论的是通过结合ValueAnimator来实现，目前我的控件只实现了从左往右（上往下）滑关闭界面。
# 需求 #
- 在界面上从左往右滑，View位置根据手势移动。
- 只拦截左右滑动，上下方向的滑动无影响。
- 子View的左右滑动事件无影响。
# 预览图 #
![](https://i.imgur.com/s08E8h0.png)
# 实现思路 #
- SwipeBackLayout：左右滑动View
- onInterceptTouchEvent：该方法只要做左右移动拦截，上下移动不拦截。
- ValueAnimator：该动画只要改变SwipeBackLayout View的位置，在ACTION_UP和界面打开时调用。
- ACTION_MOVE时，根据移动的X位移，修改SwipeBackLayout View的位置。
# 主要代码分析 #
## onFinishInflate ##
![](https://i.imgur.com/FTh8sLD.png)

该方法只要实现两种方式，一种是通过布局xml文件来初始化SwipeBackLayout；另外一种是新new SwipeBackLayout。
## onLayout ##
![](https://i.imgur.com/fMGFEpL.png)
![](https://i.imgur.com/N1m94uC.png)

该方法只要是在初始化成功之后，修改SwipeBackLayout的位置。
## onInterceptTouchEvent ##
![](https://i.imgur.com/HUFLhKP.png)
![](https://i.imgur.com/ldLebXL.png)

该方法只要是拦截左右移动和判断是否在左右不拦截的子View集合里面。
## onTouchEvent ##
![](https://i.imgur.com/gpHn4AT.png)

该方法只要在用户左右移动的时候，修改SwipeBackLayout的位置。
![](https://i.imgur.com/iodaZxp.png)
![](https://i.imgur.com/coUn5lC.png)

该方法只要是ACTION_UP的时候，需要判断当前SwipeBackLayout的left位置，如果left位置小于屏幕的一半，则使用ValueAnimator动画，让SwipeBackLayout位置还原到正常位置。否则，关闭SwipeBackLayout。
## dispatchDraw ##
![](https://i.imgur.com/9UpUCn4.png)

该方法只要是在SwipeBackLayout移动的时候，绘画阴影。
# 源码 #
具体的代码和调用Demo，可到源码地址处查看：[https://github.com/zhangliangming/SwipeBackLayout.git](https://github.com/zhangliangming/SwipeBackLayout.git "Android右滑关闭Activity界面控件")
# 最后 #
如果有问题，可到github上面留言。
