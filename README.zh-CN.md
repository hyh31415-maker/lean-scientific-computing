# 面向 Codex 的精益科研工作流

本仓库把两个 Codex Skill 统筹为一套连续科研流程：

- [`scientific-probe`](skills/scientific-probe)：负责判断**什么证据能够改变科学判断**。
- [`lean-scientific-computing`](skills/lean-scientific-computing)：负责用**最小、透明、可核验的科研代码取得这些证据**。

共同原则：

> 假说可以大胆，结论必须保守，工程复杂度必须与当前科学问题相称。

两个 Skill 不合并。科研推理与科研实现具有不同的触发条件、输出和停止规则；分开后更容易正确路由，再通过明确合同完成交接。

## 连续工作流

```text
尚未解决的问题、异常或结论
            |
            v
    $scientific-probe
       Probe Contract
            |
            v
$lean-scientific-computing
       Evidence Record
            |
            v
    $scientific-probe
  解释 / 分支 / 停止
```

- `scientific-probe` 管理竞争解释、判别预测、分析规则和证据解释。
- `lean-scientific-computing` 管理数据、方程、参数、执行路径、科研核验和项目结构。
- 同时包含科研验证与产品交付时，顺序为：

```text
科学探针 -> 精益实现 -> 证据解释 -> 确有必要时再产品化
```

不得为了判断一个效应是否存在，先建设完整服务、框架或平台。

## 发现阶段不强行套用验证阶段

`scientific-probe` 会选择三种模式之一：

- **DISCOVERY（发现）**：假说空间尚不清楚时，扩展机制候选、寻找异常并进行有边界的自适应探索。探索分支必须记录，但不能冒充预先设定的验证证据。
- **DISCRIMINATION（判别）**：已有可信竞争解释时，预先固定主判别量与规则。
- **REPLICATION（复现）**：在重跑前明确总体、排除规则、统计量、成功或失败标准及停止条件。

Probe Contract 只固定当前探针，不冻结整个研究计划。意外结果可以触发新假说和新合同，但不能通过事后更换指标或阈值被包装成原计划的成功。

## 如何选择

| 用户请求 | 首选流程 |
|---|---|
| 这个异常还有哪些非显然机制？ | `$scientific-probe` 的 DISCOVERY 模式 |
| 区分 A 与 B 的最低成本实验是什么？ | `$scientific-probe` 的 DISCRIMINATION 模式 |
| 复现一个结论，并预先定义失败 | 先 `$scientific-probe`，需要编码时再交给精益实现 |
| 把已经明确的速率方程加入模型 | `$lean-scientific-computing` |
| 执行已经冻结的对照实验 | `$lean-scientific-computing`，随后交回探针解释 |
| 在保持结果不变的前提下精简科研仓库 | `$lean-scientific-computing` |
| 为新算法建设服务，但要先证明优于基线 | 探针 -> 精益实现 -> 解释 -> 普通产品工程 |
| 部署已经验证的模型并满足可用性与安全要求 | 普通产品工程 |

完整职责边界见 [`docs/coordination.md`](docs/coordination.md)。

## 本地安装两个 Skill

仓库级：

```bash
mkdir -p .agents/skills
cp -R skills/scientific-probe .agents/skills/
cp -R skills/lean-scientific-computing .agents/skills/
```

用户级：

```bash
mkdir -p ~/.agents/skills
cp -R skills/scientific-probe ~/.agents/skills/
cp -R skills/lean-scientific-computing ~/.agents/skills/
```

也可以让 Codex 使用 `$skill-installer` 分别从两个 GitHub 目录安装。仓库根目录的 [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) 已把两个 Skill 声明为一个插件包；发布到插件目录或市场属于后续分发步骤。

建议把 [`templates/AGENTS.md`](templates/AGENTS.md) 中的简短路由规则复制到科研仓库根目录。`AGENTS.md` 只负责长期路由，具体流程由 Skill 承担。

## 典型调用

```text
使用 $scientific-probe 的 DISCOVERY 模式，为观测振荡提出机制上真正不同的
解释，并选择能够区分主要候选的最低成本观测。只固定这一项探针。
随后让 $lean-scientific-computing 完成产生 Evidence Record 所需的最小实现，
最后把证据交回 $scientific-probe 解释。
```

## 评测

- 每个 Skill 内有独立触发与行为测试；
- [`evals/routing-prompts.csv`](evals/routing-prompts.csv) 检查模式、路由与交接；
- [`evals/coordination-rubric.md`](evals/coordination-rubric.md) 检查合同完整性、探索质量、科研核验、工程克制和停止行为。

许可证：MIT。
