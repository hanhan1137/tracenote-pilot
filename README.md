# TraceNote

**看板在线，不等于这次运行真的被看见。**

TraceNote 把 Agent 的接入状态与运行元数据整理成可阅读、可复核的诊断报告。现在开放小范围 **Hermes 单机接入体检试点**：先帮你分清配置、采集器、入库记录和报告分别到了哪一步。

**[咨询试点 →](mailto:3670922501@qq.com?subject=TraceNote%20pilot)** · 联系邮箱：3670922501@qq.com

> 当前为作者自用系统发展出的协助式试点。本仓库是服务介绍与反馈入口，不是可一键安装的开源发行包。

## 适合什么情况

- 你已在 Linux 主机上运行 Hermes，想确认观察器到底接到了什么。
- 采集器显示在线，但看板一直是旧数据，不知道应该查哪一层。
- 一堆历史报错和当前状态混在一起，难以判断现在是否需要处理。
- 你希望得到一份中文体检报告和有依据的排查顺序，而不是再多一个指标面板。

## 一次试点交付什么

| 检查层 | 核对的问题 | 报告中的结果 |
|---|---|---|
| 配置 | 约定的来源是否已配置？ | 当前范围与缺失项 |
| 采集器 | 消费者当前健康，还是只有历史状态？ | 当前状态、依据与未知项 |
| 入库证据 | 有历史记录，还是有近期新记录？ | 分开呈现历史证据和近期证据 |
| 报告 | 简报是否生成，是否足够新？ | 新鲜度与建议排查步骤 |

范围确认后提供：单机单来源的接入核对、中文报告、一次结果说明与约定范围内的排障建议。部署方式、支持版本和验收项先逐项确认，未经确认的环境不直接承诺适配。

**首轮试点参考价：人民币 299 元／次。** 初步适配沟通免费；费用、具体交付和时间安排在开始付费工作前确认。本介绍不构成已成立的订单，不提供全天候运维承诺。

## 报告怎样帮助判断

下面是**模拟示例，仅解释报告结构，不是客户数据或一次真实验收结果**：

> **结论：等待近期运行证据。**
>
> 已知：来源已配置，采集器有当前健康信息，也存在历史入库记录。
>
> 未知：最近一次运行有没有进入这条采集链路。
>
> 下一步：在你正常使用 Hermes 后核对新记录及其来源身份；如果仍没有新记录，再按生产者、采集、入库的顺序检查。
>
> 不能据此判断：Agent 的工作产物是否正确。

这能避免把“服务在线”“过去采到过”和“这次接通了”混成一个绿灯。没有近期事件会保留为等待或证据不足，不直接宣布故障或成功。

## 已做过的真实工作

在作者自用 Linux 环境中，曾出现历史进程健康文件累积后被误判为当前健康故障的问题。修复后保留历史文件，分别处理退出历史与当前进程，避免靠删除记录让状态变好。新的接入体检已在该环境部署。

这是作者自用案例，尚无付费客户案例；它不证明所有版本都兼容，也不证明每次任务都成功。

## 怎样开始

发邮件到 **3670922501@qq.com**，写下以下信息即可：

1. 操作系统、Hermes 版本，以及是否已经常驻运行。
2. 最想排查的一个现象，以及你目前怎样处理。
3. 希望体检后能回答的一个问题。

不需要发送对话、提示词、任务正文、工具参数或输出、密码及密钥。初步沟通先核对是否适合；匹配后再确认范围、费用与验收。环境和业务数据由你控制。观测源按约定只读；TraceNote 自身会在约定位置保存元数据与报告。

一般产品问题也可以在本仓库提 Issue。**Issue 是公开的，请勿填写联系方式、服务器地址、私人日志或其他敏感资料。** 具体环境咨询走邮件。

## 当前支持范围

当前收费试点只聚焦自部署 Hermes 的单机接入与元数据诊断。自动判断业务产物正确性、自动修改 Agent、完整账单核算与托管订阅尚未作为本试点交付。普通 ChatGPT 桌面的内部工具调用和 Token 不在当前采集范围。

TraceNote 是独立项目，与 Hermes / Nous Research 没有官方合作或背书关系。

---

## English

**An online dashboard does not prove that your latest agent run was captured.**

TraceNote separates source configuration, collector health, historical/recent ingestion evidence, and report freshness into a readable diagnostic report. We are exploring a small, assisted pilot for people already running Hermes on Linux.

This repository is an introduction and feedback channel, not a self-serve software release. The initial pilot is scoped to one machine and one source. A reference price of CNY 299 is subject to confirming scope, compatibility, delivery, and timing before paid work begins. It does not include automatic repair, grading task outputs, or complete billing.

For an initial fit discussion, email **3670922501@qq.com** with your OS, Hermes version, and one troubleshooting problem. Please do not send conversations, task content, credentials, private logs, or tool arguments/outputs. The sample above is illustrative; the self-use case is not a customer success story.
