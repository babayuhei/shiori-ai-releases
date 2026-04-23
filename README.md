# Shiori AI Desktop — Releases

Shiori AI Desktop の**署名済みビルド配布**リポジトリです。

- 🏠 本家サイト: **[https://shiori-ai.com](https://shiori-ai.com)**
- 🔒 ソースコード: プライベートリポジトリ（[babayuhei/shiori-ai](https://github.com/babayuhei/shiori-ai)）
- 📦 配布物: このリポジトリの [Releases](https://github.com/babayuhei/shiori-ai-releases/releases) タブ

ソースは非公開、ビルド済みバイナリだけここに置いています。
アップロードは GitHub Actions が自動で実施しており、手動編集はしません。

---

## Shiori AI Desktop とは？

スマホやブラウザで動く [Shiori AI](https://shiori-ai.com) のデスクトップ相棒。
Mac を立ち上げておけば：

- **Claude Pro / Max サブスクのクォータで推論を動かす**（Anthropic API 課金ゼロ）
- **他のデバイス（スマホ・Web）からの依頼もこの Mac 経由で返す**（Desktop Bridge）
- **ノート・ミーティング録音のローカル同期**
- **アプリ自体の自動アップデート**（この Releases から裏で取得）

## 動作要件

- macOS 10.15 以降（Universal binary で Intel Mac / Apple Silicon 両対応）
- Claude Pro 以上のサブスクリプション（Claude Code CLI の認証に必要）

Windows 版は将来対応予定です。

---

## 💻 インストール手順（初回）

1. [**最新版の `Shiori_X.Y.Z_universal.dmg`**](https://github.com/babayuhei/shiori-ai-releases/releases/latest) を Safari / Chrome でダウンロード
2. `.dmg` をダブルクリックして開く
3. 表示されたウィンドウの `Shiori` アイコンを `Applications` フォルダにドラッグ
4. Finder で `アプリケーション / Shiori` を探す
5. **右クリック（Control + クリック） → 「開く」**
6. 「開発元を検証できません」という警告が出るので、もう一度 **「開く」** を押す
   - 署名無しビルドのため macOS が警告を出します。以降は普通にダブルクリックで起動できます
7. 起動後、[shiori-ai.com](https://shiori-ai.com) と同じ Google アカウントでログイン

### Gatekeeper 警告の対応（macOS Ventura 13 以降の方）

手順 5 の右クリック方法が使いづらい場合は：

- **システム設定 → プライバシーとセキュリティ** を開く
- 「"Shiori" はブロックされました」の下にある **「このまま開く」** ボタンを押す

## 🔄 アップデート（2回目以降）

起動後 8 秒で自動的にこの Releases を確認して、新しいバージョンがあれば
**裏でダウンロード**し、次回起動時に適用されます。
macOS の通知で準備完了を知らせます（通知の許可が必要）。

アプリ内の **設定 → バージョン情報** から：
- 現在のバージョン確認
- 「今すぐ確認」ボタンによる手動チェック

が可能です。

## 🔐 セキュリティについて

- すべての更新バイナリは **Tauri の公開鍵署名** で検証されています
- 悪意ある第三者が偽バイナリを混入しても、アプリ側で署名を検証して拒否します
- 公開鍵はアプリ内に埋め込み、秘密鍵は開発者のみが保持

## トラブルシューティング

| 症状 | 対処 |
|---|---|
| 起動時に「開発元を検証できません」エラー | 手順 5-6（右クリック → 開く）をやり直す |
| Bridge が「接続していません」のまま | 一度アプリを Cmd+Q で終了して起動し直す |
| 自動更新が反映されない | 設定 → バージョン情報で「今すぐ確認」を押す。DL 後は Cmd+Q → 起動で反映 |
| Claude CLI が見つからない | アプリ内の設定 → Claude Code セクションからインストール |

## ライセンス

Shiori AI Desktop はオープンソースではなく、配布バイナリのみ公開しています。
現時点では招待制のβ版として、限定ユーザーに配布しています。
一般公開のタイミングは、[shiori-ai.com](https://shiori-ai.com) でお知らせします。
