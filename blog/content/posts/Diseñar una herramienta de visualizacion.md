+++
title = "De cómo diseñar una herramienta de visualización"
date = "2022-08-27"
+++

La mayoría de diseñadores que se enfrentan a la visualización de datos se encuentran con el problema de comunicar cierta cantidad de datos de una manera clara y atractiva. Ese escenario, dependiendo de los datos y el contexto, puede ser más o menos complicado. No es lo mismo que el receptor del mensaje sea el consejo de administración de una empresa, al que se le supone un mínimo de conocimiento técnico y sobre todo interés por el mensaje; a que se esté diseñando una visualización para el gran público, que va a ser transmitida a través de la pequeña pantalla de un teléfono móvil y además, compitiendo por la atención del receptor.

Tampoco es lo mismo tener que comunicar cuál es la ocupación hotelera en las diferentes comunidades autónomas, a tener que transmitir cómo ha sido el efecto de las ofertas de descuento lanzadas a lo largo del año pasado sobre las ventas de cada producto, por tienda.

La complejidad a la que nos enfrentamos a la hora de visualizar puede crecer rápidamente por infinidad de factores. Pero siempre que conozcamos los datos antes de empezar a diseñar, estaremos en una posición de dominio suficiente para sacar un buen trabajo adelante. Consejo, si no tienes los datos antes de empezar, no aceptes un trabajo de visualización de datos porque el riesgo de que tu diseño no funcione con los datos finales es muy elevado.

Aún así hay gente que se tiene que enfrentar al último giro de tuerca, tener que diseñar una visualización de datos sin datos. Están en esa situación los encargados de diseñar no la visualización final sino la herramienta que se utilizará para crear la visualización final.

Si te vas a embarcar en ese reto te diría que simplifiques y acotes el espacio de diseño. Vamos, nada que un diseñador con experiencia no sepa... pero a veces nos emocionamos y nos volvemos locos.

## 1. Simplifica y Acota el espacio de diseño

Intenta responder a las siguientes preguntas lo antes posible:

- ¿Qué tipo de usuarios van a usar la herramienta para crear visualizaciones de datos?
- ¿Tienen conocimiento estadístico y podrán realizar transformaciones de datos?
- ¿Qué tareas tienen que cumplir esas visualizaciones? Son visualizaciones para comunicar, comprobar o descubrir información.
- ¿Cuál va a ser el público objetivo de esas visualizaciones?
- ¿En qué tipo de dispositivos se van a tener que reproducir las visualizaciones finales?
- ¿Es necesario o tiene sentido poder crear visualizaciones interactivas?
- ¿Qué tipos de datos es necesario soportar? Tabulares, Relacionales, Espaciales, Temporales...
- ¿Qué cantidad de datos es necesario manejar? Una pequeñas tablas con 2 o 3 columnas o bases de datos enteras

Teniendo todo esto claro podrás empezar a descartar características y a simplificar el problema. Si no es necesario no des soporte para interacción, no des soporte para pantallas pequeñas, no des soporte a transformaciones de datos, no des soporte para diferentes tipos de datos y tampoco para diferentes tipos de tareas.

Piensa que dar la opción de crear 5 visualizaciones no es muy difícil, pero si das la opción de visualizar para pantallas pequeñas y grandes, ya son 10, con interacción y sin interacción, se van a 20 escenarios distintos y algunos de ellos complicados, interaccionar en pantallas pequeñas no es nada sencillo. Si además añades soporte para diferentes tipos de datos encontrarás visualizaciones que funcionan para unos archivos y no para otros.

Y es que hacerlo todo añadiría complejidad no sólo a la hora de diseñar los controles de la herramienta. El diseño de las visualizaciones también se complicará, pero sobre todo, añadirá mucha complejidad al usuario final, que no lo tendrá fácil para conseguir visualizar sus datos entre tanto callejón sin salida.

## 2. Elige el paradigma adecuado

Dependiendo de las respuestas a las preguntas anteriores deberías elegir el paradigma que vas a seguir a la hora de diseñar tu herramienta de visualización. Esta decisión es con seguridad la que va a marcar de manera más profunda la forma y la función de la interfaz.

A día de hoy a hay dos líneas maestras, ya probadas, entre las que podemos elegir. O hacer una herramienta de visualización basada en una gramática visual o hacer una herramienta de visualización basada en Charts (gráficos). Existe un tercer paradigma basado en interacción directa que todavía está en fase de investigación pero que conviene seguirle la pista por prometedor.

![Paradigmas](/img/Paradigmas.png)

### Basados en gráficos

Los sistemas basados en Charts (gráficos) son los más conocidos. Herramientas como Excel o [DataWrapper](https://www.datawrapper.de/) utilizan este paradigma. El usuario empieza por navegar un menú de visualizaciones estadísticas más o menos clásicas, elige el tipo de gráfica que quiere y a continuación rellena las opciones asociadas a dicha gráfica. Lo normal es que cada gráfica pida seleccionar unas cuantas columnas del conjunto de datos para ser utilizadas como los ejes o como los colores de la visualización.

Este tipo de interfaces tiene una barrera de entrada relativamente baja a costa de limitar la flexibilidad que tiene el usuario. Si el usuario quiere crear un tipo de gráfico que no se encuentra entre los disponibles, no tendrá manera de conseguir lo que quiere. 

### Basados en gramáticas visuales 

Los sistemas basados en gramáticas visuales también son muy utilizados. El gran exponente es [Tableau](https://www.tableau.com/). En este tipo de herramientas el usuario se enfrenta a un canvas en blanco donde no empieza por seleccionar el gráfico que quiere conseguir sino que va especificándole a la herramienta cómo debe de mapear cada una de las columnas del conjunto de datos para crear la visualización deseada. Por ejemplo, si el usuario sabe que quiere crear un diagrama de dispersión elegirá una variable numérica para que defina el espacio horizontal de la gráfica y otra numérica para el espacio vertical. Por último seleccionará qué marca quiere utilizar para cada una de las filas de la tabla, por ejemplo círculos.

Este tipo de interfaces son mucho más flexibles porque no están constreñidas a un listado de gráficos predefinidos sino que podrá crear gráficos no diseñados de ante mano. La contrapartida la encontramos en la barrera de entrada. Empezar con un lienzo en blanco o tener claro qué posibilidades tiene una gramática visual no pone las cosas fáciles al que empieza de cero.

### Basados en interacción directa

Todavía en investigación, los sistemas basados en interacción directa quieren conseguir la cuadratura del círculo. Hacer un sistema tan flexible o más que los sistemas basados en gramáticas y a la vez hacerlo tan accesible como Figma o Illustraitor. Puedes jugar con prototipos como [Data Illustraitor](http://data-illustrator.cs.umd.edu) de la Universidad de Maryland, GeorgiaTech y Adobe o [Lyra](https://vega.github.io/lyra/) del [MIT](http://vis.csail.mit.edu/).

## 3. Ya estaría

Es guasa. Todavía queda lo más complicado, los detalles. Pero al menos, eligiendo el paradigma más adecuado para las necesidades de tus usuarios, sabrás que empiezas a diseñar una herramienta de visualización "a lomos de gigantes".

Si quieres seguir leyendo sobre el tema:

- El [paper que dió origen Tableau](https://mkt.tableau.com/files/Tableau-CACM-Nov-2008-Polaris-Article-by-Stolte-Tang-Hanrahan.pdf), verás que la interfaz no ha cambiado sustancialmente desde 2002. A mi juicio, esa es la prueba de un buen diseño, la prueba del tiempo.

- El [paper de Data Illustraitor](http://data-illustrator.cs.umd.edu/papers/DataIllustratorCHI18.pdf), galardonado con mejor paper de CHI 2018. Como reza la cita de William Gibson, “The future is already here. It's just not evenly distributed yet”. A mi juicio, este diseño es un pedacito de futuro.