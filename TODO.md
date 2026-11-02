# TODO

最終更新: 2026-11-02

## 要判断・要作業(担当: 未着手)

0. **仮URLでの表示崩れ(2026-11-02 確認)**: Pages の仮URL `https://ken-okabe.github.io/asahi-hp/` では、サイト内リンクと画像が `/` 始まりの絶対パスのため、`ken-okabe.github.io/` 直下を指して404になる(ページ本体は200で表示されるが、画像とメニュー遷移が壊れる)。独自ドメイン(ルート配信)では問題ない。対策案: (A) ビルド時にベースパス `/asahi-hp` を付与する(仮URL確認用。ドメイン接続時に外す)、(B) 仮URLでの確認は諦め、ローカルの `npm run dev`/`preview` で確認し、ドメイン接続後に本番確認する。

1. **Googleフォームの作成**: 「お問合せ」「お見積り」の2種類。作成後、埋め込みURLを `src/components/ContactForm.astro` の `formUrl` に設定する(現在は電話案内を表示)。お見積り用ページ(`estimate.html` は元サイトで404のため、新規作成するか要判断)。
2. **ヘッダー画像の差し替え**: `public/images/header.png.webp` は旧サービスのテンプレート由来(木目調の背景)。自前のロゴ・ヘッダーに差し替える。
3. **画像の権利確認**: 本文画像(`public/images/`)が自社撮影か、ストック素材かを確認する。
4. **未決定事項**:
   - Google Analytics (`G-GW41Y7S1DE`) を継続するか(現在は未導入)
   - トップの「お盆休み」告知(`src/data/site.json` の `notice`)を残すか
   - 外部リンク(lotas.co.jp、carbell.jp 等)の維持
   - `CNAME` を `www.lotas-asahi.com` と apex のどちらにするか(元サイトの正規URLは `www` 付き)

## 完了した作業の記録

- 元サイトのバックアップ(`backup/`)、本文抽出、Astro土台、GitHub Actions ワークフロー: `extraction-report.md` 参照
- GitHub Pages の有効化(Source: GitHub Actions): ユーザー実施済み
