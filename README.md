# tikz-avoidpath
This is a TikZ library named *avoidpath* that could be useful to draw contours of complex integrals avoiding poles.  

## Examples

* Example 1 
```latex
\documentclass[border=7mm]{standalone}
\usepackage{tikz}
\usetikzlibrary{avoidpath}

\begin{document}
  \begin{tikzpicture}
    \draw [avoid={pole={(P)},neck=2mm},with arrows=21mm]
         (0,0) node[scale=3](P){.}
        +(1,1mm) to[avoid={radius=2cm}]
        +(1,-1mm) to[avoid]
        +(1,1mm);
  \end{tikzpicture}
\end{document}
```
![example 1](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example1.png)
