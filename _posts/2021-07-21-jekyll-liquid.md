---
layout: default
categories: Github
title:  "Jekyll Liquid語法應用"
---
## Jekyll Liquid語法應用  
2021/07/21  
今天要來自學的是使用在Jekyll網站架構中常用的Liquid語法，這個語法其實在前面已經使用過了，但當時沒有去細究使用方法，只是將別人的code複製貼上，今天就來整理一些常用的功能，但應該不會整理的非常詳細，因為我在學完之後發現若只是要經營一個小網誌，真的不需要學到太多，甚至有程式基礎的人在要用的時候去查就好了。  
Liquid可以告訴Jekyll如何輸出你的網頁，使用Jekyll製作網頁的時候，網頁的內容是寫成markdown語法的，Jekyll會自動將我們放在`_posts`資料夾內的markdown檔案轉換成html檔，使用Liquid可以告訴Jekyll在輸出時遵照特定的函數行為，例如在網頁中使用for loop而不用重複輸入一樣的句子。  
這次的自學參考網站包含<a href="https://shopify.github.io/liquid/" target="_blank">Liquid官網</a>以及<a href="https://jekyllrb.com/docs/liquid/" target="_blank">Jekyll官網</a>以及之前在學習category時參照的<a href="https://blog.webjeda.com/jekyll-categories/" target="_blank">這個網站</a>。  
{% raw %}
### 基本架構  
在markdown檔案裡輸入的Liquid語法包含三個架構，分別為
- Objects：即變數本身，在markdown裡輸入時要用兩個大括弧包起來，如`{{ variable }}`。
- Tags：邏輯運算，就是寫程式常見的if、else等判定，也可以assign變數，使用時要用`{% Tags %}`包起來，本文所講到的Tags都要在外面包裹`{% Tags %}`才會被辨識，例如使用`break`的時候要打`{% break %}`，以下也會示範。
- Filters：可以改變object的輸出 (例如改格式之類的)，使用時在objects裡面添加`|`。
  
抓準這三個原則，就可以自己撰寫Liquid程式碼，沒有被Liquid規則包起來的部分，就會是以文字方式呈現在你的文章中，Liquid的運算符號在一般使用上，大於、等於、and、or這些都跟一般語言沒差異。例如if/else判斷式如下  
```
{% assign person = "Lloyd" %}     # 宣告person是Lloyd
{% if person == "Lloyd" %}        # 判斷person這個變數是否為Lloyd
  Hi Lloyd!                       # 如果是，則輸出Hi Lloyd!
{% else %}                        
  Hey who are you?                # 如果不是，則輸出Hey who are you?
{% endif %}                       # 記得結束if
```
常用的for loop當然也不能缺席  
```
{% for category in site.categories %}   # 對網頁中的每個categories都執行一次
  {{ category_name }}                   # 將categories輸出成文字
{% endfor %}
```
在loop裡面也可以添加`{% break %}`等判斷式，讓你的code更加豐富。  
另外`contains`是用來測試裡面是否包含某段數字，例如輸入
```  
{% assign A = "Six pack" %}
{% if A contains "pack" %}              #判斷是否包含pack這個字，有的話便執行輸出下面這句話
  A裡面包含pack
{% endif %}
```
使用`capture`則可以指定其包裹的物件儲存到變數裡，有點複雜，示範是這樣：
```
{% capture name %}I am name{% endcapture %}
```
這段程式碼代表"I am name"這段文字現在成為變數`name`的內容，如果我們想要讀取這段文字就使用`{{ name }}`便可以了。  
使用Liquid語言時會在轉換後的網頁留下空行，如果不想要空行的話可以更改一下你的輸入
```
{% assign username = "Lloyd" %}         #有空行
{%- assign username = "Lloyd" -%}       #沒有空行
```  
最後還有一個最重要的功能，那就是要像這篇文章一樣呈現Liquid程式碼但卻不想執行怎麼辦？  
可以透過特殊的Tags來達成，那就是`raw...endraw`，在不想執行的開頭使用Tag `raw`，在結尾使用`endraw`，其中被包裹起來的程式碼就不會執行 (不要忘記包裹Tags的格式)。  
其餘的功能我應該會在需要用到的時候到<a href="https://shopify.github.io/liquid/" target="_blank">Liquid官網</a>找就行了，聽起來很複雜的filter也在Jekyll官網有<a href="https://jekyllrb.com/docs/liquid/filters/" target="_blank">常用列表</a>。    
  
### Jekyll變數  
在Jekyll裡面有些已經被定義的變數，可以拿來使用在Liquid，這對我們來說非常方便，例如
- `site.categories`：整個網站的category列表
- `category`：在site.categories裡的每個單元
- `site.categories.某個類別名稱`：代表某個特定的category
- `post`：網誌，若是`post in site.categories.某個類別名稱`就代表該category裡所有的post  
  
Jekyll官網也有<a href="https://jekyllrb.com/docs/variables/#page-variables" target="_blank">變數列表</a>可以參考。  

### 網誌專用  
寫到這裡，Liquid真的具有相當多功能，但對於我這種只要寫網誌的人來說似乎用不太到太過複雜的判定式，所以我將寫網誌可能會用到的列在這裡  
  
**提供連結**  
有時要連結到我們特定的網誌，但不想費心去抓連結的話，只要這樣
```
{% link _posts/2016-07-26-name-of-post.md %}
```
將檔案的名稱貼上 (但要注意其母資料夾) 就可以取得你想要的連結。  
  
**建立文章列表**  
我想是最常用到的，我前面已經建立過一些文章清單了，因此在這裡就來示範建立個別頁面展示我的Soil類別文章列表，這是基礎Liquid，可以再按照自己網頁喜好去排版  
```
{% for post in site.categories.Soil %}            # 在Soil這個類別底下的所有文章
   <a href="{{ post.url }}">{{ post.title }}</a>  # 建立超連結至他們的網頁，並顯示其名稱
{% endfor %}                                      # 記得結束for loop
```
最後分享Liquid的<a href="https://www.shopify.com/partners/shopify-cheat-sheet" target="_blank">Cheat sheet</a>，以上是這次自學的內容。
{% endraw %}
