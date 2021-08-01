---
layout: default
categories: [Soil]
title:  "Quantifying soil morphology - 量化土壤剖面描述"
---  
## Quantifying soil morphology - 量化土壤剖面描述  
2021/08/01   
在剖面描述時，我們會記錄有關一個剖面裡各個化育層的特徵，包含顏色、構造、質地 (現場感覺)、結持度等，尤其在我研究的淋澱土 (Spodosol) 中顏色是一個重要的判別基準，但是剖面的描述大多都不是連續性 (continuous) 的，為了將土壤的顏色量化 (quantify) 成可以用統計處理的形式，我踏上了尋找剖面描述量化基準的路。  
  
### 概念  
Harden (1982) 的概念是建立一個可以描述土壤化育的指數 (a soil development index)，藉此比較土壤的化育程度。這個指數應能將現地描述的剖面資料轉換成一個或多個相應的量化指標。其主要的步驟如下：  
1. 給予每種描述分數，在描述**等級間的差異**給予分數 (後述)。
2. 把化育層的分數標準化 (normalization) 為範圍在0-1的指標。
3. 將化育層中的描述分數平均，每個化育層得到一個**化育層指數 (horizon index)**。
4. 將化育層指數乘以該化育層厚度，加權獲得該剖面的**剖面化育指數 (profile development index, PDI)**。
5. 最後將剖面化育指數除以剖面厚度可獲得加權平均的剖面化育指數 (weighted mean profile development index)。  
  
剖面化育指數有助於量化在現地觀察到的形態特徵並且可以比較不同剖面的化育程度，在Harden (1982) 所提出的PDI中包含了八種現地形態描述的項目：紅化 (rubification，包含顏色的hue與chroma)、質地 (total texture)、黏粒膜 (clay film)、構造 (structure)、乾結持度 (dry consistence)、濕結持度 (moist consistence)、黑化 (melanization，顏色的value) 及pH值。  
藉由研究一時間序列 (chronosequence) 土壤的形態特徵，Harden (1982) 所提出的PDI已被廣泛接受。  
  
### 給分  
給分的基準是該土壤**母質的性質**，因此母質的描述至關重要，描述完母質之後再針對不同性質的等級差異，然而此指標只用來描述**風化**，所以分數的加分是單向性的，以質地為例，隨時間進行質地會風化的更為細緻，因此只對比母質更細的化育層進行加分，但若質地變得更粗，則不進行扣分 (雖然是代表了其他成土因子或過程)。  
將性質量化後的數值稱作量化性質 (quantified property, X<sub>p</sub>)，例如量化後的質地指數稱為X<sub>t</sub> (t代表texture)，量化後的紅化指數稱為X<sub>r</sub> (r代表rubification)。以下列出級分的標準，另外原版的論文真的很不清楚，可以參考黃文樹 (2003) 整理的較易看懂  
- 紅化 X<sub>r</sub> (rubification)：每比母質增加一級的hue或chrome，就增加10分。</br>hue是遵照色帖的順序 5Y&#8594;2.5Y&#8594;10YR&#8594;7.5YR&#8594;5YR&#8594;2.5YR&#8594;10R&#8594;5R。
- 質地 X<sub>t</sub> (total texture)：根據三角圖的黏粒等級越黏一級就增加10分；黏性 (stickness) 與塑性 (plasticity) 每增加一級就增加10分。  
- 黏粒膜 X<sub>f</sub> (clay films)：根據黏粒的豐富度 (abundance)、厚度 (thickness)、位置 (location) 進行分級 (針對有黏粒膜的土壤，就不特別列出)。
- 構造 X<sub>s</sub> (structure)：根據構造等級給分，weak/moderate/strong分別為10/20/30分。</br>形狀方面platy為5分，granular, subangular blocky, angular blocky皆為10分，prismatic為20分，columnar為30分。
- 乾結持度 X<sub>d</sub> (dry consistence)：每比母質提高一級給予10分 (一般不測這個，下一個較常測)。
- 濕結持度 X<sub>m</sub> (moist consistence)：每比母質提高一級給予10分。</br>loose&#8594;very friable&#8594;friable&#8594;firm&#8594;very firm&#8594;extremely firm。
- 黑化 X<sub>v</sub> (melanization)：對於上界在100 cm深度內的剖面，顏色每比母質降低一級value就給予10分
- pH值 X<sub>pH</sub>：與母質的直接差距之絕對值，若該化育層的pH值比母質高，就為0。
  
### 標準化  
各指標分數在給定之後，為了顧及不同剖面比較的意義，要進行標準化，這裡標準化的方法是把每個化育層的分數除以該指標分數已知的最大值，使其成為0-1的數值。  
- 紅化 X<sub>r</sub> (rubification)：除以190。
- 質地 X<sub>t</sub> (total texture)：除以90。
- 黏粒膜 X<sub>f</sub> (clay films)：除以


  
### 參考文獻  
黃文樹。2003。八卦台地南部階地地形與土壤化育之研究。國立彰化師範大學地理學系碩士論文。  
Harden, J.W. 1982. A quantitative index of soil development from field descriptions: Examples from a chronosequence in central California. Geoderma, 28(1), 1-28.  
<a href="https://doi.org/10.1016/0016-7061(82)90037-4" target="_blank">https://doi.org/10.1016/0016-7061(82)90037-4</a>  
