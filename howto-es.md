# Guia para Colaborardores

Bienvenidos los contribuidores a la traduccion No oficial de libro SICP al
español!

Antes de comenzar, es necesario decir que esta vercion esta formateada en un
lenguaje (experimental) de marcas ligeras llamado [morg](https://github.com/nasciiboy/morg)
que busca ser mas sencillo que ningun otro lenguaje para crear documentacion,
mientras mantiene la mayoria de caracteristicas de otros lenguajes de marcas
como xml o los derivados de TeX. Por tanto esta es una de sus primeras pruebas
en el mundo real

Esta traduccion se realiza por respeto y admiracion al espiritu que habita en la
maquina. Manteniendo ese espiritu la obra esta bajo liciencia CC-SA 4.0 por lo
que se da por hecho que cualquier contribucion a esta se apega a dicha
licencia. Por respeto a las personas este proyecto no obliga a firmar ningun
CLA, u otro contrato similar

Happy Hacking!

## Pasos

Este trabajo se encuentra gestionado por el sitema de control de versiones git,
sobre la plataforma github en la que se realizaran los "pull request", sin
embargo si no desea registrarse en dicha plataforma, puede enviar su propuesta
de cambios dentro de un comprimido en formato *zip* o *tar* al correo
nasciiboy@gmail.com, siendo el unico requisito clonar el repositorio

    git clone https://github.com/nasciiboy/sicp.git

manternerlo actualizado con los cambios mediante el comando

    git pull

realizar los cambios correspondientes y enviar unicamente dichos cambios

La via (en github) de [contrubucion](https://gist.github.com/BCasal/026e4c7f5c71418485c1) "estandar" seria

realizar un fork al repositorio

Después de tener el repositorio en nuestra cuenta, seleccionar la dirección del
repositorio "SSH o HTTP" y clonar:

    $ git clone https://github.com/mi-usuario/NombreRepo.git

Antes de realizar modificaciones agregar la URL del repositorio original del proyecto:

    $ git remote add upstream https://github.com/nasciiboy/sicp.git

Antes de empezar a trabajar, obtener los últimos cambios del Repo Original:

    $ git pull -r upstream master

Crear una Rama, Para crear una rama usar la opción `checkout` de git:

    $ git checkout -b mi-rama-con-cambios

Realizar todos los cambios que se desea hacer al proyecto.

Agregar los archivos y hacer un commit

    $ git commit -a -m "mi commit"

Después de realizar el commit hacer el push hacia nuestro repositorio indicando
la rama que hemos creado.

    $ git push origin mi-rama-con-cambios

Dentro de github hacer un Pull Request, Hacer click en "Compare & Pull Request"

Si todo está bien, enviar con el botón "Send Pull Request".

Esperar que los cambios se revisen, acepten y mezclen en la rama principal

## Formato de commits

sientase libre de formatear sus commits como mejor le paresca!

... git, es una herramienta, un mero medio para gestionar el desarrollo de un
proyecto.

El "producto" final es el contenido en el directorio principal no el
contenido almacenado en `.git`, asi como no se comparte el editor o un
compilador con el que se hace un programa, no se considera que un proyecto
terminado tenga que contener las datos de su programa de control de versiones

los datos sobre la autoria de sus contribuidores (si es lo que se desea) seran
colocados dentro del fichero <code class="file">CONTRIBUTORS.txt</code>, que sera
el registro que se transmita en la version final de la traduccion

## Organizacion

```
.
├── CONTRIBUTORS.txt      // lista de colaboradores
├── img                   // carpeta con imagenes del libro
│   ...
├── howto-es.md           // Este fichero
├── LICENSE               // Licencia del proyecto
├── README-EN.md          // presentacion del proyecto en ingles
├── README.md             // presentacion del proyecto en español
├── sicp.morg             // fichero "maestro" del libro (ingles)
├── sicp.html             // exportacion del libro (ingles)
├── sicp-es.porg          // fichero "maestro" con la traduccion al español
├── TODO.org
└── worg-data             // carpeta con recursos para la exportacion html
    ├── worg.css          // hoja de estilo
    ├── fonts             // fuentes
    └── img               // imagenes
```

## La herramienta morg

[morg](https://github.com/nasciiboy/morg) es un programa desarrollado en
el lenguaje de programacion Go, para instalarlo priemero debe seguir los pasos
de [esta](https://github.com/nasciiboy/morg/blob/master/howto.md) guia, o si ya
tiene instalado el lenguaje Go en su sistema, puede optener la herramienta con
el comando

    go get -v github.com/nasciiboy/morg

para actualizar la herramienta a nuevas versiones

    go get -u -v github.com/nasciiboy/morg

De momento esta herramienta solo ha sido probada en el sistema GNU/Linux en la
distrubucion Fedora

Para optener la exportacion del fichero principal al formato html

    morg toHtml sicp.morg

Si desea el resaltado de sintaxis por fabor instale antes en su sistema
pygmentize (python pyments) con el comando

    pid install pygments

Para generar el fichero morg del libro en español apartir del fichero de
traduccion

    morg unPorg sicp-es.porg

Luego puede exportarlo a formato html con

    morg toHtml sicp-es.morg

## Modificaciones

Todo el trabajo de traduccion se centra en el fichero <code class="file">sicp-es.porg</code>
este contiene el contenido intacto de <code class="file">sicp.morg</code>, con
la particularidad que cada linea esta *comentada* con `# ` (`#` y un espacio en
blanco). La traduccion al español se coloca justo debajo de cada seccion en
ingles, manteniendo la indentacion del original, esto significa que se colocara
con *dos* espacios menos del inicio del contenido original comentado, es decir

```
# Esto forma parte del material original
Esta sera la traduccion del material original
```

pasemos a un ejemplo real

```
# * Unofficial @e(morg) Format
* Formato @e(morg) No Oficial

#   This is the second edition @A(SICP) book, from Unofficial morg Format.
  Esta es la seguanda edicion del libro @A(SICP), no oficial en formato morg.

#   This @l(https://github.com/nasciiboy/morg/<>morg) version is based on
#   Unofficial Texinfo Format @l(http://sicpebook.wordpress.com) (July 07, 2017),
#   based on @l(http://www.neilvandyke.org/sicp-texi/<>2.neilvandyke4).
  Esta versión en formato @l(https://github.com/nasciiboy/morg/<>morg) se basa
  en la version no oficial @l(http://sicpebook.wordpress.com/<>sicpebook) en
  formato Texinfo (Julio 07, 2017), basada en la version no oficial
  @l(http://www.neilvandyke.org/sicp-texi/<>2.neilvandyke4) convertida desde la
  @l(http://mitpress.mit.edu/sicp/<>version HTML) original de MIT Press.
```

morg cuenta con sencillas pero potentes opcienes de estructuracion y resaltado,
no es necesario conocerlas a profundidad, pero aqui estan las principales

- Todos los elementos finalizan cuando aparece una linea en blanco, exeptuando
  los "comandos" que se guian por la indentacion

- el documento se estructura por niveles de encabezado, esto es cada linea que
  inicia con uno o varios `*` seguida por almenos un espacio en blanco. El
  alcance de este encabezado, termina cuando aparece otro encabezado

- las listas inician con `-`, `+`, `1.`, `1)`, `a.` o `a)`, seguido por un
  espacio en blanco y luego su contenido debe indentarse

- las definiciones inician con `-` o `+` luego aparece el texto a definir,
  seguido por ` :: ` y luego cuaquer contenido que conforme la definicion debe
  seguir la identacion

- los "abouts" inician con `::` luego aparece el "titulo",
  seguido por ` :: ` y despues cualquer contenido que conforme la definicion debe
  seguir la identacion

- los "comandos de bloque" tienen la estructura `..el-comando opciones > argumento`. El
  cuerpo, del comando si es que tiene debe estar endentado con dos espacios.
  Los comandos pueden "cerrarse" explicitamente con `< el-comando..`, de otra
  forma terminan cuanto el contenido deja de mantener la indentacion

- existen los comandos `@`, que sirven tanto para resaltar el texto, como para
  otras opciones (futuras) mas complejas, estos comandos siguen la forma `@x(`,
  donde la `x` es el comando en si (`b` ==> bold, `e` ==> enfasis, `i` == italica,
  etc). Luego esta la abertura del comando que puede ser `(`, `[`, `{` y `<` y
  termina al encontrar el cierre, que respectivamente seria `)`, `]`, `}` y
  `>`. La variedad de este ultimo se utiliza para *evitar abiguedades* sobre el
  alcance del contenido

  Si dentro del comando `@` aparece `<>` significa el texto a la derecha de
  este, reemplazara lo que aparesca en la exportacion y el texto a la izquierda
  es el "argumento" del comando


Desde luego los comandos (`@` y de "bloque") pueden anidarse, con la salvedad
que los comandos de codigo fuente `..src > lenguaje`

Para colocar una `@` dentro del texto tal cual, utilize `@@`

## TODO

el fichero <code class="file">TODO.org</code> se encuentra la lista de
pendientes y encargados de cada labor

## Consideraciones finales

La herramienta principal con la que se realiza la traduccion ha sido *El editor*
Emacs, el cual proporciona diversas facilidades de edicion, tomando prestadas
cualidades del modo *org-mode*, considere su uso, de otra manera tendra que
editar "rusticamente", debido a la juventud del lenguaje de marcas morg

Hasta el momento he utilizado google translate (<code class="file">sicp-es.porg</code>)
tanto para la traduccion maquina, e igual para ir realizando una revicion
pararrafo a parrafo, dicho traductor, requiere de parrafos en una sola linea
para operar de forma optima. Para no tener la penosa necesidad de unir lineas a
mano utilice

    $ morg toTxt sicp.morg

esto genera el fichero <code class="file">sicp.txt</code>, con todos los
parrafos en una sola linea. Es una caracteristica sin terminar, pero bastante
util

Para finalizar todos los ficheros estan codificados en utf-8, antes de enviar
sus cambios revise la codificacion

en la traduccion, las opciones de resaltado e inclucion de mathjax, estan
desabilitadas (comando `..options >`) para evitar el cuello de botella que
suponen en el desarrollo, habilite si quiere la exportacion completa
