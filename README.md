# Linux Arctis Manager

本项目 fork 自 [elegos/Linux-Arctis-Manager](https://github.com/elegos/Linux-Arctis-Manager)，基于 2.4.1 稳定版维护。它通过 USB 与 SteelSeries Arctis 设备通信，并提供独立的 Media、Chat 输出及 ChatMix 音量控制。

Media 对应游戏和普通声音一侧；设备列表可以使用音频服务的名称规则将其显示为 Game，程序内部仍保留 `Arctis_Media` 标识。

## 构建与运行

需要 Python 3.10 或更新版本、PulseAudio 或 PipeWire 的 PulseAudio 兼容服务，以及 `pyproject.toml` 声明的依赖。

```sh
uv build
pip install dist/linux_arctis_manager-*.whl
```

- `lam-daemon`：与设备通信、创建频道、同步 ChatMix。
- `lam-gui`：图形设置界面；`lam-gui --systray` 启动托盘。
- `lam-cli`：设备权限和桌面入口管理。具体参数见各命令的 `--help`。

设备访问需要安装匹配的 udev 规则，并启用 `arctis-manager.service` 用户服务。游戏声音手动选择 Media/Game，语音程序手动选择 Chat。连接和断开时自动切换输出保持关闭。

## 许可证

保留上游版权声明，按 [GNU GPL v3](LICENSE) 分发。
