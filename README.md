# HomeKit Bridge Area and Label Filters

这是 Home Assistant 内置 HomeKit Bridge 集成的定制版本，在新增和重新配置桥接器时增加：

- 按区域包含或排除实体
- 按标签包含或排除实体
- 将区域、标签与已有的实体类型筛选组合使用
- 区域和标签使用与“要包含的域”一致的单框多选界面
- 首次添加和后续“配置”流程均为域、区域和标签提供独立的 Inclusion mode

## 安装

### 通过 HACS

1. 在 HACS 中添加此 GitHub 仓库为“自定义仓库”，类别选择“集成”。
2. 安装 `HomeKit Bridge Area and Label Filters`。
3. 重启 Home Assistant。

### 手动安装

将 `custom_components/homekit` 完整复制到 Home Assistant 配置目录：

```text
/config/custom_components/homekit
```

然后重启 Home Assistant。自定义集成使用与内置集成相同的 `homekit` domain，因此会覆盖内置 HomeKit Bridge，无需重新编译 Home Assistant。

## 兼容性

当前代码基于 Home Assistant Core `2026.8.0.dev0`，上游提交 `de37e6be451`。

覆盖内置集成意味着 Home Assistant 升级后，本仓库中的 HomeKit 代码不会自动同步。升级 Home Assistant 前请确认本仓库已同步对应版本；如果出现兼容性问题，可从 HACS 卸载本集成并重启，以恢复使用内置 HomeKit Bridge。

区域和标签会在保存配置时展开为实体。区域或标签的成员发生变化后，请重新打开 HomeKit Bridge 配置并保存一次。

## 开发

运行文件位于：

```text
custom_components/homekit
```

`src/core` 是用于同步和测试的 Home Assistant Core 源码快照，不是 HACS 安装内容。

## License

此项目基于 Home Assistant Core，遵循 Apache License 2.0。
