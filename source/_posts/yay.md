---
title: yay/paru 安装
date: 2025-1-24
---

（仅记录过程未添加中文说明）

```bash
cd ~
sudo pacman -S base-devel git
git clone https://aur.archlinux.org/yay.git
cd yay
git config --global http.sslverify false
nano PKGBUILD
```

在以下位置添加如下内容
![ac3](../img/arch-install/arch-install-step3.png)

```PKGBUILD
...
build() {
  export ...
  ...
  export GO111MODULE=on
  export GOPROXY=https://goproxy.cn
}
...
```

Ctrl+X
y
Enter

```bash
makepkg -si
```

![ac4](../img/arch-install/arch-install-step4.png)

Enter password(not root password)

```bash
yay -S paru
cd ..
rm -rf yay
```

---
