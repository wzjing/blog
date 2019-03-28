# CMD Operation

* ## File Operation

>CD Operation

1. cd directory 进入directory目录

1. cd \         进入根目录

1. D:           进入D盘

1. cd /d D:\directory   进入d盘的directory

>dir

1. dir          显示文件

1. dir /a       当前目录下的所有文件和子目录包含隐藏文件和系统文件

1. dir /a:d     只显示目录下的文件夹

1. dir /a:-d    只显示当前文件夹下的文件

1. dir /b       只显示文件名

1. dir/p        分页显示

1. dir *.exe /s 显示当前目录和根目录下所有的exe后缀的文件

>File Operation

1. rd directory    删除空目录

1. rd /s directory  删除directory目录及子目录

1. rd /q directory  安静模式:删除时不提示确认

1. md directory    新建目录

1. del directory    删除目录

1. del /p       删除每一个文件前提示

1. del /f       强制删除只读文件

1. del /s       包含子目录

1. del /q       安静模式模式，删除全局通配符时，不提示确认

1. del /a       根据属性选择要删除的文件, /a:r(只包含只读文件) 和 /a:-r(除只读文件外)

1. ren oldname newname	重命名