---
layout: default
categories: Statistic
title:  "Pearson's correlation coefficient (相關係數)"
---  
## Pearson's correlation coefficient (相關係數)  
2021/08/05  
被CEC的實驗搞了整整兩天，明天還要繼續，淋洗已經兩天了都過不去。  
距離大二的統計學已經過了三年，顯著性測試也快忘光了，雖然平時用R就好，但還是想整理一下相關係數的顯著性。  
  
### 何謂相關係數？  
在兩組資料之間有時存在著**相關性 (correlation)**，例如人的身高和體重可能大致呈現正相關，但是**相關性並不等於因果性 (causation)**，這是每個使用統計的人都需要注意到的問題，相關係數只能呈現兩組資料之間的相關性，並不代表一定有因果關係，這個有趣的網站<a href="http://tylervigen.com/spurious-correlations" target="_blank">Spourious Correlations</a>就整理了很多具有強烈相關性，但不具因果關係的資料，例如每年在泳池溺水的人數竟然跟尼可拉斯凱吉所出演的電影數有相關??  
  
在獲得兩組資料時，會利用所謂的相關係數 (correlation coefficient) 來表示他們的相關性強弱，而最常使用的就是**Pearson相關係數 (Pearson's correlation coefficient)**，又稱Pearson's product moment correlation coefficient (PPMCC)，母體的Pearson相關係數以希臘字母&rho;表示，而樣本的Pearson相關係數常以英文字母r表示。假設現在有資料組X與Y，其各自的母體平均為&mu;<sub>X</sub>與&mu;<sub>Y</sub>，則母體的Pearson相關係數可表示成以下的公式，分子是X與Y的共變異 (covariance)，分母則是兩者的標準差。   
$$\begin{aligned}
\rho &= \frac{\sum_{i=1}^{N} (X_i-\mu_X)(Y_i-\mu_Y) }{\sqrt{\sum_{i=1}^{N} (X_i-\mu_X)^2 \sum_{i=1}^{N} (Y_i-\mu_Y)^2} }\\   
&=\frac{Cov(X,Y)}{\sigma_X \sigma_Y}  
\end{aligned}$$    
相關係數是沒有單位的，而樣本方面以樣品平均值代替母體平均值後得到的Pearson相關係數表示如下  
$$\begin{aligned}
r &= \frac{\sum_{i=1}^{N} (X_i-\overline X)(Y_i-\overline Y) }{\sqrt{\sum_{i=1}^{N} (X_i-\overline X)^2 \sum_{i=1}^{N} (Y_i-\overline Y)^2} }\\
&=\frac{S_{XY}}{\sqrt{S_{XX} S_{YY}}}
\end{aligned}$$   
其中三個數值S<sub>XX</sub>、S<sub>YY</sub>及S<sub>XY</sub>是所謂的平方和 (sum of squares, SS)，將各數值減去平均後再平方加總，可以用於呈現這組數據的變異 (分散) 程度。   
$$S_{XX} =  \sum_{i} (X_i -  \overline{X} )^2 \\
S_{YY} =  \sum_{i} (Y_i -  \overline{Y} )^2 \\
S_{XY} =  \sum_{i} (X_i -  \overline{X} )(Y_i - \overline{Y})$$  
  
r介於-1至1之間，越接近-1代表負相關，越接近1則代表正相關，接近0則是**無線性相關** (不是無相關!!)，將r平方後得到的介於0-1的值即為決定係數 (coefficient of determination, R<sup>2</sup>)，決定係數R<sup>2</sup>的數值就代表了有多少比例的變異可以被這個相關性解釋，1-R<sup>2</sup>則是未被解釋的變異。  
  
### 相關係數的顯著性  
相關係數的顯著性測試使用t-test  
- 虛無假設 (H<sub>0</sub>)：&rho;=0 沒有相關性  
- 對立假設 (H<sub>1</sub>)：&rho;&#8800;0 有相關性  
  
在決定顯著水準&alpha;後，需取得t統計量 (t-statistic)，首先相關係數的標準誤差 (standard error, SE) 可以表示如下  
$$\begin{aligned}
SE_r = \sqrt {\frac{1-r^2}{n-2}}
\end{aligned}$$  
因此相關係數的t統計量為  
$$\begin{aligned}
t_0 = \frac{r-0}{\sqrt {\frac{1-r^2}{n-2}}} = r \sqrt{\frac{n-2}{1-r^2}}
\end{aligned}$$  
這個t統計量服從一個自由度n-2的t分布 (t<sub>&alpha;/2, n-2</sub>)，若t<sub>0</sub> > t<sub>&alpha;/2, n-2</sub>則可拒絕虛無假說，接受對立假說，兩組數據有相關性。  
  
### 後話  




待續
