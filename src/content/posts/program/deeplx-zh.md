---

title: 在vercel上部署deeplx
published: 2025-05-26
tags:
  - 有趣的项目
  
lang: zh

---

#### 前言

最近发现了一个项目，可以在vercel上部署deeplx，经过我的测试发现，很抗用，之前部署deeplx动不动报错的可以试试看。

[原项目](https://github.com/un-ts/deeplx)，可以给作者点个星，以示感谢哦。

fork作者的仓库，然后导入vercel部署即可。

#### 小技巧

1. 如果担心自己部署的网址被泄露可以改变一下翻译路径。        
   
   - api/translates.ts    中的``translates.ts``改为**你想要的名字**，并将其中的29行处即``POST {"text": "have a try", "source_lang": "auto", "target_lang": "ZH"} to /translate``中的``translate``做同样修改。
   
   - 继续修改 ```packages/@deeplx/core/src/api.ts```中的第2行处，以及同目录下的index.js的文件中的第三行处
   
   - 还有同目录的```translate.ts```改为```你要的名字.ts```     

2. 修改完后去部署，你就可以使用你想要的路径了，xxx.vercel.app/你的路径。

#### 😉
