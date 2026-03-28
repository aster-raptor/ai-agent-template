# Codex Subagents

このディレクトリには、`agency-agents` を Codex 向けのサブエージェント定義に圧縮した Markdown を置く。

目的:
- `spawn_agent` に渡しやすい短い役割定義を再利用する
- 元の長い personality / examples を、Codex の実務フロー向けに整理する
- 役割ごとの責務と期待成果物を固定する

収録サブエージェント:
- `backend-architect.md`
- `devops-automator.md`
- `autonomous-optimization-architect.md`
- `git-workflow-master.md`
- `data-engineer.md`
- `analytics-reporter.md`
- `executive-summary-generator.md`
- `trend-researcher.md`

使い方の目安:
- 実装やファイル変更を伴うタスク: `agent_type: "worker"`
- 調査・棚卸し・要約中心のタスク: `agent_type: "explorer"`
- 横断的で判断比重が高いタスク: `agent_type: "default"`

運用メモ:
- サブエージェントには担当範囲を明示する
- コード変更を任せる場合は、対象ファイルやディレクトリを明示する
- 既存変更を巻き戻さないことを明記する
- 返答では、変更ファイルや判断理由を短く列挙させる

元ネタ:
- Repository: https://github.com/msitarzewski/agency-agents
- License: MIT

