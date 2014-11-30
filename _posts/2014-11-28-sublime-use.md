---
layout: default
title: Sublime Text使用
---
## 解决Sublime Text 3中文显示乱码问题
1、打开Sublime Text 3，按Ctrl+～打开控制行，复制粘贴以下python代码，然后回车运行。
2. 复制并粘贴如下代码：
````python
import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)    

````
2、重启Sublime Text 3。
3、按Ctrl+Shift+P打开命令行，输入Install Package，回车，然后继续输入ConvertToUTF8，回车。
等安装好了以后，应该问题就解决了，如果还是不行，再按照安装ConvertToUTF8的方式安装GBK Encoding Support，就好了。

## 设置字体大小

1 点击工具栏中的Preferences
2 选择Preferences下的Setings-User
3 配置文件中添加 "font_size": 14.0

## 快捷键
> Ctrl+D 选词 （反复按快捷键，即可继续向下同时选中下一个相同的文本进行同时编辑）
Ctrl+G 跳转到相应的行
Ctrl+J 合并行（已选择需要合并的多行时）
Ctrl+L 选择整行（按住-继续选择下行）
Ctrl+M 光标移动至括号内开始或结束的位置
Ctrl+T 词互换
Ctrl+U 软撤销
Ctrl+P 查找当前项目中的文件和快速搜索；输入 @ 查找文件主标题/函数；或者输入 : 跳转到文件某行；
Ctrl+R 快速列出/跳转到某个函数
Ctrl+K Backspace 从光标处删除至行首
Ctrl+K+B 开启/关闭侧边栏
Ctrl+KK 从光标处删除至行尾
Ctrl+K+T 折叠属性
Ctrl+K+U 改为大写
Ctrl+K+L 改为小写
Ctrl+K+0 展开所有
Ctrl+Enter 插入行后（快速换行）
Ctrl+Tab 当前窗口中的标签页切换


Ctrl+Shift+A 选择光标位置父标签对儿
Ctrl+Shift+D 复制光标所在整行，插入在该行之前
ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找
Ctrl+Shift+K 删除整行
Ctrl+Shift+L 鼠标选中多行（按下快捷键），即可同时编辑这些行
Ctrl+Shift+M 选择括号内的内容（按住-继续选择父括号）
Ctrl+Shift+P 打开命令面板
Ctrl+Shift+/ 注释已选择内容
Ctrl+Shift+↑可以移动此行代码，与上行互换
Ctrl+Shift+↓可以移动此行代码，与下行互换
Ctrl+Shift+[ 折叠代码
Ctrl+Shift+] 展开代码
Ctrl+Shift+Enter 光标前插入行


Ctrl+PageDown 、Ctrl+PageUp 文件按开启的前后顺序切换


Ctrl+Z 撤销
Ctrl+Y 恢复撤销
Ctrl+F2 设置/取消书签
Ctrl+/ 注释整行（如已选择内容，同“Ctrl+Shift+/”效果）
Ctrl+鼠标左键 可以同时选择要编辑的多处文本


Shift+鼠标右键（或使用鼠标中键）可以用鼠标进行竖向多行选择
Shift+F2 上一个书签
Shift+Tab 去除缩进
Alt+Shift+1（非小键盘）窗口分屏，恢复默认1屏
Alt+Shift+2 左右分屏-2列
Alt+Shift+3 左右分屏-3列
Alt+Shift+4 左右分屏-4列
Alt+Shift+5 等分4屏
Alt+Shift+8 垂直分屏-2屏
Alt+Shift+9 垂直分屏-3屏


Ctrl+Shift+分屏序号 将当前焦点页分配到分屏序号页


Alt+. 闭合当前标签
Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑


Tab 缩进 自动完成
F2 下一个书签
F6 检测语法错误
F9 行排序(按a-z)
F11 全屏模式
