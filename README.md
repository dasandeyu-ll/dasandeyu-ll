<div align="center">

<!-- 打字机标题 -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&duration=3200&center=true&vCenter=true&width=680&lines=AI+Agent+Engineer+%E2%80%94+LangGraph+%2F+RAG+%2F+Multi-label+Intent,Building+production-ready+AI+agents+with+LangGraph+%26+Pydantic,Explicitly+engineering+the+uncertainty+in+LLM+systems" alt="typing" />

<p align="center">
  <b>AI Agent 工程师</b> · <b>LangGraph 状态机</b> · <b>结构化输出</b> · <b>全栈 RAG</b> · <b>分层评测</b>
</p>

<br/>

<!-- 顶部导航 -->
<a href="#about">关于</a> · <a href="#projects">项目</a> · <a href="#stack">技术栈</a> · <a href="#stats">数据</a> · <a href="#workflow">工作流</a>

<br/><br/>

<!-- 贪吃蛇动画（由 dasandeyu-ll/snake 仓库的 Actions 每日生成） -->
<p align="center">
  <img src="https://dasandeyu-ll.github.io/snake/snake.svg" alt="snake" width="100%"/>
</p>

<br/>

<!-- 社交徽章 -->
<a href="https://github.com/dasandeyu-ll"><img src="https://img.shields.io/badge/GitHub-dasandeyu--ll-181717?style=flat-square&logo=github" alt="GitHub"/></a>
<img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
<img src="https://img.shields.io/badge/LangGraph-LangChain-1c3c3c?style=flat-square" alt="LangGraph"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
<img src="https://img.shields.io/badge/Open%20Source-Lover-ff69b4?style=flat-square" alt="Love"/>

</div>

---

## 关于 <a name="about"></a>

<div align="center">
  <table>
    <tr>
      <td width="62%">
        <h3>把「不确定」显式化的 AI Agent 工程师</h3>
        <p align="left">
          专注 <b>LLM Agent 应用工程</b>：<b>LangGraph 状态机</b>、<b>结构化输出</b>（Pydantic 校验）、
          <b>混合检索 RAG</b>、<b>分层评测</b>与<b>置信度校准</b>。
          我喜欢把「模型能做什么」翻译成「系统怎么保证它靠谱」——
          用状态机约束不可跳过的迁移、用双引擎交叉验证给置信度、
          用留出集暴露真实泛化能力，而不是只报一个漂亮数字。
        </p>
        <p align="left">
          每个项目都<b>开箱即跑</b>：<code>docker compose up --build</code> 即可完整体验，
          不配置任何 API Key 也能跑通全链路（自动降级到内置规则引擎）。
        </p>
      </td>
      <td width="38%" align="center">
        <img src="https://capsule-render.vercel.app/api?type=soft&color=gradient&height=140&section=header&text=dasandeyu-ll&fontSize=40&animation=fadeIn" alt="header"/>
        <br/>
        <img src="https://github-readme-stats.vercel.app/api/top-langs?username=dasandeyu-ll&layout=compact&theme=radical&hide_border=true&langs_count=6" alt="Top Languages"/>
      </td>
    </tr>
  </table>
</div>

---

## 项目 <a name="projects"></a>

<div align="center">

| 单易分 · 智能工单分拣台 | 知溯问答 · 全栈 RAG | AI 智能模拟面试 |
|:---:|:---:|:---:|
| <img src="https://github-readme-stats.vercel.app/api/pin/?username=dasandeyu-ll&repo=danyifen&theme=radical&hide_border=true" alt="danyifen"/> | <img src="https://github-readme-stats.vercel.app/api/pin/?username=dasandeyu-ll&repo=knowtrace&theme=radical&hide_border=true" alt="knowtrace"/> | <img src="https://github-readme-stats.vercel.app/api/pin/?username=dasandeyu-ll&repo=mianba-ai-interview&theme=radical&hide_border=true" alt="mianba-ai-interview"/> |
| <a href="https://github.com/dasandeyu-ll/danyifen"><b>仓库链接</b></a> | <a href="https://github.com/dasandeyu-ll/knowtrace"><b>仓库链接</b></a> | <a href="https://github.com/dasandeyu-ll/mianba-ai-interview"><b>仓库链接</b></a> |

</div>

### 单易分 · 基于目标识别的智能工单分拣系统

> 一条客服留言不是「一个意图」，而是可以拆成 N 个 Goal，每个 Goal 独立走状态机。

- **多标签意图 + 结构化槽位**：`split → classify → extract → verify → ask / ready / human` 的 LangGraph 流程
- **不确定就交还给人**：置信度低于阈值（默认 `0.62`）或头两名意图分差过小时自动转人工，并生成追问话术，**不允许直接分拣**
- **双引擎交叉验证**：规则引擎（离线可用）+ DeepSeek 结构化输出，两者是否一致作为置信度证据
- **分层评测**：调优集 100% / 改写留出集 83.3%，总体意图准确率 97.2%、槽位 F1 0.977、转人工召回 100%
- **前端零硬编码**：意图词典、槽位 schema、阈值、状态机图全部由 `/api/meta` 下发，React + ECharts 驾驶舱

### 知溯问答 · 基于 LangGraph ReAct Agent 的全栈 RAG

- **双路检索**：FAISS 向量语义召回 + bigram 关键词召回，**RRF 融合**排序
- **SSE 真流式**：回答逐 token 推送，非伪流式
- **可溯源**：每条回答回链到知识库原文段落，附带引用片段
- **ReAct 循环**：LangGraph 驱动「检索 → 判断是否足够 → 继续检索 / 生成答案」

### AI 智能模拟面试系统

- **出题 → 追问 → 评分 → 报告** 全链路 LangGraph 状态机
- **四维评估雷达图**：ECharts 可视化多维度评分
- **Docker 一键启动**，前端 React + ECharts，后端 FastAPI

---

## 技术栈 <a name="stack"></a>

<div align="center">

| 类别 | 技术 |
|:---:|:---|
| **语言** | Python 3.10+ · JavaScript (ES6+) · SQL |
| **Agent / LLM** | LangGraph · LangChain · DeepSeek（OpenAI 兼容协议）· ReAct · 结构化输出 + Pydantic 校验 |
| **后端** | FastAPI · Uvicorn · SQLite · Pydantic v2 · pytest / 端到端 smoke test |
| **前端** | React 18 · Vite · ECharts · 原生 CSS（深色驾驶舱主题） |
| **检索** | FAISS · bigram 关键词检索 · RRF 融合重排 |
| **工程化** | Docker · docker-compose · nginx 反代 · GitHub Actions |

</div>

---

## 数据 <a name="stats"></a>

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=dasandeyu-ll&show_icons=true&theme=radical&hide_border=true&include_all_commits=true&count_private=true" height="165" alt="stats"/>
<img src="https://github-readme-stats.vercel.app/api/repo-top-langs/?username=dasandeyu-ll&layout=compact&theme=radical&hide_border=true" height="165" alt="repo langs"/>
<img src="https://github-readme-streak-stats.vercel.app?user=dasandeyu-ll&theme=radical&hide_border=true" height="165" alt="streak"/>

</div>

---

## 工作流 <a name="workflow"></a>

- **需求拆解 → 数据先行**：先定义领域模型与状态机，再写接口
- **接口驱动的前后端解耦**：后端只提供 `/api/meta` 配置，前端零硬编码渲染
- **测试即文档**：每个项目都带端到端 smoke test（识别 → 确认 → 非法迁移拒绝 → 统计 → 评测）
- **诚实的指标**：报告数字时同时给出调优集与留出集，不用训练集数字包装泛化能力

---

<div align="center">

**如果这些项目对你有帮助，欢迎 Star、Fork 或提 Issue 一起改进。**

[↑ 返回顶部](#about)

</div>
