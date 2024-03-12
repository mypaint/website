+++
title = "v0.7.0 User Guide"
summary = "Learn how to use MyPaint v0.7.0"
+++

Tutorial básico del uso de MyPaint
==================================

Versión original en inglés [aquí](http://mypaint.intilinux.com/?page_id=3).

Bienvenido a MyPaint. Este tutorial es un buen punto de partida para
aprender a usar el programa. Hay tutoriales más avanzados, por el
momento sólo en inglés, [en esta
página](http://mypaint.intilinux.com/?page_id=14).

Introducción
------------

MyPaint es un programa de pintura artística, y se especializa en la
creación de imágenes partiendo de la hoja en blanco. Es capaz de imitar
medios "reales", hasta producir estilos más "digitales". Aspira a ser
simple y rápido en lo que hace.

Sin embargo no es, por diseño, un *programa de manipulación de
imágenes*. Así que, si bien ciertamente se puede hacer todo el trabajo
creativo en MyPaint, para el toque final de ajustes de color, recorte, y
otras cuestiones de *manipulación*, se precisa pasar la imagen a un
programa especializado para esto, como [GIMP](http://www.gimp.org/).

La interfaz
-----------

[[Basic-Usage-Tutorial-MyPaintMinimalInterface-v0.7.png]]

La interfaz de MyPaint es deliberadamente minimalista, y completamente
controlable por medio de atajos del teclado. La idea es que se pueda
pintar con la menor distracción posible.

Por lo tanto, normalmente se trabaja sobre el lienzo sin que haya otra
cosa visible. Y eventualmente se presionan teclas para hacer aparecer
diálogos, que permiten por ejemplo seleccionar un color. Estos diálogos
desaparecen cuando se retoma el trabajo. Aunque algunos artistas
prefieren trabajar así, otros prefieren mantener al menos unos pocos
selectores de uso frecuente, abiertos siempre a un lado del lienzo. Esto
es a gusto de cada uno, se pueden probar ambas opciones y escoger la que
se prefiera.

Los atajos de teclado están dispuestos originalmente para que se pueda
trabajar con la mano izquierda en el teclado, y la mano derecha
encargarse de la pintura. Pero es muy fácil cambiar los atajos: todos
los comandos están en el menú, así que se coloca el cursor de ratón
sobre alguno, y se presiona la tecla deseada.

Hora de pintar
--------------

[[Basic-Usage-Tutorial-PaintingScribbles.png]]

Para pintar sobre el lienzo se presiona la punta del lápiz óptico sobre
la tableta. O, si se emplea un ratón, se presiona su botón izquierdo. En
caso de emplearse un ratón, se pueden presentar pequeños problemas entre
los trazos, ya que MyPaint realmente no está optimizado para esto. No se
puede obtener todo el poder del programa con un ratón. Se recomienda el
empleo de una tableta digital.

MyPaint utiliza la sensibilidad de presión de la tableta para lograr una
variedad de efectos. Y las futuras versiones del programa podrán
utilizar otras características del lápiz óptico, como su angulación y
rotación, en las tabletas que las posean. Se pueden retocar los ajustes
de la tableta en la entrada de menú Editar→Preferencias .

Selección de la brocha
----------------------

[[Basic-Usage-Tutorial-v0.7-BrushList.png]]

Presiona B para abrir el diálogo que presenta todas las brochas
disponibles. Para seleccionar alguna se da un clic. Se pueden arrastrar
y soltar para ordenarlas a gusto.

Por ejemplo, escoge la brocha llamada Smudge+, que hace uso de la
sensibilidad a la presión de la tableta. Prueba pintar presionando
fuerte, y gradualmente reduce la presión. Verás que con la reducción de
la presión la brocha empieza a difuminar la pintura existente en el
lienzo, y deja de agregar color.

Hay una buena cantidad de brochas poderosas provistas junto con el
programa, y es interesante jugar con todas. También se pueden crear
brochas. Pero ese es un tópico avanzado y tiene dedicado [su propio
tutorial](http://mypaint.intilinux.com/?page_id=173), por el momento
sólo en inglés.

Ajustes de la brocha en tiempo real
-----------------------------------

[[Basic-Usage-Tutorial-ResizingBrush.png]]

Presiona la tecla F para agrandar la brocha, y la tecla D para
achicarla. Esto funciona incluso durante la ejecución de un trazo. El
contorno del cursor, que tiene la forma de la brocha, varía mostrando el
tamaño actual.

También se pueden asignar atajos a otras propiedades de la brocha para
que cambien en tiempo real, tales como la opacidad (qué tanto se deja
ver del lienzo a través de la pintura), o cuán claro u oscuro es el
color. Estos comandos se pueden hallar en las entradas del menú Brocha y
Color.

De todas formas, es importante recordar que estos comandos pueden no
definir exactamente las propiedades de una brocha en particular. Muchas
brochas tienen sus propiedades basadas en la presión o en la velocidad
del trazo, por ejemplo. Y lo que se cambia con el teclado es sólo el
valor base.

Deshacer y borrar
-----------------

[[Basic-Usage-Tutorial-Erased-area.png]]

Uno de los comandos más útiles de todo programa es Deshacer (Z o Ctrl-Z)
y su hermano Rehacer (Y o Ctrl-Y). Se emplean para revertir o volver a
traer los cambios efectuados.

También se puede borrar partes de la obra convirtiendo a la brocha
actual en un borrador, con la tecla E. Para volver a pintar se presiona
E nuevamente. Si se tiene un lápiz óptico con una punta borrador,
debería funcionar como se espera. Simplemente da vuelta el lápiz para
borrar.

La tecla Borrar limpia el lienzo.

Cambio del color
----------------

[[Basic-Usage-Tutorial-v0.7-ColourChooser.png]]

Presiona la tecla G para abrir el diálogo de color GTK. Es una rueda de
color normal. Escoge el color. Presiona G nuevamente para liberarte del
diálogo.

Gabaratea un poco con este nuevo color, y presiona V para hacer aparecer
un selector de color. Aparece en el lugar que esté el cursor, con el
color actual en el centro. Al alejarse del centro, el color cambia
gradualmente de acuerdo a distintos parámetros. Su apariencia exacta
varía un poco entre las versiones de MyPaint, así que puede no lucir
exactamente como la imagen de la derecha).

Simplemente haz clic sobre el color al que quieras cambiar, y el
selector se va. Esta es una manera muy rápida de obtener matices de
mismo color. haz clic por segunda vez para hacer aparecer un selector
alternativo.

A menudo cuando se pinta se cambia de tanto en tanto entre unos pocos
colores. MyPaint recuerda los últimos cinco colores usados. Presionando
la tecla X repetidas veces se pasa entre ellos fácilmente.
Opcionalmente, se puede hacer lo mismo presionando el botón derecho del
ratón.

En lugar de seleccionar desde un diálogo emergente, se pueden escoger
colores directamente desde el lienzo. Apunta a un sitio y presiona la
tecla R. Esto obtiene el color debajo del cursor. No se necesita hacer
clic con el ratón. El color escogido aparece por un instante en la
pantalla. Si prefieres puedes lograr lo mismo con un clic en el lienzo
mientras mantienes presionada la tecla Ctrl.

Vistas del lienzo sin límite
----------------------------

[[Basic-Usage-Tutorial-RotatedView.png]]

El borde de la pantalla no es el final. El lienzo de MyPaint crece a
medida que se expande la obra. Sólo la memoria de tu computadora pone el
límite. Puedes desplazarte alrededor del área usando el botón del medio
del ratón, o manteniendo presionada la barra espaciadora. Y puedes
acercarte o alejarte de la obra usando las teclas + y - respectivamente.

Algo usual en los pintores es mirar la obra desde distintos ángulos (es
una técnica para encontrar desproporciones en dibujos de anatomía y
retratos, por ejemplo). MyPaint permite rotar la vista de la pintura y
también espejarla para cada lado. Si te pierdes, usa Reiniciar
(ampliación, rotación, espejado) desde el menú Ver.

Una cosa a recordar es que estos comandos te permiten ver el lienzo de
distintas maneras, pero no modifican a la obra en sí. Si por ejemplo,
guardas una pintura rotada, volverá a aparecer sin rotar cuando la abras
más tarde. Si realmente deseas rotar, espejar o ampliar la pintura, usa
GIMP.

Fondos y capas
==============

[[Basic-Usage-Tutorial-BackgroundPattern.png]]

Cuando inicies MyPaint por primera vez, verás un lienzo blanco. Ahora
dirígete al menú Capas y selecciona Fondo... serás bienvenido por un
selector de fondos. Permite darle distintos aspectos al lienzo, desde
varios colores a varios patrones de papel, y más. Si lo deseas también
puedes guardar un fondo por defecto, así aparece siempre cuando abras el
programa.

[[Basic-Usage-Tutorial-v0.7-LayerMenu.png]]

MyPaint viene con capas. Una capa es el equivalente a ubicar una
transparencia sobre el trabajo y pasar a pintar sobre ella. Se las puede
imaginar apiladas una sobre la otra, y lo que se haga en una capa no
afecta a ninguna otra. Todas las capas están sobre el fondo previamente
mencionado.

Cuando se inicia MyPaint se tiene una sola capa sobre un fondo blanco.
Para comprobarlo, gabaratea un poco sobre esta capa con una brocha
grande, y luego crea una nueva capa sobre ésta con Ctrl+PageUp. La
pantalla hace un flash para mostrar que la nueva capa está vacía.

Ahora estás sobre la nueva capa. Pinta un poco sobre los trazos
anteriores, y luego intenta borrar el trabajo. Hallarás que sólo el
color de esta capa es afectado.

Para cambiar entre las capas de la pila, usa PageUp y PageDown. Al
hacerlo, la pantalla hará flashes para mostrar sólo el contenido de la
capa actual. También puedes saltar a una capa colocando el cursor sobre
algo visible de la misma y presionando la tecla H.

Las capas son útiles para experimentar sin arruinar el trabajo previo.
Te puedes deshacer de las capas combinándolas hacia abajo en la pila,
con Ctrl+Delete .

Presionando Shift+Delete se borra la capa actual, y su contenido se
pierde.

Guardar y exportar la obra
==========================

[[Basic-Usage-Tutorial-File-menu.png]]

MyPaint puede guardar y abrir imágenes, tales como PNG, JPG y ORA
(OpenRaster, un estándar en proceso de evolución en el mundo del
software libre).

Guarda en ORA cuando quieras suspender momentáneamente tu trabajo y
continuarlo luego, es el único formato que además guarda la estructura
de capas.

Por el momento GIMP no tiene la funcionalidad necesaria para abrir ORA,
así que debes exportar como PNG para poder abrirla en dicho programa.
Evita JPG hasta que quieras publicar la imagen terminada en la web.

La función Guardar como boceto de MyPaint, que tiene por atajo la tecla
F2, guarda la obra en su forma actual, con un número que se va
incrementando cada vez. Es útil para experimentar rápido con distintos
conceptos e ideas.

De ahora en adelante...
=======================

Con suerte, este ha sido un buen comienzo para trabajar con MyPaint. Si
tienes más preguntas o sugerencias, hay una página con más recursos
[aquí](http://mypaint.intilinux.com/?page_id=14) (por el momento sólo en
inglés). Allí también hallarás tutoriales y enlaces a galerías que
contienen obras de arte creadas con el programa.

Una vez que hayas tocado todo un poco y desees aprender más, podrías
leer sobre una de las capacidades más importantes de MyPaint, la de
crear tus propias brochas. Se describe en [este
tutorial](http://mypaint.intilinux.com/?page_id=173), de momento sólo en
inglés.

¡Que te diviertas!

