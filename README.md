# 提供Bladeテンプレート — BookShelf（書籍レビューアプリ）

## このリポジトリについて

本リポジトリは、模擬案件「BookShelf（書籍レビューアプリ）」で使用する **提供済みBladeテンプレートおよびフロントエンドリソース（CSS / JS）** を配布するためのリポジトリです。

受講生は、本リポジトリの `resources/` ディレクトリを自分のLaravelプロジェクトに移入して使用します。

> **注意:** このリポジトリ単体ではアプリケーションとして動作しません。受講生が作成するLaravelプロジェクトに `resources/` を移入して初めて機能します。

## ブランチ構成

| ブランチ | 用途 | 移入タイミング |
|---|---|---|
| `basic` | 基本機能用テンプレート | 基本機能の実装開始時 |
| `advanced` | 応用機能用テンプレート | 基本機能完了後、応用機能の着手時 |

### basic → advanced での主な変更点

- **追加**: `resources/views/reports/index.blade.php`（マイ読書レポート画面）
- **追加**: `resources/views/notifications/index.blade.php`（通知一覧画面）
- **追加**: `resources/views/reading-plans/`（読書計画の一覧・作成・編集画面）
- **変更**: `resources/views/books/index.blade.php`（キーワード検索・ジャンルフィルタ・ソート追加）
- **変更**: `resources/views/books/create.blade.php`（ISBN検索フォーム追加）

## 使い方

### Step 1: 基本機能の実装開始時（basic ブランチ）

#### 1. リポジトリをクローン

ターミナルで、自分のLaravelプロジェクトとは **別の場所** に以下を実行します。

```bash
git clone -b basic https://github.com/coachtech-prepared-file/Preparedblade-mockcase-BookShelf.git
```

#### 2. Finder（またはエクスプローラー）でフォルダを開く

```bash
open Preparedblade-mockcase-BookShelf   # macOS の場合
```

Windows の場合はエクスプローラーでクローン先のフォルダを開いてください。

#### 3. resources/ を自分のプロジェクトに移入

クローンしたフォルダ内の `resources/` を、自分のLaravelプロジェクトの `resources/` に **上書き** でコピー（またはドラッグ＆ドロップ）してください。

#### 4. クローンしたフォルダの削除

移入が完了したら、クローンした `Preparedblade-mockcase-BookShelf` フォルダは不要です。
Finder（またはエクスプローラー）上でゴミ箱に移動してください。

### Step 2: 応用機能の着手時（advanced ブランチ）

基本機能の実装が完了し応用機能に着手する際に、**advanced ブランチ** から `resources/` を再取得します。

手順は Step 1 と同様ですが、クローン時のブランチを `advanced` に変更してください。

```bash
git clone -b advanced https://github.com/coachtech-prepared-file/Preparedblade-mockcase-BookShelf.git
```

以降は Step 1 の手順 2〜4 と同じです。`resources/` を上書きで移入してください。

---

<details>
<summary>補足: コマンドのみで移入する方法</summary>

GUI を使わず、コマンドだけで移入することもできます。

```bash
# 自分のプロジェクトの親ディレクトリで実行（basic の場合）
git clone -b basic https://github.com/coachtech-prepared-file/Preparedblade-mockcase-BookShelf.git temp-blade

# resources/ を自分のプロジェクトに上書きコピー
cp -r temp-blade/resources/ your-project/resources/

# 不要になったクローンを削除
rm -rf temp-blade
```

> **【重要】`rm -rf` の取り扱いについて**
>
> `rm -rf` は、指定したディレクトリを **確認なしで完全に削除** するコマンドです。
> **誤ったパスを指定すると、自分のプロジェクトや重要なファイルが取り返しのつかない形で削除されます。**
>
> - 実行前に、削除対象のパス（上記例では `temp-blade`）が正しいことを **必ず** 確認してください
> - パスに自信がない場合は、上記 GUI での削除（ゴミ箱に移動）を強く推奨します

</details>

## 含まれるファイル一覧

```
resources/
├── css/
│   └── app.css
├── js/
│   └── app.js
└── views/
    ├── auth/
    │   ├── login.blade.php
    │   └── register.blade.php
    ├── books/
    │   ├── _form.blade.php
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   ├── index.blade.php
    │   └── show.blade.php
    ├── components/
    │   ├── app-layout.blade.php
    │   ├── application-logo.blade.php
    │   ├── auth-session-status.blade.php
    │   ├── danger-button.blade.php
    │   ├── dropdown-link.blade.php
    │   ├── dropdown.blade.php
    │   ├── guest-layout.blade.php
    │   ├── input-error.blade.php
    │   ├── input-label.blade.php
    │   ├── modal.blade.php
    │   ├── nav-link.blade.php
    │   ├── primary-button.blade.php
    │   ├── responsive-nav-link.blade.php
    │   ├── secondary-button.blade.php
    │   └── text-input.blade.php
    ├── favorites/
    │   └── index.blade.php
    ├── genres/
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   ├── index.blade.php
    │   └── show.blade.php
    ├── layouts/
    │   └── navigation.blade.php
    ├── notifications/            ← advanced ブランチのみ
    │   └── index.blade.php
    ├── ranking/
    │   └── index.blade.php
    ├── reading-plans/            ← advanced ブランチのみ
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   └── index.blade.php
    ├── reports/                  ← advanced ブランチのみ
    │   └── index.blade.php
    ├── reviews/
    │   └── edit.blade.php
    └── welcome.blade.php
```

## 注意事項

- このリポジトリ単体では動作しません。受講生が作成するLaravelプロジェクトに `resources/` を移入して使用してください。
- フロントエンドの環境構築（Vite, Tailwind CSS, Alpine.js 等）は、要件シートの「環境構築手順」シートを参照してください。
