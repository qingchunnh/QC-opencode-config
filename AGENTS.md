# Language
使用用户的语言回复用户
代码注释默认使用英文，除非用户指定代码注释的语言

# Code style
默认添加代码注释，除非用户明确要求不添加

# Tool Use Reminder
`glob` 和 `grep` 工具底层使用 `ripgrep`，默认情况下以 `.` 开头的隐藏目录以及 `.gitignore` 文件中列出的文件和目录都不会被遍历，也不会出现在搜索和列表结果中。
除非当前工作目录下包含 `.ignore` 文件并列出
例如:
```.ignore
!.github/
!node_modules/
```
这会使 `ripgrep` 取消忽略 `.ignore` 文件里的规则，即使已在 `.gitignore` 中列出也能进行搜索
如果当前工作目录下包含 `.ignore` 文件时请留意
建议如果要使用 `glob` 工具查找可能是隐藏目录或隐藏文件或以 `.` 开头的目录时，建议搭配 `ls` 命令进行交叉验证或直接使用 `ls` 命令
