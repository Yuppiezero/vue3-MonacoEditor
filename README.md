# Vue3 + Monaco Editor 汉化版

这是一个完整的 Vue3 项目，集成了完全汉化的 Monaco Editor（VS Code 的编辑器核心）。所有的右键菜单、命令面板、提示信息等都已经被汉化为中文。

## 功能特性

### 🎯 完全汉化

- ✅ 右键菜单全部中文

- ✅ 命令面板 (Ctrl/Cmd + Shift + P) 中文显示

- ✅ 状态栏提示中文

- ✅ 查找替换界面中文

- ✅ 代码提示和错误提示中文

- ✅ 所有编辑器命令中文

### 🔧 编辑器功能

- 支持 JavaScript、HTML、CSS、TypeScript 等多种语言

- 代码高亮显示

- 智能代码提示

- 括号自动补全

- 代码格式化

- 查找替换 (Ctrl/Cmd + F)

- 转到定义 (F12)

- 重命名符号

- 代码折叠

- 多光标编辑

- 命令面板

### 🎨 界面特性

- 深色主题 (vs-dark)

- 迷你地图

- 行号显示

- 自动换行

- 括号匹配高亮

- 代码缩略图

## 快速开始

### 安装依赖

```bash
npm install
```

### 运行开发服务器

```bash
npm run dev
```

### 构建生产版本

```bash
npm run build
```

## 使用方法

### 基本使用

```vue
<template>
  <MonacoEditor 
    v-model="code"
    language="javascript"
    height="400px"
    theme="vs-dark"
    @save="handleSave"
  />
</template>

<script setup>
import MonacoEditor from './components/MonacoEditor.vue'
import { ref } from 'vue'

const code = ref('// 你的代码')

function handleSave(value) {
  console.log('保存的代码:', value)
}
</script>
```

### Props 属性

|属性名|类型|默认值|说明|
|-|-|-|-|
|`value`|String|`''`|编辑器内容|
|`language`|String|`'javascript'`|语言类型 (javascript, html, css, typescript, json 等)|
|`theme`|String|`'vs-dark'`|主题 (vs, vs-dark, hc-black)|
|`height`|String|`'400px'`|编辑器高度|
|`readonly`|Boolean|`false`|是否只读|

### Events 事件

|事件名|参数|说明|
|-|-|-|
|`change`|`value: String`|内容改变时触发|
|`save`|`value: String`|保存时触发 (Ctrl/Cmd + S)|

### 暴露的方法

通过 `ref` 可以调用以下方法：

```vue
<template>
  <MonacoEditor ref="editorRef" />
  <button @click="formatCode">格式化代码</button>
</template>

<script setup>
import { ref } from 'vue'

const editorRef = ref()

function formatCode() {
  editorRef.value.formatDocument()
}
</script>
```

|方法名|说明|
|-|-|
|`formatDocument()`|格式化整个文档|
|`focus()`|聚焦到编辑器|
|`getValue()`|获取编辑器内容|
|`setValue(value)`|设置编辑器内容|

## 快捷键

### 常用快捷键

|Windows/Linux|macOS|功能|
|-|-|-|
|`Ctrl + S`|`Cmd + S`|保存|
|`Ctrl + Z`|`Cmd + Z`|撤销|
|`Ctrl + Y`|`Cmd + Shift + Z`|重做|
|`Ctrl + X`|`Cmd + X`|剪切|
|`Ctrl + C`|`Cmd + C`|复制|
|`Ctrl + V`|`Cmd + V`|粘贴|
|`Ctrl + A`|`Cmd + A`|全选|
|`Ctrl + F`|`Cmd + F`|查找|
|`Ctrl + H`|`Cmd + Option + F`|查找替换|
|`F12`|`F12`|转到定义|
|`Shift + F12`|`Shift + F12`|查找所有引用|
|`Ctrl + Space`|`Cmd + Space`|触发建议|
|`Ctrl + Shift + P`|`Cmd + Shift + P`|命令面板|

### 多光标编辑

|Windows/Linux|macOS|功能|
|-|-|-|
|`Alt + Click`|`Option + Click`|在点击位置添加光标|
|`Ctrl + Alt + ↑`|`Cmd + Option + ↑`|在上方插入光标|
|`Ctrl + Alt + ↓`|`Cmd + Option + ↓`|在下方插入光标|
|`Ctrl + D`|`Cmd + D`|选择下一个匹配项|

### 代码折叠

|Windows/Linux|macOS|功能|
|-|-|-|
|`Ctrl + Shift + [`|`Cmd + Option + [`|折叠|
|`Ctrl + Shift + ]`|`Cmd + Option + ]`|展开|
|`Ctrl + K Ctrl + 0`|`Cmd + K Cmd + 0`|全部折叠|
|`Ctrl + K Ctrl + J`|`Cmd + K Cmd + J`|全部展开|

## 右键菜单功能

右键菜单包含以下中文选项：

- 📝 **剪切** - 剪切选中的文本

- 📋 **复制** - 复制选中的文本

- 📌 **粘贴** - 粘贴剪贴板内容

- 🔍 **查找** - 打开查找框

- 🔁 **替换** - 打开替换框

- 🎨 **格式化文档** - 格式化整个文件

- 🎯 **格式化选定内容** - 格式化选中的代码

- ➡️ **转到定义** - 跳转到变量/函数定义

- 👁️ **预览定义** - 在弹出窗口中预览定义

- 🔗 **查找所有引用** - 查找所有使用该符号的地方

- ✏️ **重命名** - 重命名符号

- 🔧 **快速修复** - 显示快速修复建议

- 🔄 **重构** - 重构代码

- 📦 **源代码操作** - 源代码相关操作

- 📥 **组织导入** - 整理 import 语句

- 🔤 **排序导入** - 按字母排序 import

- 🗑️ **删除未使用的导入** - 清理未使用的 import

- 🎛️ **命令面板** - 打开命令面板

## 命令面板

使用 `Ctrl/Cmd + Shift + P` 打开命令面板，包含所有可用的编辑器命令，全部显示为中文：

- 📄 格式化文档

- 🎯 格式化选定内容

- 🔍 查找

- 🔁 替换

- 📍 转到行/列

- 🔖 转到符号

- ➡️ 转到定义

- 👁️ 预览定义

- 🔗 查找所有引用

- ✏️ 重命名

- 🔧 快速修复

- 🔄 重构

- 📦 源代码操作

- 📥 组织导入

- 🔤 排序导入

- 🗑️ 删除未使用的导入

- 🗺️ 切换迷你地图

- 👁️ 切换空白字符渲染

- 📝 切换自动换行

- 📊 切换侧边栏

## 支持的语言

Monaco Editor 支持多种编程语言，包括：

- ✅ JavaScript / TypeScript

- ✅ HTML / XML

- ✅ CSS / SCSS / LESS

- ✅ JSON

- ✅ Markdown

- ✅ Python

- ✅ Java

- ✅ C / C++

- ✅ C#

- ✅ PHP

- ✅ Go

- ✅ Rust

- ✅ YAML

- ✅ SQL

- ✅ 更多...

## 自定义配置

你可以在 `MonacoEditor.vue` 组件中修改编辑器配置：

```javascript
// 修改字体
fontSize: 16,
fontFamily: 'Fira Code, Consolas, monospace',

// 启用/禁用功能
minimap: { enabled: false }, // 禁用迷你地图
wordWrap: 'off', // 禁用自动换行
lineNumbers: 'off', // 隐藏行号
scrollBeyondLastLine: true, // 允许滚动到最后一行之后
```

## 浏览器兼容性

- ✅ Chrome 60+

- ✅ Firefox 55+

- ✅ Safari 12+

- ✅ Edge 79+

## 项目结构

```
vue3-monaco-chinese/
├── public/
├── src/
│   ├── components/
│   │   └── MonacoEditor.vue  # 汉化的 Monaco Editor 组件
│   ├── App.vue               # 主应用组件
│   └── main.js              # 应用入口
├── package.json
├── vite.config.js
├── index.html
└── README.md
```

## 许可证

MIT License

## 贡献

欢迎提交 Issue 和 Pull Request！

---
<img src="https://raw.githubusercontent.com/Yuppiezero/vue3-MonacoEditor/refs/heads/main/db05b84e71ed50e8033bd68ef7649879.png" width="400">

**享受完全汉化的代码编辑体验！** 🎉
