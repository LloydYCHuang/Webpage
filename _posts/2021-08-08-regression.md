---
layout: default
categories: Statistic
title:  "Regression analysis (迴歸分析)"
---  
## Regression analysis (迴歸分析)  
2021/08/10  
研究完相關係數之後發現迴歸跟相關密不可分，不如一次研究清楚，建議先看過[相關係數](https://lloydychuang.github.io/statistic/2021/08/05/correlation.html)的網誌。  
話說不知是迴歸還是回歸，我個人是偏向寫迴歸，畢竟寫回歸好像是要回去哪裡一樣，另外我覺得寫得很好的統計學用書 - 沈明來老師的生物統計學入門也是寫迴歸。  
  
### Simple linear regression (簡單線性迴歸)  
簡單線性迴歸也是用於呈現兩組數據中的相關性 (correlation)，並且進一步以數學模型建立兩個變數X與Y之間的關係，例如我們想知道增加1公斤氮肥用量時，水稻產量會增加多少公斤，這就是線性迴歸可以告訴我們的。  
  
簡單線性迴歸可將變數x與變數y的關係以線性表示成一條直線  
$$y = \beta_0+ \beta_1 x + \varepsilon $$  
其中x稱作獨立變數 (independent variable)，y則稱作依變數 (dependent variable)。  
&beta;<sub>0</sub>是直線的截距，&beta;<sub>1</sub>是直線的斜率，&beta;<sub>1</sub>又被稱為迴歸係數 (regression coefficient)，&epsilon;則是誤差 (error)，又稱為殘差 (residual)。  
  
### 簡單線性迴歸的方程式建立  
計算迴歸方程式最常見的方法是最小平方法 (least squares)，這個方法就是求得誤差項&epsilon;最小。  
假設我們所要估計的方程式為$$\widehat{y} =  \widehat{\beta_0} + \widehat{\beta_1} x$$，加了帽子表示為估計，那麼誤差項就是把實際的y值減去估計值  
$$S(\widehat{\beta_0},\ \widehat{\beta_1}) = \sum_{i=1}^{n} (y_i-\widehat{\beta_0}-\widehat{\beta_1}x_i)^2$$  
計算這個含有&beta;<sub>0</sub>與&beta;<sub>1</sub>的多項式之最小值，使用微分方式如下  
$$\begin{aligned}
\frac{\partial S(\widehat{\beta_0},\ \widehat{\beta_1})}{\partial \widehat{\beta_0}} &= -2\sum (y_i-\widehat{\beta_0}-\widehat{\beta_1}x_i)=0\\
\frac{\partial S(\widehat{\beta_0},\ \widehat{\beta_1})}{\partial \widehat{\beta_1}} &= -2\sum (y_i-\widehat{\beta_0}-\widehat{\beta_1}x_i)x_i=0
\end{aligned}$$  
常數-2都可以約分掉，把summation展開成三項後，上兩式的右半邊可整理為  
$$\begin{aligned}
n\widehat{\beta_0}+\widehat{\beta_1} \sum x_i &= \sum y_i\\
\widehat{\beta_0} \sum x_i + \widehat{\beta_1} \sum x_i^2 &= \sum x_i y_i
\end{aligned}$$  
上面兩式稱作**正規方程式 (normal equations)**，進一步解正規方程式 (不要怕，就是國中學的解方程式) 可以轉成這兩個式子  
$$\begin{aligned}
\widehat{\beta_0} \sum x_i + \frac{\widehat{\beta_1}}{n} (\sum x_i)^2 &= \frac{1}{n} (\sum x_i) \times (\sum y_i) \\
\widehat{\beta_0} \sum x_i + \widehat{\beta_1} \sum x_i^2 &= \sum x_i y_i
\end{aligned}$$  
再做進一步的解方程式就得到  
$$\widehat{\beta_0} [\sum x_i^2 - \frac{(\sum x_i)^2}{n}] = \sum x_i y_i - \frac{\sum x_i \times \sum y_i}{n} \\$$  
$$\widehat{\beta_0}$$

  
  
S(\widehat{\beta_0},\ \widehat{\beta_1}) = 
Y =  \widehat{\beta_0} + \widehat{\beta_1} X
### Multiple linear regression (多元線性迴歸)  
基本上換湯不換藥，用於呈現一組變數Y與多組變數X<sub>1</sub>、X<sub>2</sub>、X<sub>3</sub>......到X<sub>k</sub>之間的關係，亦可表示成一條直線。  
$$Y = \beta_0+ \beta_1 X_1 + \beta_2 X_2 + \beta_3 X_3 + ... + \beta_k X_k + \varepsilon $$

待續
