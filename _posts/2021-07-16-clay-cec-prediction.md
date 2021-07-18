---
layout: default
categories: [Journal comments]
title:  "Comment#7 Prediction of Soil Clay Content and Cation Exchange Capacity Using Visible Near-Infrared Spectroscopy, Portable X-ray Fluorescence, and X-ray Diffraction Techniques"
---  
## Comment#7 Prediction of Soil Clay Content and Cation Exchange Capacity Using Visible Near-Infrared Spectroscopy, Portable X-ray Fluorescence, and X-ray Diffraction Techniques  
2021/07/15  
這篇的impact factor在土壤領域算蠻高的，Environmental Science & Technology官網上2020有9.028，我們來看看他有沒有這個價值。  
  
Topic:  
Chen, Y., Gao, S., Jones, E.J., and Singh, B. 2021. Prediction of Soil Clay Content and Cation Exchange Capacity Using Visible Near-Infrared Spectroscopy, Portable X-ray Fluorescence, and X-ray Diffraction Techniques. Environmental Science & Technology, 55(8), 4629-4637.  
<a href="https://doi.org/10.1021/acs.est.0c04130" target="_blank">https://doi.org/10.1021/acs.est.0c04130</a>  
  
### Introduction  
本研究是針對土壤的黏粒含量與陽離子交換容量 (cation exchange capacity, CEC) 進行預測，這兩種性質的重要性就不用提了。三種儀器被用來偵測土壤產出的訊號，這三種都是光譜儀器，包含visible and near infrared spectroscopy (Vis-NIR), portable X-ray fluorescence spectroscopy (pXRF) 以及X-ray diffractometer (XRD)，其中前兩項已經可做到攜帶式的現地 (in situ) 偵測，有機會我也來介紹一下。  
為了達到較好的預測，得嘗試不同儀器所產出的預測效果，由於這三種儀器可以偵測的土壤訊號不同，本研究便是要探討此三種儀器的結合效果，pXRF雖能偵測元素含量，但對礦物並無法辨識，XRD雖可偵測礦物但某些結構較不完整的礦物使用Vis-NIR反而可以得到訊號，因此測試這三種儀器的單獨VS結合預測效果便是本研究的目的。  
  
### Materials and Methods  
**Study area**  
使用的是兩組legacy data，第一組是來自澳洲新南威爾斯Lower Namoi地區，簡稱NAM組，包含125個地點的0-10 cm與30-40 cm土壤。另一組是來自澳洲昆士蘭St George地區，簡稱SGE組，包含82個地點的0-10 cm與50-60 cm土壤，這些土壤原本皆是以stratified sampling方式採樣。樣品總數為367 (NAM組216+SGE組151)。  
NAM組有河流流經並且地勢平坦，這使得該地成為土壤肥沃的氾濫平原，土壤樣品來自農業用地及自然植被都有；SGE組也是位於氾濫平原，是小麥、棉花種植地，也用於綿羊畜牧，該地母質為sandstone及shale，多包含Alfisols, Aridisols及Vertisols。兩個組別的水分境況皆為ustic至aridic，溫度境況皆為thermic。  
  
**Vis-NIR**  
使用的是ASD AgriSpec搭配contact probe，光源為鹵素燈，且使用Spectralon作為空白校正，取得350-2500 nm的光譜後進行Savitzky-Golay平滑化 (window size = 11，使用二階多項式)，剔除signal-to-noise ratio過高的波長後得到500-2450 nm的光譜。然後把光譜轉換成absorbance，並經過standard normal variate baseline correction。不得不說他們的步驟寫得很詳細。  
  
**pXRF**  
使用Niton XL3t pXRF，他們的儀器有4條beam，能量範圍6-50 keV，樣品與儀器只間隔polypropylene film，每個樣品一次掃描120秒並執行三重複。兩個NIST標準品 (2709及2711a) 被用來每小時校正一次樣品。  
根據迴歸分析發現Fe, Ti, K, Si與Al這五個元素和目標性質 (clay, CEC) 有正相關且在土壤中含量較大，故使用於後續建模。  
  
**XRD**  
土壤僅經過風乾磨碎處理，並未分離黏粒部分也沒有鉀鎂飽和，是單純測量整體土壤的繞射圖譜。使用CuK&alpha;掃描18-70&deg;的繞射圖譜，並使用26.64&deg; 2&theta;的石英作為基準將所有圖譜對齊。  
  
**Modeling**  
使用Cubist模型進行預測，總共使用六種變數組合分別為Vis-NIR, pXRF, XRD, VisNIR-pXRF, VisNIR-XRD, pXRF-XRD及VisNIR-pXRF-XRD。模型根據兩組資料 (NAM及SGE) 各自建立並交互試驗預測效果，資料組分為75% calibration及25% validation，並以50次隨機的重新分組作為cross-validation，這50次的validation set的資料會進行記錄。  
模型表現使用validation set的Lin's concordance correlation coefficient (CCC) 及root mean square error (RMSE) 作評量標準，這些數值再進一步使用ANOVA來分析不同變數組合間有無顯著差異。  
  
### Results and discussion  
供試土壤多呈現鹼性 (平均pH > 8)、有機碳低(< 1%)，高CEC (> 300 mmol<sub>c</sub> kg<sup>-1</sup>) 及高黏粒含量 (NAM組 > 50%；SGE組 > 30%)，CEC/clay的比例較高 (由於土壤含有許多CEC較高的smectite)。  
VisNIR光譜大致上呈現類似的形狀，在1400, 1900及2200 nm有較高的吸光度，2200 nm是kaolinite等層狀矽酸鹽的吸收峰，包含kaolinite, illite及smectite均會吸收，故此波段的吸光度與黏粒含量呈正相關。  
Al, Si, K, Ti及Fe由pXRF測定的元素組成中，NAM組具有較高的Al, K, Ti, Fe濃度，特別是Fe濃度與SGE組差異最大，這符合NAM組較高黏粒含量的特徵 (但話說這組圖似乎legend寫反了，我選擇相信內文)。  
XRD結果中，由於是整體土壤的結果，以quartz為最主要的礦物 (因為砂粒基本上都是quartz吧，那個圖譜不放大來看只有兩根quartz波峰在4.26&#8491;及3.343&#8491;，更不用說3.343&#8491;的波峰直接蓋掉了illite在這裡也會有的波峰)，土壤也缺少muscovite。我個人覺得XRD的結果只照出了兩根quartz peaks，但是這個含量可以估算砂粒含量，砂粒含量又和黏粒含量成負相關，因此可以說是利用quartz含量去預測與其相反的黏粒含量吧。  
  
**Model performance**  
單獨儀器且相同組別土壤的比較中，pXRF是預測CEC最好的儀器
- NAM: CCC = 0.79, RMSE = 64.9 mmol<sub>c</sub> kg<sup>-1</sup>
- SGE: CCC = 0.85, RMSE = 80.0 mmol<sub>c</sub> kg<sup>-1</sup>  
  
至於黏粒含量則較有差異，NAM組的黏粒預測一樣是pXRF達到最好的效果  
- NAM: CCC = 0.89, RMSE = 5.2%  
  
而預測SGE組黏粒含量則是由XRD勝出  
- SGE: CCC = 0.91, RMSE = 5.7%  
  
但值得一提的是，各組的預測能力其實並沒有非常明顯的差距，CCC值均達0.77以上，RMSE也沒有相差太多。預測CEC時效果最差的是XRD，可想而知因為大部分smectite的波峰都被蓋過去了，無法偵測smectite成為一大敗筆，雖然作者說效果較差但XRD在預測NAM組及SGE組時CCC分別也有0.77與0.80。  
預測黏粒含量時效果最差的是VisNIR (但CCC也分別有0.85及0.91，要我說的話其實沒有到很差)，這是由於VisNIR沒有quartz的訊號，因此和砂粒相關的quartz便無法測量。  
  
結合儀器且相同組別土壤的比較中，所有組別的CCC都提升了1-12%，且RMSE均下降10-46%，以VisNIR與pXRF結合達到最好的CEC預測效果  
- NAM: CCC = 0.82, RMSE = 58.6 mmol<sub>c</sub> kg<sup>-1</sup>
- SGE: CCC = 0.87, RMSE = 74.0 mmol<sub>c</sub> kg<sup>-1</sup>  
  
以及黏粒含量預測效果  
- NAM: CCC = 0.95, RMSE = 3.3%  
- SGE: CCC = 0.94, RMSE = 4.3%  
  
至於添加XRD資料達成三組儀器結合的組別，預測能力並沒有顯著上升，這代表VisNIR和pXRF兩者便可作足夠的預測，XRD若能納入黏土礦物的資料可能效果會更好。作者也強調應該繼續探尋土壤性質與光譜訊號之間的關聯性。  
  
**Transfer model performance**  
這部分利用跨組交互驗證的方法，將NAM組的模型使用在SGE組做驗證，反之亦然。  
將一組的模型使用在另一組上所獲得的預測效果比同組內預測較為差，RMSE比組內驗證高了2-3倍。這樣的狀況下，在CEC的預測上XRD比其餘兩種儀器都具有更好的效果  
- NAM模型-SGE驗證: CCC = 0.52, RMSE = 167 mmol<sub>c</sub> kg<sup>-1</sup>
- SGE模型-NAM驗證: CCC = 0.37, RMSE = 175 mmol<sub>c</sub> kg<sup>-1</sup>  
  
而黏粒含量則是由VisNIR與XRD分別取得最好的效果
- NAM模型-SGE驗證: XRD最佳，CCC = 0.85, RMSE = 9.49%
- SGE模型-NAM驗證: VisNIR最佳，CCC = 0.72, RMSE = 10.2%
  
另外跨組驗證的所有儀器組合都顯著提升預測的準確程度。XRD在組間驗證表現亮眼，可能因為XRD的晶體繞射圖譜對於不同區域的土壤是不會改變的，但VisNIR與pXRF的相關性卻可能隨礦物組成與有機碳含量改變而影響，因此VisNIR與pXRF的robustness相較XRD圖譜為低，這兩個儀器需要針對當地的母質、環境因素做校正。  
  
### Comment  
這篇文章最創新的地方應該是納入XRD圖譜做預測，並且有進行組間交互驗證。XRD的預測能力有點出乎我的意料之外，畢竟他的圖譜看起來就是兩根quartz的峰，在組內驗證時每種儀器的效果其實都很好，CCC都很高，RMSE很小，但跨組驗證時問題就出現了，因為proximal sensor的訊號-性質關聯性與土壤的環境因素有關 (例如礦物組成就會有很大差異)，而此時XRD的好處便浮現了，由於礦物特徵的d-spacing不會隨著環境因素改變，跨組造成的影響對XRD問題不大，反而其他儀器的問題就顯現出來了。  
要解決這個問題的方法我想只有一個，而且作者也說了，那就是進一步探討土壤性質與訊號之間的關聯性，建立直接的連結，才能夠在不同組土壤中達到準確的預測。  
  
### 英文單字  
meandering：(adj.) 彎曲的  
horticulture：(n.) 園藝
