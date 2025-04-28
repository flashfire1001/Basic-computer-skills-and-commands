好！！  
你要的都是**真正高级且实用**的内容了！🔥  
我给你按模块详细讲清楚，**从基础到进阶，配例子讲**，  
让你不仅懂，还能自己马上动手练习！

---

# 🔥【进阶Bash技巧大全】🔥

---

## ① 查找 (`find`) — 全盘搜，秒杀手动翻找！

### 基本格式
```bash
find 起始目录 -条件 动作
```

---

### 常用例子

| 命令 | 含义 |
|:----|:----|
| `find . -name "*.txt"` | 当前目录下找所有 `.txt` 文件 |
| `find /home -type d -name "test"` | 在 `/home` 下找名字叫 `test` 的目录 |
| `find . -size +10M` | 找大于10MB的文件 |
| `find /var/log -mtime -7` | 找7天内修改过的文件 |

---

### 高级加动作
比如找到就**删除**，加上 `-exec`
```bash
find . -name "*.tmp" -exec rm {} \;
```
- 找到所有 `.tmp` 文件并删除。
- `{}` 代表找到的每一个文件。
- `\;` 结尾（记得有空格）。

---

## ② 批量操作 — 批量重命名、批量删除、批量处理

---

### 批量重命名文件
比如把所有 `.JPG` 改成 `.jpg`
```bash
for file in *.JPG; do mv "$file" "${file%.JPG}.jpg"; done
```
- `for` 遍历所有 `.JPG` 文件
- `mv` 改名，把 `.JPG` 去掉换成 `.jpg`

---

### 批量删除某种文件
比如删除所有 `.log` 文件：
```bash
rm *.log
```
如果子目录也要删，用 `find`
```bash
find . -name "*.log" -exec rm {} \;
```

---

### 批量新建多个文件
```bash
touch file{1..10}.txt
```
生成：`file1.txt`, `file2.txt`, ..., `file10.txt`

---

## ③ 正则表达式匹配 — 超灵活搜索神器！

---

在 `find` 或 `grep` 里经常用正则（regex）

### grep 基本用法
```bash
grep "关键词" 文件名
```

比如：
```bash
grep "hello" test.txt
```
找出 `test.txt` 里所有含 "hello" 的行。

---

### 高级grep（支持正则）
```bash
grep -E "ab|cd" test.txt
```
找出 `ab` 或 `cd` 的行。

```bash
grep -E "[0-9]{3,5}" test.txt
```
找出文件里**出现3到5位数字**的地方。

---

### 配合 find 一起用

找出所有包含 "error" 的日志文件
```bash
find /var/log -name "*.log" -exec grep "error" {} \;
```

---

## ④ 自动备份脚本 — 小项目实战！

---

### 需求
每天晚上，把 `~/Documents` 备份一份到 `~/backup` 文件夹，并且加上日期后缀。

---

### 完整脚本示范（叫 `backup.sh`）
```bash
#!/bin/bash

# 定义源目录和备份目录
SOURCE_DIR=~/Documents
BACKUP_DIR=~/backup

# 获取当前时间，格式：2025-04-27
DATE=$(date +%F)

# 创建备份文件夹（如果不存在）
mkdir -p "$BACKUP_DIR"

# 打包 Documents 为压缩包
tar -czvf "$BACKUP_DIR/Documents_backup_$DATE.tar.gz" -C "$SOURCE_DIR" .

echo "✅ 备份完成：$BACKUP_DIR/Documents_backup_$DATE.tar.gz"
```

---

### 怎么用

1. 保存上面的脚本为 `backup.sh`
2. 给它加执行权限：
```bash
chmod +x backup.sh
```
3. 执行：
```bash
./backup.sh
```
4. 每天定时自动运行（加到 `crontab`）
```bash
crontab -e
```
添加一行：
```bash
0 23 * * * /路径/到/backup.sh
```
👉 代表每天晚上23:00自动跑一次备份！

---

# 🛠️ 总结

| 模块 | 用法 | 特点 |
|:----|:----|:----|
| `find` | 查找文件或文件夹 | 条件+动作，万能搜索 |
| 批量操作 | `for`循环、批量 `mv/rm` | 管理大量文件 |
| 正则 | `grep -E` | 灵活匹配文本 |
| 自动脚本 | `bash + crontab` | 自动化备份、轻松无忧 |

---

# ✨ 如果你掌握了上面这套，  
- 你的 Linux 基础就已经进阶到了**能写小工具、能运维系统**的水平了。
- 你离真正成为 Linux "半个高手" 只差练习和实战了！

