lang => [es](README-ES.md)

SICP
====

This is a new Morg and HTML5 version of "Structure and Interpretation of Computer
Programs" by Abelson, Sussman, and Sussman. It comes from the lineage of
[Unofficial Texinfo Format](http://sicpebook.wordpress.com) based on
[Unofficial Texinfo Format](http://www.neilvandyke.org/sicp-texi/) that was
converted from the original [HTML version](http://mitpress.mit.edu/sicp/) at The
MIT Press.

Source
------

The root directory contains the [morg](https://github.com/nasciiboy/morg/)
source in `sicp.morg.` To recreate the HTML file:

```bash
go get -v github.com/nasciiboy/morg
git clone https://github.com/nasciiboy/sicp.git
cd sicp
morg toHtml sicp.morg
```

You will need `git`, [golang](https://golang.org/) and [pygmentize](http://pygments.org/) (source code higlight)

if you prefer view in terminal try:

```bash
morg tui sicp.morg
```

Acknowledgements
----------------

* Lytha Ayth
* Neil Van Dyke
* Gavrie Philipson
* Li Xuanji
* J. E. Johnson
* Matt Iversen
* Eugene Sharygin
* Sarabanderest

License
-------

licensed under Creative Commons Attribution-ShareAlike 4.0 International License ([cc by-sa](http://creativecommons.org/licenses/by-sa/4.0/)).

Collaborate with the translation into Spanish
---------------------------------------------

[Donate](https://liberapay.com/nasciiboy/donate) to little nasciiboy, for more
info see [this](http://nasciiboy.github.io/prog/dot-slash-sicp2es/) post
