# Daily Forge 内容发布规范（强制执行）

> 任何后续 update_dayXXX.py / fill_missing_days.py / 其他自动化脚本，必须严格遵守本文档规范。

## 1. 三大板块定义（不可混淆）

| 标签 | section | 内容方向 | ❌ 禁止 |
|------|---------|----------|--------|
| `tag-t` 思维模型 | 02 | 经典认知/心理/系统/经济等思维模型 | 副业、商业模式、SaaS、变现 |
| `tag-d` 设计启发 | 03 | UI/UX 设计原则、案例、规范 | 副业、SaaS 工具构想 |
| **`tag-m` AI前沿** | 03 | **真实 AI 工具 / 真实设计资讯 / 行业趋势** | **❌ 副业、SaaS 工具构想、变现路径、个人创业** |

**永远不要再使用以下标签和内容**（用户明确要求）：
- ❌ `tag-a 副业思路`
- ❌ `tag-m AI/副业` 
- ❌ `tag-m 副业思路`
- ❌ "副业思路" / "副业启示" / "AI/副业" 等任何文字
- ❌ section-eyebrow-title 写"AI前沿 / 副业思路"

## 2. 标签强制规则

```html
<!-- ✅ 正确 -->
<span class="tag tag-m">AI前沿</span>

<!-- ❌ 禁止 -->
<span class="tag tag-a">副业思路</span>
<span class="tag tag-m">AI/副业</span>
<span class="tag tag-m">副业思路</span>
```

```html
<!-- ✅ section eyebrow 正确写法 -->
<span class="section-eyebrow-title">AI / 设计资讯</span>

<!-- ❌ 禁止 -->
<span class="section-eyebrow-title">AI前沿 / 副业思路</span>
```

## 3. AI 前沿卡片内容方向（按主题选）

发布新卡时，必须从以下方向选 1 个：

### A) AI 工具 & 模型（最优先）
- 旗舰 AI：GPT-4o/Claude 3.5/Gemini 2.0/Llama 3.3/Mistral
- AI 编程：Cursor/Windsurf/GitHub Copilot/Devin/Aider
- AI 设计：V0/Galileo/Krea/Locofy/Builder.io
- AI 写作：Notion AI/Claude Artifacts/ChatGPT Canvas/Jasper
- AI 多模态：Sora/Veo 2/可灵/Suno/ElevenLabs/Runway
- AI Agent：Computer Use/AutoGPT/LangChain/n8n

### B) 设计趋势 & 工具
- 设计系统：Material 3/Apple HIG/IBM Carbon/Adobe Spectrum
- 设计工具：Figma 新功能/Token Studio/Storybook/Code Connect
- UX 趋势：极简化/Linear Method/Stripe Dashboard 美学
- 游戏 UI：UE5 UMG/Unity UI Toolkit/Godot 4

### C) AI 行业应用
- 医疗：Apple Watch/MedGemini/Eko AI
- 法律：Harvey AI/CoCounsel/Lexis+
- 金融：BloombergGPT/Stripe Radar/IndexGPT
- 教育：Khanmigo/Brilliant/Duolingo Max
- 客服：Klarna AI/Intercom Fin/Salesforce Service AI

## 4. 卡片质量标准（每张必备）

```html
<div class="card" data-fav-id="dXX-ai-tool-name" data-fav-title="工具名">
<div class="card-head"><h3><i data-lucide="bot" class="ic-inline"></i><span>新闻标题：xxx 工具/趋势</span></h3><span class="tag tag-m">AI前沿</span></div>
<p>1-2 句概述 + <strong>关键数据/估值</strong>。</p>
<ul>
  <li><strong>真实公司/产品名：</strong>具体描述（带数据：估值/用户数/营收）</li>
  <li><strong>真实公司/产品名：</strong>具体描述</li>
  <li><strong>真实公司/产品名：</strong>具体描述</li>
</ul>
<div class="card-actions">...保留原有按钮结构...</div>
<div class="card-deep" data-deep-id="dXX-ai-tool-name"><div class="card-deep-inner-wrap"></div></div>
</div>
```

## 5. DEEP_CONTENT 规范

每张 AI 前沿卡的深度阅读必须包含：
1. **历史溯源**：年份+原始论文/书籍+真实引文
2. **3 个真实案例**：带数据（营收、估值、用户数、转化率）
3. **4 个应用维度**：真实工具/平台/技术
4. **3 项可执行**：本周可以试用/学习/订阅的具体工具

**禁止**：
- ❌ 创业建议（如"月流水预估 ¥30K"）
- ❌ 定价模型（如"个人 ¥99/月"）
- ❌ "如何变现" / "副业起步" 等话术

## 6. 标准卡片模板（直接复制使用）

详见 `c:/tmp/build_new_AI_cards.py` 中的 `card()` 函数。

## 7. 自动化脚本检查清单（写脚本时必查）

- [ ] section-eyebrow-title 是 `AI / 设计资讯` 而非 `AI前沿 / 副业思路`
- [ ] 所有 tag 都是 `tag-m AI前沿`，无 `tag-a 副业思路`
- [ ] 没有"副业"二字（grep 验证）
- [ ] 卡片标题是真实 AI 工具/设计资讯，不是 SaaS 工具构想
- [ ] 要点列表带真实数据/估值（不是变现路径）
- [ ] DEEP_CONTENT 含 3 真实案例 + 4 应用维度 + 3 可执行
- [ ] div 平衡（用 `node` 验证）
- [ ] JS 0 syntax error（用 `new Function()` 验证）

## 历史变更
- 2026-05-22：用户明确要求 AI 前沿板块禁止副业内容。45 张副业卡全部改写为 AI/设计资讯，74 处"副业"字样清零。
