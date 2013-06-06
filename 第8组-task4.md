高校交友平台应用建模
====================


**1 概要**


1.1目的

西安电子科技大学作为一间历史悠久，学风浓厚的大学，学生都忙于学习之中，对课外活动参与热情度低，社交圈子小，缺乏锻炼社交能力的机会。学生与老师之间的交流也少，通知、课件等的信息都无法直接传递。同时，西安虽然高校林立，但是各所高校之间间隔较大，日常交流甚少，不利于西电与各兄弟院校的友好合作和交流。建立高校交友平台可以增加老师与学生，不同院系、不同高校学生之间的交流，促进资源共享。


1.2 主要内容
     
能够建立西安电子科技大学全校师的交友平台，不单单是同学与同学之间的交友，更包括老师和同学的交流，通过此平台，同学之间可以聊天、约定活动等的社交交流，老师和同学之间也可以进行信息发布、课件上传、教学反馈等的功能。更希望日后可以推广到不同高校之间，让不同高校的同学有更好的交流平台，让理科和文科学校能通过交流，互补缺点。
     
**2 需求分析**
     
2.1主要功能
     
高校网络交友平台的功能分为后台管理、展示界面、BT下载三个部分，具体功能说明如下：
     
1.登录与注册
     
用户登录时要输入学号或邮箱号作为用户名，并输入密码登录。新用户要注册个人信息才能够登录。
     
2.在线展示
     
用户只要登录到网站后，就可以在线浏览所加好友们的新鲜事，包括文字、图片和日志。可以对新鲜事、图片、日志等进行收藏或者转发。
     
3.留言功能
     
每个用户界面设一个留言板，能够实现好友间互相留言。
     
4.在线交流
     
好友发表或自己发表的内容可以进行实时在线交流，实现好友之间直接的交流，可以是文字或表情的方式。
     
5.用户上传功能
     
用户可以将有用的信息上传至网上，供大家下载。
     
6.BT下载功能
     
用户达到一定积分之后可以进行下载，以达到资源共享。
     
7.后台管理服务
     
管理员可以修改部分内容，实时更新网站内容，也可以上传一些有用的资源。
     
8.查找并添加好友功能
     
可以根据想要查找好友的姓名及学校找到所需的好友，可以进行添加，将对方加入你的好友列表。
     
9.设置权限
     
用户可以设置个人权限，日志等仅限好友可见等方法。
     
**3 Web应用建模**
     
3.1 系统参与者及用例
     
1. 系统参与者：
     
1）用户
     
2）管理员
     
2. 系统用例：
     
1）用户：注册与登录

管理好友列表

修改个人信息

在线聊天

发布信息

上传资源

下载资源

修改账户信息

2）管理员：设置权限

管理资源

后台维护





3.2 系统用例图

![picture](http://ww2.sinaimg.cn/mw1024/a13a2bc1tw1e56ogiicy2j20ey0g6wfh.jpg "用例图1")
 


3.3 页面类图 

![类图](http://ww4.sinaimg.cn/mw1024/a13a2bc1tw1e56oyw5wnsj20fg0bfmyb.jpg "页面类图")



页面类主要分为以下几类：

1）	登录与浏览页面用于用户登陆时操作界面，主要方法有：

browse()用于展示页面内容

userLogin()用于用户登录操作

checkEmpty()用于判断是否输入为空

listInfo()用于展列出登录后的信息

2）	信息发布页面类，主要方法有：

browse()用于浏览页面内容

publishNews()用于发布新鲜事

commit()用于确认发送信息

cancel()用于取消发送

3）	上传资源页面，主要方法有：

browse()用于浏览页面内容

checkFiles()检查上传路径和文件

choose()用于选择该文件

uploading()用于上传文件

commit()用于确认上传

cancel()取消上传

4）	下载资源页面，主要方法有：

browse()用于浏览页面内容

showListInfo()展示信息列表

choose()选择下载项

download()确定下载 

5）	好友管理页面，主要方法有：

browse()用于浏览页面内容

showListInfo()展示好友信息列表

searchFriend()查找好友

add()添加好友

delete()删除好友

special()设置特别好友

6）	聊天页面，主要方法有：

Input()输入信息

Send()发送信息

Close()关闭对话框

3.4系统类图

![类图2](http://www.baidupcs.com/thumbnail/63b43122ded2ceced1fd004bf046e55d?fid=655247319-250528-2808626060&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-siFxRYsvgwlfWyDCUnCUGEe3IwQ%3D&rt=sh&expires=8h&size=c850_u580&quality=100)
类图说明：

1）用户类主要方法：

login()用于用户登录

updateInfo()用于用户更新自己的个人信息

upload()用于用户下载资源

2）好友列表类与用户类时多对一的关系，一个用户包含多个好友信息，主要方法有：

add()添加好友

getInfo()获取好友信息

delete()删除好友

search()查找好友

3）资源类与用户类也是多对一的关系，主要方法有：

upload()上传的资源

download()下载资源

update()更新资源

delete()删除资源

comment()评论资源

4）管理员类，主要方法有

login()管理员登录

updateInfo()更新信息

setpriority()设置权限

change()更改站内内容

3.5数据库类图


![tu](http://www.baidupcs.com/thumbnail/b3f7e74ad82f0077864f51680109bcdf?fid=655247319-250528-1541738037&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-6Js%2FlRyx2ETreNyiT75Z8siZxCw%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

数据库用来存储网站上的信息，主要方法包括：

addData()添加数据

deleteData()删除数据

updateData()更新数据

getData()取出数据

insertData()插入数据


3.6 系统时序图

1.用户发布新鲜事

![a](http://www.baidupcs.com/thumbnail/5c9a73be1c211976af015be8b573dff8?fid=655247319-250528-2713466254&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-ZNQezB7uWCC1eKGlDXA8z9KiF6w%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

由此可知，用户登录之后发布新鲜事过程，可以确认发布或者取消发布，最后数据存放于数据库中。

2.用户好友操作

![f](http://www.baidupcs.com/thumbnail/6ae365cc531ec3b5db606cde585db712?fid=655247319-250528-2531306739&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-Eqhpt2Yw%2BUDY4vPG0VQYEJUn15o%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

用户进入好友管理页面后，可以进行添加、删除、查找和取出好友信息的操作。

3.用户上传资源

![d](http://www.baidupcs.com/thumbnail/c39ae30d0ebd24a6599ecca1a6771b0a?fid=655247319-250528-808256973&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-r8bcZL2nNuMUO8oj0MV%2BYFnmWvQ%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

用户进入上传资源页面，可以选择上传资源，或取消，最终更改的数据保存在数据库内。


4.用户下载资源

![b](http://www.baidupcs.com/thumbnail/1840ecf3396e6ff0e0109eb6d6fd2208?fid=655247319-250528-3695943629&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-qYfyuxngx8B827E2pYihChUeRiA%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

用户进入下载资源界面后，可以从展示的资源列表中，选择下载资源。

5.用户更改个人信息


![a](http://www.baidupcs.com/thumbnail/9ad21980cb4a4e0231c1e15ee7d8768c?fid=655247319-250528-4056378360&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-zsKVhlKQoSdOca0mglJI5Bd5mvg%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

用户更改个人信息，最终结果存放在数据库内


6.管理员管理资源

![e](http://www.baidupcs.com/thumbnail/226b7dd261198563ff2f2ad7c7582914?fid=655247319-250528-2679450106&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-uzKeWcA8eqkDfeWTZmiUTr6AVlk%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

管理员可以删除、上床或更改资源类，修改结果存放在数据库内。


7.管理员设置权限

![c](http://www.baidupcs.com/thumbnail/48719d44db288092dcdcf0a1ffd08b0d?fid=655247319-250528-2555583149&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-z%2BWC0WgHYtuicaNdEI2IrhVharg%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

管理员设置管理员权限，更改用户信息或者管理员信息。

3.7系统活动图


1）学生用户活动图

![zz](http://www.baidupcs.com/thumbnail/800cd6bf9a78ed2f06d071ab465a13b6?fid=655247319-250528-1333769462&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-%2FKJR3KFvNOeLwYLyVnwZYM7MrBM%3D&rt=sh&expires=8h&size=c850_u580&quality=100)

主要展示了用户登录个人主页进行好友操作，修改个人信息或发布新鲜事的活动。

2）管理员活动图

![l](http://www.baidupcs.com/thumbnail/00108fbce197187536e0e8813fbe455d?fid=655247319-250528-897102547&time=1370511256&sign=FDTAR-DCb740ccc5511e5e8fedcff06b081203-vH7RCL6ZtNeMjxM8gH2D91oTC5w%3D&rt=sh&expires=8h&size=c850_u580&quality=100)


**4 结束语**


通过对高校交友平台的建模，确定了系统的对象实体以及其职责，确定了系统的用例和具体操作。通过建立用例的活动图确定了活动顺序。为我们平台的建立提供了方便，帮助我们按照实际情况或需要的样式对系统进行可视化，提供一种详细说明系统的结果或行为的方法，给出一个指导系统构造的模板。选择要创建什么模型，对如何动手解决问题和如何形成解决方案有着意义深远的影响，每一种模型可以在不同的精度级别上表示最好的模型，是与现实相联系的单个模型是不充分的。对每个重要的系统最好用一组几乎独立的模型去处理。





