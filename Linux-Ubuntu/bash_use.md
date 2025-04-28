
# 🖥️  **bash**（终端）常用指令总结（Ubuntu通用版）

### 🔵 目录与文件操作

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `pwd` | 查看当前所在目录 | `pwd` |
| `ls` | 列出当前目录下的文件 | `ls` |
| `ls -l` | 列详细信息（权限、大小等） | `ls -l` |
| `ls -a` | 列出所有文件（包括隐藏） | `ls -a` |
| `cd 路径` | 切换目录 | `cd /home/jimmyxu` |
| `cd ~` | 回到主目录 | `cd ~` |
| `cd ..` | 返回上一级目录 | `cd ..` |
| `mkdir 文件夹名` | 创建新目录 | `mkdir myfolder` |
| `rmdir 文件夹名` | 删除空目录 | `rmdir myfolder` |
| `rm -r 文件夹名` | 强制删除文件夹和内容 | `rm -r myfolder` |

---

### 🔵 文件操作

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `touch 文件名` | 新建空文件 | `touch hello.txt` |
| `cp 源 目标` | 复制文件或文件夹 | `cp a.txt b.txt` |
| `cp -r 源 目标` | 递归复制整个文件夹 | `cp -r folder1 folder2` |
| `mv 源 目标` | 移动或重命名 | `mv a.txt /home/jimmyxu/` |
| `rm 文件名` | 删除文件 | `rm a.txt` |

---

### 🔵 查看文件内容

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `cat 文件名` | 直接显示文件内容 | `cat hello.txt` |
| `less 文件名` | 分页查看（推荐） | `less hello.txt` |
| `head 文件名` | 看前10行 | `head hello.txt` |
| `tail 文件名` | 看后10行 | `tail hello.txt` |
| `tail -f 文件名` | 实时追踪文件变化（看日志超好用） | `tail -f /var/log/syslog` |

---

### 🔵 系统与进程管理

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `top` | 查看实时系统资源占用 | `top` |
| `htop` | 更好看的系统监控（要安装） | `htop` |
| `ps aux` | 查看当前所有进程 | `ps aux` |
| `kill 进程号` | 杀掉一个进程 | `kill 1234` |
| `kill -9 进程号` | 强制杀掉（无法关闭时用） | `kill -9 1234` |

---

### 🔵 权限相关

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `chmod 权限 文件名` | 改变文件权限 | `chmod 755 run.sh` |
| `chown 用户:用户组 文件名` | 改变文件所有者 | `chown jimmy:jimmy run.sh` |
| `sudo 命令` | 以管理员身份执行命令 | `sudo apt update` |

---

### 🔵 网络指令（基本）

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `ping 地址` | 测试网络连接 | `ping www.baidu.com` |
| `curl 地址` | 下载网页内容 | `curl www.example.com` |
| `wget 地址` | 下载文件 | `wget https://example.com/file.zip` |

---

### 🔵 软件包管理（Ubuntu 用 apt）

| 指令 | 作用 | 示例 |
|:-----|:-----|:-----|
| `sudo apt update` | 更新软件列表 | `sudo apt update` |
| `sudo apt upgrade` | 升级所有已安装软件 | `sudo apt upgrade` |
| `sudo apt install 包名` | 安装新软件 | `sudo apt install git` |
| `sudo apt remove 包名` | 卸载软件 | `sudo apt remove git` |

---

## 📦 常用小技巧

| 技巧 | 说明 | 示例 |
|:-----|:-----|:-----|
| `Tab` 自动补全路径或命令 | `cd Docu`（按Tab自动补全为 Documents） |
| `↑ ↓` 回顾历史指令 | 按上键可以回到上次输入的命令 |
| `Ctrl + C` | 终止当前命令运行 | 比如取消 ping |
| `Ctrl + L` | 清屏 | 比 `clear` 命令还快 |
| `!!` | 重复上一个命令 | `!!` 直接执行 |
| `sudo !!` | 上一条命令加 sudo 重跑 | 超好用！ |

---

