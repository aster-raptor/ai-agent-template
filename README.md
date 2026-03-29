# AI エージェント開発環境テンプレート

このリポジトリは、AI エージェントを活用した開発環境を素早く立ち上げるためのテンプレートです。

主対象は Codex ですが、他のクライアントでも読み替えやすいように構成しています。

## このテンプレートで扱うもの

- `MCP`
  - 外部ツール、ドキュメント、各種サービスをエージェントに接続します。
- `Plugins`
  - Codex 固有のワークフローバンドルです。Skills、アプリ連携、MCP サーバーを含められます。
- `Skills`
  - リポジトリ内で管理し、チームで再利用できる作業手順です。
- `Subagents`
  - Codex の custom agent 機能で使う `.codex/agents/*.toml` 定義です。詳細は [.codex/agents/README.md](C:\Develop\ai-agent-template\.codex\agents\README.md) を参照してください。

## クイックスタート

1. [.codex/config.toml.example](C:\Develop\ai-agent-template\.codex\config.toml.example) を `.codex/config.toml` にコピーします。
2. 必要な MCP サーバーを有効化し、必要に応じて [.env.example](C:\Develop\ai-agent-template\.env.example) を元に環境変数を設定します。
3. [skills/README.md](C:\Develop\ai-agent-template\skills\README.md) を参考にローカル Skill を追加し、必要であれば Codex の plugin directory から Plugins を導入します。
4. [.codex/agents/README.md](C:\Develop\ai-agent-template\.codex\agents\README.md) を参考に custom subagent を追加または調整します。

## Skills の導入方法

### リポジトリ同梱の Skill を使う場合

1. `skills/<skill-name>/SKILL.md` を作成します。
2. Skill の説明、使う場面、手順、期待する出力を記述します。
3. Git に含めて共有します。

このテンプレートでは、まずリポジトリ同梱の Skill を標準運用にするのがおすすめです。

### マーケットや curated な Skill を使う場合

1. Codex で `$skill-installer` を使って Skill を導入します。
2. 個人利用ならローカル設定でそのまま使います。
3. チーム共通にしたい場合は、内容を確認した上で repo 配下の `skills/` に取り込み、Git 管理へ寄せます。

## Subagents の導入方法

現在の Codex では、Subagent は Markdown ではなく `.codex/agents/*.toml` として定義します。

1. `.codex/agents/<name>.toml` を作成します。
2. `name`, `description`, `developer_instructions` を記述します。
3. 必要なら `model`, `model_reasoning_effort`, `sandbox_mode` などを追加します。
4. Git で共有し、各端末で同じ定義を利用します。

## リポジトリ構成

- [docs/agent-tooling-overview.md](C:\Develop\ai-agent-template\docs\agent-tooling-overview.md)
  - Codex / Claude Code / Cursor の概念対応を整理したガイド
- [docs/codex-setup.md](C:\Develop\ai-agent-template\docs\codex-setup.md)
  - Codex CLI / App / IDE 向けの導入手順
- [docs/catalog.md](C:\Develop\ai-agent-template\docs\catalog.md)
  - MCP / Plugins / Skills の推奨スターターカタログ
- [skills/README.md](C:\Develop\ai-agent-template\skills\README.md)
  - ローカル Skill の追加・管理方法
- [.codex/agents/README.md](C:\Develop\ai-agent-template\.codex\agents\README.md)
  - Codex 互換の custom subagent 定義方法
- [subagents/README.md](C:\Develop\ai-agent-template\subagents\README.md)
  - 旧 Markdown 形式からの移行案内

## 推奨する導入順

以下の順で導入すると扱いやすくなります。

1. まず MCP を追加して、共通のツールやドキュメント参照を使えるようにする
2. 次に Skills を追加して、リポジトリ固有の定型作業を再利用できるようにする
3. 必要に応じて Codex Plugins を追加し、外部アプリ連携をまとめて使えるようにする
4. 並列実行や役割分担が必要になったら `.codex/agents/*.toml` の Subagents を追加する

## 補足

- Codex の MCP 設定は `config.toml` で管理されます。このテンプレートでは project-scoped な `.codex/config.toml` を前提にしています。
- Codex Plugins のインストール自体は Codex の plugin directory から行い、設定ファイルは主に有効・無効の管理に使います。
- このリポジトリの Skills は、依存を増やさずに新しいプロジェクトへ持ち込みやすい最小構成にしています。
- Subagents は現行 Codex docs に合わせて `.codex/agents/*.toml` で管理します。