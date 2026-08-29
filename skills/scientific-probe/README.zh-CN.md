# Scientific Probe

`scientific-probe` 负责科研流程中的认识论层：扩展假说空间、寻找真正具有判别力的观测、为单项探针确定分析规则，并根据实际证据更新判断。

它不负责科研仓库架构或代码精简；这些实现任务由同一套件中的 `$lean-scientific-computing` 承担。

## 三种模式

- **DISCOVERY**：假说空间不完整或出现意外结果。允许有边界的自适应探索，但必须记录所有分支、指标变化和筛选过程；结果只能标为探索性。
- **DISCRIMINATION**：已有竞争解释。看到结果前固定主判别量、分析规则、决策规则和停止条件。
- **REPLICATION**：复现既有结论。重跑前固定总体、排除规则、预处理、统计量、成功或失败标准及停止条件。

Probe Contract 只固定当前探针，不会冻结整个研究计划。意外证据可以产生新合同，但不能被事后修改的指标或阈值包装成原计划成功。

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

- 一个效应是否存在；
- 哪个机制更能解释观测；
- 一个异常还可能来自哪些非显然机制；
- 什么实验能够区分竞争假说；
- 一个结果是否成功复现；
- 当前证据究竟支持什么；
- 下一项最低成本探针是什么。

不适合作为主流程：

- 实现已经明确的方程或算法；
- 整理参数、数据或输出路径；
- 精简过度工程化的科研仓库；
- 普通文献摘要；
- 部署已经验证的产品系统。

## 安装

仓库级：

```bash
mkdir -p .agents/skills
cp -R scientific-probe .agents/skills/
```

用户级：

```bash
mkdir -p ~/.agents/skills
cp -R scientific-probe ~/.agents/skills/
```

## 典型调用

```text
使用 $scientific-probe 的 DISCOVERY 模式分析这个未被现有模型解释的异常。
提出机制上真正不同的候选，避免只给主流解释换措辞；选择一项最低成本的
判别探针。需要修改仓库时，把 Probe Contract 交给
$lean-scientific-computing，最后再解释 Evidence Record。
```

在科研仓库中，建议同时安装两个 Skill，并采用仓库根目录 [`templates/AGENTS.md`](../../templates/AGENTS.md) 中的路由规则。
