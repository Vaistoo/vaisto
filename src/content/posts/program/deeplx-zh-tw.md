---

title: 在vercel上部署deeplx
published: 2025-05-26
tags:
  - 有趣的项目
  
lang: zh-tw

---

#### 前言

最近發現了一個專案，可以在 Vercel 上部署 deeplx，經過我的測試發現非常穩定，以前部署 deeplx 動不動報錯的人可以試試看。

[原專案](https://github.com/un-ts/deeplx)，可以給作者點個星，表達感謝。

Fork 作者的倉庫，然後匯入到 Vercel 即可部署。

#### 小技巧

1. 如果擔心自己部署的網址被外洩，可以修改一下翻譯的路徑。
   
   - 在 `api/translates.ts` 中，將 `translates.ts` 改成**你想要的名稱**，並修改第 29 行中 `POST {"text": "have a try", "source_lang": "auto", "target_lang": "ZH"} to /translate` 裡的 `translate` 為相同名稱。
   
   - 接著修改 `packages/@deeplx/core/src/api.ts` 的第 2 行，以及同一目錄下 `index.js` 的第 3 行。
   
   - 同樣目錄下的 `translate.ts` 也要改成 `你要的名字.ts`。

2. 修改後部署，你就可以使用你想要的路徑了，例如：`xxx.vercel.app/你的路徑`。

#### 😉
