lang => [en](README-EN.md)

SICP
====

Esta es una nueva version en formato Morg y HTML de "Structure and
Interpretation of Computer Programs" por Abelson, Sussman, y Sussman.

Biene del linaje de la Version Texinfo no
Oficial [sicpebook](http://sicpebook.wordpress.com) basada en la Version Texinfo
no Oficial [neilvandyke](http://www.neilvandyke.org/sicp-texi/) convertida desde
la [version HTML](http://mitpress.mit.edu/sicp/) original de MIT Press.

Codigo
------

El directorio principal contiene el fuente [morg](https://github.com/nasciiboy/morg/)
en `sicp.morg.` Para crear el fichero HTML:

```bash
go get -v github.com/nasciiboy/morg
git clone https://github.com/nasciiboy/sicp.git
cd sicp
morg toHtml sicp.morg
```

Unicamente necesita tener instalado `git` y [golang](https://golang.org/)

Si prefiere verlo en terminal, intente:

```bash
morg tui sicp.morg
```

Agradecimientos
---------------

* Lytha Ayth
* Neil Van Dyke
* Gavrie Philipson
* Li Xuanji
* J. E. Johnson
* Matt Iversen
* Eugene Sharygin
* Sarabanderest

Licencia
--------

licenciado bajo Creative Commons Attribution-ShareAlike 4.0 International License ([cc by-sa](http://creativecommons.org/licenses/by-sa/4.0/)).

Colaborar con la traduccion al Español
--------------------------------------

ver [howto-es.md](howto-es.md)
