---
 layout: post
 title: 2018-04-30-ContentProvider封装SharedPreferences功能，解决跨进程存取值的问题
---
# 引言 #

之前项目使用了SharedPreferences来保存数据，然而项目修改为多进程后，SharedPreferences保存数据却出现了数据没有更新的问题，当然SharedPreferences设置了MODE_MULTI_PROCESS后可以使数据同步，不过官方已经废弃了原先的MODE_MULTI_PROCESS, 并且建议跨进程存取值还是用ContentProvider之类的更靠谱一些。

# 思路分析 #
由于ContentProvider提供了对底层数据存储方式的抽象，底层我们可以使用SQLite，MongoDB等等，当然也可以使用SharedPreferences来实现

# 调用用法 #

## 继承 ##
![](https://i.imgur.com/72XGw4b.png)
## 声明 ##
![](https://i.imgur.com/daxZdRA.png)
## 相关API ##
![](https://i.imgur.com/wlhdM2O.png)

![](https://i.imgur.com/kcyTksE.png)

# 源码 #
- 项目地址：[ContentProvider封装SharedPreferences功能，解决跨进程存取值的问题](https://github.com/zhangliangming/PreferencesProvider.git)
- 具体的代码和调用Demo：[https://pan.baidu.com/s/15SixU_nviX1ppK74gxL3dg](https://pan.baidu.com/s/15SixU_nviX1ppK74gxL3dg)  密码: u8hw

# 参考 #

[ContentProvider从入门到精通](https://www.jianshu.com/p/f5ec75a9cfea)

[http://bbs.51cto.com/thread-1070974-1.html](http://bbs.51cto.com/thread-1070974-1.html)


# 最后 #
如果有问题，可到github上面留言。