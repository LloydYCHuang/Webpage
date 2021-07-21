---
layout: default
categories: R
title:  "Force-directed graph的R實作"
---
## Force-directed graph的R實作  
2021/07/21  
今天要來學習force-directed graph，最早看到這種呈現方式是在大四下學期專題討論所選用的文章<a href="https://doi.org/10.1016/j.geoderma.2019.113997" target="_blank">Enhanced soil profile visualization using portable X-ray fluorescence (PXRF) spectrometry</a>當中的呈現方式，<a href="https://idatavisualizationlab.github.io/Soil/demos.html" target="_blank">連結在此</a>，那時我馬上被這種呈現方法震撼到了，而且心想總有一天要學會這種方法。  
  
### 何謂force-directed graph?  
Force-directed graph是一種繪圖的方法，在平面或空間中配置節點 (node) 與連線 (edge)，並利用演算的方式配置節點位置以及連線的長度，使不同連線盡可能不相交、連線長度也均等。  
演算法參與的部分是在所謂的力 (force)，利用如同彈簧一般的虎克定律掌管連線兩端節點的距離，利用如同靜電排斥力一般的庫倫定律掌管沒有連線的兩個節點的距離，也就是說，藉由運算不同節點之間的引力及斥力，可以將圖形保持在簡潔有力的樣子，也可以與圖片互動進而改變圖片，想成一個自己調整長相的圖片吧！  
要用到force-directed graph就須使用到以JavaScript所寫成的Data-Driven Documents (D3)，因此使用的R套件也是奠基於D3的。  
  
### 以R繪製force-directed graph  
學習的過程比我想像中簡單，已經有非常棒的<a href="https://christophergandrud.github.io/networkD3/" target="_blank">networkD3套件解說</a>，完全可以自己上手，有興趣的人建議直接看<a href="https://cran.r-project.org/web/packages/networkD3/networkD3.pdf" target="_blank">套件的使用說明</a>。    
我們使用的套件稱為`networkD3`，是將D3使用到R裡面的套件，首先下載並library出來。   
```
install.packages("networkD3")  
library(networkD3)  
```  
**simpleNetwork**  
函數`simpleNetwork`可以繪製最為基礎的圖，前面說過force-directed graph是以連接點跟點所繪製的，因此要建立資料時，就必須清楚連接點-目標，例如底下這個假想的土壤元素相關圖。  
```
src <- c("K", "K", "Na", "Na", "Ca", "Ca", "N")
target <- c("Na", "Ca", "N", "Ca","S", "F", "P")
networkData <- data.frame(src, target)
simpleNetwork(networkData, fontSize = 20, fontFamily = "sans-serif")  
```  
<iframe src="https://lloydychuang.github.io/assets/graph-demo1.html" scrolling="no"></iframe>  
而這個函數可以操作的部分如下  
```
simpleNetwork(Data, Source = 1, Target = 2,       # 指定哪一個column是source/target
              height = NULL, width = NULL,        # 輸出圖高度
              linkDistance = 50, charge = -30,    # 有關力的參數
              fontSize = 7, fontFamily = "serif", # 剩下就是一些美編了，opacity是透明度，在R裡面常見
              linkColour = "#666", nodeColour = "#3182bd", opacity = 0.6, zoom = F)
```
  
**forceNetwork**  
函數`forceNetwork`可以處理更複雜一點的圖，但要輸入的也更複雜，先來看他可操作的部分
```
forceNetwork(Links, Nodes, Source, Target, Value, NodeID, Nodesize, Group,
             height = NULL, width = NULL,
             colourScale = JS("d3.scaleOrdinal(d3.schemeCategory20);"), fontSize = 7,
             fontFamily = "serif", linkDistance = 50,
             linkWidth = JS("function(d) { return Math.sqrt(d.value); }"),
             radiusCalculation = JS(" Math.sqrt(d.nodesize)+6"), charge = -30,
             linkColour = "#666", opacity = 0.6, zoom = FALSE, legend = FALSE,
             arrows = FALSE, bounded = FALSE, opacityNoHover = 0,
             clickAction = NULL)
```
美編的部分先不論，最明顯的是需要輸入的變數增加成8個了  
- `Links`：就是畫幾條線的部分，每個link要包含Source、Target及Value
- `Nodes`：幾個節點，每個node要包含NodeID、Nodesize及Group
- `Source`：出發點，以數字從0開始編號
- `Target`：終點，以數字從0開始編號
- `Value`：線的粗細
- `NodeID`：節點命名，要注意的是在這裡給定第一個node時，會從0開始編號，所以編號要注意！
- `Nodesize`：節點大小
- `Group`：若要依照組別著色，就要給定group  
  
現在也實際創造一組資料來做示範  
```
src <- c(0, 0, 0, 0, 1, 1, 1, 2, 2, 3, 4, 5)
target <- c(1, 2, 3, 4, 4, 5, 6, 3, 4, 6, 6, 6)
value <- c(1, 2, 3, 4, 5, 6, 7, 1, 2, 3, 4, 5)
links <- data.frame(src, target, value)
colnames(links) <- c("source", "target", "value")

name <- c("K", "Na", "Ca", "Mg", "Al", "Si", "P")
group <- c(1, 2, 3, 1, 1, 2, 2)
size <- c(1, 1, 2, 2, 3, 3, 4)
nodes <- data.frame(name, group, size)
colnames(nodes) <- c("name", "group", "size")

forceNetwork(Links = links, Nodes = nodes,
             Source = "source", Target = "target",
             Value = "value", NodeID = "name",
             Group = "group", opacity = 0.8, Nodesize="size")
```  
有了這種繪圖工具，可以創造更為有說服力的圖示，因此下一步就是匯出檔案，以`saveNetwork`可以匯出獨立的html檔
```  
library(magrittr)
  
simpleNetwork(networkData) %>%
saveNetwork(file = 'demo.html')
```  
若要放入到RMarkdown後輸出html也是完全OK的，那如果要插入到另一個html的網站裡呢？很遺憾的我找了一個晚上還是不知道如何將繪製的可以互動的force-directed graph插入到Github Pages裡面。  

