---
layout: default
categories: Statistic
title:  "Pearson's correlation coefficient (相關係數)"
---  
## Regression analysis (迴歸分析)  
2021/08/05  
被CEC的實驗搞了整整兩天，明天還要繼續，淋洗已經兩天了都過不去。  
話說不知是迴歸還是回歸，我個人是偏向寫迴歸，畢竟寫回歸好像是要回去哪裡一樣。  
  
所謂的相關係數 (correlation coefficient) 來表示他們的相關性強弱，相關係數常以英文字母r或是希臘字母&rho;表示，其定義為  
$$\begin{aligned}
r = \frac{\sum_{i=1}^{N} (X_i-\mu_X)(Y_i-\mu_y) }{\sqrt{\sum_{i=1}^{N} (X_i-\mu_X)^2 \sum_{i=1}^{N} (Y_i-\mu_Y)^2} }=\frac{S_{XY}}{S_{XX} S_{YY}}  
\end{aligned}$$  
其中  
$$S_{XX} =  \sum_{i} (X_i -  \overline{X} )^2 \\
S_{YY} =  \sum_{i} (Y_i -  \overline{Y} )^2 \\
S_{XY} =  \sum_{i} (X_i -  \overline{X} )(Y_i - \overline{Y})$$  
  
r介於-1至1之間，越接近-1代表負相關，越接近1則代表正相關，接近0則是**無線性相關** (不是無相關!!)，將r平方後得到的介於0-1的值即為決定係數 (coefficient of determination, R<sup>2</sup>)，這三個數值S<sub>XX</sub>、S<sub>YY</sub>及S<sub>XY</sub>是所謂的平方和 (sum of squares, SS)，將各數值減去平均後再平方加總，可以用於呈現這組數據的變異 (分散) 程度。
  
### 相關係數的顯著性  
相關係數r的顯著性是很常做的測試，用R產出一大張相關係數表是很讓人心曠神怡的 (然後發現都不顯著QQ)。  
相關係數的顯著性測試



待續
