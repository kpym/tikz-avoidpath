# tikz-avoidpath
This is a TikZ library named *avoidpath* that could be useful to draw contours of complex integrals avoiding poles.  

## How to use it
* Put `tikzlibraryavoidpath.code.tex` file in a folder accessible by latex. 
  For example in the same folder as your main file.
* Load the library with 
```latex
\usetikzlibrary{avoidpath}
```

## Basic usage examples

![example 3](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example3.png)
![example 4](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example4.png)
![example 5](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example5.png)
![example 5b](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example5b.png)
![example 7](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example7.png)

## More complexe examples

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

* Example 2 
```latex
  \begin{tikzpicture}[thick]
    \draw[help lines] (-.5,-.5) grid +(4,4);
    \draw[preaction={pattern=north west lines, pattern color=gray},
          with arrows at positions={18mm,55mm,95mm,1}]
      (0,0)
        to[avoid={pole={(1,0)},radius=2mm}]
      (1.5,0)
        to[avoid={pole={(2,0)},radius=2mm}]
      (2.9,0)
        arc(0:90:2.9) -- cycle
      (1,1) circle[reversed with radius=5mm];
  \end{tikzpicture}
  ```
![example 2](https://raw.githubusercontent.com/kpym/tikz-avoidpath/master/examples/avoidpath-example2.png)

## Additional styles

* `[with arrows=35mm]` put arrows every 35mm
* `[with arrows at positions={35mm,70mm,140mm}]` put arrows at 35mm,70mm,140mm
* `circle[reversed with radius=1cm]` style to draw reversed circle (helpful to not fill inside)

## License

This file may be distributed and/or modified

  1. under the LaTeX Project Public License and/or
  2. under the GNU Public License.

Both licenses are available in the LICENSES folder.

