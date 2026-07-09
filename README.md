# Tavo MCP Server

为 [Tavo](https://tavo.app) 角色扮演平台提供完整的 **MCP (Model Context Protocol)** 远程管理接口。

> ⚠️ **声明**：本包为 Tavo MCP Server 的 Operit 平台适配封装。MCP 服务端及其所有工具归 **Tavo 平台** 所有，本人仅负责 Operit 包封装与文档维护，非工具集创作者。

---

## 版本

**v1.0.0**

## 简介

Tavo MCP Server 将 Tavo 平台的完整数据管理能力通过 MCP 协议暴露，使 AI 助手（如 Operit）能够直接操作角色卡、世界书、正则脚本、预设、人格、聊天会话、消息、输入框和插件等全部数据类型。

## 工具概览

### 📊 状态
| 工具 | 说明 |
|------|------|
| `tavo_status` | 获取 Tavo MCP 服务运行状态及数据资产统计 |

### 🎭 角色卡（Character）
| 工具 | 说明 |
|------|------|
| `tavo_character_search` | 按名称搜索角色卡 |
| `tavo_character_get` | 按 ID 读取角色卡完整数据 |
| `tavo_character_create` | 创建新角色卡 |
| `tavo_character_update` | 按 ID 更新角色卡元数据 |
| `tavo_character_import_card` | 导入 V3/SillyTavern 格式角色卡 JSON（含内嵌世界书和正则脚本） |
| `tavo_character_delete` | 按 ID 删除角色卡 |

### 📚 世界书（Lorebook）
| 工具 | 说明 |
|------|------|
| `tavo_lorebook_search` | 按名称搜索世界书 |
| `tavo_lorebook_get` | 按 ID 读取世界书完整数据 |
| `tavo_lorebook_create` | 创建新世界书 |
| `tavo_lorebook_update` | 按 ID 更新世界书（名称、条目等） |
| `tavo_lorebook_import` | 导入 V3/SillyTavern 格式世界书 |
| `tavo_lorebook_delete` | 按 ID 删除世界书 |
| `tavo_lorebook_entry_upsert` | 在世界书中插入或更新单条条目 |
| `tavo_lorebook_entry_delete` | 在世界书中删除单条条目 |

### 🔧 正则脚本（Regex）
| 工具 | 说明 |
|------|------|
| `tavo_regex_search` | 按名称搜索正则脚本 |
| `tavo_regex_get` | 按 ID 读取正则脚本 |
| `tavo_regex_create` | 创建新正则脚本 |
| `tavo_regex_update` | 按 ID 更新正则脚本 |
| `tavo_regex_import` | 导入正则脚本 |
| `tavo_regex_delete` | 按 ID 删除正则脚本 |
| `tavo_regex_entry_upsert` | 在正则脚本中插入或更新单条规则 |
| `tavo_regex_entry_delete` | 在正则脚本中删除单条规则 |
| `tavo_regex_test` | 测试正则替换规则（输入→匹配→替换→输出） |

### 🎛️ 预设（Preset）
| 工具 | 说明 |
|------|------|
| `tavo_preset_search` | 按名称搜索预设 |
| `tavo_preset_get` | 按 ID 读取预设 |
| `tavo_preset_create` | 创建新预设 |
| `tavo_preset_update` | 按 ID 更新预设 |
| `tavo_preset_import` | 导入预设 |
| `tavo_preset_delete` | 按 ID 删除预设 |
| `tavo_preset_entry_upsert` | 在预设中插入或更新配置项 |
| `tavo_preset_entry_delete` | 在预设中删除配置项 |
| `tavo_preset_set_active` | 激活指定预设 |

### 👤 人格（Persona）
| 工具 | 说明 |
|------|------|
| `tavo_persona_search` | 按名称搜索人格 |
| `tavo_persona_get` | 按 ID 读取人格 |
| `tavo_persona_create` | 创建新人格 |
| `tavo_persona_update` | 按 ID 更新人格 |
| `tavo_persona_delete` | 按 ID 删除人格 |
| `tavo_persona_set_active` | 激活指定人格 |

### 💬 聊天（Chat）
| 工具 | 说明 |
|------|------|
| `tavo_chat_search` | 按标题搜索聊天会话 |
| `tavo_chat_get` | 按 ID 读取聊天（可选含消息） |
| `tavo_chat_create` | 创建新聊天会话 |
| `tavo_chat_update` | 更新聊天元数据、成员和覆盖设置 |
| `tavo_chat_delete` | 删除聊天会话 |
| `tavo_chat_copy` | 复制聊天会话 |
| `tavo_chat_reset` | 重置聊天消息/状态 |
| `tavo_current_chat_get` | 读取当前活跃聊天 |
| `tavo_current_chat_set` | 设置当前活跃聊天 |

### ✉️ 消息（Message）
| 工具 | 说明 |
|------|------|
| `tavo_message_find` | 在聊天中查找消息 |
| `tavo_message_get` | 按 ID 或索引读取消息 |
| `tavo_message_count` | 统计聊天消息数量 |
| `tavo_message_append` | 向聊天追加消息 |
| `tavo_message_insert` | 在指定索引插入消息 |
| `tavo_message_update` | 更新消息内容 |
| `tavo_message_delete` | 删除消息 |

### ⌨️ 输入框（Input）
| 工具 | 说明 |
|------|------|
| `tavo_input_get` | 读取当前输入框文本 |
| `tavo_input_set` | 设置当前输入框文本 |
| `tavo_input_append` | 向输入框追加文本 |
| `tavo_input_clear` | 清空输入框 |
| `tavo_input_send` | 通过 UI 发送输入框内容 |

### 🔌 插件管理（Plugin）
| 工具 | 说明 |
|------|------|
| `tavo_plugin_search` | 搜索已安装插件 |
| `tavo_plugin_get` | 读取插件清单和配置 |
| `tavo_plugin_package` | 打包插件源码为可安装 zip |
| `tavo_plugin_install` | 安装插件 |
| `tavo_plugin_uninstall` | 卸载插件 |
| `tavo_plugin_set_enabled` | 启用/禁用插件 |
| `tavo_plugin_set_config` | 设置插件配置项 |
| `tavo_plugin_reset_config` | 重置插件配置为默认值 |
| `tavo_plugin_validate_manifest` | 验证插件清单 |
| `tavo_plugin_get_runtime_contributions` | 列出已启用插件的运行时贡献 |

---

## 安装与使用

### 前置条件

1. **Tavo 平台**已安装并运行
2. Tavo 中已开启 MCP Server（默认地址 `http://127.0.0.1:7347/mcp`）
3. 获取 MCP Server 的 Bearer Token（在 Tavo 设置中查看）

> ⚠️ **重要提醒**：Tavo 需要保持**前台运行**或**小窗模式**，否则系统可能会断开 MCP Server 连接。

### 在 Operit 中配置

#### 方式一：发送完整配置连接（推荐）

直接向 AI 助手发送 Tavo MCP 的连接信息，AI 将自动完成配置：

```
Tavo MCP Server: <版本号>
Server URL: http://127.0.0.1:7347/mcp
Authorization: Bearer <你的Token>
```

> ⚠️ **安全提示**：分享配置时请务必将 `<你的Token>` 替换为实际 Token，不要在公开场合泄露完整连接信息。

#### 方式二：手动配置

1. 在 Operit 中添加远程 MCP 配置
2. 填入以下信息：
   - **endpoint**：`http://127.0.0.1:7347/mcp`
   - **bearerToken**：你的 Tavo MCP Token
3. 启用该 MCP 插件

### 使用示例

通过 AI 助手自然语言即可调用，例如：

- 「搜索名为 Derek 的角色卡」
- 「导入这张 PNG 角色卡到 Tavo」
- 「汉化世界书 ID 36 的所有条目」
- 「获取当前聊天记录」
- 「向当前聊天发送一条消息」

---

## 许可证

MIT License

---

## 归属声明

- **MCP Server**：[Tavo](https://tavo.app) 版权所有
- **Operit 包封装**：[kikiba0152](https://github.com/kikiba0152)
