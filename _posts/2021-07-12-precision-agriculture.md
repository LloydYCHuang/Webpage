---
layout: default
categories: [Journal comments]
title:  "Comment#3 Prediction of soil nutrient content via pXRF spectrometry and its spatial variation in a highly variable tropical area"
---  
2021/07/12  
剛剛在挑選要看的期刊時對自己說了一句「就看這個好了」，然後又突然驚訝的對自己說「還以為你有資格挑啊，當然是全看啊」，研究生的生活就是這麼的樸實無華。  
  
Topic:  
Pelegrino, M.H.P., Silva, S.H.G., de Faria, Á.J.G., Mancini, M., dos Santos Teixeira, A.F., Chakraborty, S., Weindorf, D.C., Guimarães Guilherme, L.R., and Curi, N. 2021. Prediction of soil nutrient content via pXRF spectrometry and its spatial variation in a highly variable tropical area. Precision Agriculture, 1-17.  
<a href="https://doi.org/10.1007/s11119-021-09825-8" target="_blank">https://doi.org/10.1007/s11119-021-09825-8</a>  
這篇文章來自期刊Precision agriculture，似乎是因為很新所以我找不到volume，官網上也找不到，引用格式請見諒。  
智慧農業的應用上，proximal sensor的發展已逐漸趨向成熟，唯獨臺灣在土壤感測似乎無法接軌，本篇的標題非常淺顯易懂，作者中包含了巴西的NIR專家S.H.G. Silva及德州科技大學的pXRF專家D.C. Weindorf，所以我在看到標題只有pXRF時有點小驚訝。  
  
### Introduction  
本研究針對巴西的土壤進行proximal sensor的研究，現在使用proximal sensor已經可以針對不同土壤性質做出有效的預測模型，然而這些預測模型多是區域性的，因此時常會針對區域性進行研究，這可能也是Geoderma Regional這麼多人投的原因？  
由於農業資源的日益重要，智慧農業/精準農業所追求高效率的農業方式，利用proximal sensor來監控土壤性質進而達到精準的施肥、灌溉等耕作行為，便成為重要的一環，順帶一提根據International Society of Precision Agriculture在2019年所提出的精準農業定義如下   
_Precision agriculture is a management strategy that gathers, processes and analyzes temporal, spatial and individual data and combines it with other information to support management decisions according to estimated variability for improved resource use efficiency, productivity, quality, profitability and sustainability of agricultural production._   
精準農業藉由分析土壤營養元素的空間變異性，得以**最佳化**產能以及土地使用效率，這種分區管理的方式將在未來成為主流。  
然而，若是持續以傳統的wet chemistry方式分析土壤營養元素等性質，其所消耗的時間與成本過大，尤其是在熱帶開發中國家，受限於經費等問題並無法分析過多樣品。因此，為了克服這種限制，許多的方法用來繪製更精確的土壤圖，例如地理統計 (geostatistics)、迴歸分析、fuzzy logic及機器學習 (machine learning)，在搭配上proximal sensor的快速產出資料後，此種結合帶來極快的土壤圖繪製能力。  
其中手持式X射線螢光儀 (portable X-ray fluorescence spectrometry, pXRF) 就是一個常被使用的儀器，他可以定量土壤中的全量元素組成，搭配統計模型可以利用這些全量元素含量來預測土壤性質。  
因此本研究便是利用pXRF來預測土壤中的可交換性Ca、有效K與有效P的含量，並嘗試找出最佳的預測模型。  
  
### Materials & methods  
研究在巴西Minas Gerais省的University of Lavras校地進行，實驗地區面積約為315 ha (供參考一下大安森林公園的面積是26 ha)，年均溫20.4&deg;C且年雨量為1460 mm。土壤母質包含75% granitic-gneiss (花崗片麻岩) 與20% gabbro (輝長岩)，剩下5%為沉積物，
地區內土壤分類包含了Oxisols, Ultisols, Inceptisols, Entisols與Histosols，具相當大的變異性。  
在區域內以土鑽採集90個點的A化育層 (0-20 cm)，在有機質較多的地區會先清除表面有機質再採集。  
可交換性Ca<sup>2+</sup>利用KCl萃取，有效K與P利用Mehlich-1方法萃取，K<sup>+</sup>濃度利用AES (atomic emission spectrometer) 定量、P濃度以分光光度計、Ca<sup>2+</sup>以AAS (atomic absorption spectrometer) 測定。  
使用Bruker model S1 Titan LE pXRF進行測定60秒，並且測定NIST標準品2710a與2711a的回收率，多數元素落在80-120%，但K、Ca、Mn、Fe、V有被低估，而P則是高估超過400%，這些是常見的pXRF回收率數字，但現在要追求的並非精準度，所以可接受，這些數字後續分析達到的預測能力才是重點。共有15個元素資料進行後續建模，包含Al, Ca, Cl, Cr, Cu, Fe, K,
Mn, Ni, P, Si, Ti, V, Zn, 及Zr。其中覺突兀的是Cl因為一般認為Cl應該不是很準確的，不知後續是否有特殊意義。  
  
**Modeling**  
隨機將樣品區分modeling (75%, 共63個樣品) 與validation (25%, 共27個樣品)，三種預測方法包含linear regression (LR), 2nd degree polynomial regression (PR), power regression (PwR) 及stepwise multiple linear regression (SMLR)。  
模型的評量標準包括：  
- Coefficient of determination, R<sup>2</sup>
- Mean absolute error, MAE (即實際值-預測值的絕對值進行平均)
- Root mean square error, RMSE
- Residual prediction deviation, RPD (標準差除以RMSE，RPD > 2代表極好，RPD > 1.4代表可接受，小於1.4代表不好)  
  
### Spatial  
用90個點去預測315 ha，以multilevel B-spline內插法進行土壤圖的繪製，再以Lin's concordance correlation coefficient (CCC) 進行比較，此法可以比較不同方法繪製的土壤圖之間的一致性與相關性。  
  
http://biostat.tmu.edu.tw/oldFile/enews/ep_download/ep_download.php?f=10stat.pdf


未完...可能會先把淋澱土的review看完，這篇有空閒的時間看
