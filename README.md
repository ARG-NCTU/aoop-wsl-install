# Windows 與 macOS Ubuntu 安裝教學

## Windows：安裝 WSL2 + Ubuntu

> Windows 請使用 **PowerShell / Windows Terminal**。

### 1. 開啟系統管理員權限的 Windows Terminal

如果目前已經在一般 PowerShell，可以輸入：

```powershell
Start-Process wt -Verb RunAs
```

系統會開啟具有系統管理員權限的 Windows Terminal。

---

### 2. 查看可安裝的 Linux 發行版

```powershell
wsl --list --online
```

---

### 3. 安裝 WSL2 與 Ubuntu 24.04

```powershell
wsl --install -d Ubuntu-24.04
```

這個指令會自動安裝 WSL 所需元件並安裝 Ubuntu。

---

### 4. 重新啟動 Windows

安裝完成後，將電腦重新啟動。

---

### 5. 第一次啟動 Ubuntu

重新開機後，在 Windows 搜尋欄搜尋：

```text
Ubuntu
```

點選 Ubuntu 開啟。

第一次啟動時，Ubuntu 會要求建立 Linux 使用者名稱與密碼。

例如：

```text
Enter new UNIX username: kevin
New password:
Retype new password:
```

輸入密碼時畫面不會顯示字元，這是正常的。

完成後就會進入 Ubuntu Terminal。

---

### 6. 更新 Ubuntu

進入 Ubuntu 後執行：

```bash
sudo apt update
sudo apt upgrade -y
```

Windows 的 WSL2 + Ubuntu 安裝完成。

---

# macOS：安裝 Ubuntu

macOS **不能安裝 WSL**，因為 WSL 是 Windows 專用功能。

如果需要真正的 Ubuntu，可以使用 **UTM 虛擬機**。

---

## 1. 確認 Mac 架構

開啟 Terminal：

```bash
uname -m
```

如果看到：

```text
arm64
```

代表 Apple Silicon Mac，例如 M1、M2、M3、M4、M5。

Ubuntu 請下載 **ARM64** 版本。

如果看到：

```text
x86_64
```

代表 Intel Mac。

Ubuntu 請下載 **AMD64 / x86_64** 版本。

---

## 2. 安裝 Homebrew

如果尚未安裝 Homebrew，在 Terminal 執行：

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

安裝結束後，依 Terminal 最後顯示的指示把 Homebrew 加入 PATH。

---

## 3. 安裝 UTM

```bash
brew install --cask utm
```

安裝完成後可以直接開啟：

```bash
open -a UTM
```

---

## 4. 下載 Ubuntu

前往 Ubuntu 官方網站下載 Ubuntu LTS ISO：

https://ubuntu.com/download

Apple Silicon：

```text
ARM64
```

Intel Mac：

```text
AMD64 / x86_64
```

---

## 5. 在 UTM 建立 Ubuntu

開啟 UTM 後依序選擇：

```text
Create a New Virtual Machine
→ Virtualize
→ Linux
```

選擇剛才下載的 Ubuntu ISO。

建議至少設定：

```text
CPU：4 Cores
RAM：4～8 GB
Disk：40 GB 以上
```

接著啟動虛擬機並依 Ubuntu 安裝畫面完成：

```text
語言
鍵盤
使用者名稱
密碼
磁碟安裝
```

安裝完成後重新啟動 Ubuntu。

---

## 6. 更新 Ubuntu

開啟 Ubuntu Terminal：

```bash
sudo apt update
sudo apt upgrade -y
```

macOS 的 Ubuntu 虛擬機安裝完成。
