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
  
當NIR主要依靠非直接的關係 (如共變異) 來預測土壤性質時，樣品量的多寡就會大幅影響到校正的好壞。現今很多國家都已經建立屬於自己的土壤光譜資料庫 (Spectrum library)，並可透過大量 (上千個) 樣本進行校正。前人文獻也指出，透過添加 (spike) 相對少量 (小於100個) 地區性樣品可以大幅的提高模型預測的精準度。  
  
當樣本數太小時，常會因為樣本太過接近而導致校正效果不好，若使用大量樣本的資料庫就可以降低這個問題，


