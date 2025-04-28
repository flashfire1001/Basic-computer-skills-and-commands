# nautilus tricks for linux.

Ubuntu 自带的文件管理器叫 **Nautilus**，实际上就是 Files 图标后面的程序。稍微懂一点终端技巧,可以提升效率.

---

### 1.**在终端当前位置，想直接打开图形界面的 "文件管理器"（就是 Files 这个程序）**

在终端输入

```bash
nautilus .
```

就能打开当前目录了！

code . 等IDE也是这么打开的

✅ 直接跳出图形界面的窗口，定位到你现在终端所在的地方。

---

### 2. 如果想要打开别的目录，比如打开 `/home/jimmyxu/Downloads`，就可以：

```bash
nautilus ~/Downloads
输入绝对或者相对路径即可.
```

---

### ⚠️ 注意
如果你遇到报错比如：

```
No protocol specified
Unable to init server: Could not connect: Connection refused
```
那是因为你用的是 `sudo` 导致的。  
**不要用 `sudo nautilus` 除非真的需要管理员权限打开 Files！**

正常用户运行就够了。

---

### ✨（小升级）想偷懒更快的话，可以给自己加个小别名 alias：

编辑 `~/.bashrc`：

```bash
nano ~/.bashrc
```

加一句：

```bash
alias f='nautilus .'
```

保存后：

```bash
source ~/.bashrc
```

以后只要在终端打 `f`，一秒打开当前目录的 Files！🚀

---

