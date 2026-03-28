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
  - 委譲先の役割定義です。詳細は [subagents/README.md](C:\Develop\ai-agent-template\subagents\README.md) を参照してください。

## クイックスタート

1. [.codex/config.toml.example](C:\Develop\ai-agent-template\.codex\config.toml.example) を `.codex/config.toml` にコピーします。
2. 必要な MCP サーバーを有効化し、必要に応じて [.env.example](C:\Develop\ai-agent-template\.env.example) を元に環境変数を設定します。
3. [skills/README.md](C:\Develop\ai-agent-template\skills\README.md) を参考にローカル Skill を追加し、必要であれば Codex の plugin directory から Plugins を導入します。
4. [subagents/README.md](C:\Develop\ai-agent-template\subagents\README.md) を参考に Subagent 定義をそのまま再利用します。

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

Subagent には Skill のような専用インストーラはありません。Markdown ファイルをリポジトリに置いて管理します。

1. `subagents/<name>.md` を配置します。
2. 役割、責務、得意領域、期待する出力を書きます。
3. `spawn_agent` で使うときに、その定義を参照または読み込んで利用します。
4. 複数端末で共有したい場合は、このリポジトリ配下で Git 管理します。

## リポジトリ構成

- [docs/agent-tooling-overview.md](C:\Develop\ai-agent-template\docs\agent-tooling-overview.md)
  - Codex / Claude Code / Cursor の概念対応を整理したガイド
- [docs/codex-setup.md](C:\Develop\ai-agent-template\docs\codex-setup.md)
  - Codex CLI / App / IDE 向けの導入手順
- [docs/catalog.md](C:\Develop\ai-agent-template\docs\catalog.md)
  - MCP / Plugins / Skills の推奨スターターカタログ
- [skills/README.md](C:\Develop\ai-agent-template\skills\README.md)
  - ローカル Skill の追加・管理方法
- [subagents/README.md](C:\Develop\ai-agent-template\subagents\README.md)
  - 既存の役割ベース委譲定義

## 推奨する導入順

以下の順で導入すると扱いやすくなります。

1. まず MCP を追加して、共通のツールやドキュメント参照を使えるようにする
2. 次に Skills を追加して、リポジトリ固有の定型作業を再利用できるようにする
3. 必要に応じて Codex Plugins を追加し、外部アプリ連携をまとめて使えるようにする
4. 大きな作業や並列化したい作業では Subagents を使う

## 補足

- Codex の MCP 設定は `config.toml` で管理されます。このテンプレートでは project-scoped な `.codex/config.toml` を前提にしています。
- Codex Plugins のインストール自体は Codex の plugin directory から行い、設定ファイルは主に有効・無効の管理に使います。
- このリポジトリの Skills は、依存を増やさずに新しいプロジェクトへ持ち込みやすい最小構成にしています。
- Subagents は配布物というより repo 同梱の役割定義として扱うのが管理しやすいです。