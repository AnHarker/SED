###SED
>&emsp;用法：
&emsp;&emsp;sed[option]... 'script' inputfile...
&emsp;常用选项：
&emsp;&emsp;-n&emsp;不输出模式空间内容到屏幕，即不自动打印
&emsp;&emsp;-e&emsp;多点编辑
&emsp;&emsp;-f /PATH/SCRIPT_FILE&emsp;从指定文件中读取编辑脚本
&emsp;&emsp;-r&emsp;支持使用扩展正则表达式
&emsp;&emsp;-i.bak&emsp;备份文件并原处编辑
&emsp;&emsp;nl&emsp;显示行号
&emsp;script:
&emsp;&emsp;'地址命令'
地址定界：
&emsp;不给地址：对全文进行处理
&emsp;单地址：
&emsp;&emsp;&emsp;#: 指定的行，$：最后一行
&emsp;&emsp;&emsp;/pattern/：被此处模式所能够匹配到的每一行
&emsp;地址范围：
&emsp;&emsp;&emsp;#,#
&emsp;&emsp;&emsp;#,+#
&emsp;&emsp;&emsp;/pat1/,/pat2/
&emsp;&emsp;&emsp;#,/pat1/
&emsp; ~：步进
&emsp;&emsp;&emsp;1~2 奇数行
&emsp;&emsp;&emsp;2~2 偶数行
编辑命令：
&emsp;&emsp;d&emsp;删除模式空间匹配的行，并立即启用下一轮循环
&emsp;&emsp;p&emsp;打印当前模式空间内容，追加到默认输出之后
&emsp;&emsp;a [\]text&emsp;在指定行后面追加文本，支持使用\n实现多行追加
&emsp;&emsp;i[\]text&emsp;在行前面插入文本
&emsp;&emsp;c [\]tex&emsp;t替换行为单行或多行文本
&emsp;&emsp;w /path/file&emsp;保存模式匹配的行至指定文件
&emsp;&emsp;r /path/file&emsp;读取指定文件的文本至模式空间中匹配到的行后
&emsp;&emsp;=&emsp;为模式空间中的行打印行号
&emsp;&emsp;!&emsp;模式空间中匹配行取反处理
&emsp;s///&emsp;查找替换,支持使用其它分隔符，s@@@，s###
&emsp;替换标记：
&emsp;&emsp;g行内全局替换
&emsp;&emsp;&emsp;p显示替换成功的行
&emsp;&emsp;&emsp;w /PATH/FILE&emsp;将替换成功的行保存至文件中

高级编辑命令
>- P：打印模式空间开端至\n内容，并追加到默认输出之前
- h: 把模式空间中的内容覆盖至保持空间中
- H：把模式空间中的内容追加至保持空间中
- g: 从保持空间取出数据覆盖至模式空间
- G：从保持空间取出内容追加至模式空间
- x: 把模式空间中的内容与保持空间中的内容进行互换
- n: 读取匹配到的行的下一行覆盖至模式空间
- N：读取匹配到的行的下一行追加至模式空间
- d: 删除模式空间中的行
- D：如果模式空间包含换行符，则删除直到第一个换行符的模式空间中的文本，并不会读取新的输入行，而使用合成的模式空间重新启动循环。如果模式空间不包含换行符，则会像发出d命令那样启动正常的新循环