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
簡單線性迴歸用於呈現兩組數據中的相關性 (correlation)，並且進一步以數學模型建立兩個變數X與Y之間的關係，例如我們想知道增加1公斤氮肥用量時，水稻產量會增加多少公斤，這就是線性迴歸可以告訴我們的。  
  
簡單線性迴歸可將變數x與變數y的關係以線性表示成一條直線  
$$y = \beta_0+ \beta_1 x + \varepsilon $$  
其中x稱作獨立變數 (independent variable)，y則稱作依變數 (dependent variable)。  
&beta;<sub>0</sub>是直線的截距，&beta;<sub>1</sub>是直線的斜率，&beta;<sub>1</sub>又被稱為迴歸係數 (regression coefficient)，&epsilon;則是誤差 (error)，又稱為殘差 (residual)。  
  
### 簡單線性迴歸的方程式建立  
計算迴歸方程式最常見的方法是最小平方法 (least squares)，這個方法就是求得誤差項&epsilon;最小。  
假設我們所要估計的方程式為$$\widehat{y} =  \widehat{\beta_0} + \widehat{\beta_1} x$$，加了帽子表示為估計，那麼誤差項就是把實際的y值減去估計值，為避免正負抵消所以平方。  
$$S(\widehat{\beta_0},\ \widehat{\beta_1}) = \sum_{i=1}^{n} (y_i-\widehat{\beta_0}-\widehat{\beta_1}x_i)^2$$  
求這個含有&beta;<sub>0</sub>與&beta;<sub>1</sub>的多項式之最小值發生時的&beta;<sub>0</sub>與&beta;<sub>1</sub>，使用微分如下  
$$\begin{aligned}
\frac{\partial S(\widehat{\beta_0},\ \widehat{\beta_1})}{\partial \widehat{\beta_0}} &= -2\sum (y_i-\widehat{\beta_0}-\widehat{\beta_1}x_i)=0\\
\frac{\partial S(\widehat{\beta_0},\ \widehat{\beta_1})}{\partial \widehat{\beta_1}} &= -2\sum (y_i-\widehat{\beta_0}-\widehat{\beta_1}x_i)x_i=0
\end{aligned}$$  
常數-2都可以約分掉，把summation展開成三項後，上兩式可整理為  
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
$$\widehat{\beta_1} [\sum x_i^2 - \frac{(\sum x_i)^2}{n}] = \sum x_i y_i - \frac{\sum x_i \times \sum y_i}{n} \\$$  
$$\begin{aligned}
\widehat{\beta_1} 
&= \frac{\sum x_i y_i - \frac{\sum x_i \times \sum y_i}{n}}{\sum x_i^2 - \frac{(\sum x_i)^2}{n}} \\
&= \frac{\sum x_i y_i -\frac{\sum x_i \times \sum y_i}{n} - \frac{\sum x_i \times \sum y_i}{n} + \frac{\sum x_i \times \sum y_i}{n}}{\sum x_i^2 -2 \frac{(\sum x_i)^2}{n} + \frac{(\sum x_i)^2}{n}} \\
&= \frac{\sum x_i y_i -\overline y \times \sum x_i - \overline x \times \sum y_i + n\ \overline x\ \overline y}{\sum x_i^2 - 2 \overline x \sum x_i + n \overline x^2}\\
&= \frac{\sum (x_i-\overline x)(y_i - \overline y)}{\sum (x_i - \overline x)^2}\\
&=\frac{S_{xy}}{S_{xx}}
\end{aligned}$$  
如何，意不意外，迴歸係數&beta;<sub>1</sub>就是S<sub>xy</sub>/S<sub>xx</sub>，不懂這兩個平方和的可以複習[相關係數](https://lloydychuang.github.io/statistic/2021/08/05/correlation.html)，求得迴歸係數後得到  
$$\widehat \beta_0 = \overline y - \widehat \beta_1 \overline x$$  
如此即可得到迴歸直線$$\widehat{y} =  \widehat{\beta_0} + \widehat{\beta_1} x$$，要注意到**數據的平均值一定會落在迴歸直線上**。  
  
### Multiple linear regression (多元線性迴歸)  
多元線性迴歸，又稱複迴歸，基本上換湯不換藥，是用於呈現一組依變數y與k組獨立變數x<sub>1</sub>、x<sub>2</sub>、x<sub>3</sub>......到x<sub>k</sub>之間的線性關係，變數的迴歸係數大小會代表這個變數對於預測y的貢獻程度，迴歸係數越大，表示這個獨立變數只要變化一點就會影響很大。  
$$y = \beta_0+ \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_3 + ... + \beta_k x_k + \varepsilon $$  
建立複迴歸方程式的方法也是最小平方法，原則上跟簡單線性迴歸一樣，只是因為變數很多，要微分很多次，就不展開計算過程 (反正我們也是用`lm`函數解決一切對吧)。  
  
### 迴歸的假設檢定  
簡單線性迴歸與多元線性迴歸都可以進行假設檢定，且原理類似，都是使用變方分析 (ANOVA)，當我們成功預測出一條迴歸線之後，通常有變異 (誤差) 存在。  
實際測量的數值為$$y_i$$，我們預測的數值為$$\widehat y_i$$，並且平均值為$$\overline y$$。此時測量值與平均值的差就是總變異為 ($$y_i - \overline y$$)，而迴歸線可以解釋的變異是預測值與平均值的差 ($$\widehat y_i - \overline y$$)，通常總變異是比迴歸所解釋的變異還要高的，相減之後的差值就是迴歸線無法解釋的變異，即殘差 (residual)。為了計算變異，我們將這些數值都平方後加總為平方和 (sum of squares)。  
$$\begin{aligned}
y_i - \overline y &= (\widehat y_i - \overline y) + (y_i - \widehat y_i) 將此式左右平方並展開\\
\sum (y_i - \overline y)^2 &= \sum(\widehat y_i - \overline y)^2 + \sum(y_i - \widehat y_i)^2 \\
總變異 &= 迴歸解釋的變異 + 殘差平方和 \\
SST &= SSR\ +\ SSE
\end{aligned}$$  
如果是簡單線性迴歸的話，這三個平方和可進一步表示如下  
- SST (total)：總平方和 = $$\sum (y_i - \overline y)^2 = S_{yy}$$
- SSR (regression)：迴歸平方和 = $$\sum(\widehat y_i - \overline y)^2 =  \sum (\beta_0 + \beta_1 x_i - \beta_0 - \beta_1 \overline x)^2 = \beta_1^2 \sum (x_i - \overline x)^2 = \beta_1^2 S_{xx} = \beta_1 S_{xy}$$  
- SSE (error)：誤差平方和 = SST-SSR = $$S_{yy}- \beta_1 S_{xy}$$
  
多元複迴歸時計算則要用到矩陣，比較複雜，就不展開。  
檢定時依序可檢定 (1) 整體的迴歸效果 (2) 迴歸係數 (3) 截距  

**(1) 整體的迴歸效果檢定**  
使用ANOVA，要檢定的是迴歸所解釋的變異 (SSR) 是否比誤差的變異 (SSE) 來的多，如果由迴歸解釋的變異比較多，就代表這個迴歸是好的。  
- 虛無假設 (H<sub>0</sub>)：&beta;<sub>1</sub> = &beta;<sub>2</sub> = &beta;<sub>3</sub> = ... = &beta;<sub>k</sub> = 0 全部的迴歸係數都是0  
- 對立假設 (H<sub>1</sub>)：至少一個迴歸係數不是0  
      
代表迴歸變異的平方和是SSR，其自由度 (degree of freedom) 是所使用的獨立變數數目k，如果是簡單線性迴歸則k = 1。  
把平方和除以自由度則得到均方 (mean square, MS)，分別計算迴歸的均方誤差 (MSR, regression) 與誤差的均方誤差 (MSE, error) 後相除即為F統計量 (F-statistic)。  
查找自由度為k/(n-k-1)的F分布 (F<sub>k, n-k-1</sub>) 相比較，若F<sub>0</sub> > F<sub>&alpha;, k, n-k-1</sub>則可拒絕虛無假說，接受對立假說，至少有一個迴歸係數不是0，這個迴歸模型是有效的。檢定時所需的參數整理成表格如下    
  
| 變異來源 | 自由度 | 平方和 | 均方誤差 | F統計量 |   
| :---: | :---: | :---: | :---: | :---: |   
| 迴歸 | k | SSR | MSR = SSR/k | F<sub>0</sub> = MSR/MSE |   
| 誤差 | n-k-1 | SSE = SST-SSR | MSE = SSE/(n-k-1) |  |    
| 總計 | n-1 | SST |  |  |     
{: .tablelines}   
  
每一個變數都要用掉一個自由度，截距也用掉一個自由度，因此誤差的自由度是n-k-1。
  
**(2) 迴歸係數的檢定**  
上面的檢定只能告訴你整體的模型，但並不能告訴你個別的迴歸係數是不是0，除非是簡單線性迴歸這種k = 1的狀況，那樣的話整體的檢定就等同於迴歸係數的檢定。  
如果有多個獨立變數的情況，**需要檢定k次**，個別檢定這些迴歸係數是否為0。  
- 虛無假設 (H<sub>0</sub>)：&beta;<sub>i</sub> = 0 
- 對立假設 (H<sub>1</sub>)：&beta;<sub>i</sub> &#8800; 0  
  
迴歸係數&beta;<sub>i</sub>的抽樣分布 (sampling distribution) 服從自由度n-k-1的t-distribution，其檢定統計量為  
$$t_0 = \frac{\beta_i-0}{\sqrt{Var(\beta_i)}} = \frac{\beta_i}{\sqrt{MSE/S_{xx}}}$$  
若t<sub>0</sub> > t<sub>&alpha;/2, n-k-1</sub>則可拒絕虛無假說，接受對立假說，這個迴歸係數不為0，如果是簡單線性迴歸的話這個檢定結果會跟 (1) 相同，但如果是複迴歸就要注意有些變數的迴歸係數可能不顯著。  
在建立複迴歸模型時，要確保模型內的每個變數都是有用的，也就是迴歸係數不為0，要達成這個方法常見可使用逐步迴歸 (stepwise regression) 每次增加/減少一個變數，從沒有變數開始一次增加一個顯著的變數稱為向前增加 (forward addition)，從所有變數開始一次刪除一個不顯著的變數則稱作往後刪除 (backward elimination)。  
  
**(3) 截距的檢定**  
和 (2) 同樣的道理也可以檢定截距&beta;<sub>0</sub>是否為0，這裡就直接列出t統計量了，假設方面和前一個大同小異，也符合自由度n-k-1的t分布。  
$$t_0 = \frac{\beta_0-0}{\sqrt{Var(\beta_0)}} = \frac{\beta_0}{\sqrt{MSE\ (\frac{1}{n} + \frac{\overline x^2}{S_{xx}})}}$$  
若t<sub>0</sub> > t<sub>&alpha;/2, n-k-1</sub>則可拒絕虛無假說，接受對立假說，這個迴歸係數不為0。  
  
### It's (not) all about R<sup>2</sup>  
在衡量模型時決定係數 (coefficient of determination, R<sup>2</sup>) 是很重要的指標，這次讓我們用變異的觀點來看，R<sup>2</sup>是可以被迴歸所解釋的變異百分比，所以自然而然  
$$R^2 = \frac{SSR}{SST} = 1-\frac{SSE}{SST}$$  
在簡單線性迴歸時就會跟上次在[相關係數](https://lloydychuang.github.io/statistic/2021/08/05/correlation.html)網誌講決定係數算法一樣。  
但是在加入的獨立變數越來越多時，比較多的變數自然會有比較多的變異，這可能會導致R<sup>2</sup>有膨脹的現象，所以有一個考慮到自由度校正的adjusted R<sup>2</sup>，計算如下  
$$Adjusted\ R^2 = 1-\frac{SSE/(n-k)}{SST/(n-1)}$$  
將變異SSE與SST除以自由度以校正因過多變數導致的膨脹效應，可以考慮使用，雖然實際上看到有特別強調校正的期刊文章也不多。  
  
### 基本假設    
為何基本假設會在最後提呢？因為這最重要但是非常多的文章都忽略了，在進行迴歸分析時，**資料和殘差都必須滿足基本假設**：
1. 獨立性 (independent)：殘差應該要是獨立的，我們可以繪製殘差圖 (residual plot) 來觀察是否有特定趨勢，若殘差有趨勢則表示有問題
2. 常態性 (normality)：資料與殘差都應該符合常態分布
3. 變方同質性 (homogeneity of variance)：可以使用Levene's test來檢測變方的一致性
4. 線性關係 (linearity)：預測的獨立變數與依變數必須呈線性關係 (殘差不用)
  
如果有基本假設未被滿足，通常可以透過轉換 (transform) 來讓資料滿足基本假設。  
  
### 資料的共線性 (collinearity)  
在複迴歸裡若變數之間具共線性 (即x之間彼此相關)，則模型會具有重複的變數，讓模型的效果被高估，此時可以衡量變異膨脹因子 (variance inflation factor, VIF)



待續
