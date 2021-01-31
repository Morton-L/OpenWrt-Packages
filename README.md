# OpenWrt packages feed

## 说明 - Description

该项目专用于向 [BoltWrt](https://github.com/Morton-L/BoltWrt) 项目提供软件包,其中包含了社区维护的编译脚本.<br>

## 用法 - Usage

该软件源调用地址已放置在 [BoltWrt](https://github.com/Morton-L/BoltWrt) 项目根目录中,并默认启用状态<br>
该项目为 [BoltWrt](https://github.com/Morton-L/BoltWrt) 项目定制,不保证可以在其他环境或程序代码中拥有良好的兼容性与可靠性.
如您希望在 [BoltWrt](https://github.com/Morton-L/BoltWrt) 分支版本中使用该软件源,可以通过编辑 [BoltWrt](https://github.com/Morton-L/BoltWrt) 项目根目录的`feeds.conf.default`文件来实现.<br>
并运行命令:
```
./scripts/feeds update packages
./scripts/feeds install -a -p packages
```
 
## 指南 - Guidelines

请查阅 [CONTRIBUTING.md](CONTRIBUTING.md) 文件.

## Changelog - 变更记录

该项目的变更记录将会体现在 [BoltWrt](https://github.com/Morton-L/BoltWrt) 项目中.

## License

[GPL](LICENSE)


