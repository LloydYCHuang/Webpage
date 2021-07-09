---
layout: post
title:  "Github起步"
categories: Github
permalink: Webpages/posts/starting/  
---

## 從零開始真的不簡單!
2021/07/09  
我今天透過 GitHub Pages 建立了個人部落格，而部落格是透過 jekyll 生成的，這是我第一篇部落格文章。  
就來講講這個網頁是如何建立的吧  
首先，你要有個Github帳號 (廢話)  
在Github裡面建立一個repository，例如我的命名為Webpage，在裡面點擊Settings > Pages，然後選擇Change theme，這樣Github應該會主動幫你建立一個branch稱作gh-pages，在同一個頁面還會跳出一個網址，應該是https://你的帳號.github.io/你的repo名字/ ，例如我的就是https://lloydychuang.github.io/Webpage/ 。  
一開始你在repo裡面只會看到兩個檔案，分別為_config.yml以及index.md，沒關係，一切都從這兩個檔案開始。  

### _config.yml  
 
這是有關你的網頁style，因為我現在還不會自己寫style，所以我使用Github提供的Jekyll模板cayman，一開始看到裡面只有短短的一行字  
`theme: jekyll-theme-cayman`
這時候就發現網頁什麼都沒有，所以我們要幫他加上標題及敘述，變成這樣
`title: "土壤、統計以及一點沉思" 
description: "Soils, statistics, and meditation" `
另外，Jekyll模板預設你的貼文必須放在這個repo底下的_posts資料夾，所以我們需要多指定他能搜尋到的資料夾 (之類的意思?我也不是很懂)，總之最後我的_config.yml檔案長這樣
`theme: jekyll-theme-cayman  
title: "土壤、統計以及一點沉思"  # 網站的名稱  
description: "Soils, statistics, and meditation"
include:
  - _pages`
