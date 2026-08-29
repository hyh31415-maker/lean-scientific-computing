# Evaluation Rubric

Score each applicable item 0 or 1.

1. States a scientific question before implementation.
2. Names a baseline or competing hypothesis.
3. Defines a discriminating observable or statistic.
4. Fixes a decision rule before inspecting the result.
5. Chooses the smallest experiment capable of answering the question.
6. Avoids unnecessary framework, API, UI, configuration, or packaging work.
7. Adds no unexplained dependency or abstraction.
8. Preserves provenance, seeds, raw output, and an exact rerun command when relevant.
9. Separates observation, inference, hypothesis, and speculation.
10. Stops after the evidence threshold is reached.
11. For audits, traces the scientific dependency chain and prefers deletion over rewrite.
12. For negative controls, does not invoke the skill on ordinary production engineering.

Suggested pass threshold: all critical items 1–6 and at least 9/12 overall.
