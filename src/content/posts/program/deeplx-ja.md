---

title: Vercel に deeplx をデプロイする
published: 2025-05-26
tags:
  - 有趣的项目
  
lang: ja
abbrlink: deploy-deeplx-on-vercel
---
#### 前書

最近、Vercel上にdeeplxをデプロイできるプロジェクトを見つけました。実際にテストしてみたところ、とても安定して使えることがわかりました。以前のdeeplxデプロイがすぐにエラーを出してしまっていた人は、ぜひ試してみてください。

[元のプロジェクト](https://github.com/un-ts/deeplx) — 作者に感謝の気持ちとしてスターをつけるのもいいかもしれません。

作者のリポジトリをフォークして、Vercelにインポートすればすぐにデプロイできます。

#### 小技

1. デプロイしたURLの漏洩が心配な場合は、翻訳パスを変更することができます。
   
   - `api/translates.ts` の `translates.ts` を**好きな名前**に変更し、29行目の `POST {"text": "have a try", "source_lang": "auto", "target_lang": "ZH"} to /translate` の `translate` も同様に変更します。
   
   - 次に、`packages/@deeplx/core/src/api.ts` の2行目と、同じディレクトリにある `index.js` の3行目も修正してください。
   
   - 同じディレクトリ内の `translate.ts` も `your_name.ts` に変更します。

2. 修正後にデプロイすれば、`xxx.vercel.app/your_path` のように任意のパスで利用できます。

#### 😉