# aisee-icons

Aisee 设计系统图标库 — React SVG 组件

---

## 安装

在前端项目的 `package.json` 中添加：

```json
"dependencies": {
  "aisee-icons": "github:ccbaka/aisee-icons#main"
}
```

然后运行：

```bash
npm install
```

---

## 更新图标

每次设计师更新图标后，前端运行：

```bash
npm update aisee-icons
```

---

## 使用方式

```jsx
import { LineMenuFilter, FillArrowLoop, LinePeopleGoal } from 'aisee-icons'

// 基本用法
<LineMenuFilter />

// 自定义大小和颜色
<LineMenuFilter size={20} color="#CFFF29" />

// 使用当前文字颜色（推荐，跟随主题）
<FillArrowLoop size={16} color="currentColor" />

// 加 className 控制样式
<LinePeopleGoal className="my-icon" />
```

---

## 命名规则

SVG 文件名 → React 组件名（自动转换）

| SVG 文件名 | 组件名 |
|-----------|--------|
| `line_menu_filter.svg` | `LineMenuFilter` |
| `fill_arrow_loop.svg` | `FillArrowLoop` |
| `line_people_goal.svg` | `LinePeopleGoal` |

规则：下划线分隔 → 每个单词首字母大写

---

## 查看所有可用图标

```jsx
import { ICON_NAMES } from 'aisee-icons'

console.log(ICON_NAMES) // ['line_menu_filter', 'fill_arrow_loop', ...]
```

---

## 设计师更新流程

1. 从 Figma 导出 SVG 文件
2. 把 SVG 文件放入 `src/icons/` 目录
3. `git add . && git commit -m "add: new icons" && git push`
4. GitHub Actions 自动构建（约 1 分钟）
5. 通知前端运行 `npm update aisee-icons` 即可

---

## 目录结构

```
aisee-icons/
├── src/
│   ├── icons/          ← ⭐ 设计师只需操作这个目录
│   │   ├── line_menu_filter.svg
│   │   └── ...
│   ├── components/     ← 自动生成，勿手动修改
│   └── index.ts        ← 自动生成，勿手动修改
├── dist/               ← 自动生成，勿手动修改
├── scripts/
│   └── build-icons.js
└── .github/
    └── workflows/
        └── build.yml
```
