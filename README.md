# README

create your empty repository

    git init

create a submodule with reveal.js
warning: use https submodule (not ssh) for making GitHub pages happy.
It will initialise the submodules without problems.

    git submodule add https://github.com/hakimel/reveal.js.git


    git submodule add https://github.com/mathjax/MathJax.git
    cd MathJax 
    git checkout tags/2.7.9
    cd ..
    git add MathJax
    git commit -m "mj version 2.7.9"


pick a released version, 
take a look https://github.com/hakimel/reveal.js/releases to select a valid tag

    cd reveal.js && git checkout tags/3.9.2 && cd ..

now you are ready to create your slides in your repository

http://cgroll.github.io/research_tools/output/markdown.slides.html


pandoc -s \
    -t revealjs  \
    --mathjax=MathJax/es5/tex-mml-chtml.js \
    -V revealjs-url=reveal.js \
    -o slides.html slides.md



pandoc -t beamer slides.md -o slides.pdf \
    -V theme:default -V colortheme:dolphin 


decktape reveal slides.html slidesdt.pdf


