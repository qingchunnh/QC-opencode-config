# Language
1. **回复语言**
   - 使用用户使用的语言进行回复
2. **代码注释语言**
   - 默认遵循当前工作目录中现有代码库的代码注释语言(包括新建文件)
   - 如果当前工作目录为全新项目(非基于现有代码库)，则默认使用英文
   - 如果用户明确指定代码注释语言，则使用用户指定的语言

# Code style
1. **代码注释添加**
   - 默认添加代码注释，除非用户明确要求不添加代码注释 
2. **代码注释格式**
   - 默认遵循当前工作目录中现有代码库的代码注释格式(包括新建文件)
   - 如果当前工作目录为全新项目(非基于现有代码库)，则默认添加规范的代码注释

# Git commit specification
1. **提交信息语言**
   - 默认使用当前工作目录中已有的提交历史语言
   - 如果当前工作目录无提交历史，则默认使用英文
   - 如果用户明确指定 Git 提交信息语言，则使用用户指定的语言
2. **提交信息规范**
   - 默认遵循当前工作目录中已有的提交历史风格
   - 如果当前工作目录中无提交历史，则严格遵循下方规范

## Commit Format
```
<type>: <description>

[optional body]

[optional footer(s)]
```
**Do not use scope**

## Commit Types
| Type       | Purpose                        |
| ---------- | ------------------------------ |
| `feat`     | New feature                    |
| `fix`      | Bug fix                        |
| `docs`     | Documentation only             |
| `style`    | Formatting/style (no logic)    |
| `refactor` | Code refactor (no feature/fix) |
| `perf`     | Performance improvement        |
| `test`     | Add/update tests               |
| `build`    | Build system/dependencies      |
| `ci`       | CI/config changes              |
| `chore`    | Maintenance/misc               |
| `revert`   | Revert commit                  |

## Generate Commit Message

Analyze the diff to determine:

- **Type**: What kind of change is this?
- **Description**: One-line summary of what changed (present tense, imperative mood, <72 chars)

# Tool Use Reminder
`glob` 和 `grep` 工具底层使用 `ripgrep`，默认情况下以 `.` 开头的隐藏目录以及 `.gitignore` 文件中列出的文件和目录都不会被遍历，也不会出现在搜索和列表结果中。
除非当前工作目录下包含 `.ignore` 文件并列出
例如:
```.ignore
!.github/
!node_modules/
```
这会使 `ripgrep` 取消忽略 `.ignore` 文件里的规则，即使已在 `.gitignore` 中列出也能进行搜索
要使用 `glob` 工具查找可能是隐藏目录或隐藏文件或以 `.` 开头的目录时，请搭配 `ls` 命令进行交叉验证