---
layout: default
categories: [Journal comments]
title:  "Comment#11 On the discrimination of soil samples by derivative diffuse reflectance UV–vis-NIR spectroscopy and chemometric methods"
---  
## Comment#11 On the discrimination of soil samples by derivative diffuse reflectance UV–vis-NIR spectroscopy and chemometric methods  
2021/07/26  
作夢也想不到會寫超過10篇網誌，今天的內容是鑑識科學，也不能只停留在土壤及農業，多角化才能開創藍海對吧。雖然這次的內容不是我使用的可攜式儀器，但一樣的光譜範圍，原理是差不多的。  
  
Topic:  
Chauhan, R., Kumar, R., Kumar, V., Sharma, K., and Sharma, V. 2021. On the discrimination of soil samples by derivative diffuse reflectance UV–vis-NIR spectroscopy and chemometric methods. Forensic Science International, 319, 110655.  
<a href="https://doi.org/10.1016/j.forsciint.2020.110655" target="_blank">https://doi.org/10.1016/j.forsciint.2020.110655</a>  
  
### Introduction  
在鑑識科學 (forensic science) 領域中，土壤是一種重要的微量物證 (trace evidence)。由於其可轉移的性質 (transferable property)，土壤可以附著在嫌疑犯的衣著、鞋子或是車輛。以往的土壤分析包含化學性質、物理性質分析的速度較慢，因此光譜法的快速便成為一大優點，本文所使用的UV-vis-NIR光譜法更是其中的佼佼者。UV-vis-NIR光譜法可辨識並定量土壤中的有機/非有機物質，與土壤學不同的是，鑑識科學中通常能夠取得的土壤樣品量是非常少的 (誰像你土壤學用鏟子挖)，且光譜法尚未被廣泛應用。  
但是，由於光譜的複雜性，必須利用統計方法才有辦法分辨不同來源土壤的差異性，因此本文會使用一些統計方法。而為了減少樣品前處理，因此並不使用桌上型UV-vis-NIR光譜儀常用的穿透式 (transmission mode)，而是使用擴散反射式 (diffuse reflectance mode)，就如同在土壤近地感測上所使用的。  
另外樣品還會經過加熱處理，是因為要模擬縱火 (arson) 事故中的殘留土壤。這段前言讀完只覺得應用性無窮。  
  
### Materials and methods  
**土壤收集**  
在印度西北部收集五個州的土壤，包含Rajasthan (Y1)、Haryana (Y2)、Chandigarh Tricity (Y3)、Punjab (Y4) 及Delhi NCR (Y5)，每個州內又有為數不一的採樣城市，總共18個地點。在劃定一個長寬皆為10 m的區域後，土壤中的人造物質會先被移除，從表土及15 cm深處收集各500 g土壤，每個地點收集五重複 (四個角與中央)，表土編號S1-S18 (surface)，15 cm深處的土編號D1-D18 (depth)。樣品室溫風乾後通過10 mesh的篩網 (2 mm)，但保留一部分不過篩以觀察過篩的影響，表土樣本另外以650&deg;C烘乾觀察。  
  
**光譜方法**  
使用Shimadzu 2600 Series UV-vis-NIR光譜儀搭配ISR-2600 plus Integrating Sphere (一個搭配零件，以圓形的鏡面聚集光線)，僅使用0.5-1 mg的土樣進行量測。空白校正使用硫酸鋇 (barium sulfate, BaSO<sub>4</sub>) 粉末作為100%反射的參考，共量測200-1400 nm波長範圍的反射率，但700-1400 nm波長的特徵較少故此段波長不進行後續統計分析。  
擴散反射的反射率光譜先轉換成吸光度，這部分利用Kubelka-Munk (K-M) transformation，並取得一階微分的光譜。重複性有經過五重複的測試結果為重複性良好。  
  
**統計分析**  
Discriminating power (DP)：  
作者以人工方式比較不同波峰在每種土壤出現的差異性，來自不同兩地的土壤就是一組可能的區別，而觀察兩者的波峰位置，若波峰位置一致，則代表並無法被區別出來，這就是Discriminating power，衡量樣品能夠被光譜資料區別的能力，DP的計算方法為  
$$DP = \frac{Number \, of \, Discrimated \, Sample}{Number \, of \, Possible \, Sample \, Pair} \times 100$$  
  
Cluster analysis：  
目的是要分群 (clustering) 的話，兩種常見的方法包含hierarchical clustering analysis (HCA) 及k-means，但在使用這分群方法之前先以standard normal variate (SNV) 方法進行標準化。在260-600 nm範圍內的光譜經SNV後以1 nm的解析度進行HCA。  
  
Linear discriminant function analysis (LDA)：  
由於表土是最容易被帶走而成為物證的，故僅對表土進行分類 (classification)，而分類的方法為LDA，可以將組內差異最小化並且使組間差異最大化，並且以leave-one-out cross-validation作為交叉驗證方法。  
衡量標準包括canoical correlation、eigenvalue及Wilks' Lambda。  
  
### Results and discussions  
**光譜特徵**  
呈現的是光譜的一次微分，且經過SNV與Savitzky-Golay平滑化來去除雜訊，作者辨識到的特徵中較為重要的有  
- 285 nm: Lignin , humic acid (double bonds)
- 290 nm: Aromatic
- 312, 355, 395 nm: Glutamic acid and Fulvic acid
- 430 nm: Fe<sup>3+</sup> oxide
- 460 nm: hematite and goethite
- 600 nm: Zinc  
  
其他還有可以參考作者原文。整體而言200-260 nm代表芳香環、不飽和的有機化合物與可溶性有機碳；261-280 nm代表芳香環與腐植化 (humification) 程度；281-300 nm與&#960;-&#960;&#42;的電子有關 (因此也跟芳香環有關)；301-500 nm則與glutamic acid, fulvic acid, Pb及鐵氧化礦物有關；501-600 nm與黏土礦物、針鐵礦 (hematite) 及Zn有關；最後601-700 nm則跟鐵氧化物有關。  
  
**Peak to peak comparison**  
在人工比對出現波峰後，有些組別的光譜特徵相當一致，這些波峰特徵相近的組別在人為比對中沒有被區別出來，也多為鄰近地區的土樣，這些無法被區分的組別即為DP計算中的分子，而分母為所有可能的區別，即為N(N-1)/2。  
表土DP = 96.08%，15 cm深度的土DP = 97.39%，因此分別程度是很好的。
  
待續





