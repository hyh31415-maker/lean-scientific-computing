# Scientific Probe

`scientific-probe` 负责把已经界定的科学目标、异常、竞争解释或复现任务变成一项有边界的探针：确定判别观测、固定分析与停止规则，并根据实际 Evidence Record 更新判断。

它不负责科研仓库架构或代码精简；这些实现任务由同一套件中的 `$lean-scientific-computing` 承担。

如果同时安装了 `exploratory-science`，开放式假说组合、概念模型发展和研究方向选择由后者负责；只有在某项探针需要正式冻结、复现或防止事后选择时，才交给本 Skill。快速、可逆的探索不需要两边来回切换。

它不会把“能够支持强结论的证据”误当成“决定下一步行动所需的证据”。在观测稀疏、噪声大或规律只在局部区域、季节、类群或环境条件下成立时，可以把这些规律作为有明确适用域的工作证据，优先设计一项可逆、低成本而有判别力的探针；不必等待普适定律，也不能把局部结果直接外推为普遍结论。

## 三种模式

- **DISCOVERY**：已经界定异常或搜索目标，但当前探针需要有限调整。允许有边界的自适应探索，但必须记录所有分支、指标变化和筛选过程；结果只能标为探索性。
- **DISCRIMINATION**：已有竞争解释。看到结果前固定主判别量、分析规则、决策规则和停止条件。
- **REPLICATION**：复现既有结论。重跑前固定总体、排除规则、预处理、统计量、成功或失败标准及停止条件。

Probe Contract 只固定当前探针，不会冻结整个研究计划。意外证据可以产生新合同，但不能被事后修改的指标或阈值包装成原计划成功。

只冻结会改变当前推断的选择。文件格式、框架、完整边缘情况和次要分析若不影响本轮解释或执行，可记录后置，不应阻塞核心探针。

## 职责边界

```text
科学问题或异常
  -> $scientific-probe
  -> Probe Contract
  -> $lean-scientific-computing
  -> Evidence Record
  -> $scientific-probe
  -> 解释 / 分支 / 停止
```

适用请求：

- 如何为一个已界定的效应存在性问题固定判别规则；
- 已形成的候选机制中，哪个更能解释观测；
- 如何探查一个已经界定的异常；
- 什么实验能够区分竞争假说；
- 一个结果是否成功复现；
- 当前证据究竟支持什么；
- 下一项最低成本探针是什么。

不适合作为主流程：

- 开放式假说组合、概念模型发展或总体研究方向选择；
- 实现已经明确的方程或算法；
- 整理参数、数据或输出路径；
- 精简过度工程化的科研仓库；
- 普通文献摘要；
- 部署已经验证的产品系统。

## 安装

本 Skill 允许 Codex 根据普通科研请求自动选择；也可以通过 `$scientific-probe` 显式指定。

从本仓库根目录安装到项目：

```bash
mkdir -p .agents/skills
cp -R skills/scientific-probe .agents/skills/
```

从本仓库根目录安装到用户目录：

```bash
mkdir -p ~/.agents/skills
cp -R skills/scientific-probe ~/.agents/skills/
```

## 典型调用

```text
使用 $scientific-probe 的 DISCOVERY 模式分析这个未被现有模型解释的异常。
提出机制上真正不同的候选，避免只给主流解释换措辞；选择一项最低成本的
判别探针。需要修改仓库时，把 Probe Contract 交给
$lean-scientific-computing，最后再解释 Evidence Record。
```

在科研仓库中，建议同时安装两个 Skill，并采用仓库根目录 [`templates/AGENTS.md`](../../templates/AGENTS.md) 中的路由规则。
