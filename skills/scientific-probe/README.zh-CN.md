# Scientific Probe Skill

这个 Codex skill 用来防止把科学问题过早改造成软件工程项目。它要求 Codex 先定义竞争假说、判别观测、最小实验、决策规则和停止条件，然后在默认复杂度预算内实现。

## 安装

仓库级安装：

```bash
mkdir -p .agents/skills
cp -R scientific-probe .agents/skills/
```

用户级安装：

```bash
mkdir -p ~/.agents/skills
cp -R scientific-probe ~/.agents/skills/
```

Codex 通常会自动发现变更；没有出现时重启 Codex。

## 使用

显式调用：

```text
Use $scientific-probe to test whether mechanism A explains phenomenon B.
```

或：

```text
使用 $scientific-probe。先给出 H0/H1、判别统计量、最小实验和停止条件；不要建立通用框架。
```

## 建议的 AGENTS.md 路由规则

为了提高自动触发可靠性，可在仓库根目录的 `AGENTS.md` 加入：

```markdown
For tasks whose primary objective is to test, reproduce, explain, or discriminate a scientific claim, invoke $scientific-probe before editing code. Treat code as experimental apparatus, not as the product. Do not enter production engineering until the scientific stop condition is reached or the user explicitly requests it.
```

## 验证

`scientific-probe/evals/trigger-prompts.csv` 包含显式触发、隐式触发、混合任务和反例任务。先手动运行其中几条，确认当前 Codex 版本能正确调用并遵守 skill；再根据实际失误补充案例。

## 关键限制

Skill 是工作流指令，不是强制执行的编译器或策略引擎。最稳妥的组合是：

1. 任务中显式写 `$scientific-probe`；
2. 在 `AGENTS.md` 添加上面的路由规则；
3. 用 eval 样例持续检查误触发、漏触发和工程化回归。
