<div align="center">

<a href="https://github.com/EastDong314">
  <img src="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=600&size=26&pause=1200&color=58A6FF&center=true&vCenter=true&width=720&lines=Backend+%26+Full-stack+Engineer;Building+tooling+that+makes+AI+agents+reliable;Agent+skills+%C2%B7+workflow+protocol+%C2%B7+data+pipelines;Java+%C2%B7+Spring+%C2%B7+TypeScript+%C2%B7+Python" alt="EastDong" />
</a>

**我把「让 AI agent 可靠干活」需要的那层工程基础设施做出来。**

跨 agent 的 skill 分发、可复盘的协作流程、能长期跑的数据管道。

<p>
  <a href="https://github.com/EastDong314/agent-skills"><img src="https://img.shields.io/badge/agent--skills-9_skills_%C2%B7_6_agents-2F81F7?style=for-the-badge&logo=python&logoColor=white" /></a>
  <a href="https://github.com/EastDong314/AI-Project-Workflow-Template"><img src="https://img.shields.io/badge/workflow-5_skills_%C2%B7_4_state_files-8957E5?style=for-the-badge&logo=markdown&logoColor=white" /></a>
  <a href="https://github.com/EastDong314/SourceMesh"><img src="https://img.shields.io/badge/SourceMesh-TypeScript_%C2%B7_Playwright-3178C6?style=for-the-badge&logo=typescript&logoColor=white" /></a>
</p>

<sub>📍 China · 后端与全栈为主，AI 工程化为重点 · 生产代码在私有仓库，公开仓库是可复用的工具与流程</sub>

</div>

---

## Featured Work / 精选项目

<table>
<tr>
<td width="50%" valign="top">

### 🧩 [agent-skills](https://github.com/EastDong314/agent-skills)

**一套 skill，装进所有 agent。** 把散落在各台机器上的个人 agent skill 收拢成一个仓库：`git clone` + `./install.sh`，DSH / Codex / pi / Claude Code / OpenCode 立刻拿到同一套能力。

- 覆盖 **6 类 agent 目标**，默认写入跨 agent 共享池 `~/.agents/skills`
- 覆盖前自动备份到带时间戳目录，`--dry-run` / 软链模式 / 按名装单个 skill
- 自带 `check-skills.py`：校验 frontmatter、`name` 与目录一致性、硬编码路径、引用文件是否存在、Python 可编译

`Python` · `Bash`

</td>
<td width="50%" valign="top">

### 🔁 [AI-Project-Workflow-Template](https://github.com/EastDong314/AI-Project-Workflow-Template)

**把「两个模型怎么协作」写进文件，而不是留在聊天记录里。** Codex 负责对齐、规划、验收、评审；pi 负责实现、验证、修 bug。

- **5 个 skill** 串成闭环：`grill-with-docs` → `plan-acceptance` → `implement` → `review-md`，出问题先走 `diagnose`
- 项目状态沉淀为 `.ai-workflow/{GOAL,PLAN,ACCEPTANCE,REVIEW}.md`，可交接、可回溯
- 含可直接复制的仓库模板与 public-safe 的 pi 配置，新项目一条 PowerShell 命令初始化

`PowerShell` · `Markdown`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🕸️ [SourceMesh](https://github.com/EastDong314/SourceMesh)

**给下游系统供数的采集中枢。** 基于 Playwright 的多源采集服务，为 TradingP / SignalReactor 提供可复用的行情与市场情报。

- 9 个模块 / ~670 行 TypeScript，CLI 一行命令按源采集或全量采集
- cron 调度 + 多源配置化（selector / 字段映射），加一个源只改 `config.ts`
- 三档存储：PostgreSQL（Prisma）/ Redis / 内存，按部署环境切换

`TypeScript` · `Playwright` · `Prisma` · `PostgreSQL` · `Redis`

</td>
<td width="50%" valign="top">

### 📟 [esp32-s3-desk-terminal](https://github.com/EastDong314/esp32-s3-desk-terminal)

**一块常亮的桌面终端，不是缩水版手机 App。** LCKFB SZPI ESP32-S3（16MB Flash / 8MB PSRAM / 2.0" ST7789 + FT6336 触摸 / ES7210 + ES8311 音频）：盯合约行情、背单词卡、AI 翻译、随手录音。

- **951 行规格文档**：产品/设计/后端/硬件/极客多角色分析 + 板级验证笔记 + roadmap
- 明确的工程边界：固件不存交易所私钥、不存 AI API key，行情只读展示
- 本地优先：断网时卡片复习与录音照常可用

`ESP-IDF` · `C` · `硬件`

</td>
</tr>
</table>

---

## Architecture / 这套东西怎么串起来

```mermaid
flowchart TD
    A["grill-with-docs · 对齐范围与术语"] --> B["plan-acceptance · GOAL / PLAN / ACCEPTANCE"]
    B --> C["implement · 按计划执行"]
    C --> D["review-md · 评审 diff 产出 REVIEW"]
    D -->|changes requested| C
    D -->|passed| E["merge"]
    F["diagnose · 证据优先定位"] -.-> C
```

> 规划与实现由不同模型承担，中间用文件交接。状态在仓库里，不在聊天记录里——换个会话、换个人接手都能继续。

---

## At a Glance / 一目了然

<div align="center">

<img src="https://img.shields.io/badge/Public_repos-6-2F81F7?style=flat-square" />
<img src="https://img.shields.io/badge/Agent_skills-9-8957E5?style=flat-square" />
<img src="https://img.shields.io/badge/Agent_targets-6-3FB950?style=flat-square" />
<img src="https://img.shields.io/badge/Workflow_skills-5-D29922?style=flat-square" />
<img src="https://img.shields.io/badge/TypeScript_LOC-668-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Spec_lines-951-BC8CFF?style=flat-square" />

</div>

---

## Tech Stack / 技术栈

<div align="center">

**Languages**

<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/C%23%20%2F%20.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white" />
<img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white" />
<img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white" />

**Backend & Data**

<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white" />

**Infra & Delivery**

<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" />
<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" />

**AI & Agents**

<img src="https://img.shields.io/badge/MCP-000000?style=flat-square&logo=anthropic&logoColor=white" />
<img src="https://img.shields.io/badge/Codex-412991?style=flat-square&logo=openai&logoColor=white" />
<img src="https://img.shields.io/badge/Claude%20Code-D97757?style=flat-square&logo=anthropic&logoColor=white" />
<img src="https://img.shields.io/badge/RAG%20%2F%20Vector%20DB-1F6FEB?style=flat-square&logo=databricks&logoColor=white" />

</div>

---

## How I Work / 工作方式

- **Design for failure** — 幂等、重试策略、优雅降级，先假设会挂
- **Measure before optimize** — 先 profile 再调优，不猜
- **Automate the boring part** — 把重复动作固化成脚本、模板、skill
- **Write it down** — 决策与权衡落成文档，下次不用重新想

> 私有仓库里是业务系统（高并发订单、内部运营平台、AI 辅助知识流）；公开仓库里是这些系统磨出来的**方法**与**工具**。

---

## Now / 近况

- 🔭 在把 agent skill 生态做成**跨工具可移植**的一层：一处维护，处处可用
- 🧪 在用「文件即状态」的方式约束多模型协作，减少规划与实现之间的漂移
- 📟 补 ESP32-S3 固件：先把板级 bring-up 和离线优先的 UI 跑通
- ✍️ 持续把私有项目里可复用的部分脱敏后开源

---

<div align="center">

<a href="mailto:cryeshiren@gmail.com"><img src="https://img.shields.io/badge/Email-cryeshiren@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white" /></a>
<a href="https://github.com/EastDong314"><img src="https://img.shields.io/badge/GitHub-@EastDong314-181717?style=flat-square&logo=github&logoColor=white" /></a>

<br /><br />

<sub><i>"Ship robust systems. Keep learning in public."</i></sub>

<br />

<img src="https://komarev.com/ghpvc/?username=EastDong314&label=Profile%20views&color=58A6FF&style=flat-square" alt="profile views" />

</div>



---

<!-- TEMP-MERMAID-PROBE2 -->
## probe2


**P1_solid_arrow**

```mermaid
flowchart TD
    A["grill-with-docs · 对齐范围与术语"] --> B["plan-acceptance · GOAL / PLAN / ACCEPTANCE"]
    B --> C["implement · 按计划执行"]
    C --> D["review-md · 评审 diff 产出 REVIEW"]
    D -->|changes requested| C
    D -->|passed| E["merge"]
    F["diagnose · 证据优先定位"] --> C
```


**P2_dotted_unquoted**

```mermaid
flowchart TD
    F --> C
    C --> D
    F -.-> D
```


**P3_dotted_only**

```mermaid
flowchart TD
    A["a"] -.-> B["b"]
```
