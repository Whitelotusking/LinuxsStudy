# Linux的目录结构
- linux路径描述方式

1.在linux中，路径之间的层级关系，使用:/来表示

2.linux没有像windows一样的盘符，只有一个顶级目录，称之为根目录
而windows有多个顶级目录，即盘符

3.开头表示的时顶级目录，后面表示的是层级关系
# Linux命令入门
- 命令通用格式
command [-options][parameter]
该格式对应：命令 选项 参数
## ls命令入门
- 语法：ls [-a -l -h][Linux路径]
- 作用：列出当前工作目录下有什么内容
### Home目录
- 定义：每一个用户在Linux系统的专属目录在windows中也有一个这样对应的目录
### ls命令的参数和选项
参数:
- -a：将隐藏的内容展示出来, .开头的文件或者文件夹被默认隐藏
- -l：把平铺展示内容变成列展出
- -h：显示文件的大小，必须和l组合使用
以上的命令可以进行组合使用，功能会出现叠加
写法：
- ls -a -l
- ls -al
- ls -la
以上种都是可以的
## cd命令和pwd命令
### cd命令
- 定义：更改更改当前所在的工作目录
- 语法：cd [linux路径]
- cd命令不需要选项
- cd命令直接执行，不写参数，表示回家目录
### pww命令
- 定义：输出当前所在的工作目录
- 语法：pwd
- 无选项无参数
## 相对路径和绝对路径
- 绝对路径：以根目录为起点，描述路径的方法，以/开头
- 相对路径：以当前目录为七点，描述的方法，无需/开头
- .表示当前目录,比如cd./Desktop表示切换到当前目录下的Desktop目录内，和cd Desktop效果一致
- .. 表示上一级目录，比如cd ..可以切换到上一级目录，cd../..切换到上二级目录
- ~ 表示HOME目录，比如cd~可以切换到Home目录,组合的话可以切换到Home目录下的任意文件如cd ~/Desktop
## mkdir命令
-定义：通过mkdir命令可以创建新的目录（文件夹）
-语法：mkdir [-p] [Linux路径]
注意这里的参数必须要有
- 这里的- p选项可以创建多级目录，比如要创建/good/test 的test文件但是没有good文件，这时候- p就可以实现创建good然后再创建test
## touch、cat、more命令
### touch命令
- touch创建文件
- 语法：touch Linux路径
- 定义：创建文件（不是文件夹）
### cat命令
- 定义：查看文件内容,将内容一次性全部展出
- 语法：cat Linux路径
### more命令
-定义：查看文件，可以将内容多的文件用翻页形式去看
-语法：cat Linux路径
 可以按q键退出，按空格键翻页
 ## cp、mv、rm命令
### cp命令
- 定义cp [-r] 参数1 参数2
- 参数1 2分别表示要复制的文件，要被复制到的地方以及叫什么名字
- r是用于复制文件夹的情况

> cp -r 文件夹名 要改的名字
> cp 文件名 要改的名字
> 注意：如果只有名字的话表示在当前的目录下去复制
### mv命令
- 定义：移动文件或者文件夹到目标地址
- 语法：mv 参数1 参数2
注意这里如果没有目标目录则会相当于改名
### rm命令
- 定义：可以用于文件夹的删除
- 语法：rm [-r -f] 参数可以无限多
- 参数表示要删除的文件或者文件夹路径，按照空格去隔开
- -r 选项用于文件夹的删除，-f表示强制删除，**一般来说普通用户是无法使用的，要通过su - root命令去切换到root状态（内核态）,exit退回到用户态**
- *通配符，rm是支持通配符的
- test*匹配以test开头的内容
- *test匹配以test结尾的内容
- *test *表示匹配任何包含test的内容 
- 别用-rf参数，不然要寄的
## which、find命令、通配符、find命令按文件大小查找
### which命令
- 定义：查找对应命令所在的路径
###  find命令
- **按文件名查找**，类似windwos在此电脑中的搜索
- 语法：find 起始路径 -name "被查找文件名"，为了确保能在整个系统完成搜索，可以切换到root用户获取管理员权限
- **按文件大小查找**
- 语法 find 起始路径 -size +| - n[KMG]
-  +-表示大于和小于,n表示数字大小，KMG是大小单位
## grep命令
### grep命令
- 定义：过滤文件的关键字
- 语法 grep [-n] 关键字 文件路径
- 选项n,可以显示过滤关键字所在的行号
- 关键字表示过滤的关键字
- 文件路径表示要过滤文件的路径，如果不填的话可以作为管道符的输入路径
### wc命令
- 定义：统计文件的行数，单词数量等
- 语法：wc [-c -m -l -w] 文件路径
- -c,统计bytes数量
- -m,统计字符数量
- -l,统计行数
- -w,统计单词数量
### 管道符
定义：左边的输出作为右边的输入
语法：命令 | 命令
**但是要求左边的命令有内容的输出**
## echo命令、
### echo命令
- 定义：在命令行输出指定内容
- 语法：echo 输出内容,如果内容比较长内容要用“”包含
### 反引号' '
- 定义：在反引号内的内容会作为命令去执行 
- 可以搭配echo去输出使用
### 重定向符
- \>将左边的命令结果覆盖写到右边的文件中
- \>>将左边的命令结果追加写到右边的文件中
### tail命令
- 定义：查看文件尾部内容，跟踪文件的最新更改
- -f表示持续跟踪
- -num，这里的num是数字代表看尾部的多少行
- 语法：tail [-f -num] Linux路径
- ctlr+c键可以推出tail命令的跟踪状态
# Linux用户和权限
- 定义：root用户拥有最大的系统操作权限
- 语法：su - root切换到root用户
- exit可以退出到普通用户
- sudo命令，可以避免长期使用root命令带来系统损坏，可以为普通命令授权临时用root身份去执行
- 语法：sudo 其它命令
- **但是必须要去配置sudo认证**
> 
> su - root
> 用户名 ALL=(ALL) NOPASSWORD:ALL在认证文件中最后一行加上
> 这表示给普通用户所有命令的权限，并且不需要密码
## chmod命令
- 定义：修改文件、文件夹的权限信息，**只有文件或者文件夹的所属用户或者root用户可以使用chmod命令去修改权限信息**
- 语法：chmod [-R] 权限 文件或文件夹
- 选项-R，对文件夹内的全部内容应用同样的操作
>示例：
>chmod u=rwx,g=rx,o=x hello.txt
>u表示user所属用户权限,g表示group组权限,o表示other其它用户权限
>r w x分别表示读 写 执行权限

- 权限的数字序号：这是指用chmod命令时修改对应的用户和组时用数字去代表rwx的组合或者去表示无权限
## chown命令
- 定义：chmod命令是无法去修改属于其他用户或者组的文件的，必须进入root模式才可以,但是chown命令可以做到把文件的用户或者组换到别的组或者用户
- 语法：chown [-R] 用户：用户组 文件或文件夹
- -R的作用和chmod中的R一样
> ：的作用是分割开用户和用户组
> 实例：
> 1.chown root hello.txt，将hello.txt所属用户组修改为root
> 2.chown :root hello.txt，将hello.txt所属用户组修改为root
> 3.chown root:用户 hello.txt，将hello.txt所属的用户修改到root，用户组改为itheima
> 注意：丢给Root的时候可能会没有权限，这时候要切换到root的时候去修改
# Linux基本操作
## 快捷按键
- ctrl+c强制停止 执行中的东西强制停止
- ctrl+d 1.退出登录的用户 2.退出特定的程序
- history查看历史命令
- ctrl+r 关键字 去搜索历史命令
- ctrl+a 跳到开头
- ctrl+e 跳到结尾
- ctrl+键盘左键 左跳一个单词
- ctrl+键盘右键 右跳一个单词
- ctrl+l 清空内容
## 软件安装
- 语法：yum -y install|remove|search 软件名称
- rpm后缀是linux包
- y是自动确认
## 软件启动
- systemctlm命令可以管理很多三方和系统内置的软件,能被管理的软件也称为服务
- 语法：systemctl start|stop| status|enable|disable
- 例如系统的服务：sshd（ssh远程连接）、network(副网络服务)、NetworkManager（主网络服务）
- 不过要注意有的服务没有被systemctl管理这时候要自己添加
## 软链接
- 本质是创建一个快捷方式到别的地方，然后在别的地方去使用
- 语法 ln -s 参数1 参数2，-s表示创建软链接，参数1是被链接的文件或文件夹，参数2是要链接去的目的地
- 注意：软链接必须使用绝对路径
- ## date命令
- 可以查看系统的时间
- 语法 date [-d] [+字符串]，-d按照给定的字符串去显示日期
- 时区修改
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg3NTYzMzk2NSwtODUyMDQyMDIwLDIzOD
g3NTUzNiw2NDcxODk2NTgsLTE3NDI1ODYxNzMsLTQxODc0MTgx
NCw3MTAwMzkyNzcsMTQwNjk3MDMzNCwtMTIzNjM2MDU3MiwtMT
MyNTcwMDAzMCwtMTQzNTc0NTA0NCwtMTg4MzYxNTU5MSwxOTkw
OTYyOTQ1LC05MDAzOTY2NSwtMTE3MjIxNzY4OSwyNTQzNDQwOT
MsODMxMTY2NDIxLC0xMDYwMjM0NTAyLC0xMTYxNzY1MDMsLTIw
NzMyMDgzODRdfQ==
-->