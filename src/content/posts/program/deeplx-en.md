---

title: Deploy deeplx on Vercel
published: 2025-05-26
tags:
  - 有趣的项目
  
lang: en
abbrlink: deploy-deeplx-on-vercel

---
#### Preface

Recently, I discovered a project that allows deploying deeplx on Vercel. After my testing, I found it to be very reliable. If you've had issues with previous deeplx deployments frequently throwing errors, you might want to give this a try.

[Original Project](https://github.com/un-ts/deeplx) — consider giving the author a star to show your appreciation.

Fork the author's repository and import it into Vercel to deploy.

#### Tips

1. If you're worried about your deployed URL being leaked, you can change the translation path.
   
   - In `api/translates.ts`, rename `translates.ts` to **a name you prefer**, and also update line 29 where it says `POST {"text": "have a try", "source_lang": "auto", "target_lang": "ZH"} to /translate`, replacing `translate` accordingly.
   
   - Then modify line 2 in `packages/@deeplx/core/src/api.ts`, and also line 3 in the `index.js` file in the same directory.
   
   - Also rename `translate.ts` in the same directory to `your_name.ts`.

2. After making the changes and deploying, you can use your desired path like: `xxx.vercel.app/your_path`.

#### 😉