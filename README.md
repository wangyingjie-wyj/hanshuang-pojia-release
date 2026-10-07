# 寒霜破甲 · 便携版发布仓库

本仓库用于分发 **寒霜破甲工具** Windows 便携版完整包（免安装 / 解压即用）。

> 源码仓库：[wangyingjie-wyj/hanshuang-pojia](https://github.com/wangyingjie-wyj/hanshuang-pojia)
> 本仓库只放构建产物，源码仓库保持干净。

## 下载

| 文件 | 大小 | 说明 |
| --- | --- | --- |
| `寒霜破甲.zip` | 146.3 MiB (153,384,899 字节) | Windows x64 便携版完整包 |

SHA-256：`0A69F348A0032B93D812FD4DB4ABE3B0633ADC9FDFD0380B074E7BC12C309456`

单文件超过 GitHub 100 MB 直接推送限制，因此由 **Git LFS** 托管。

### 方式一：git clone（需先装 Git LFS）

```bash
git lfs install
git clone https://github.com/wangyingjie-wyj/hanshuang-pojia-release.git
```

只取最新版、不要历史：

```bash
git lfs install
git clone --depth 1 https://github.com/wangyingjie-wyj/hanshuang-pojia-release.git
```

### 方式二：只下文件

进入仓库页面 → 点 `寒霜破甲.zip` → **Download raw file**。

> 如果 clone 下来只有 1 KB 的文本指针而不是真实压缩包，说明本机没装 Git LFS：
> 装好后在本仓库目录执行 `git lfs pull` 即可补齐。

## 使用

1. 解压 `寒霜破甲.zip` 到**纯英文路径**（中文路径可能导致启动异常）
2. 双击 `寒霜破甲工具.exe` 运行
3. 卸载：运行目录内的 `卸载-便携版.bat`

### 包内结构

```
寒霜破甲.zip
├── 寒霜破甲工具.exe          # 主程序 (Electron 便携版)
├── 卸载-便携版.bat           # 便携版卸载脚本
├── resources/
│   ├── app.asar              # 应用主体
│   ├── install*.ps1          # 各工具链安装脚本
│   └── 寒霜v*.md             # 文档
├── locales/                  # 多语言资源
└── *.dll / *.pak / *.bin     # Electron 运行时
```

## 校验

```powershell
git lfs ls-files --long                        # 查看 LFS OID (SHA-256) 与字节数
certutil -hashfile 寒霜破甲.zip SHA256          # 与上方 SHA-256 比对
```

## 环境要求

- Windows 10 / 11 x64
- 免安装，无需管理员权限

## 更新发布

```bash
cp 新的寒霜破甲.zip .
git add 寒霜破甲.zip && git commit -m "更新寒霜破甲便携版"
git push
```
