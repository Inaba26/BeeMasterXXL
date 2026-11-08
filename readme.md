## Upstream

本项目 fork 自 [BigOrangeQWQ/BeeMasterXXL](https://github.com/BigOrangeQWQ/BeeMasterXXL)，上游为 [hxync/BeeMasterXXL](https://github.com/hxync/BeeMasterXXL)。

## 分支

- `main`：当前开发分支
- `beta1`：适配 GTNH 2.9.0-beta-1
- `beta2`：适配 GTNH 2.9.0-beta-2
- `beta3`：适配 GTNH 2.9.0-beta-3 (可能也适用于RC1、RC2及2.9.0正式版，待测试)

## 组装需求

相比普通的机器人装配线，机器人需要额外安装**因特网卡（Internet Card）**，否则无法下载和更新脚本。
其余要求见[wiki相关页面](https://gtnh.huijiwiki.com/wiki/%E6%8C%87%E5%8D%97:%E8%9C%9C%E8%9C%82%E8%82%B2%E7%A7%8D%E8%87%AA%E5%8A%A8%E5%8C%96#%E9%A1%B9%E7%9B%AE1_BeeMasterXXL)

## 安装（首次）

在机器人的 OC 终端执行（按你的 GTNH 版本选择分支）：

```
wget https://raw.githubusercontent.com/Inaba26/BeeMasterXXL/beta1/installer.lua
installer
```

> beta3 环境把 URL 中的 `beta1` 换成 `beta3`。

installer 会下载全部脚本（包括 `config.lua`，已存在的同名文件会被覆盖），适合全新安装或整体重置。

## 更新

如果机器人里还没有 `upgrade.lua`，先手动拉取一次：

```
wget https://raw.githubusercontent.com/Inaba26/BeeMasterXXL/beta1/upgrade.lua
upgrade
```

以后每次更新只需在终端运行 `upgrade` 即可。运行时会询问仓库地址和分支/标签，回车使用默认值；将来仓库迁移或要切到某个 tag 时，在提示处输入新地址/标签即可。脚本会覆盖除 `config.lua` 外的所有脚本，`config.lua` 和基因数据 `data.txt` 不受影响。升级完成后重新运行 `bee.lua`。

> 切换 GTNH 版本（如 beta1 升 beta2）时，重新跑对应分支的 installer 即可。
