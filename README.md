# JuliaTEX
## Introduction 
I've been searching for how to typeset  Julia in TEX files, the problem is that package  Minted doesn't work for custom defined Julia types. I found this lexer solution on the Web.  
## Steps	
Instead of installing the lexer in your Pygments installation, you can keep the lexer with your TeX documents.	

	 1. If your lexer file is named "jl.py" and the class is "Julia1Lexer", put jl.py in the same directory as your main TeX source file
	 2. Specify the language in minted with \\begin\{minted\}\{jl.py:Julia1Lexer -x\}  code
	 	\\end\{minted\}.

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
