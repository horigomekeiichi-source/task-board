# Task Board Project

## 概要

タスク管理ボードアプリケーション。

## 技術スタック

- フレームワーク: React 18
- 言語: JavaScript (JSX)
- ビルドツール: Vite 5
- スタイリング: CSS Modules (`*.module.css`)
- 状態管理: React 組み込み (`useState` / `useEffect`)
- 永続化: `localStorage`
- パッケージマネージャー: npm

## 開発コマンド

```bash
# 依存関係インストール
npm install

# 開発サーバー起動
npm run dev

# ビルド
npm run build

# テスト実行
npm test
```

## Git 運用ルール

**コードを変更するたびに GitHub へプッシュすること。**

### 手順

1. 変更をステージング
   ```bash
   git add <変更ファイル>
   ```

2. コミット（変更内容を簡潔に記述）
   ```bash
   git commit -m "feat: 機能の説明"
   ```

3. GitHub へプッシュ
   ```bash
   git push origin main
   ```

### コミットメッセージ規約

| プレフィックス | 用途 |
|---|---|
| `feat:` | 新機能追加 |
| `fix:` | バグ修正 |
| `refactor:` | リファクタリング |
| `style:` | フォーマット変更（動作に影響なし） |
| `docs:` | ドキュメント更新 |
| `test:` | テスト追加・修正 |
| `chore:` | ビルド設定・依存関係の更新 |

### ブランチ戦略

- `main`: 本番リリース用の安定ブランチ
- `feature/<機能名>`: 新機能開発用
- `fix/<バグ名>`: バグ修正用

新機能・修正は `feature/` または `fix/` ブランチで作業し、PR を通じて `main` へマージする。

## デプロイ先

https://horigomekeiichi-source.github.io/task-board/

`main` ブランチへのプッシュで GitHub Actions が自動ビルド・デプロイを実行する。

## 命名規約

### コンポーネント

| 対象 | 規約 | 例 |
|---|---|---|
| コンポーネント関数 | PascalCase | `TaskItem`, `AddTaskForm` |
| コンポーネントファイル | PascalCase + `.jsx` | `TaskItem.jsx` |
| CSS Modules ファイル | コンポーネント名と同名 + `.module.css` | `TaskItem.module.css` |
| CSS クラス名 | camelCase | `.taskText`, `.deleteBtn` |
| Props / 変数 | camelCase | `isCompleted`, `onDelete` |
| イベントハンドラ | `handle` プレフィックス | `handleKeyDown`, `handleSubmit` |
| コールバック Props | `on` プレフィックス | `onAdd`, `onToggle`, `onDelete` |

### ファイル構成

新しいコンポーネントは `src/components/` 以下に配置する。

```
src/
  components/
    TaskItem.jsx
    TaskItem.module.css
  App.jsx
  App.module.css
  main.jsx
  index.css
```

## コーディング規約

- コメントは原則不要。変数名・関数名で意図を明示する
- セキュリティ: ユーザー入力は必ずバリデーションを行う
