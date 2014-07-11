SublimeText-Plugins-Usage
=========================

常用SublimeText插件的使用方法，不定时更新，以下内容仅记录Mac下的使用情况，Windows下请自行寻找解决方案（区别就在于菜单位置不同）。  

*Mac按键表*   
    *⌘（command）*   
    *⌥（option）*    
    *⇧（shift）*    
    *⇪（caps lock）*    
    *⌃（control）*    
    *↩（return）*    
    *⌅（enter）*


###安装SublimeText插件###
先启用Package Control，作用是安装插件时很方便，启用方法：菜单栏 – View – Show Console，贴入以下代码并回车，然后重启Sublime。 

   	import urllib2,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp) if not os.path.exists(ipp) else None;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())  
   
安装好后，按 `⌘+⇧+P` 或者点击菜单栏 `SublieText->Preference->Package Control` 打开包控制窗口。输入install，然后选择 `Package Control:Install Package` 并回车。

接下来在新窗口中输入要安装的插件名称并回车即可。


###Format CSS - CSS格式化插件###
安装后可以发现菜单栏的Edit有一个'CSS Format'选项，先**选中一部分代码**，然后点击这个命令。   

具体效果如下。

####Expanded####
```
.menu, .menu .i {
	list-style: none;
	padding: 0 0 0.5em;
}
.menu:before {
	content: "[";
}
.menu:after {
	content: "]";
}
```
####Expanded(Break Selectors)####
```
.menu,
.menu .i {
	list-style: none;
	padding: 0 0 0.5em;
}
.menu:before {
	content: "[";
}
.menu:after {
	content: "]";
}
```
####Compact####
```
.menu, .menu .i { list-style: none; padding: 0 0 0.5em; }
.menu:before { content: "["; }
.menu:after { content: "]"; }
```
####Compact(No Spaces) ####
```
.menu,.menu .i{list-style:none;padding:0 0 0.5em;}
.menu:before{content:"[";}
.menu:after{content:"]";}
```
####Compact(Break Selectors)####
```
.menu,
.menu .i { list-style: none; padding: 0 0 0.5em; }
.menu:before { content: "["; }
.menu:after { content: "]"; }
```
####Compact(Break Selectors,No Spaces)####
```
.menu,
.menu .i{list-style:none;padding:0 0 0.5em;}
.menu:before{content:"[";}
.menu:after{content:"]";}
```
####Compressed####
```
.menu,.menu .i{list-style:none;padding:0 0 0.5em}.menu:before{content:"["}.menu:after{content:"]"}
```