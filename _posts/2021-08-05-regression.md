---
layout: default
categories: Statistic
title:  "Regression analysis (迴歸分析)"
---  
## Regression analysis (迴歸分析)  
2021/08/05  
被CEC的實驗搞了整整兩天，明天還要繼續，淋洗已經兩天了都過不去。  
話說不知是迴歸還是回歸，我個人是偏向寫迴歸，畢竟寫回歸好像是要回去哪裡一樣。  
  
### Simple linear regression (簡單線性迴歸)  
簡單線性迴歸用於呈現兩組數據中的相關性 (correlation)，若要呈現變數X與變數Y之間的相關性，以簡單線性迴歸可以表示成一條直線  
$$Y = \beta_0+ \beta_1 X + \varepsilon $$  
其中的&beta;<sub>0</sub>是直線的截距，&beta;<sub>1</sub>是直線的斜率，又被稱為迴歸係數 (regression coefficient)，&epsilon;則是誤差 (error)。  
在產出迴歸線之後，還會用所謂的相關係數 (correlation coefficient) 來表示他們的相關性強弱，相關係數常以英文字母r或是希臘字母&rho;表示，其定義為  
$$r = \frac{\sum_{i=1}^{N} (X_i-\mu_X)(Y_i-\mu_y) }{\sqrt{\sum_{i=1}^{N} (X_i-\mu_X)^2 \sum_{i=1}^{N} (Y_i-\mu_Y)^2} }=\frac{S_{XY}}{S_{XX} S_{YY}}  $$  
其中  
$$S_{XX} =  \sum_{i} (X_i -  \overline{X} )^2 \\
S_{YY} =  \sum_{i} (Y_i -  \overline{Y} )^2 \\
S_{XY} =  \sum_{i} (X_i -  \overline{X} )(Y_i - \overline{Y})$$  
  
而r介於-1至1之間，這三個數值S<sub>XX</sub>、S<sub>YY</sub>及S<sub>XY</sub>是很重要的，因為他們就是所謂的平方和 (sum of squares, SS)，請務必先記好這三個數值，
  
### 迴歸係數的顯著性




待續
