# TODO

最終更新: 2026-11-02

## 要判断・要作業(担当: 未着手)

0. **【ドメイン接続時に必須】仮URL用ベースパス処理の撤去**: 仮URL(`https://ken-okabe.github.io/asahi-hp/`)で表示するため、`.github/workflows/deploy.yml` の「`node tools/prefix-base.mjs`(`BASE_PATH: /asahi-hp`)」ステップが、ビルド後にリンク・画像へ `/asahi-hp` を付けている。独自ドメイン(ルート配信)では**このステップを削除する**(残すとリンクが壊れる)。あわせて `CNAME` を追加する。なお `tools/prefix-base.mjs` 自体は無害なので残してよい。

1. **Googleフォームの作成**: 「お問合せ」「お見積り」の2種類。作成後、埋め込みURLを `src/components/ContactForm.astro` の `formUrl` に設定する(現在は電話案内を表示)。お見積り用ページ(`estimate.html` は元サイトで404のため、新規作成するか要判断)。
2. **ヘッダー画像の差し替え**: `public/images/header.png.webp` は旧サービスのテンプレート由来(木目調の背景)。自前のロゴ・ヘッダーに差し替える。
3. **画像の権利確認**: 本文画像(`public/images/`)が自社撮影か、ストック素材かを確認する。
4. **未決定事項**:
   - Google Analytics (`G-GW41Y7S1DE`) を継続するか(現在は未導入)
   - トップの「お盆休み」告知(`src/data/site.json` の `notice`)を残すか
   - 外部リンク(lotas.co.jp、carbell.jp 等)の維持
   - `CNAME` を `www.lotas-asahi.com` と apex のどちらにするか(元サイトの正規URLは `www` 付き)

## 完了した作業の記録

- 仮URL対応(案A)。ビルド後に `tools/prefix-base.mjs` で `/` 始まりのリンク・画像へ `BASE_PATH` を付与。ローカルで `/asahi-hp/` 配下に配置し、67ページ・内部リンク4,288件が全て到達できることを確認(2026-11-02)。

- 元サイトのバックアップ(`backup/`)、本文抽出、Astro土台、GitHub Actions ワークフロー: `extraction-report.md` 参照
- GitHub Pages の有効化(Source: GitHub Actions): ユーザー実施済み
