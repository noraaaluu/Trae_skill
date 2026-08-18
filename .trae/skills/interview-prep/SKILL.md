---
name: "interview-prep"
description: "根据JD和简历生成完整的面试准备HTML方案。当用户提供JD+简历，或提到面试准备、面试攻略、面试方案时调用。"
---

# 面试准备方案生成器

根据用户提供的 **JD（岗位描述）** 和 **简历**，生成一份完整的、结构化的 **HTML 面试准备方案**。

## 输入要求

用户需提供：
1. **JD**：目标岗位的完整描述文本
2. **简历**：应聘者的完整简历文本

可选输入：
- 面试岗位方向（如：数据分析、产品经理、运营等）
- 面试公司/行业信息
- 应聘者的自我补充说明

## 输出格式

生成一个单文件 HTML：`interview-prep-guide.html`

## 准备方案结构（必须包含以下所有板块）

### 板块 1：自我介绍
- 控制在 **1.5-2分钟（约350字）**
- 结构：**我是谁 → 我有什么能力 → 为什么投这个岗**
- 标注重音关键词（面试官最关注的点）
- 明确列出「不要说的」内容
- 语速控制提醒

### 板块 2：JD 核心要求拆解
- 逐条拆解 JD 中的硬性要求 vs 软性要求
- 标注应聘者已满足 vs 需补位的项
- 给出每个"需补位"项的应对话术策略

### 板块 3：简历深挖映射
- 将简历经历映射到 JD 要求
- 每段经历提炼 **STAR 法则** 叙述框架
- 识别简历中的"亮点"和"潜在追问点"
- 给出每段经历的参考话术

### 板块 4：专业能力检验问答
根据岗位方向，生成以下类型的问题：

#### 通用必问
- Q3-1 指标定义：岗位核心指标的通俗解释 + 参考话术
- Q3-2 专业工具/方法论：常用工具在该岗位场景下的具体用法
- Q3-3 行业/品类认知：行业基本格局 + 目标公司定位
- Q3-4 职业规划：短期/长期规划，与岗位发展路径对齐

#### 岗位定制必问
- 数据分析岗：
  - 指标定义（CTR、CVR、ROI、ARPU 等）+ 通俗解释 + 判断口诀
  - 数据工具实战（Power BI/Excel/Python 在投放/分析场景下的具体用法，含 DAX 公式 / Power Query 步骤 / pandas 逻辑）
  - 从数据看出问题的典型场景（如 CTR 下降、CPI 飙升、漏斗断崖、地区差异、消耗高 ROI 低），每个场景含数据示例 + 问题定位 + 优化建议
- 产品岗：需求分析框架、竞品分析方法、数据决策案例
- 运营岗：活动策划思路、用户增长路径、内容运营方法论
- 技术岗：系统设计思路、技术选型考量、踩过的坑与解决方案

#### 加分题
- Q3-7 竞品认知：主要竞品及其差异化，目标公司的竞争优势
- Q3-8 创意/业务钩子：一个具体的创意/增长钩子，含有效性数据 + 平台特性建议

每个问题必须包含：
- **得分点**：回答中的关键要素
- **参考话术**：可直接使用的口语化回答
- **延伸追问预判**：面试官可能接着问的问题

### 板块 5：思维与经验
- 一个核心场景的**思维导图式拆解**（如指标排查、用户流失归因、投放优化路径）
- 用通俗类比说明复杂概念（如"做生意的常识"类比指标）
- 体现跨领域能力迁移（如翻译的质量审核 → 内容运营的质量把控 → 广告投放的素材优化）

### 板块 6：情景模拟
- 2-3 个岗位高频情景题
- 每个情景给出：答题框架 + 参考话术
- 情景类型：紧急事件处理 / 数据异常排查 / 策略制定

### 板块 7：反问环节
- 3-5 个高质量反问问题（不要问薪资、加班等基础问题）
- 反问方向：业务挑战、团队期待、成长路径、技术/业务趋势
- 标注"可以问"和"不要问"的问题

### 板块 8：面试备忘单（Cheat Sheet）
- **今晚必做**：最高优先级的记忆清单
- **关键词/数据速记**：需要精确记住的数字、指标名、竞品名
- **话术骨架**：核心回答的框架关键词
- **临场应急**：卡壳时的救场策略

## 生成规则

### 内容风格
1. **口语化**：所有参考话术必须是口语化表达，不是书面语
2. **具体可执行**：不说空话，每个建议都有具体的内容
3. **应聘者视角**：站在应聘者的角度，考虑他们的背景和短板
4. **差异化定位**：帮助应聘者找到与其他候选人的差异点
5. **通俗类比**：用生活化的例子解释专业概念

### 个性化适配
- 根据应聘者的背景（专业、经历、证书）定制差异化亮点
- 识别应聘者的"非典型背景"并转化为优势（如翻译专业 → 海外市场优势）
- 将 past experience 的技能迁移到 target role（如审核经验 → 质量把控 → 投放素材优化）
- 根据目标公司的业务特点调整内容

### HTML 样式（科技清新风格 Tech Fresh）

整体风格定位：**浅色背景 + 科技蓝主色 + 青色渐变 + 毛玻璃质感**，营造现代、干净、专业的视觉体验。

#### CSS 变量定义
```css
:root {
  /* 主色调 */
  --tech-blue: #2D7FF9;           /* 主标题、强调色 */
  --tech-blue-light: #4A90D9;      /* 次级标题、链接 */
  --cyan-start: #00C6FF;           /* 渐变起点 */
  --cyan-end: #0072FF;             /* 渐变终点 */

  /* 背景色 */
  --bg-primary: #F5F7FA;           /* 页面主背景 */
  --bg-card: rgba(255, 255, 255, 0.75);  /* 卡片背景（半透明，配合毛玻璃） */
  --bg-solid: #FFFFFF;             /* 实心背景（表格等） */

  /* 文字色 */
  --text-primary: #1A2332;         /* 正文主色 */
  --text-secondary: #5A6A7F;       /* 次要文字 */
  --text-muted: #8A99AB;           /* 辅助说明 */
  --text-accent: #2D7FF9;          /* 强调文字 */

  /* 边框与分割 */
  --border-light: rgba(45, 127, 249, 0.12);  /* 卡片边框 */
  --border-divider: rgba(0, 0, 0, 0.06);     /* 分割线 */

  /* 状态色 */
  --accent-green: #00BFA5;         /* 已匹配 */
  --accent-orange: #FF9800;        /* 需补位 */
  --accent-red: #FF5252;           /* 不要说/禁忌 */

  /* 阴影 */
  --shadow-card: 0 2px 12px rgba(45, 127, 249, 0.08);
  --shadow-hover: 0 4px 20px rgba(45, 127, 249, 0.15);
}
```

#### 视觉组件规范

**1. 页面背景**
- 主背景色 `#F5F7FA`，叠加 subtle 网格线（`linear-gradient` 重复背景，线条 `rgba(45,127,249,0.03)`）
- 顶部和底部各加一个微渐变光晕（`radial-gradient`，青蓝色，半径 600px，透明度 0.06-0.10）

**2. 卡片样式（核心容器）**
```css
.card {
  background: var(--bg-card);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid var(--border-light);
  border-radius: 16px;
  box-shadow: var(--shadow-card);
  padding: 28px 32px;
  margin-bottom: 20px;
  transition: box-shadow 0.3s ease;
}
.card:hover {
  box-shadow: var(--shadow-hover);
}
```

**3. 标题样式**
- H1（页面主标题）：渐变文字（`background: linear-gradient(135deg, #00C6FF, #0072FF); -webkit-background-clip: text`），字号 28px，加粗
- H2（板块标题）：科技蓝 `#2D7FF9`，字号 22px，左侧 4px 渐变竖线装饰（`border-left: 4px solid; border-image: linear-gradient(#00C6FF, #0072FF) 1`）
- H3/H4：`#4A90D9`，字号 16-18px

**4. 标签/徽章**
```css
.tag {
  display: inline-block;
  padding: 2px 12px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: 500;
}
.tag-ok {      /* 已匹配 */
  background: linear-gradient(135deg, #00BFA5, #00C6FF);
  color: #FFFFFF;
}
.tag-gap {     /* 需补位 */
  background: linear-gradient(135deg, #FF9800, #FFC107);
  color: #FFFFFF;
}
.tag-no {      /* 不要说 */
  background: linear-gradient(135deg, #FF5252, #FF9800);
  color: #FFFFFF;
}
```

**5. 引用框/话术框**
```css
.quote-box {
  background: rgba(0, 198, 255, 0.05);
  border-left: 3px solid var(--tech-blue);
  border-radius: 0 12px 12px 0;
  padding: 16px 20px;
  position: relative;
}
.quote-box::before {  /* 右上角引号装饰 */
  content: '"';
  position: absolute;
  top: 5px;
  right: 15px;
  font-size: 40px;
  color: rgba(45, 127, 249, 0.15);
}
```

**6. 步骤/流程指示器**
- 圆形数字徽章：`background: linear-gradient(135deg, #00C6FF, #0072FF); color: white; border-radius: 50%; width: 28px; height: 28px;`

**7. 折叠/展开交互**
- 默认折叠，点击展开（`<details>` + JS 增强）
- 展开时卡片底部渐显动画（`transition: max-height 0.4s ease`）
- 折叠按钮用科技蓝箭头图标

**8. 表格样式**
- 表头：`background: rgba(45, 127, 249, 0.06); color: var(--tech-blue)`
- 行分隔：`border-bottom: 1px solid var(--border-divider)`
- 圆角表格容器，溢出隐藏

**9. 备忘单特殊样式**
- 背景用更深的卡片色 `rgba(255,255,255,0.95)`，突出重要性
- 关键词用高亮标记：`background: linear-gradient(180deg, transparent 60%, rgba(0,198,255,0.25) 60%)`
- 打印样式：`@media print { body: white bg, cards: white bg no shadow, expand all }`

#### 响应式规范
- 桌面端：卡片最大宽度 860px，居中
- 平板：卡片宽度 100%，padding 缩减至 20px 24px
- 移动端（<600px）：标题字号缩减（H1→22px, H2→18px），卡片 padding 16px，标签换行
- 移动端背景光晕隐藏，减少视觉干扰

#### 字体规范
- `font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif`
- 行高：正文 1.8，标题 1.4
- 字号：正文 15px，标题 18-28px，辅助说明 13px

### 质量检查
生成后必须检查：
1. 所有板块是否完整
2. 参考话术是否口语化
3. 应聘者的亮点是否都被挖掘
4. JD 和简历的映射是否准确
5. 备忘单是否精炼

## 使用示例

**用户输入**：
```
JD: 数据分析岗，负责广告投放数据监控与优化...
简历: XX大学翻译硕士，有Power BI、Excel、Python数据分析经验...
```

**输出**：生成 `interview-prep-guide.html`，包含完整的 8 个板块，每个板块针对该用户的背景和岗位定制内容。