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
$$\begin{aligned}
\widehat{\beta_0} 
&= \frac{\sum x_i y_i - \frac{\sum x_i \times \sum y_i}{n}}{\sum x_i^2 - \frac{(\sum x_i)^2}{n}} \\
&= \frac{\sum x_i y_i -\frac{\sum x_i \times \sum y_i}{n} - \frac{\sum x_i \times \sum y_i}{n} + \frac{\sum x_i \times \sum y_i}{n}}{\sum x_i^2 -2 \frac{(\sum x_i)^2}{n} + \frac{(\sum x_i)^2}{n}} \\
&= \frac{\sum x_i y_i -\overline y \times \sum x_i - \overline x \times \sum y_i + n\ \overline x\ \overline y}{\sum x_i^2 - 2 \overline x \sum x_i + n \overline x^2}\\
&= \frac{\sum (x_i-\overline x)(y_i - \overline y)}{\sum (x_i - \overline x)^2}\\
&=\frac{S_{xy}}{S_{xx}}
\end{aligned}$$  
如何，意不意外，迴歸係數&beta;<sub>1</sub>就是S<sub>xy</sub>/S<sub>xx</sub>，不懂的可以複習[相關係數](https://lloydychuang.github.io/statistic/2021/08/05/correlation.html)，求得迴歸係數後即可得到  
$$\widehat \beta_0 = \overline y - \widehat \beta_1 \overline x$$  
  
### Multiple linear regression (多元線性迴歸)  
多元線性迴歸，又稱複迴歸，基本上換湯不換藥，是用於呈現一組變數y與多組變數x<sub>1</sub>、x<sub>2</sub>、x<sub>3</sub>......到x<sub>k</sub>之間的線性關係。  
$$y = \beta_0+ \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_3 + ... + \beta_k x_k + \varepsilon $$  
建立複迴歸方程式的方法也是最小平方法，原則上跟簡單線性迴歸一樣，只是因為變數很多，要微分很多次，就不展開計算過程 (反正我們也是用`lm`函數解決一切對吧)。  
  
### 迴歸的假設檢定  
簡單線性迴歸與多元線性迴歸都可以進行假設檢定，且原理類似，都是使用變方分析 (ANOVA)，當我們成功預測出一條迴歸線之後，通常有變異 (誤差) 存在，總變異為$$y_i - \overline y$$，而我們的迴歸線可以解釋一部分的變異為$$\widehat y_i - \overline y$$，那麼他們相減之後就是迴歸線無法解釋的誤差，如下的加總起來  
$$\begin{aligned}
y_i - \overline y &= (\widehat y_i - \overline y) + (y_i - \widehat y_i) \\
\sum (y_i - \overline y)^2 &= \sum(\widehat y_i - \overline y)^2 + \sum(y_i - \widehat y_i)^2 \\
總變異 &= 迴歸解釋的變異 + 其他的變異 \\
SST &= SSR\ +\ SSE
\end{aligned}$$  
這三個平方和 (sum of squares) 為  
- SST (total)：總平方和 = $$\sum (y_i - \overline y)^2 = S_{yy}$$
- SSR (regression)：迴歸平方和 = 
- SSE (error)：誤差平方和 = 
  
\sum(y_i - \widehat y_i)^2 = \sum (y_i - \widehat \beta_0 - \widehat \beta_1 x_i)^2\\
\sum(\widehat y_i - \overline y)^2 = 


待續
