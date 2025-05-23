# 🚀【Bash 高级实战项目清单】🚀

## ① 一键打包项目并上传 GitHub 🚀

**需求**：  

- 把当前项目文件夹压缩成 `.tar.gz`
- 自动推送到 GitHub 仓库（commit + push）

---

**脚本示范（叫 `git_push.sh`）**：
```bash
#!/bin/bash

# 获取当前目录名作为项目名
PROJECT_NAME=$(basename "$PWD")
DATE=$(date +%F)

# 压缩项目
tar -czvf "${PROJECT_NAME}_${DATE}.tar.gz" .

# Git操作
git add .
git commit -m "Backup on ${DATE}"
git push

echo "✅ 打包并推送完成！"
```

---

**使用方法**：
```bash
chmod +x git_push.sh
./git_push.sh
```

> （提前确保你 `git remote` 配置好，并登录过 GitHub）

---

## ② 定时同步本地笔记到云盘 ☁️

**需求**：
- 把 `~/notes` 文件夹同步到某个云盘本地同步目录，比如 `~/GoogleDrive/notes_backup`

---

**脚本示范（叫 `sync_notes.sh`）**：
```bash
#!/bin/bash

# 定义源目录和目标目录
SOURCE_DIR=~/notes
TARGET_DIR=~/GoogleDrive/notes_backup

# 创建目标目录（如果不存在）
mkdir -p "$TARGET_DIR"

# 使用 rsync 高效同步（只同步变化的）
rsync -av --delete "$SOURCE_DIR/" "$TARGET_DIR/"

echo "✅ 笔记同步完成！"
```

---

**定时自动同步设置**：
```bash
crontab -e
```
添加一行：
```bash
0 * * * * /路径/到/sync_notes.sh
```
（每小时自动同步一次！）

---

## ③ 监控某目录变化，自动备份 🔥

**需求**：
- 监控 `~/Documents`
- 只要一有变化（新增、修改文件），自动备份一份。

---

**脚本示范**（依赖 `inotifywait` 工具）：

安装依赖：
```bash
sudo apt install inotify-tools
```

脚本 `auto_backup_on_change.sh`：
```bash
#!/bin/bash

WATCH_DIR=~/Documents
BACKUP_DIR=~/backup

mkdir -p "$BACKUP_DIR"

while true; do
    inotifywait -r -e modify,create,delete "$WATCH_DIR"
    DATE=$(date +%F_%H-%M-%S)
    tar -czvf "$BACKUP_DIR/Documents_backup_$DATE.tar.gz" -C "$WATCH_DIR" .
    echo "📦 检测到变化，已自动备份！"
done
```

> 运行后，会持续监视，一有改动就自动打包备份。

---

## ④ 一键清理系统垃圾 🚽

**需求**：
- 快速清理 `.log`，临时文件，缓存等垃圾文件。

---

**脚本示范（叫 `clean_system.sh`）**：
```bash
#!/bin/bash

echo "🧹 开始清理系统缓存和日志..."

# 清理 apt 缓存
sudo apt clean

# 清理无用依赖
sudo apt autoremove -y

# 清理日志
sudo journalctl --vacuum-time=7d

# 删除临时文件
sudo rm -rf /tmp/*
sudo rm -rf ~/.cache/thumbnails/*

echo "✅ 清理完成！"
```

---

## ⑤ 超帅一键测速脚本 📈

**需求**：
- 测试当前网络速度（下载、上传）

---

**脚本示范（叫 `speed_test.sh`）**：

安装测速工具：
```bash
sudo apt install speedtest-cli
```

脚本内容：
```bash
#!/bin/bash

echo "🚀 正在测试网络速度..."
speedtest-cli
```

---

# 🔥 整体总结

| 项目 | 作用 | 关键词 |
|:----|:----|:----|
| 一键打包上传 GitHub | 项目快速备份、push | `tar` + `git` |
| 笔记同步云盘 | 自动数据同步 | `rsync` |
| 目录变动自动备份 | 实时监控文件变化 | `inotifywait` |
| 系统清理脚本 | 提升系统干净度 | `apt clean` + `rm` |
| 网络测速脚本 | 测试下载上传速度 | `speedtest-cli` |

---

# ✨ 如果你要练：

✅ 每一个项目  
✅ 都能独立写一版自己的改良版（比如加参数、日志记录）  
✅ 过一遍后，**真正做到自动化你的日常工作流**

👉 **到时候你自己就能写 Bash 工具级小程序了！！**  
绝对不是停留在 “命令会敲敲” 的水平了。🔥

---

# 🚀
要不要我再送你一份 👉  
【Bash 实战专项挑战清单（20个题目打怪升级版）】？  

比如：
- 写一个 **自动压缩+传输到远程服务器** 的脚本  
- 写一个 **一键生成新项目结构模板**  
- 写一个 **定时截屏保存桌面截图**  

要的话我可以直接给你打包一版「专项闯关清单」+「参考答案思路」！

 
👉 "**一键生成项目模板**" + "**定时截屏保存桌面**"  
（而且讲解得又快又细，方便你直接拿来用+魔改！）

---

# 🛠️ 项目一：一键生成新项目结构模板

## 🎯 目标
一条命令，自动生成一套像这样标准的工程目录：

```
myproject/
├── src/
├── include/
├── build/
├── README.md
└── Makefile
```

---

## ✅ 脚本示范（叫 `create_project.sh`）
```bash
#!/bin/bash

# 输入项目名字
PROJECT_NAME=$1

# 检查输入
if [ -z "$PROJECT_NAME" ]; then
  echo "❗ 请输入项目名称！"
  echo "用法：./create_project.sh 项目名"
  exit 1
fi

# 创建项目目录结构
mkdir -p "$PROJECT_NAME"/{src,include,build}

# 创建空文件
touch "$PROJECT_NAME/README.md"
touch "$PROJECT_NAME/Makefile"

echo "✅ 项目 $PROJECT_NAME 创建成功！"
```

---

### 📚 使用方法
1. 保存为 `create_project.sh`
2. 加执行权限：
   ```bash
   chmod +x create_project.sh
   ```
3. 使用：
   ```bash
   ./create_project.sh myapp
   ```
   就能自动生成 `myapp/` 整个目录！

---
> ✨ 进阶扩展：可以加上默认初始化 `git init`，或者根据语言选不同模板（要的话我还能给你升到"超级版"）

---

# 🛠️ 项目二：定时截屏保存桌面截图

## 🎯 目标
- 每10分钟自动截一次屏
- 保存到 `~/Pictures/Screenshots` 文件夹
- 文件名带时间戳

---

## ✅ 脚本示范（叫 `auto_screenshot.sh`）

### 安装工具
先安装 `gnome-screenshot` （默认Ubuntu基本都有）
```bash
sudo apt install gnome-screenshot
```

---

### 脚本内容
```bash
#!/bin/bash

# 截图保存目录
SAVE_DIR=~/Pictures/Screenshots

# 创建目录（如果没有）
mkdir -p "$SAVE_DIR"

# 文件名：年月日-时分秒.png
FILENAME=$(date +%Y-%m-%d_%H-%M-%S).png

# 截图并保存
gnome-screenshot -f "$SAVE_DIR/$FILENAME"

echo "📸 截图保存到 $SAVE_DIR/$FILENAME"
```

---

### 📚 手动测试
```bash
chmod +x auto_screenshot.sh
./auto_screenshot.sh
```
会看到在 `Pictures/Screenshots/` 文件夹下生成一张以时间命名的截图。

---

### ⏰ 定时自动截屏（配合 crontab）

1. 打开定时任务
```bash
crontab -e
```
2. 添加任务，比如每10分钟截图一次：
```bash
*/10 * * * * /完整路径/到/auto_screenshot.sh
```
意思是：每隔10分钟跑一次脚本！

---

# 🔥 进阶玩法（想升级的话）

- **设置定时只截图当前窗口**  
  `gnome-screenshot -w -f ...`
- **设置截图时不显示鼠标指针**  
  `gnome-screenshot --remove-border -f ...`
- **配合`zip`打包所有截图上传到云盘**！

---

# ✨ 总结

| 脚本 | 功能 | 技术点 |
|:----|:----|:----|
| create_project.sh | 快速搭建项目目录 | `mkdir` `{}` 多目录 | 
| auto_screenshot.sh | 自动桌面截图存档 | `gnome-screenshot` + `crontab` |

---

# 🚀 你已经在冲击「准自动化工程师」路线了

要不要我顺便也给你配一份：
> "**bash爆改版create_project.sh**"（比如：一键选 C++、Python、Web三种项目模板）

或者：
> "**bash自动整理截图文件到按月归档目录**"

这些都很简单，但一练就是质变！🌟

想继续解锁的话，直接告诉我：**冲！** ✨  
要不要继续？💬