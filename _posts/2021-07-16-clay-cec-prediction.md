---
layout: default
categories: [Journal comments]
title:  "Comment#7 Prediction of Soil Clay Content and Cation Exchange Capacity Using Visible Near-Infrared Spectroscopy, Portable X-ray Fluorescence, and X-ray Diffraction Techniques"
---  
## Comment#7 Prediction of Soil Clay Content and Cation Exchange Capacity Using Visible Near-Infrared Spectroscopy, Portable X-ray Fluorescence, and X-ray Diffraction Techniques  
2021/07/15  
這篇的impact factor還蠻高的，Environmental Science & Technology有7.864，我們來看看他有沒有這個價值。  
  
Topic:  
Chen, Y., Gao, S., Jones, E.J., and Singh, B. 2021. Prediction of Soil Clay Content and Cation Exchange Capacity Using Visible Near-Infrared Spectroscopy, Portable X-ray Fluorescence, and X-ray Diffraction Techniques. Environmental Science & Technology, 55(8), 4629-4637.  
<a href="https://doi.org/10.1021/acs.est.0c04130" target="_blank">https://doi.org/10.1021/acs.est.0c04130</a>  
  
### Introduction  
本研究是針對土壤的黏粒含量與陽離子交換容量 (cation exchange capacity, CEC) 進行預測，這兩種性質的重要性就不用提了。三種儀器被用來偵測土壤產出的訊號，這三種都是光譜儀器，包含visible and near infrared spectroscopy (Vis-NIR), portable X-ray fluorescence spectroscopy (pXRF) 以及X-ray diffractometer (XRD)，其中前兩項已經可做到攜帶式的現地 (in situ) 偵測，有機會我也來介紹一下。  
為了達到較好的預測，得嘗試不同儀器所產出的預測效果，由於這三種儀器可以偵測的土壤訊號不同，本研究便是要探討此三種儀器的結合效果，pXRF雖能偵測元素含量，但對礦物並無法辨識，XRD雖可偵測礦物但某些結構較不完整的礦物使用Vis-NIR反而可以得到訊號，因此測試這三種儀器的單獨VS結合預測效果便是本研究的目的。  
  
### Materials and Methods  
**Study area**  
使用的是兩組legacy data，第一組是來自澳洲新南威爾斯Lower Namoi地區，簡稱NAM組，包含125個地點的0-10 cm與30-40 cm土壤。另一組是來自澳洲昆士蘭St George地區，簡稱SGE組，包含82個地點的0-10 cm與50-60 cm土壤，這些土壤原本皆是以stratified sampling方式採樣。  
NAM組有河流流經並且地勢平坦，這使得該地成為土壤肥沃的氾濫平原，土壤樣品來自農業用地及自然植被都有；SGE組也是位於氾濫平原，是小麥、棉花種植地，也用於綿羊畜牧，該地母質為sandstone及shale，多包含Alfisols, Aridisols及Vertisols。兩個組別的水分境況皆為ustic至aridic，溫度境況皆為thermic。  
  
**Vis-NIR**  
使用的是ASD AgriSpec搭配contact probe，光源為鹵素燈，且使用Spectralon作為空白校正，取得350-2500 nm的光譜後進行Savitzky-Golay平滑化 (window size = 11，使用二階多項式)，剔除signal-to-noise ratio過高的波長後得到500-2450 nm的光譜。然後把光譜轉換成absorbance，並經過standard normal variate baseline correction。不得不說他們的步驟寫得很詳細。  
  
**pXRF**  
使用Niton XL3t pXRF，他們的儀器有4條beam，能量範圍6-50 keV，樣品與儀器只間隔polypropylene film，每個樣品一次掃描120秒並執行三重複。兩個NIST標準品 (2709及2711a) 被用來每小時校正一次樣品。  
根據迴歸分析發現Fe, Ti, K, Si與Al這五個元素和目標性質 (clay, CEC) 有正相關且在土壤中含量較大，故使用於後續建模。  
  
**XRD**  

  
meandering：彎曲的  
horticulture：園藝
