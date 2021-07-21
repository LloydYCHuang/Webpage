# This is the backup of codes  
先不要透漏太多我的個人訊息XD  
可以研究的內容：  
illite轉變成vermiculite或是smectite的差異  
anti-gibbsite effect  
  
You can use the [editor on GitHub](https://github.com/LloydYCHuang/Webpage/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown
---
title: "networkD3.demo"
output: html_document
---

```{r message =FALSE,warning=FALSE}
library(networkD3)
src <- c("K", "K", "Na", "Na", "Ca", "Ca", "N")
target <- c("Na", "Ca", "N", "Ca","S", "F", "P")
networkData <- data.frame(src, target)
simpleNetwork(networkData)  
```

```{r message =FALSE,warning=FALSE}
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

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/LloydYCHuang/Webpage/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

HTML寫法
<ul style="line-height:200%">
  <li style="line-height:200%">123</li>
  <li>123</li>
</ul>


