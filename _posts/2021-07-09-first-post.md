---
layout: post
title:  "Github起步"
categories: Github  
permalink: /start/
---

## 從零開始真的不簡單!
2021/07/09  
我今天透過 GitHub Pages 建立了個人部落格，而部落格是透過 jekyll 生成的，這是我第一篇部落格文章。  
就來講講這個網頁是如何建立的吧  
首先，你要有個Github帳號 (廢話)  
在Github裡面建立一個repository，例如我的命名為Webpage，在裡面點擊Settings > Pages，然後選擇Change theme，這樣Github應該會主動幫你建立一個branch稱作gh-pages，在同一個頁面還會跳出一個網址，應該是`https://你的帳號.github.io/你的repo名字/` ，例如我的就是`https://lloydychuang.github.io/Webpage/` 。  
一開始你在repo裡面只會看到兩個檔案，分別為_config.yml以及index.md，沒關係，一切都從這兩個檔案開始。  

### _config.yml  
 
這是有關你的網頁style，因為我現在還不會自己寫style，所以我使用Github提供的Jekyll模板cayman，一開始看到裡面只有短短的一行字<br/>
`theme: jekyll-theme-cayman`  
這時候就發現網頁什麼都沒有，所以我們要幫他加上標題及敘述，變成這樣  
```
theme: jekyll-theme-cayman
title: "土壤、統計以及一點沉思"  
description: "Soils, statistics, and meditation" 
```
另外，Jekyll模板預設你的貼文必須放在這個repo底下的_posts資料夾，所以我們需要多指定他能搜尋到的資料夾 (之類的意思?我也不是很懂)，總之最後我的_config.yml檔案長這樣
```
theme: jekyll-theme-cayman  
title: "土壤、統計以及一點沉思"  
description: "Soils, statistics, and meditation"
include:
  - _pages
```

### index.md
這應該是最簡單的部分了  
index.md會成為你的主頁，別人進入你的網頁看到的第一頁，只要輸入你想要的東西就好，當作自己的首頁，但其實我還不太熟悉這種操作方式。  
簡而言之，Jekyll可以把我們用markdown所編寫的內容都轉換成html並且發布在Github上面，因此對於我這種不太懂的人是很適合的入門方式，[這個部落格](https://ktinglee.github.io/)教會我很多事情，而且可以直接看他的Github學習。  
另外，我嘗試在我的首頁加上我的文章列表，這是複製了[Jekyll官網的文章](https://jekyllrb.com/docs/posts/)，可以直接複製code貼在index裡面，就可以產出一個文章列表。   
```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```

### 還有最重要的文章呢?
要發布文章，首先要在repo底下建立一個資料夾`_posts`，一個字都不能改，建立資料夾的方式就是在建立新檔案時在輸入`_post/檔案名稱`即可創立新資料夾，而檔案名稱也不能亂取，要叫做`yyyy-mm-dd-名稱.md`，前面要輸入年月日共8碼，例如我這篇文章就命名叫`2021-07-09-first-post.md`。  
檔案建立好後，要在檔案的開頭加上一段YAML程式碼 (對，我也還不知道這是什麼)
```
---
layout: post
title:  "標題"
categories: 自己訂類別
permalink: /start/  #文章會掛在https://lloydychuang.github.io/Webpage/posts/starting/這個地方的意思
---
```
然後就可以在這個檔案裡面自由編寫你要的內容，成功發布第一篇文章吧!

<a href="https://lloydychuang.github.io/Webpage/">Back</a>


