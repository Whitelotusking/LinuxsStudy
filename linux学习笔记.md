---


---

<h1 id="linux的目录结构"><span class="prefix"></span>Linux的目录结构<span class="suffix"></span></h1>
<ul>
<li>linux路径描述方式</li>
</ul>
<p>1.在linux中，路径之间的层级关系，使用:/来表示</p>
<p>2.linux没有像windows一样的盘符，只有一个顶级目录，称之为根目录<br>
而windows有多个顶级目录，即盘符</p>
<p>3.开头表示的时顶级目录，后面表示的是层级关系</p>
<h1 id="linux命令入门"><span class="prefix"></span>Linux命令入门<span class="suffix"></span></h1>
<ul>
<li>命令通用格式<br>
command [-options][parameter]<br>
该格式对应：命令 选项 参数</li>
</ul>
<h2 id="ls命令入门"><span class="prefix"></span>ls命令入门<span class="suffix"></span></h2>
<ul>
<li>语法：ls [-a -l -h][Linux路径]</li>
<li>作用：列出当前工作目录下有什么内容</li>
</ul>
<h3 id="home目录"><span class="prefix"></span>Home目录<span class="suffix"></span></h3>
<ul>
<li>定义：每一个用户在Linux系统的专属目录在windows中也有一个这样对应的目录</li>
</ul>
<h3 id="ls命令的参数和选项"><span class="prefix"></span>ls命令的参数和选项<span class="suffix"></span></h3>
<p>参数:</p>
<ul>
<li>-a：将隐藏的内容展示出来, .开头的文件或者文件夹被默认隐藏</li>
<li>-l：把平铺展示内容变成列展出</li>
<li>-h：显示文件的大小，必须和l组合使用<br>
以上的命令可以进行组合使用，功能会出现叠加<br>
写法：</li>
<li>ls -a -l</li>
<li>ls -al</li>
<li>ls -la<br>
以上种都是可以的</li>
</ul>
<h2 id="cd命令和pwd命令"><span class="prefix"></span>cd命令和pwd命令<span class="suffix"></span></h2>
<h3 id="cd命令"><span class="prefix"></span>cd命令<span class="suffix"></span></h3>
<ul>
<li>定义：更改更改当前所在的工作目录</li>
<li>语法：cd [linux路径]</li>
<li>cd命令不需要选项</li>
<li>cd命令直接执行，不写参数，表示回家目录</li>
</ul>
<h3 id="pww命令"><span class="prefix"></span>pww命令<span class="suffix"></span></h3>
<ul>
<li>定义：输出当前所在的工作目录</li>
<li>语法：pwd</li>
<li>无选项无参数</li>
</ul>

