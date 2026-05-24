# 计划清单

一款简洁高效的 Android 计划管理应用，支持按日/周/月/季/年维度制定计划，配合智能提醒帮助你高效管理时间。

## 功能特性

- **多维度计划管理** — 日计划、周计划、月计划、季计划、年计划，五种类型一目了然
- **紧急程度分级** — 紧急（橙色）、一般（蓝色）、次要（绿色），颜色区分优先级
- **智能通知提醒** — 根据计划类型自动设置开始提醒和截止提醒
- **重复计划** — 支持按日/周/月/季/年自动重复，按周期自动编号（第1期、第2期...）
- **自然日历对齐** — 重复计划按自然日历边界划分（周计划按周一~周日，月计划按月初~月末等）
- **计划完成管理** — 手动标记完成，已完成计划自动归档
- **主题切换** — 浅色模式、深色模式、跟随系统三种主题

## 技术栈

| 技术 | 版本 |
|------|------|
| Expo SDK | 56 |
| React Native | 0.85.3 |
| React Navigation | 7.x |
| expo-notifications | 本地推送通知 |
| AsyncStorage | 数据持久化 |

## 项目结构

```
3.PlanListApp/
├── App.js                        # 入口文件
├── app.json                      # Expo 配置
├── src/
│   ├── constants/theme.js        # 颜色和主题定义
│   ├── contexts/AppContext.js    # 全局状态管理（Context + useReducer）
│   ├── utils/
│   │   ├── storage.js            # AsyncStorage 封装
│   │   ├── notifications.js      # 通知调度
│   │   └── dateUtils.js          # 日期工具函数
│   ├── components/
│   │   ├── PlanCard.js           # 计划卡片组件
│   │   ├── TabBar.js             # Tab 切换栏
│   │   ├── DatePickerField.js    # 日期选择器
│   │   └── ConfirmModal.js       # 确认弹窗
│   ├── navigation/AppNavigator.js
│   └── screens/
│       ├── HomeScreen.js         # 首页（计划列表）
│       ├── AddPlanScreen.js      # 新增/编辑计划
│       ├── PlanDetailScreen.js   # 计划详情
│       ├── SettingsScreen.js     # 设置
│       └── AboutScreen.js        # 关于
└── 开发过程/                      # 签名密钥和历史 APK
```

## 权限说明

| 权限 | 用途 |
|------|------|
| `RECEIVE_BOOT_COMPLETED` | 开机后重新调度通知 |
| `SCHEDULE_EXACT_ALARM` | 精确定时通知 |
| `USE_EXACT_ALARM` | Android 12+ 精确闹钟 |

## 许可证

MIT License
