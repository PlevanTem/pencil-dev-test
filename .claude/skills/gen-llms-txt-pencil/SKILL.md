---
skill_name: "gen-llms-txt-pencil"
description: "Generate standardized llms.txt documentation for Pencil design systems (.pen files) to enable LLMs to understand visual structures, Auto Layout rules, and Design-as-Code patterns."
version: "1.0.0"
last_updated: "2026-02-06"
tags:
  - pencil-dev
  - pen-files
  - design-as-code
  - documentation
  - llms-txt
author: "Antigravity"
---

# SKILL: Technical Documentation for Pencil Design Systems (llms.txt)

You are an AI writing assistant specialized in documenting Pencil-based design systems. Your role is to generate standardized `llms.txt` and `llms-full.txt` files that help LLMs understand the visual hierarchy, property mappings, and architectural patterns of Pencil `.pen` files.

---

## Objective | 目标

Generate standardized `llms.txt` documentation that bridges the gap between Pencil's visual designs and development-ready specifications. This allows AI agents to accurately "read" design intentions from `.pen` files and generate compliant code or design modifications.

通过标准化的 `llms.txt` 文档，将 Pencil 的视觉设计与开发规范连接起来。这使得 AI 代理能够准确地从 `.pen` 文件中“读取”设计意图，并生成合规的代码或设计修改。

> [!IMPORTANT]
> **Pencil Core | Pencil 核心**: Documentation must reflect Pencil's "Design-as-Code" philosophy, where `.pen` JSON files are the primary source of truth.
> 
> 文档必须体现 Pencil 的“设计即代码”理念，其中 `.pen` JSON 文件是主要的实项源。

---

## File Types | 文件类型

| File Type | Purpose | Content Scope |
|-----------|---------|---------------|
| `llms.txt` | Quick Map<br/>快速地图 | Directory of `.pen` components, their locations, and intent.<br/>`.pen` 组件目录、其位置和设计意图。 |
| `llms-full.txt` | Detailed Specs<br/>详细规范 | Node hierarchies, specific property mappings (fill, stroke, gap), and Auto Layout rules.<br/>节点层级、具体属性映射（填充、描边、间距）以及自动布局规则。 |

---

## Pencil Writing Principles | Pencil 写作原则

### Layout & Property Precision | 布局与属性精度
- **Coordinate System**: Explain the coordinate system (x, y) if relevant to layout logic.
- **Auto Layout**: Detail the mapping of `gap`, `padding`, `justifyContent`, and `alignItems` to the target framework (e.g., Flexbox).
- **Property Accuracy**: Document exact hex values (`fill`) and corner radii (`cornerRadius`) found in the `.pen` JSON.

### Component Translation | 组件转换
- **Variants**: Document how variants are named (e.g., using "Key=Value" format in frame names).
- **Reusable Frames**: Identify which frames are intended as reusable components (`"reusable": true`).

---

## Required Structure for Pencil Docs | Pencil 文档结构要求

### llms-full.txt Schema Template | 模板

```text
============================================================
llms-full.txt - [Project Name] Pencil Design System
============================================================

# 1. METADATA | 元数据
PROJECT_NAME: [Project Name]
SOURCE_FORMAT: Pencil .pen (version 2.x)
SYNC_TARGET: [e.g., React/Tailwind, Vue, etc.]
LAYOUT_ENGINE: Pencil Auto Layout (Flex-compatible)

# 2. GLOBAL DESIGN TOKENS (Extracted from .pen) | 全局设计令牌
## 2.1 Colors | 颜色
- primary: #hex (re-mapped from [Component Name] fill)
## 2.2 Typography | 排版
- font-family: [Name]
- sizes: [H1=..., Body=...]

# 3. COMPONENT SPECIFICATIONS | 组件规范
# Format: Component | .pen File | Node Hierarchy | Logic

---
COMPONENT: [Name]
PEN_PATH: [Path to .pen file]
NODE_NAME: [Target Frame Name]
PROPERTIES: {
  "layout": "flex",
  "padding": "[values]",
  "gap": "[value]"
}
VARIANT_MAPPING: {
  "state=hover": "Node ID: [ID] with fill [Hex]"
}
---

# 4. TRANSFORMATION RULES | 转换规则
1. Use Flexbox for all frames with `layout: "flex"`.
2. Map `cornerRadius` to CSS `border-radius`.
3. Handle absolute positioning for nodes with `enabled: false` as hidden or conditional.

# 5. FORBIDDEN PATTERNS | 禁用模式
- No hardcoded absolute x/y if Auto Layout is active.
- No direct manipulation of Node IDs; use semantic names.

```

---

## Implementation Workflow | 实施工作流程

1. **Analyze .pen Structure**: Use tools to parse the component tree (frames, text, paths).
2. **Identify Patterns**: Detect recurring spacing, sizing, and color tokens.
3. **Map to Requirements**: Correlate `.pen` nodes to UI components and their states.
4. **Generate Guide**: Write the `llms.txt` specifically for Pencil-aware agents.

---

**End of SKILL (Pencil Edition)**
