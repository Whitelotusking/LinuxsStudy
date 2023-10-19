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
- touch创建文件夹
- 语法：touch Linux路径
- 定义：创建文件（不是文件夹）
### cat命令
- 定义：查看文件内容,将内容一次性全部展出
- 语法：cat Linux路径
### more命令
-定义：查看文件，可以将内容多的文件用翻页形式去看
-语法：cat Linux路径
 可以按q键退出，按空格键翻页
 ## cp、mv、rm

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU4ODA5MjI5NCwtNjA1Mzg0ODQxLDYyOT
E0NDU4N119
-->