SublimeText-Plugins-Usage
=========================

常用SublimeText插件的使用方法，不定时更新，以下内容仅记录Mac下的使用情况，Windows下请自行寻找解决方案（区别就在于菜单位置不同）。  

*Mac按键表*   
    *⌘（command）*   *⌥（option）*    *⇧（shift）*    *⇪（caps lock）*   *⌃（control）*    *↩（return）*    *⌅（enter）*


### 安装Package Control ###
先启用Package Control，作用是安装插件时很方便，启用方法：菜单栏 – View – Show Console，贴入以下代码并回车，然后重启Sublime。 

   	import urllib2,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp) if not os.path.exists(ipp) else None;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())  
   
安装好后，按 `⌘+⇧+P` 或者点击菜单栏 `SublimeText->Preference->Package Control` 打开包控制窗口。

  - 安装插件：输入install，然后选择 `Package Control:Install Package` 并回车。
  - 卸载插件：输入remove，然后选择 `Package Control:Remove Package` 并回车，然后选择下拉列表中已安装的插件。

接下来在新窗口中输入要安装的插件名称并回车即可。

---

### Format CSS - CSS格式化###
安装后可以发现菜单栏的Edit有一个'CSS Format'选项，先**选中一部分代码**，然后点击这个命令。   

具体效果如下。

#### Expanded ####
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
#### Expanded(Break Selectors) ####
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
#### Compact ####
```
.menu, .menu .i { list-style: none; padding: 0 0 0.5em; }
.menu:before { content: "["; }
.menu:after { content: "]"; }
```
#### Compact(No Spaces) ####
```
.menu,.menu .i{list-style:none;padding:0 0 0.5em;}
.menu:before{content:"[";}
.menu:after{content:"]";}
```
#### Compact(Break Selectors) ####
```
.menu,
.menu .i { list-style: none; padding: 0 0 0.5em; }
.menu:before { content: "["; }
.menu:after { content: "]"; }
```
#### Compact(Break Selectors,No Spaces) ####
```
.menu,
.menu .i{list-style:none;padding:0 0 0.5em;}
.menu:before{content:"[";}
.menu:after{content:"]";}
```
#### Compressed ####
```
.menu,.menu .i{list-style:none;padding:0 0 0.5em}.menu:before{content:"["}.menu:after{content:"]"}
```
---
### Emmet - 快速编写HTML ###
Emmet的前身就是zen coding，它使用仿CSS选择器的语法来生成代码，大大提高了HTML/CSS代码编写的速度。

#### 快速编写HTML ####
1.初始化页面

新建一个.html文件，输入`！`或者`html:5`然后按`tab`键，可以看到快速生成了一个html5格式的文档。   

*  `html:5` 或`!`：用于HTML5文档类型
*  `html:xt`：用于XHTML过渡文档类型
*  `html:4s`：用于HTML4严格文档类型

2.添加CLASS、ID属性等   

输入`p.bar#foo`按`tab`（后文省略按`tab`）

3.元素嵌套和分组

`h1 > (h2 + p)`

*  `>`：子元素符号，表示嵌套的元素
*  `+`：同级标签符号
*  `^`：可以使该符号前的标签提升一行
*  `()`：分组

4.隐式标签

Emmet会根据父级标签来判段生成何种标签，如，直接输入`.bar`会直接生成一个`<div class="bar"></div>`的标签，而在`ul`中输入`.bar`时则会生成`<li class="bar"></li>`。

*  li：用于ul和ol中
*  tr：用于table、tbody、thead和tfoot中
*  td：用于tr中
*  option：用于select和optgroup中

5.多个重复元素

如：`ul>li*3`   

6.带属性的元素

如`ul>li.item$3`就会产生如下代码：   
```
   <ul>		
     <li class="item1"></li><li class="item2"></li><li class="item3"></li>
   </ul>   
```

##### 快速编写CSS ######
这里不写了，感觉css完全不需要用到这个，IDE已经能很好的满足需求了。


官网[详细语法](http://docs.emmet.io/cheat-sheet/)

---

### Terminal - 打开命令行窗口定位到当前文件路径 ###
安装完成后，有两种方式调用：

  1. 对着文件右键可以看到有一个`Open Terminal Here`的选项   
  1. `⌘+⇧+T`  

这个会打开默认的terminal，电脑安装了iTerm2，所以放弃这个。

---

### MacTerminal - 打开命令行窗口定位到当前文件路径 ###
安装完成后，调用方法：
- `⌘+⌃(ctrl)+T`

---

### JSFormatter - JS格式化 ###
调用方式：

  1.`Ctrl+Alt+F`

### Color Highilighter - 高亮CSS文件中的颜色
安装完成后，需进行简单的配置，Preferences → Package Settings → Color Highlighter → Settings – User，添加以下代码：
```
{
  "ha_style": "filled"
}
```

### DocBlockr - 创建文档块
在函数上面输入`/**`，然后按`Tab`键即可。
