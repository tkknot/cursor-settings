# 統合Cursor Rules
最終更新日: 2024年3月25日

## 目次
1. [shortcuts.mdc](#1-shortcutsmdc)
2. [branch.mdc](#2-branchmdc)
3. [git.mdc](#3-gitmdc)
4. [language.mdc](#4-languagemdc)
5. [directory.mdc](#5-directorymdc)
6. [development.mdc](#6-developmentmdc)

<a id="1-shortcutsmdc"></a>
## 1. shortcuts.mdc
元ファイル: `.cursor/rules/shortcuts.mdc`

---
description: 
globs: 
alwaysApply: false
---
---
description: 開発コマンドのショートカットエイリアス
globs: ["**/"]
alwaysApply: true
---
# ショートカットエイリアス

## コンサルティングコマンド
- `/ask`: "以下の問題について多角的な分析と具体的な提案を提供してください: [ISSUE]。
  以下の観点を考慮してください:
  1) メリットとデメリット
  2) 技術的な実現可能性
  3) リスクと対策
  4) 代替ソリューション。
  箇条書きで分析を提示し、推奨ソリューションで締めくくってください。"

- `/plan`: "以下の機能の実装のための詳細な作業計画を作成してください: [FEATURE]。
  含めるべき内容:
  1) 前提条件と制約
  2) 詳細な作業項目（時間見積もり付き）
  3) 依存関係
  4) リスクと対策
  5) 成功基準。
  各フェーズに明確な目標を持つフェーズ別の計画を提示してください。"

## デバッグと改善コマンド
- `/debug`: "以下のバグに対して体系的なデバッグを実行してください: [BUG SYMPTOMS]。
  手順:
  1) 5〜7つの可能性のある原因を列挙
  2) 各原因を評価（高/中/低の確率）
  3) 検証方法の提案
  4) 最も可能性の高い1〜2つの原因に絞り込み
  5) 具体的な修正案の提示。
  利用可能なログやエラーメッセージを考慮してください。"

- `/refactor`: "以下のコードをリファクタリングしてください: [CODE]。
  以下の観点で改善を提案してください:
  1) 読みやすさ
  2) 保守性
  3) パフォーマンス
  4) テスト容易性。
  各改善点の根拠を含め、優先順位をつけてください。
  リファクタリング前後のコード比較を示してください。"

## ドキュメントとコメントコマンド
- `/doc`: "以下のコードのドキュメントを作成してください: [CODE]。
  含めるべき内容:
  1) 概要と目的
  2) アーキテクチャ/設計の説明
  3) 主要機能の詳細
  4) API仕様（入出力、例外）
  5) 使用例
  6) 重要な注意点。
  適宜ダイアグラムを使用してください。"

- `/cmt`: "以下のコードにコメントを追加してください: [CODE]。
  コメントは以下を明確にすべきです:
  1) 処理の意図と目的
  2) 重要な前提条件
  3) 特殊なロジックの説明
  4) 潜在的なリスクと考慮事項。
  コードの読みやすさを損なわずに必要な情報を提供しながら、コメントを簡潔に保ってください。"

- `/log`: "以下のコードにロギングを追加してください: [CODE]。
  考慮すべき点:
  1) 適切なログレベル（ERROR/WARN/INFO/DEBUG）
  2) 運用監視に必要な情報
  3) パフォーマンスへの影響
  4) 個人情報/機密情報の取り扱い。
  具体的なログメッセージと出力タイミングを提案してください。"

## コード品質コマンド
- `/test`: "以下のコードのテストを作成してください: [CODE]。
  以下のテストケースを含めてください:
  1) 通常ケース
  2) エラーケース
  3) 境界値
  4) エッジケース。
  テストの目的と期待される結果を指定し、モック/スタブの使用戦略を示してください。"

- `/review`: "以下のコードをレビューしてください: [CODE]。
  以下の観点をチェックしてください:
  1) 機能要件への準拠
  2) コーディング標準への準拠
  3) セキュリティ
  4) パフォーマンス
  5) エラー処理
  6) テストカバレッジ。
  優先度レベル（高/中/低）付きでフィードバックを提供してください。"

- `/explain`: "以下のコードを詳細に説明してください: [CODE]。
  含めるべき内容:
  1) 全体的な処理フロー
  2) 主要な変数/関数の役割
  3) アルゴリズムの説明
  4) 設計上の考慮事項
  5) 潜在的な問題点。
  適宜ダイアグラムを使用してください。"

- `/rewrite`: "以下のコードの代替実装アプローチを提案してください: [CODE]。
  以下の観点に焦点を当てた複数の異なる実装パターンを検討してください:
  1) 読みやすさと保守性の向上
  2) 効率性とパフォーマンスの最適化
  3) 最新の言語機能とベストプラクティスの使用
  4) エラー処理の改善
  5) 拡張性の強化
  6) 同じ言語内の異なる実装パターン（関数型、オブジェクト指向など）
  各実装パターンについて、利点、欠点、どのような場合に選択すべきかを説明してください。
  推奨パターンとその根拠に関する推奨事項を提供してください。"

- `/tdd`: "テスト駆動開発（TDD）の手順を案内してください。

  TDDプロセス:
  0) まず、'doc/tdd/todo.md'にTODOリストを作成します（ファイルが存在しない場合は作成）。
     機能や問題を具体的なタスクに分解してこのリストに記載します。
  
  各タスクについて以下のサイクルを繰り返します:
  1) TODOリストから次のタスクを選択
  2) 期待される動作を定義する失敗するテストを作成
  3) テストをパスさせるための最小限のコードを実装
  4) テストがパスすることを確認
  5) テストがパスしたら、`/commit`コマンドを使用して変更をコミット（todo.mdを除く）
  6) テストが引き続きパスすることを確認しながらコードをリファクタリング
  7) リファクタリング後、再度`/commit`コマンドを使用して変更をコミット
  8) 完了したタスクをTODOリストから削除
  9) todo.mdのすべての項目が完了するまで上記の手順を繰り返す
  
  各サイクルで提供すべき内容:
  - 明確なテストアサーションと期待される結果
  - 最小限の実行可能なコードによる実装提案
  - コード品質を向上させるためのリファクタリング推奨事項
  - エッジケースとエラー処理に関する考慮事項
  
  最もシンプルなタスクから始めて、徐々に複雑なタスクに取り組んでください。
  すべてのTODO項目が完了したら、開発が完了したことを確認してください。"

## Git操作コマンド
- `/commit`: "以下の変更をコミットします: [CHANGES]。
  以下を含むコミットメッセージを作成します:
  1) プレフィックスの選択
  2) 変更の要約（50文字以内）
  3) 詳細な変更の説明
  4) 関連する問題/チケット。
  変更を論理的なコミット単位に分割すべきかどうかを評価します。"

- `/pr`: "以下の変更についてプルリクエストを作成します: [CHANGES]。
  含めるべき内容:
  1) 変更の要約
  2) 詳細な説明
  3) 関連する問題/チケット
  4) レビュアー
  5) ラベル/マイルストーン。
  変更を論理的なコミット単位に分割すべきかどうかを評価します。"

- `/push`: "以下の変更をリモートリポジトリにプッシュします: [BRANCH]。
  プッシュ前のチェック:
  1) コミットの論理性
  2) テスト実行結果
  3) コードレビューの状態
  4) コンフリクトの状態。
  リベースまたはスカッシュの必要性を評価します。"

- `/pull`: "リモートリポジトリから最新の変更を取得します: [BRANCH]。
  実行手順:
  1) ローカル作業状態の確認
  2) フェッチ戦略（マージ/リベース）の決定
  3) コンフリクト解決ポリシーの確認。
  コンフリクトが発生した場合の解決手順を提供します。"

- `/prcomment`: "現在のブランチのプルリクエストにレビューコメントを作成します。
  以下の手順で自動的に実行します:
  1) 現在のブランチ名を取得
  2) 関連するプルリクエストを特定
  3) ブランチの変更を分析:
     - 変更されたファイルのリスト
     - 各ファイルの変更（追加/削除/修正）
  4) 生成されたコメントをプルリクエストに投稿"

- `/checkout`: "ブランチの切り替えまたは作成: [BRANCH]。
  チェックアウト前のチェック:
  1) 現在の作業状態（コミットされていない変更）
  2) ブランチの存在確認
  3) リモートブランチの状態
  4) 新規作成の場合のベースブランチの選択。
  必要に応じてスタッシュの推奨事項と、チェックアウト後の手順を提供します。"

## ダイアグラム作成コマンド
- `/draw`: "以下の内容についてダイアグラムを作成してください: [CONTENT]。
  以下の要素を含めてください:
  1) 全体構造
  2) コンポーネント間の関係
  3) データフロー
  4) 主要インターフェース。
  ダイアグラムを簡潔で理解しやすく保ち、必要に応じて補足説明を追加してください。"

## ユーティリティコマンド
- `/mergerules`: "以下のタスクを実行してください:
  1) プロジェクト内のすべての`.cursor/rules/*.mdc`ファイルを検索
  2) 各ファイルの内容を収集
  3) 新しいファイル`.cursor/doc/masterrules.md`を作成（ディレクトリが存在しない場合は作成）
  4) すべてのルールのフロントマター（`---`で囲まれた部分）と内容を統合
  5) 統合されたファイルのパスと含まれるルールの数を報告" 

<a id="2-branchmdc"></a>
## 2. branch.mdc
元ファイル: `.cursor/rules/branch.mdc`

---
description: ブランチ管理ルール
globs: 
alwaysApply: false
---
---
description: ブランチ管理ルール
globs: ["**/.git/**"]
alwaysApply: true
---
# ブランチ管理
## ブランチタイプ
- main: "本番環境対応のコード"
- develop: "開発統合ブランチ"
- feature/*: "新機能開発ブランチ"
- bugfix/*: "バグ修正ブランチ"
- refactor/*: "リファクタリングブランチ"
- update/*: "機能更新ブランチ"
- docs/*: "ドキュメント更新ブランチ"

## ブランチ保護
```
プルリクエストと承認なしにMAIN/MASTERブランチにマージしないでください
```

<a id="3-gitmdc"></a>
## 3. git.mdc
元ファイル: `.cursor/rules/git.mdc`

---
description: "
globs: 
alwaysApply: false
---
---
description: Gitルールとコミットプレフィックス
globs: ["**/.git/**", "**/.gitignore"]
alwaysApply: true
---
# Gitルール
## コマンド
- Gitコマンドを実行する際は常に--no-pagerを追加する
- 指示があるまでリモートにプッシュしない

## コミットプレフィックス:
- feat: "新機能の追加"
- update: "機能の修正"
- fix: "バグ修正または誤字修正"
- docs: "ドキュメントの追加"
- style: "フォーマット変更、インポート順序の調整、またはコメントの追加"
- refactor: "機能に影響を与えないコードのリファクタリング"
- test: "テストの追加または修正"
- ci: "CI/CDに関連する変更"
- docker: "Dockerfileの修正またはコンテナ関連の変更"
- chore: "その他の変更"
- init: "プロジェクトの初期化とセットアップ"
- build: "ビルドシステムまたは外部依存関係の変更"
- perf: "パフォーマンス改善の変更"
- revert: "以前のコミットの取り消し"
- i18n: "国際化の変更"
- a11y: "アクセシビリティの変更"
- security: "セキュリティ関連の変更"

<a id="4-languagemdc"></a>
## 4. language.mdc
元ファイル: `.cursor/rules/language.mdc`

---
description: 
globs: 
alwaysApply: false
---
---
description: 言語設定
globs: ["**/"]
alwaysApply: true
---
# 言語設定
すべてのメッセージは日本語が必要です。

<a id="5-directorymdc"></a>
## 5. directory.mdc
元ファイル: `.cursor/rules/directory.mdc`

---
description: 
globs: 
alwaysApply: false
---
---
description: ディレクトリ構造ルール
globs: ["**/"]
alwaysApply: true
---
# ディレクトリ構造
TODO: 採用する技術とプロジェクト要件に基づいてディレクトリ構造をカスタマイズする

<a id="6-developmentmdc"></a>
## 6. development.mdc
元ファイル: `.cursor/rules/development.mdc`

---
description: 
globs: 
alwaysApply: false
---
---
description: 開発フローとプロセス
globs: ["**/"]
alwaysApply: true
---
# 開発フロー
## 機能開発ステップ
1. 新しいブランチを作成
2. 初期化コマンドを実行（例：bun init、uv init）
3. gitを初期化
4. 推奨されるディレクトリ構造を確認し、不足している場合は作成
5. 必要なライブラリをインストール
6. コマンドを使用して開発準備完了を確認
7. 機能/変更を実装
8. テストを実行
9. 失敗するテストを修正
10. テストがパスしたらコミット
11. CHANGELOG.mdに変更ログを記述
12. docs/**.mdに変更を記述

## バグ修正ステップ
1. 影響を受ける領域を慎重に調査
2. 新しいブランチを作成
3. 変更を実装
4. テストを実行
5. 失敗するテストを修正
6. テストがパスしたらコミット
7. CHANGELOG.mdに変更ログを記述
8. docs/**.mdに変更を記述