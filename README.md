

<h1 align="center">🧠 Ai Call Center 大模型呼叫</h1>

<p align="center">
  <b> Knowledge Brain for Java</b> —— 让 Java 团队零门槛拥有企业级 AI 呼叫中心系统<br/>
  基于 <b>Java 17 + Spring Boot 3 </b>构建的开箱即用、模型中立的 <b>RAG + LLM 呼叫中心系统</b><br/>
  <sub>Call Center，Contact Center，呼叫中心，客服系统，工单系统，智能外呼，大模型呼叫中心，智能呼叫中心，RAG搜索模块，AI；FreeSWITCH，LLM Call Center,AI Call Center,大模型呼叫中心,大模型客服系统，可以对接市面上主流模型与私有模型等！</sub>
</p>

<p align="center">
  <a href="https://openjdk.org/projects/jdk/17/"><img src="https://img.shields.io/badge/Java-17%2B-green" alt="Java21plus"></a>
  <a href="https://spring.io/projects/spring-boot"><img src="https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen" alt="SpringBoot3"></a>
  <a href="https://github.com/langchain4j/langchain4j"><img src="https://img.shields.io/badge/LangChain4j-1.x-green" alt="LangChain4j"></a>
</p>
<p align="center">
    <a href="#技术栈与关键组件">技术栈与关键组件</a> ·
    <a href="#系统架构">系统架构</a> ·
    <a href="#在线Demo">在线Demo</a> ·
    <a href="#企业定制合作">企业合作</a>
</p>
<p align="center">
  [<a href="README.md">中文（简体）</a>] | [<a href="README.md">English</a>]
</p>

## ✨ 呼叫中心核心能力

| 能力                           | 说明                                                                                                            |
|:-----------------------------|:--------------------------------------------------------------------------------------------------------------|
| 🔍 知识库问答                     | 上传 PDF / Word / TXT / Markdown 等文档或自动爬取网页，自动完成分段 → 向量化 → 入库 → 构建 RAG，显著减少大模型幻觉；支持文档内图片融合向量化，实现图文混合检索          |
| 🧠 Advanced RAG / AgenticRAG | 向量、全文、混合多路召回 + Reranker 重排序；结合意图识别、条件分支，由智能体动态决策检索路径，支持多跳问答                                                   |
| ⚙️ 可视化IVR交互式语音应答）      | 提供灵活的语音菜单设计，大模型接入,MCP接入，引导客户自助完成查询、报修等常见操作，减轻人工坐席压力，提升服务效率                                                 |
| 📜 可视化工单工作流               | 工作流引擎采用基于PVM（Process Virtual Machine）的架构模式，支持bpm协议中的多种节点功能，表结构简单明了，易于扩展及后期运维                                                |
| 🤝 与CRM集成                     | 支持与主流CRM系统无缝集成，自动同步客户信息，实现客户数据的全面整合与利用，为个性化服务提供数据支持                                                        |
| ⏰ 坐席管理                        | 提供全面的坐席管理工具，包括实时监控、录音回放、工单管理、绩效统计等，帮助管理者优化团队运作，提升服务质量                                                |
| 🌐 模型中立                      | 私有模型（Ollama / Xorbits Inference / LocalAI）与国内外公有模型：通义千问、DeepSeek、豆包、混元、GLM、Kimi、GPT、Claude、Gemini 等           |
| 🧩 无缝集成                      | RESTful API、iframe / Web SDK 嵌入组件、OpenAI 兼容对话接口、stream_http MCP 接入方式，5 分钟接入现有系统                               |
| 🎙️ 多模态                      | **多模态融合向量**：文档中文本与图片融合为统一向量，支持图文混合的跨模态检索（阿里云百炼 / 火山方舟视觉向量模型）；ASR 语音识别、TTS 语音合成、OCR 图像识别、Stable Diffusion 图像生成 |
| 🔒 权限与安全                     | 基于 Sa-Token 的细粒度权限（应用 / 知识库 / 工具 / 模型）、审计日志、groovy-sandbox 脚本沙箱                                               |



## 技术栈与关键组件

### 后端技术栈
- **框架**：Spring Boot 3.3.1、MyBatis-Plus、Spring Security、SA-TOKEN。
- **数据库**：MySQL（主库）、Pg vector(向量库)、qdrant（向量缓存）、Redis（缓存与会话）。
- **消息队列**：RabbitMQ（异步任务处理）。
- **通信协议**：SIP（FreeSWITCH）、MRCP V2（语音交互）。

### 核心组件
- **FreeSWITCH**：VoIP 核心引擎，处理媒体流与信令。
- **Kamailio**：SIP 代理服务器，实现负载均衡与安全防护。
- **ESL 客户端**：通过 Java Netty 实现与 FreeSWITCH 的交互。
  
## 系统架构
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/architecture_overview_freeswitch.png"  width="100%" />
      <br/>
      架构部署图.
    </td>
  </tr>
</table>

## 系统截图
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/cc-index.png"  width="100%" />
      <br/>
      话务系统首页.
    </td>
    <td width="50%" valign="top">
      <img src="docs/cc-ivr-deubg.png"  width="100%" />
      <br/>
      IVR工作流可视化编辑，及在线调试.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
       <img src="docs/ticket-index.png"  width="100%" />
      <br/>
      工单系统首页.
    </td>
    <td width="50%" valign="top">
     <img src="docs/ticket-view.png"  width="100%" />
      <br/>
      工单流转轨迹追踪.
    </td>
  </tr>
</table>

## 在线Demo
- 话务系统在线 Demo：http://118.195.135.225/ui     （自动登陆账号为普通用户权限）
- 工单系统在线 Demo：http://118.195.135.225/tk  （自动登陆账号为普通用户权限）

## 应用案例
- **产品演进** 本团队深耕呼叫中心行业经验15年，大模型呼叫中心迭代5年以上由早期智能客服项目，演进到以python为核心的大模型产品，于近期再次迭代到以java为主要架构的产品
- **客户行业** 分布于运营商，知名高校，水利，供暖集团
  
## 企业定制合作
需要**私有化部署、二次开发、团队培训**等深度合作？可提供专属方案与报价：

- 私有化 / 内网环境部署
- 业务场景定制开发与系统集成
- 源码合作

联系作者微信，获取专属方案与报价。
<table>
  <tr>
    <td width="400px" height="400px" valign="top">
      <img src="docs/wx.jpg" />
      <br/>
      联系我
    </td>
  </tr>
</table>



