# LLM伴走プロジェクト テンプレート

LLM（特に Claude Code）と協働してプロジェクトを進めるための、汎用スターターテンプレート。

正本ドキュメント（PROJECT.md）／変更管理ルール／LLM役割分担／成功指標・撤退条件、といった「LLM協働プロジェクトの骨格」だけを最小構成で用意してあります。

---

## 使い方

1. このリポジトリをクローン（またはテンプレートとして新規リポジトリを作成）
2. Claude Code を起動し、こう投げる:

   ```
   このテンプレを最適化して
   ```

3. Claude Code が対話的にヒアリングを行い、`PROJECT.md` をあなたのプロジェクトに合わせて埋めます
4. 不要なファイルの削除提案・初回コミットまで自動で進みます

ヒアリング項目の詳細は [`doc/init-questionnaire.md`](doc/init-questionnaire.md) を参照。

---

## ファイル構成

```
llm-project-template/
├── PROJECT.md                  # プロジェクト正本（初期化で埋まる）
├── CLAUDE.md                   # Claude Code 用指示書
├── doc/
│   ├── init-questionnaire.md   # 初期化ヒアリング手順（初期化後は削除）
│   ├── change-classes.md       # 変更管理4クラスの詳細
│   ├── evaluation-template.md  # 監査役LLM向け評価テンプレート
│   ├── project-context.md      # 監査役LLM向けコンテキスト
│   └── retreat-conditions.md   # 撤退条件・成功指標
├── logs/                       # 記録・ログ用
├── .env.example                # 環境変数サンプル
├── .gitignore
└── README.md
```

---

## 設計思想

- **正本は1つ（PROJECT.md）。** プロジェクトの全情報をここに集約
- **LLM役割分担。** オーナー（実装責任）／スカウト（情報収集）／監査役（評価）の3役で分業
- **変更管理は4クラス。** 軽い変更は速く、重い変更は慎重に
- **撤退条件は先に決める。** 感情ではなく数字で判断
