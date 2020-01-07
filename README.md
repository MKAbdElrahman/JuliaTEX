# JuliaTEX
Some source files I use when I need to typeset Julia in Latex documents.

## Introduction 
I've been searching for how typeset  Julia in TEX files, the problem is package  minted doesn't work for custom defined Julia types. I found this lexer solution on the Web.  
## Steps	
Instead of installing the lexer in your Pygments installation, you can keep the lexer with your TeX documents.	
	 -  If your lexer file is named "jl.py" and the class is "Julia1Lexer", put jl.py in the same directory as your main TeX source file
	 - Specify the language in minted with \\begin\{minted\}\{jl.py:Julia1Lexer -x\}  \#code
	 	\\end\{minted\}.
