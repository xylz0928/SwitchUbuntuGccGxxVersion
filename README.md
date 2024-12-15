# SwitchUbuntuGccGxxVersion
To switch the default GCC/G++ version on Ubuntu

[Chinese Version | 中文说明](https://github.com/xylz0928/SwitchUbuntuGccGxxVersion/blob/master/README_CN.md))

## Cause
When we compile openwrt on Github Action with OS version:  
  
-    ubuntu-latest    (22.04)  
-    ubuntu-24.04
  
We may face the issue if you select some packages related to node/clang:  
  
`ERROR: package/feeds/packages/gn [host] failed to build.`  

## Usage
To solve this issue, you can take this repository,  
-  After your step [Initial Environment]  
-  Before your step [Clone Source Code]  
  
```
- name: Switch GCC/GXX Version
    uses: xylz0928/SwitchUbuntuGccGxxVersion@v1.0.7
    with:
      TargetVer: '12'
```

  If you don't put [with] parameters, the default version will be set to GCC-12 and G++-12 which are tested good to compile openwrt  

  Refer to Github Action:  
      x86 or 360T7 of:  
          @xylz0928/Openwrt-Make-x86_7621  
  if you wanna a real production instant.  

## Acknowledgments
  - [GitHub Actions](https://github.com/features/actions)
  - [OpenWrt](https://github.com/openwrt/openwrt)
  - [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
  - [hanwckf/immortalwrt-mt798x](https://github.com/hanwckf/immortalwrt-mt798x)
  - [xylz0928/Openwrt-Make-x86_7621](https://github.com/xylz0928/Openwrt-Make-x86_7621)
