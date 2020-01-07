# JuliaTEX
## Introduction 
I've been searching for how to typeset  Julia in TEX files, the problem is that package  Minted doesn't work for custom defined and many standard julia types. I found a solution based on extending a local lexer with the new types.  
## Steps	
Instead of installing the lexer in your Pygments installation, you can keep the lexer with your TeX documents.	

	 1. If your lexer file is named "jl.py" and the class is "Julia1Lexer", put jl.py in the same directory as your main TeX source file
	 2. Specify the language in minted with \\begin\{minted\}\{jl.py:Julia1Lexer -x\}  code
	 	\\end\{minted\}.

###
```latex
\usepackage{minted} 
\newcommand{\jlinline}[1]{\mintinline{jl.py:Julia1Lexer -x}{#1}}

\newminted[julia]{jl.py:Julia1Lexer -x}{frame=lines,framerule=1pt,linenos,fontfamily=courier,framesep=2mm,fontsize=\scriptsize,xleftmargin=21pt}
```
### a julia listing  environement
```latex
\begin{julia}
f(x::Number) = x^2
\end{julia}
```
### an inline command 
```latex
This is an inline  julia code \jlinline{f(x::Number) = x^2}.
```
