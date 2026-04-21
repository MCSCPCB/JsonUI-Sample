# chatTrigger 模板

这是一个纯 JSON UI 的聊天触发示例。

当前行为：

- 在聊天里发送严格等于 `开始` 的文本时，HUD 中央图片显示。
- 在聊天里发送严格等于 `结束` 的文本时，HUD 中央图片隐藏。
- 触发判断用的是 `#message_text_box_content = '开始' / '结束'`，不是包含判断。
- 模板尝试在 `chat_screen` 根级拦截 `button.send`，让 `开始` 和 `结束` 不再按普通聊天发送。

目录说明：

- `RP/manifest.json`
  资源包 manifest。
- `RP/ui/_global_variables.json`
  模板总开关变量。以后改触发词时，优先改这里。
- `RP/ui/chat_screen.json`
  拦截发送动作，把 `开始/结束` 分发到自定义按钮事件。
- `RP/ui/hud_screen.json`
  在 HUD 放一个隐藏 toggle，接收显示/隐藏按钮事件，并控制图片显隐。
- `RP/textures/ui/chat_trigger_placeholder.png`
  占位图片，你可以直接替换成自己的贴图。

使用建议：

- 先把 `RP` 整包放进资源包目录测试。
- 如果你要改触发词，只改 `RP/ui/_global_variables.json`：
  `$flag_for_chat_trigger_show`
  `$flag_for_chat_trigger_hide`
- 如果你要改图片路径，也改 `RP/ui/_global_variables.json` 里的 `$chat_trigger_texture`。
