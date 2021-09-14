---
layout: default
categories: [Soil]
title:  "Quantifying soil morphology - 量化土壤剖面描述"
---  
## Quantifying soil morphology - 量化土壤剖面描述  
2021/08/01   
在剖面描述時，我們會在現地記錄一個剖面裡各個化育層的特徵，包含顏色、構造、質地、結持度等，尤其在我研究的淋澱土 (Spodosol) 中顏色是一個重要的判別基準，但是剖面的描述大多都不是連續性 (continuous) 的，為了將土壤的顏色量化 (quantify) 成可以用統計處理的形式，我踏上了尋找剖面描述量化基準的路。  
  
### 概念  
Harden (1982) 的量化概念是建立一個土壤化育的指數 (soil development index)，藉此比較土壤的化育程度。這個指數應能將現地描述的剖面資料轉換成一個或多個相應的量化指標。其主要的步驟如下：  
1. 給予每種描述分數，在描述**等級間的差異**給予分數 (後述)。
2. 把化育層的分數進行標準化 (normalization) 為範圍在0-1的指標。
3. 將化育層中的描述分數平均，每個化育層得到一個**化育層指數 (horizon index)**。
4. 將化育層指數乘以該化育層厚度，加權獲得該剖面的**剖面化育指數 (profile development index, PDI)**。
5. 最後將剖面化育指數除以剖面厚度可獲得加權平均的剖面化育指數 (weighted mean profile development index)。  
  
剖面化育指數有助於量化在現地觀察到的形態特徵並且可以比較不同剖面的化育程度，在Harden (1982) 所提出的PDI中包含了八種現地形態描述的項目：紅化 (rubification，包含顏色的hue與chroma)、質地 (total texture)、黏粒膜 (clay film)、構造 (structure)、乾結持度 (dry consistence)、濕結持度 (moist consistence)、黑化 (melanization，顏色的value) 及pH值。  
藉由研究一時間序列 (chronosequence) 土壤的形態特徵，Harden (1982) 所提出的PDI已被廣泛接受。  
  
### 如何給分  
給分的方法是化育層**相對於母質的性質**，因此母質的描述至關重要，描述完母質之後再針對不同性質的等級差異，計算母質與該化育層的性質差異，然而此指標只用來描述**風化**，所以分數的加分是單向性的，以質地為例，隨時間進行質地會風化的更為細緻，因此只對比母質更細的化育層進行加分，但若質地變得更粗，則不進行扣分 (雖然是代表了其他成土因子或過程)。  
將性質量化後的數值稱作量化性質 (quantified property, X<sub>p</sub>)，例如量化後的質地指數稱為X<sub>t</sub> (t代表texture)，量化後的紅化指數稱為X<sub>r</sub> (r代表rubification)。以下列出級分的標準，另外原版的論文真的很不清楚，可以參考黃文樹 (2003) 整理的較易看懂  
- 紅化 X<sub>r</sub> (rubification)：每比母質增加一級的hue或chrome，就增加10分，需計算乾濕顏色差的總和。hue是遵照色帖的順序 5Y&#8594;2.5Y&#8594;10YR&#8594;7.5YR&#8594;5YR&#8594;2.5YR&#8594;10R&#8594;5R。
- 質地 X<sub>t</sub> (total texture)：根據三角圖的黏粒等級越黏一級就增加10分；黏性 (stickness) 與塑性 (plasticity) 每增加一級就增加10分。  
- 黏粒膜 X<sub>f</sub> (clay films)：根據黏粒的豐富度 (abundance)、厚度 (thickness)、位置 (location) 進行分級，是針對有黏粒膜的土壤，就不特別列出。
- 構造 X<sub>s</sub> (structure)：根據構造等級給分，weak/moderate/strong分別為10/20/30分。形狀方面platy為5分，granular, subangular blocky, angular blocky皆為10分，prismatic為20分，columnar為30分。
- 乾結持度 X<sub>d</sub> (dry consistence)：每比母質提高一級給予10分 (一般不測這個，下一個較常測)。
- 濕結持度 X<sub>m</sub> (moist consistence)：每比母質提高一級給予10分。順序是loose&#8594;very friable&#8594;friable&#8594;firm&#8594;very firm&#8594;extremely firm。
- 黑化 X<sub>v</sub> (melanization)：對於上界在100 cm深度內的剖面，顏色每比母質降低一級value就給予10分
- pH值 X<sub>pH</sub>：與母質的直接差距之絕對值，若該化育層的pH值比母質高，就為0。
  
### 標準化  
各指標分數在給定之後，為了顧及不同剖面比較的意義，要進行標準化，標準化的方法是把每個化育層的分數除以該指標分數量化後的最大值 (current maximum)，使其成為0-1的數值，標準化後的值會加下標n。  
- 紅化 X<sub>rn</sub> (rubification)：除以量化後最大值190。
- 質地 X<sub>tn</sub> (total texture)：除以量化後最大值90。
- 黏粒膜 X<sub>fn</sub> (clay films)：對於大於0的數值皆減去20後，除以量化後最大值130 (不足0者為0)。
- 構造 X<sub>sn</sub> (structure)：除以量化後最大值60。
- 乾結持度 X<sub>dn</sub> (dry consistence)：除以量化後最大值50的兩倍，即除以100。
- 濕結持度 X<sub>mn</sub> (moist consistence)：除以量化後最大值50的兩倍，即除以100。
- 黑化 X<sub>vn</sub> (melanization)：除以量化後最大值70。
- pH值 X<sub>pHn</sub>：除以母質的pH。  
  
Harden (1982) 的PDI是最常被使用的量化方法，引用次數超過600次，原因是可以完整的把所有描述的特徵都整合成一個分數進行比較。  
  
### 顏色所代表的意義  
我研究量化形態特徵的原因是要將淋澱土的顏色量化以進行比較與統計計算，因此特別關注顏色的意義。孟氏色帖 (Munsell color chart) 包含hue、value及chroma三個項目，在土壤風化過程中游離鐵增加且呈現氧化環境時hue會變紅且chroma會增加 (變亮)，此過程即稱為紅化 (rubification)，在原文中**乾濕兩種的顏色都會被計算並加總**。  
在土壤表層被有機質染黑後value會下降，此過程即為黑化 (melanization)，根據原文黑化指的是100 cm深度內由有機質造成的現象，更深的土壤中與有機質較無關係。  
  
### 其他顏色的量化指標  
除了Harden (1982) 所提出的指標外，也有其他的指標，簡單介紹幾個我找到的，例如Hurst (1977) 提出的Redness Rating (RR) 可以分辨針鐵礦 (goethite) 及赤鐵礦 (hematite) 在土壤裡的多寡。方法是先給定hue的數值H&#42;，分別對應5R (H&#42; = 5)、10R (H&#42; = 10)、5YR (H&#42; = 15)、10YR (H&#42; = 20) 以此類推。  
$$RR = \frac{H^{\ast} \times Chroma}{Value}$$  
  
奠基於此，Torrent et al. (1983) 進一步建立了與赤鐵礦相關的顏色量化指標。赤鐵礦的紅色可以很有效的蓋過針鐵礦的黃色，只要高於1.7%的赤鐵礦就可以讓土壤呈現紅色，因此顏色指標與赤鐵礦含量相當有關。因此Torrent et al. (1983) 的Redness Rating是以下的形式  
$$RR = \frac{(10-Hue) \times Chroma}{Value}$$   
Hue的項目是10減去YR前的數字，即10YR減去10，7.5YR減去7.5，5YR減去5，2.5YR減去2.5，10R則不用減，因此顏色越紅會越大，這個RR值與土壤中赤鐵礦的含量有良好的線性關係，實驗土壤來自歐洲與巴西 (R<sup>2</sup> = 0.814與0.760)。   
    
Mokma (1993) 則嘗試建立與淋澱土中的鐵鋁與有機碳含量相關的顏色量化指標，在淋澱土中洗出層 (eluvial horizon, E層) 的value高於A、B層，而淋澱層 (spodic horizon, Bhs層) 則具有最紅的hue與最低的value，特別的是在該文章中chroma是隨著深度增加的 (該文章整理了密西根州內468個淋澱土剖面資料，頁數也不長，建議可以參考)。  
顏色的三個項目均與無定型物質 (amorphous compound) 呈負相關，尤其是與焦磷酸抽出的有機碳含量。為了建立與無定型物質相關的顏色量化指標，hue的轉換方法為10R = 0，2.5YR = 2.5，5YR = 5，7.5YR = 7.5，10YR = 10，2.5Y = 12.5，5Y = 15，而value及chroma再加上去，如5YR 3/2的量化值為5+3+2 = 10。  
這個數值與無定型物質中的碳含量關係較鐵鋁來的高，無定型物質越高該指標越低，且在不同種類的淋澱土中相關性皆良好。  
額外補充，該文獻也發現了焦磷酸萃取的碳和ODOE的高相關性 (r = 0.73) 並建立迴歸式如下：  
ODOE = 0.19 C<sub>p</sub> - 0.04  
  
最後是Gobin et al. (2000) 建立複雜的redness index (RI) 與color index (CI)，由於計算過程太過複雜就不在這裡寫，這是一個考慮前面文獻後提出的方程式，可以綜合性討論土壤的化育作用，但是這篇的引用數比起Harden (1982) 差多了，看來有時還是最簡單的較好用。  
總之這些是常見用於量化土壤顏色的方法，又以一開始提的Harden (1982) 最常見，但是要記錄乾濕的顏色，對於沒有乾顏色的過往資料可能有些棘手，我正在處理的淋澱土資料就可能沒有。Harden (1982) 和Torrent et al. (1983) 是用於對應赤鐵礦，和淋澱土的目的又不同，至於Mokma (1993) 呢？引用數是比較少一點，但可以考慮看看。  
  
### 淋澱土 POD index  
終於，被我找到一篇專門針對淋澱化作用所進行的量化指標，且是由淋澱土方面的權威R.J. Schaetzl所寫的。  
由Schaetzl (1988) 提出的這個指標稱作POD index。在理論架構過程中，淋澱化作用被考慮為一項讓土壤化育、分層並且提升剖面內異質性 (profile anisotropy) 的過程。在淋澱化過程中洗出層 (E) 與洗入層 (Bhs) 都會有所變化，B層會變得更紅 (有關hue)、更黑 (有關value)，並在過程中進一步化育分層，因此這個指標必須能代表淋澱化過程中剖面化育且分層的特性。  
POD的名字來源是因為在原本俄語的Podzol與英文的Spodosol都含有POD三個字母，POD index是用來描述具有淋澱化特徵的土壤，要計算POD需要滿足的條件是擁有E層與B層，計算過程如下：  
- 擁有不只一個E層時，使用value最高的E層做為E<sub>value</sub>。  
- 針對所有的B層都進行計算 (不包含CB、BC之類的，但對於淋澱化土壤的BE、EB可以視作B)。
- 當E層的value &#62; B層的value時，計算E<sub>value</sub> - B<sub>value</sub>，反之則跳過這個B層。
- 將E<sub>value</sub> - B<sub>value</sub>乘以一個常數，之後加總所有的B層計算結果。
  
最後一步需要乘的常數取決於E層和B層的hue有沒有差異，規則如下：  
- 若hue沒有改變，常數為1
- 若hue改變，常數為以2為底的「改變級數」的次方 (若從5YR到7.5YR差1，則常數為2<sup>1</sup> = 2，若從5YR到10YR差2，則常數2<sup>2</sup> = 4這樣)
  
原文裡有流程圖更容易懂，建議去看，總之POD指數的計算方法可以簡單表示成  
$$POD \ index = \Sigma \Delta V \cdot 2 ^{\Delta H}$$  
&Delta;V代表E層與B層間value的差異，&Delta;H代表hue的差異。這個指標不能用在有Ap層的土壤 (耕犁過的)，沒有E層的土壤也不能用。  
在Schaetzl (2013) 對於美國723個淋澱化土壤剖面進行計算的結果中，非淋澱土 (但都有E層，具淋澱化現象) 的POD多在2以下，在Typic Haplorthods中平均為11.6，介於中間的Entic Haplorthods則為2-6。  
因此可設立一個標準，即非淋澱土者POD < 2，Entic Haplorthods的POD介於2-6，Typic Haplorthods則具有POD > 6的性質，但當然也存在一些離群值。  
作者進一步對344個其他文獻描述的淋澱化土壤進行測驗，且故意選擇非美國的淋澱化土壤，約有60%的正確率，這驗證了POD指標的實用性。  
  
**POD VS. 時間**  
在計算一時間序列土壤中的五個剖面POD指標後，發現與時間的相關性是指數型，時間越長則POD增加的越快。  
**POD VS. 排水**  
在比較Typic Haplorthods (排水良好)、Aquic Haplorthods (排水稍不良)、Aeric Haplaquods (排水不良) 及Typic Haplaquods (排水相當不良) 這四種淋澱土的POD指數後，發現POD值是以Aeric Haplaquods最高，Typic Haplaquods次之，而後是Aquic Haplorthods與Typic Haplorthods。  
Aquods比Orthods的化育程度更高，且現地也通常會觀察到較深色的Bhs層。在排水良好且地下水面升降差異大的地區，較利於淋澱化作用，因此至少有水位升降的Aeric Haplaquods才會有最高的POD值，而Typic Haplaquods一直呈現水飽和的狀況則較不利淋澱化作用。  
  
POD指標可以用在分類、時間序列評估、排水性質評估上，且在分辨淋澱土與淋澱化土壤上，有60%的正確度，這應該可以考慮應用在淋澱化土壤的量化分析上。  
   
### 參考文獻  
黃文樹。2003。八卦台地南部階地地形與土壤化育之研究。國立彰化師範大學地理學系碩士論文。  
Gobin, A., Campling, P., Deckers, J., and Feyen, J. 2000. Quantifying soil morphology in tropical environments methods and application in soil classification. Soil Science Society of America Journal, 64(4), 1423-1433.  
<a href="https://doi.org/10.2136/sssaj2000.6441423x" target="_blank">https://doi.org/10.2136/sssaj2000.6441423x</a>   
Harden, J.W. 1982. A quantitative index of soil development from field descriptions: Examples from a chronosequence in central California. Geoderma, 28(1), 1-28.  
<a href="https://doi.org/10.1016/0016-7061(82)90037-4" target="_blank">https://doi.org/10.1016/0016-7061(82)90037-4</a>    
Hurst, V.J. 1977. Visual estimation of iron in saprolite. Geological Society of America Bulletin, 88, 174-176.   
Mokma, D.L. 1993. Color and Amorphous Materials in Spodosols from Michigan. Soil Science Society of America Journal, 57(1), 125-118.  
<a href="https://doi.org/10.2136/sssaj1993.03615995005700010024x" target="_blank">https://doi.org/10.2136/sssaj1993.03615995005700010024x</a>  
Schaetzl, R.J., and Mokma, D.L. 1988. A numerical index of Podzol and Podzolic soil development. Physical Geography, 9(3), 232-246.  
<a href="https://doi.org/10.1080/02723646.1988.10642352" target="_blank">https://doi.org/10.1080/02723646.1988.10642352</a>  
Torrent, J., Schwertmann, U., Fechter, H., and Alferez, F. 1983. Quantitative relationships between soil color and hematite content. Soil Science, 136(6), 354-358.  
<a href="https://doi.org/10.1097/00010694-198312000-00004" target="_blank">https://doi.org/10.1097/00010694-198312000-00004</a>   
