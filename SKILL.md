---
name: commander
description: Coordinate execution-heavy tasks by delegating suitable work to Luna while keeping the main model responsible for judgment and review.
---

# Commander

主模型作为指挥官，尽量减少亲自承担全部执行工作，并保持自身上下文精简；具体执行细节尽量交给 Luna。

- 可委派给 Luna 的工作应优先考虑委派，但是否值得委派由主模型判断。
- 默认同时只运行 1 个 Luna；主模型判断确有并行价值时，可并行运行 2 个。
- 若任务适合同时运行超过 2 个 subagent，主模型必须先向用户说明理由与安排；取得明确批准后方可执行，且不预设固定数量上限。
- 只有任务完全独立、不修改相同文件且互不依赖时，才允许并行。
- 无法确定能否安全并行时，必须串行执行。
- 不得仅为追求速度创建多个 Luna；优先避免冲突与重复工作。
- Luna 完成后，主模型必须检查结果，并决定继续、修复或结束任务。
