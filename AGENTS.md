# Operating System
- 当前运行环境为 **macOS**
- Bash 工具使用 **zsh** 执行命令
- 系统中未安装 `rg`，请勿使用该命令

# Language
1. **回复语言**
   - 使用用户使用的语言进行回复
2. **代码注释语言**
   - 默认遵循当前工作目录中现有代码库的代码注释语言(包括新建文件)
   - 如果当前工作目录为全新项目(非基于现有代码库)，则默认使用英文作为代码注释语言
   - 如果用户明确指定代码注释语言，则使用用户指定的语言

# Code style
1. **代码注释添加**
   - 默认添加代码注释，除非用户明确要求不添加代码注释
2. **代码注释格式**
   - 默认遵循当前工作目录中现有代码库的代码注释格式(包括新建文件)
   - 如果当前工作目录为全新项目(非基于现有代码库)，则默认添加规范的代码注释

# Clarification
- 如果有任何不清楚的地方，向用户询问更多信息

# Git commit specification
1. **提交信息语言**
   - 默认使用当前工作目录中已有的提交历史语言
   - 如果当前工作目录无提交历史，则默认使用英文作为提交信息语言
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
1. **搜索工具行为**
   - `glob` 和 `grep` 默认不会遍历以 `.` 开头的隐藏目录以及 `.gitignore` 中列出的文件和目录，也不会将其包含在搜索和列表结果中
2. **隐藏文件交叉验证**
   - 当需要查找隐藏目录、隐藏文件或以 `.` 开头的目录时，应搭配 `ls` 命令进行交叉验证

# Code Verification
- 需要运行验证时，先列出计划运行的验证命令，询问用户是否需要执行，每次都必须经用户明确同意后才可执行

# File Operations
- 禁止在当前工作目录以外创建、修改、覆盖任何文件或目录（包括临时文件），如确有需要，每次执行前必须先说明操作内容和路径，经用户明确同意后才可执行
- 禁止以任何直接或间接方式（包括命令、脚本，或编写并运行程序）删除、移动、复制、重命名任何位置的文件或目录
- 如果确实需要执行删除、移动、复制、重命名文件或目录操作，必须告知用户并提供对应操作或命令，由用户手动执行
- 用户要求开发的功能本身涉及删除、移动、复制、重命名文件或目录操作时，必须先询问用户并获得许可