### Requirements  
- Node.js (Should be at least Node.js 8.10, recommends 10.0 or higher)  
- Git
### 参考文档
- [butterfly文档](https://docs.jerryc.me/theme-page.html#page-front-matter)
- [hexo](https://hexo.io/docs/)
### Install node.js  
```bash
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```
### Install hexo
```bash
npm install -g hexo-cli
npm install
```

### 创建 layout

### 创建 page
default layout: `post`, `page` and `draft`

```bash
hexo new [layout] [page name]
```
### 写 page  
### Page Front-matter  
 
 
<pre><code>
---  
title:  
date:  
type: (tags,link,categories這三個頁面需要配置)  
comments: (是否需要顯示評論，默認true)  
description:  
top_img: (設置頂部圖)  
mathjax:  
katex:  
aside:  
---
</code></pre>  


### Post Front-matter  

<pre><code>
---  
title:  
date:  
tags:  
categories:  
keywords:  
description:  
top_img: (除非特定需要，可以不寫)  
comments  是否顯示評論(除非設置false,可以不寫)  
cover:  縮略圖  
toc:  是否顯示toc (除非特定文章設置，可以不寫)  
toc_number: 是否顯示toc數字 (除非特定文章設置，可以不寫)  
copyright: 是否顯示版權 (除非特定文章設置，可以不寫)  
mathjax:  
katex:  
hide:  
---  
```

### Drafts
You can use the publish command to move drafts to the source/_posts folder. 

```
hexo publish [layout] title
```
Block Quote   
Code Block
...  
[tag plug](https://hexo.io/docs/tag-plugins)

### 音乐
QQ音乐
### 电影
豆瓣电影




