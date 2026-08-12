# IP Switcher — 更新確認用マニフェスト

IP Switcher (Windows 常駐型 IP 切替ツール) が「新しいバージョンが出ているか」を確認するためだけのリポジトリです。

**このリポジトリに含まれるもの: `version.json` のみ。**
ソースコード・インストーラ・バイナリは一切含まれません (それらは非公開リポジトリと社内共有で管理しています)。

## version.json

アプリはこの URL を HTTPS GET し、自身のバージョンと比較します。

```
https://raw.githubusercontent.com/isao3a/ipswitcher-updates/main/version.json
```

| フィールド | 意味 |
|---|---|
| `schemaVersion` | マニフェスト形式のバージョン (現在 1) |
| `version` | 最新リリースのバージョン (`x.y.z.w`) |
| `releasedAt` | リリース日 (`YYYY-MM-DD`) |
| `notes` | 変更点の短い説明 (アプリの通知に表示) |
| `downloadPage` | 入手先ページの URL。空の場合はアプリ側の設定値を使用 |

アプリはこの内容を信用しない前提で扱います (バージョン文字列の厳密パース・文言の長さ制限・URL のホスト検証)。
