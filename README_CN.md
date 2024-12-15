# SwitchUbuntuGccGxxVersion
To switch the default GCC/G++ version on Ubuntu
切换Ubuntu的默认GCC/G++版本

[English Version | 英文说明](README.md)

## 缘由
当我们使用Github Action，通过一下系统版本来编译Openwrt时：  
  
-    ubuntu-latest    (22.04)  
-    ubuntu-24.04
  
我们可能遇到以下错误（当你选择了一些与node/clang相关的包）：  
  
`ERROR: package/feeds/packages/gn [host] failed to build.`  

## 使用
为了解决该问题，你可以使用本仓库，  
-  在此步骤后：[Initial Environment | 初始化环境]  
-  在此步骤前：[Clone Source Code | 克隆源码]  
  
```
- name: Switch GCC/GXX Version
    uses: xylz0928/SwitchUbuntuGccGxxVersion@v1.0.7
    with:
      TargetVer: '12'
```

  如果你不设置 `with` 参数, 则其默认版本会被设置为`GCC-12`和`G++-12`，这个版本在编译`Lean's Openwrt`和`hanwckf/immortalwrt-mt798x`时验证成功。  

  如果你需要一个真实的生产实例，参考以下：  
      x86 或 360T7 来自于:  
          @xylz0928/Openwrt-Make-x86_7621  

## 参考
  - [GitHub Actions](https://github.com/features/actions)
  - [OpenWrt](https://github.com/openwrt/openwrt)
  - [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
  - [hanwckf/immortalwrt-mt798x](https://github.com/hanwckf/immortalwrt-mt798x)
  - [xylz0928/Openwrt-Make-x86_7621](https://github.com/xylz0928/Openwrt-Make-x86_7621)
