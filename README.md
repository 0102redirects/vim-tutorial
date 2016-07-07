# vim-tutorial

http://my.oschina.net/joshuazhan/blog/122539

1. 背景
在终端Vim中粘贴代码时，发现插入的代码会有多余的缩进，而且会逐行累加。原因是终端把粘贴的文本存入键盘缓存（Keyboard Buffer）中，Vim则把这些内容作为用户的键盘输入来处理。导致在遇到换行符的时候，如果Vim开启了自动缩进，就会默认的把上一行缩进插入到下一行的开头，最终使代码变乱。

2. 解决


（1）命令模式 
使用“:set nosmartindent”和“:set noautoindent”取消自动缩进，然后再粘贴即可。完成后再开启自动缩进“:set smartindent”和“:set autoindent”，以上命令都可使用简写，比如“:set si”，可通过Vim的帮助“:help smartindent”查看相应说明。

（2）Paste模式
Vim的编辑模式中，还有一个Paste模式，在该模式下，可将文本原本的粘贴到Vim中，以避免一些格式错误。通过“:set paste”和“:set nopaste”进入和退出该模式


＃===================
多行注释： 1. 进入命令行模式，按ctrl + v进入 visual block模式（可视快模式），然后按j, 或者k选中多行，把需要注释的行标记起来 2. 按大写字母i，再插入注释符，例如// 3. 按esc键就会全部注释了（我的是按两下）

取消多行注释： 1. 进入命令行模式，按ctrl + v进入 visual block模式（可视快模式），按小写字母L横向选中列的个数，例如 // 需要选中2列 2. 按字母j，或者k选中注释符号 3. 按d键就可全部取消注释


＃===================
vim-flake8: autocmd BufWritePost *.py call Flake8() let g:flake8_show_in_file=1 let g:flake8_show_quickfix=0 let g:flake8_error_marker='EE' " set error marker to 'EE' let g:flake8_warning_marker='WW' " set warning marker to 'WW' let g:flake8_pyflake_marker='' " disable PyFlakes warnings let g:flake8_complexity_marker='' " disable McCabe complexity warnings let g:flake8_naming_marker='' " disable naming warnings"

＃===================
The-NERD-Commenter : \cc (去掉注释 \cu)

＃===================
ctags -R 设置好了tags文件，在定位变量/函数的定义时，最常用的快捷键是： Ctrl + ] 跳转到变量或函数的定义处，或者用命令 :ta name 而使用快捷组合键 Ctrl + o/t 返回到跳转前的位置。

另外，ctags不会生成局部变量的索引，不过可以使用gd组合键（对光标所在处的word进行快捷查找定位）来定位，也是相当快捷的。
