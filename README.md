# vim-tutorial

http://my.oschina.net/joshuazhan/blog/122539

1. 背景
在终端Vim中粘贴代码时，发现插入的代码会有多余的缩进，而且会逐行累加。原因是终端把粘贴的文本存入键盘缓存（Keyboard Buffer）中，Vim则把这些内容作为用户的键盘输入来处理。导致在遇到换行符的时候，如果Vim开启了自动缩进，就会默认的把上一行缩进插入到下一行的开头，最终使代码变乱。

2. 解决


（1）命令模式 
使用“:set nosmartindent”和“:set noautoindent”取消自动缩进，然后再粘贴即可。完成后再开启自动缩进“:set smartindent”和“:set autoindent”，以上命令都可使用简写，比如“:set si”，可通过Vim的帮助“:help smartindent”查看相应说明。

（2）Paste模式
Vim的编辑模式中，还有一个Paste模式，在该模式下，可将文本原本的粘贴到Vim中，以避免一些格式错误。通过“:set paste”和“:set nopaste”进入和退出该模式
