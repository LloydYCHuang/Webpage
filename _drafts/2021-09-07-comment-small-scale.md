---
layout: default
categories: [Journal comments]
title:  "Comment#12 Near-infrared spectroscopy for within-field soil characterization: small local calibrations compared with national libraries spiked with local samples"
---  
## Comment#12 Near-infrared spectroscopy for within-field soil characterization: small local calibrations compared with national libraries spiked with local samples  
2021/09/07  
怎麼想都覺得樣本數太少會成為一大弱點，要做機器學習而且變數這麼多，最近想說如果被問到該怎麼辦？  
所以我來了。  
沒有別的解法，就是重新搜索文獻尋找資料，因此Comment系列再次開始，我發現強迫自己在一段時間內讀完內文並且寫Comment是一個很棒的知識吸收方式。老話一句：你必須非常努力，才能看起來毫不費力。  
  
Topic:  
Wetterlind, J., and Stenberg, B. 2010, Near-infrared spectroscopy for within-field soil characterization: small local calibrations compared with national libraries spiked with local samples. European Journal of Soil Science, 61: 823-843. <a href="https://doi.org/10.1111/j.1365-2389.2010.01283.x" target="_blank">https://doi.org/10.1111/j.1365-2389.2010.01283.x</a>  
  
### Introduction  
土壤的近紅外光譜 (near-infrared,NIR) 已經被廣泛利用在各項智慧農業所需要的土壤性質量測上，由於其極快的資料收集速度，可以快速的對土壤性質有所掌握，但是NIR對土壤性質的預測仍須奠基於傳統濕化學分析的性質，因此校正樣品 (calibration samples) 成為必要，如何權衡所需要的精準度與採集校正樣品所耗費的時間，一直是個重要的問題，尤其是在預測小範圍地區的資料。  
  
有時大規模的樣本所建立之校正，不一定能對小範圍的資料做到很好的預測，因為有些土壤性質與光譜的關係是因地而異 (site-specific)。例如每個地區所含有的土壤有機質種類可能都不一樣，各地區的礦物與質地也都不同，不可一概而論。  
  
NIR區域的1730、1760、2050與2300-2350 nm的吸光值通常被視為跟有機質有關，而最強烈的特徵是黏粒的O-H鍵伸縮 (stretching) 與金屬-OH鍵的合頻 (combination) 與倍頻 (overtone)。而除了有機質與礦物以外的土壤性質，例如鹽類與pH，就必須透過共變異 (co-variation) 來預測，這些共變異更有可能隨著地區不同而改變。  
  
當NIR主要依靠非直接的關係 (如共變異) 來預測土壤性質時，樣品量的多寡就會大幅影響到校正的好壞。現今很多國家都已經建立屬於自己的土壤光譜資料庫 (spectrum library)，並可透過大量 (上千個) 樣本進行校正。前人文獻也指出，透過添加 (spike) 相對少量 (小於100個) 地區性樣品可以大幅的提高模型預測的精準度。  
  
當樣本數太小時，常會因為樣本太過接近而導致校正受到特定的土壤種類影響，若使用大量樣本的資料庫就可以降低這個問題，然而過於龐大的資料庫通常較難預測特定小地區的土壤。因此本篇文章的重點就是在探討使用國家級的光譜資料庫與地區性的小樣本校正兩者哪個比較好，抑是在大資料庫中添加小樣本能夠有更好的表現。  
  
### Materials and methods  
**國家級與地區性資料庫**  
本文使用瑞典國內所收集的396個土壤表土 (0-20 cm) 樣品組建的資料庫，樣品分析過程為將樣品風乾磨碎過2 mm篩網後進行有機碳 (SOC)、質地吸管法 (clay)、pH值與醋酸銨-乳酸 (P-AL) 萃取的磷濃度，括弧內是代號。地區性資料庫則是利用瑞典南部農業區的四個農場建立，每個農場採取25個土壤表土樣本，並且經過相同的處理與實驗。除此之外，每個農場均額外採取81-112個樣本作為驗證樣本 (validation samples)。  
  
**Vis-NIR**  
使用FieldSpec Pro FR scanning instrument進行量測，以光纖 (bare fiber) 連接一個20 W的鹵素燈距離樣品7 cm的距離紀錄反射光譜，並有使用Spectralon白板校正空白。  
  
**資料庫處理**  
為了同時包含國家資料庫的大量數據，並兼顧地區性校正，作者對每個農場均特別挑出50個與地區性土壤的光譜最相近的樣本組成縮小的國家資料庫。即假設若光譜類似，可能土壤中的組成物也類似，相似與否是利用國家資料庫經過主成分分析後得到變數權重，再將四個農場的土壤依此權重計算得分，前六個主成分的得分會拿來比較。  
  
**資料庫校正**  
作者使用Unscrambler 9.7軟體來進行，將資料轉為吸光度 (absorbance) 後進行2階多項式，21點區間 (second-order polynomial in segments of 21 points) 的Savitzky-Golay光譜平滑化。短的波長由於過多雜訊故不使用，主要使用460-2490 nm的資料，水的波峰 (1840-1941 nm) 也被移除以增進效果。  
使用偏最小平方法迴歸 (partial least squares regression, PLSR) 建立模型，針對四個農場都分別建立縮小的國家資料庫與地區性資料庫模型，並且在國家資料庫與縮小的國家資料庫中皆嘗試添加5、10、15、20或25個地區樣本再獨立建模。  
模型驗證使用額外採取的驗證樣本計算R<sup>2</sub>、RMSEP (root mean squared error of prediction) 及bias-corrected SEP (在RMSEP的方程式中再減掉一個bias，如下)。  
  
$$\begin{aligned}
RMSEP &= \sqrt{\frac{\sum_{i=1}^n(\widehat{y}_i-y_i)^2 }{n}}\\
Bias &= \frac{\sum_{i=1}^n(\widehat{y}_i-y_i)}{n}\\
SEP &= \sqrt{\frac{\sum_{i=1}^n(\widehat{y}_i-y_i-Bias)^2 }{n-1}}
\end{aligned}$$  
  
另外，RPD (ratio of performance to deviation) 是將驗證組的標準差除以RMSEP來計算，RPD也是衡量預測效果的指標之一，RPD > 2是相當好的預測，RPD < 1.4則較為不可信。  
  
### Results  
由於結果較多，就只呈現重要的部分。  
**PCA投影**  
全國資料庫的主成分分析結果中前兩個主成分均可解釋超過70%的變異，將其建立的投影應用在地區性資料繪製score plot，可以找到與地區性資料性質相近的土壤資料，進而挑選出縮小的全國資料庫中的50個點。  
  
**校正結果**  
地區性校正的結果普遍以clay及SOC表現最好，而各地區的預測效果有所差異，但最重要的是和其他組別的比較。總體來說，地區性校正的RMSEP幾乎都是最小的，其他指標也幾乎是，尤其是跟國家資料庫比時，資料數龐大的國家資料庫並無法對小範圍的變異做出鑑別，甚至其RMSEP幾乎都是全部組別裡最高的。  
  
雖然地區性樣本只有25個，卻能比國家資料庫表現更好，縮小的全國資料庫的50個點表現也跟全國資料庫差不多。然而，spike過後的資料庫卻呈現驚人的結果，光是添加5個地區性樣本到全國資料庫，通常就能降低RMSEP，在有的組別中添加5個地區性樣本竟然能降低超過一半的RMSEP。  
  
相較於RMSEP的下降，SEP的下降就沒有那麼明顯，


