---
name: ux-spec
description: 维护企业级UX设计规范，涵盖样式主题（颜色、字体、间距、圆角、阴影）、设计组件、设计模板等。当用户提及设计系统、设计规范、主题色、品牌色、设计组件、企业UI、UX规范、design tokens、design system时使用此skill。也用于创建新的设计规范、扩展现有规范、或查询设计token。
---

# UX Spec Skill

本skill用于维护企业级UX设计规范，提供完整的设计系统支持，包括样式主题（Design Tokens）、设计组件、设计模板等。

## 数据源

规范数据位于 skill 目录下:

```
ux-spec/
├── SKILL.md
└── data/
    ├── theme-colors/        # 主题色规范 (已实现)
    ├── typography/           # 文本样式 (预留)
    ├── spacing/             # 间距系统 (预留)
    ├── border-radius/       # 圆角规范 (预留)
    ├── shadow/              # 阴影规范 (预留)
    ├── opacity/             # 透明度规范 (预留)
    ├── border/              # 边框规范 (预留)
    ├── components/          # 设计组件 (预留)
    ├── templates/           # 设计模板 (预留)
    └── patterns/            # 设计模式 (预留)
```

## 已实现功能

### 主题色 (Theme Colors)

**数据文件:** `data/theme-colors/theme-colors.csv`

**字段说明:**
| 字段 | 说明 |
|------|------|
| S_Keywords | 关键词/分类 |
| S_Synonyms | 同义词/使用场景 |
| O_Token | 设计 token 名称 |
| O_Hex | 十六进制颜色值 |
| O_Pixso_Path | Pixso 组件路径 |

**色彩分类 (共24个token):**
- **Primary (品牌色系)** - 5个: 主色、悬停、点击、浅色、极浅
- **Success (成功色系)** - 3个: 主色、悬停、浅色
- **Info (信息色系)** - 2个: 主色、浅色
- **Warning (警告色系)** - 2个: 主色、浅色
- **Error (错误色系)** - 3个: 主色、悬停、浅色
- **Text (文字色系)** - 4个: 主文字、次要文字、占位文字、禁用文字
- **Border (边框色系)** - 2个: 主边框、次边框
- **Background (背景色系)** - 2个: 主背景、次背景
- **Link (链接色)** - 1个

## 使用方式

### 查询主题色

1. 读取 `data/theme-colors/theme-colors.csv` 获取完整的主题色规范
2. 根据用途筛选合适的颜色:
   - 品牌/主色调 → Primary 系列
   - 成功/完成状态 → Success 系列
   - 信息/提示 → Info 系列
   - 警告/注意 → Warning 系列
   - 错误/危险 → Error 系列
   - 文字颜色 → Text 系列
   - 边框/分割线 → Border 系列
   - 背景色 → Background 系列
   - 链接 → Link 系列

### 应用主题色

根据场景返回对应的 hex 值和 token 名称:

- **按钮主色**: `Primary (#0067D1, token: AUI-Color_Primary)`
- **成功状态**: `Success (#00A870, token: AUI-Color_Success)`
- **错误提示**: `Error (#F53F3F, token: AUI-Color_Error)`
- **主要文字**: `Text Main (#1D2129, token: AUI-Color_Text_Main)`
- **次要文字**: `Text Secondary (#4E5969, token: AUI-Color_Text_Secondary)`
- **页面背景**: `Background Main (#FFFFFF, token: AUI-Color_BG_Main)`
- **卡片背景**: `Background Secondary (#F7F8FA, token: AUI-Color_BG_Secondary)`

### 扩展规范

当需要添加新的设计维度时:

1. 在 `data/` 下创建对应的文件夹 (如 `typography/`)
2. 编写 CSV 数据文件，包含清晰的字段定义
3. 更新本 SKILL.md 添加模块说明

## 规范原则

- **一致性**: 所有设计决策需遵循现有规范
- **可扩展性**: 预留模块便于未来扩展
- **可追溯性**: 每个 token 需关联设计工具中的源路径
- **语义化**: 使用语义化的命名而非视觉描述

## 触发场景

- 用户询问设计系统或设计规范
- 需要应用主题色/品牌色
- 创建或扩展UX设计组件
- 查询设计token值
- 需要保持UI一致性
