# Pencil 设计新范式 D2C2D 能力测试

## 项目简介

本项目旨在测试和验证基于 Pencil 设计工具的新范式 D2C2D（Design to Code to Design）能力，探索设计与代码之间的双向转换流程。

## 项目目标

- **D2D (Design to Design)**: 测试在 Pencil 中基于组件库进行设计的能力
- **D2C (Design to Code)**: 测试从 Pencil 设计文件生成可用代码（HTML、React 等）的能力
- **组件复用**: 验证基于 ArcoDesign 组件库的设计规范应用

## 项目结构

```
pencil-dev test/
├── .claude/skills/      # Claude 自动化助手技能
│   ├── gen-llms-txt/    # 标准化 UI 规范生成技能
│   └── gen-llms-txt-pencil/ # Pencil 专用 D2C2D 规范生成技能
├── arcoui/              # ArcoDesign pencil 组件库
│   ├── components/      # .pen 格式组件源码
│   ├── llms.txt         # 组件库快速索引 (LLM 友好)
│   └── llms-full.txt    # 完整组件规范与设计令牌 (LLM 友好)
├── test/                # 实验记录和测试文件
│   └── exp log.md       # 详细实验日志
├── exp4.pen             # Pencil 设计文件
├── exp5.pen             # Pencil 设计文件
├── exp6.pen             # Pencil 设计文件
└── README.md            # 项目说明文档
```

## AI 辅助能力 (Claude Skills)

本项目集成了专门为 AI 辅助开发设计的技能，可通过 Claude 助手调用：

### 1. gen-llms-txt
用于生成标准化的 `llms.txt` 规范文档，帮助 AI 工具理解任何 UI 组件库、API 和使用模式。遵循行业领先的技术协作实践。

### 2. gen-llms-txt-pencil
**Pencil 专版**。深入理解 Pencil 的 `.pen` 文件结构、自动布局（Auto Layout）引擎和属性映射。专门用于架起 Pencil 视觉设计与开发代码之间的桥梁。

## LLM 友好文档 (llms.txt)

在 `arcoui/` 目录下，我们提供了遵循 `llms.txt` 规范的文档：
- **`llms.txt`**: 适合 AI 快速扫描的组件目录。
- **`llms-full.txt`**: 包含详细的元数据、AI 生成强制约束（禁止硬编码）、全局设计令牌和核心组件 API 示例。

## 实验内容

### Experiment 1: 基于设计组件生成

使用 [Arco Design](https://arco.design/) 设计规范进行测试：

#### 1.1 D2C(HTML) 生成
- 直接通过 AI 大模型生成 HTML 代码
- 场景：云服务监控看板控制台页面

#### 1.2 D2D(Pencil) 生成（含组件库 & 样式规范）
- 在 Pencil 中使用 ArcoUI 组件库
- 参考样式规范进行设计

#### 1.3 D2D(Pencil) 生成（无组件库 & 样式规范）
- 不依赖组件库的纯 Pencil 设计
- 对比组件库的影响

#### 1.4 D2D(Pencil) 完整流程
- 完整的组件引用和样式规范测试
- 验证设计一致性

#### 1.5 D2D(Pencil) B端应用场景
- 测试场景：B端云服务控制台概览页
- 模仿字节跳动火山引擎设计语言
- 验证复杂布局的生成能力

#### 1.6 D2C(React) 生成
- 从设计生成 React 组件代码
- 测试现代前端框架集成

### Experiment 2: (待补充)

更多实验内容正在进行中...

## 技术栈

- **设计工具**: Pencil
- **组件库**: [Arco Design](https://arco.design/)
- **目标代码**: HTML, React
- **AI 辅助**: 大语言模型辅助设计和代码生成
- **规范标准**: [llms.txt](https://llms.txt.org/)

## 使用方法

1. 打开 `.pen` 文件查看设计稿
2. 查看 `test/exp log.md` 了解详细实验过程和结果
3. 参考 `arcoui/` 目录中的 `llms.txt` 文档，辅助 AI 进行代码生成
4. 使用 `@[gen-llms-txt-pencil]` 技能为您的 Pencil 设计生成最新规范

## 关键发现

详细的实验记录、提示词、生成结果和对比分析请参考 `test/exp log.md` 文件。

## 参考资料

- [Arco Design 官方文档](https://arco.design/)
- Pencil 组件化快捷键：`Ctrl + Alt + K`
- [llms.txt 规范建议](https://llms.txt.org/)

## 项目状态

🚧 进行中 - 持续更新实验结果

---

**最后更新**: 2026-02-06
