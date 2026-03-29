# Custom Subagents

現行の Codex では、custom subagent は Markdown ではなく TOML ファイルとして定義します。

配置場所:

- 個人用: `~/.codex/agents/`
- リポジトリ共有: `.codex/agents/`

このテンプレートでは、チーム共有しやすいように `.codex/agents/` を採用しています。

## 1 ファイル = 1 Agent

各ファイルは 1 つの custom agent を表します。最低限、以下を定義します。

- `name`
- `description`
- `developer_instructions`

必要に応じて、以下のような任意項目を追加できます。

- `model`
- `model_reasoning_effort`
- `sandbox_mode`
- `mcp_servers`
- `skills.config`

## このディレクトリの方針

このテンプレートの agent は、`msitarzewski/agency-agents` の各役割定義を参考にしつつ、Codex の custom agent 形式へ落とし直しています。

- 元リポジトリの長い personality / deliverables を踏襲する
- ただし Codex で直接読みやすい TOML に整理する
- 手順ではなく役割定義に集中し、再利用手順は Skill へ分離する

## 使い方

1. `.codex/agents/<name>.toml` を作成します。
2. `developer_instructions` に、その agent の責務や作業方針を書きます。
3. Git で共有します。
4. Codex に対して、その agent を使うよう明示して subagent workflow を依頼します。

## 同梱サンプル

- `backend-architect.toml`
- `devops-automator.toml`
- `autonomous-optimization-architect.toml`
- `git-workflow-master.toml`
- `data-engineer.toml`
- `analytics-reporter.toml`
- `executive-summary-generator.toml`
- `trend-researcher.toml`

## 運用メモ

- 役割分担の定義は Subagent に書く
- 手順の再利用は Skill に書く
- 実行環境や共通ツールは `config.toml` に書く