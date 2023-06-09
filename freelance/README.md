# Freelance site

Sitio trabajado solamente con etiquetas html y CSS, para conocer los fundamentos para crear un sitio

### Seccion 5 | Esquematizacion de un sitio básico

- para el uso de iconos existen diferentes proveedores

  - [tablericons](https://tablericons.com/)
  - [heroicons](https://heroicons.com/)
  - [fontawesome](https://fontawesome.com/)

- Las dimensiones de los iconos son tomados segun lo propuesto por el tutor

Cada elemento del formulario label e input, fueron colocados dentro de un div

#### Etiquetas que sirven para agrupar contenido

`<header>` Encabezados y navegacion principal de un sitio

`<footer>` pie de pagina del site, informacion conglomerada

`<nav>` navegacion a diferentes partes de un sitio

`<main>` Informacion que se puede considerar importante

`<section>` secciones que añaden valor al main

`<article>` articulos de importancia, que pueden o no pertencer a un sitio

`<aside>` informacion que aparece como noticia relevante, pero corta

`<div>` agrupacion de los anteriores, su proposito es caracter de manipulacion con CSS

---

### Sección 6 | Conociendo CSS. Básico

Estructura que se maneja en CSS, para darle diseño a la web

- por elemento

```css
p {
  color: blue;
}
```

- por clases (.), definido en html

```css
.cliente {
  color: blue;
}
```

- por id(#) y solamente se puede usar en una etiqueta unica, y no pueden repetirse

```css
#cliente {
  color: blue;
}
```

- por atributos que se definieron en el html

```css
[src='logo.jpg'] {
  color: black;
}
```

- combinacion de descendentes, considerese de padre a hijos en una clase o id en especifico

```css
.cliente .nombre {
  color: yellow;
}
```

- todos los hijos, ojo que la diferencia esta en el "_>_"

```css
.cliente > p {
  color: green;
}
```

_Consideraciones_

- las propiedades se van utilizando segun sea el ultimo definido

- utilizar un _preload_ para el css, cargue mas rapido

`<link rel="preload" href="css/style.css" as="style">`

- unidades de medidas utilizadas:

> em: basado el tamaño del documento

> px: pixeles segun pantalla de donde se visualiza

> rem: relativo al documento, al elemento padre

- para formatear el codigo y que se adapte en cualquier dipositivo se trabajará con el siguiente formato. "reinicio del documento"

```css
html {
  font-size: 62.5%;
}
body {
  font-size: 16px;
}
```

### Espeficidad en CSS

Al trabajar en CSS, se realiza con mayor enfasis detallar los cambios a realizar al documento y este debe ir directamente amarrado con la etiqueta, se recomienda usar clases, mas especifico sea el selector este se aplicara primero dejando de lado aquellos que esten debajo, por ende no funciona como cascadas
!important bloquea lo anteriormente definido

```css
h1.titulo span {
  font-size: 2rem;
}
```

codigo

![Detalle en codigo ](img/especificidad_2.png 'Description')

html

![Visualizacion](img/especificidad.png 'Description')

### Definiendo la hoja de estilos CSS

#### Variables

Los pseudoelementos son caracteristicas que no existen, pero se usan dentro de una condicion CSS para utlizarlos. Por ello da paso a los _customs properties_

Los customs properties son valores que se crean y utilizan como default en todo el proyecto, estos pueden cambiar; pero la ventaja que se tienen es que cada vez que se realiza un cambio solo se manda a llamar el custom propierties y no por el valor definido

```css
:root {
  maincolor: #ffffff;
  secondcolor: #00000;
}
```

Para poder utilizar los customs properties, solamente es de llamar a la variable en si, con _*var*_

```css
.titulo {
  color: var(--maincolor);
}
```

#### Fuentes y normalize

- Fuentes

  La gran mayoria de las fuentes utilizadas son provenientes de [google fonts](https://fonts.google.com/), al escoger una fuente del abanico de opciones es necesario linkear de la siguiente manera en nuestro archivo html

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Freelance Site</title>
  <!--Notese que las fuentes van primero que las hojas de estilo. Especificidad-->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Krub:wght@200;400;700&display=swap"
    rel="stylesheet" />
  <link rel="preload" href="css/style.css" as="style" />
  <link rel="stylesheet" href="css/style.css" />
</head>
```

- Normalize
  Reset a que los elementos sean consistentes en todos los navegadores.
  Se recomienda que este en un archivo aparte
  [Normalize](https://necolas.github.io/normalize.css/)

- Consideraciones en el css

  - se pueden escribir 2 o mas clases en un atributo
  - width: ancho de un atributo
  - margin: en que posicion se coloca un elemento _top_, , _right_, _bottom_, _left_.
    ```css
    .conteiner {
      margin: 0 auto 0 auto;
    }
    ```
  - display block | inline
    block: el elemento se coloca debajo del otro, ocupando todo el espacio disponible
    inline: se posiciona a la derecha, con el espacio requerido y el siguient lo coloca a la derecha

  - padding: separacion dentro del elemento, este lo hace hacia adentro del mismo. Referencia las manecillas del reloj

#### BEM Modulos y utilidades

- Block
  `.card {}`

  Bloque que englobara varios elementos, se le puede denominar como block main

- Elements

  `.card__titulo{}`

  `.card__imagen{}`

  `.card__boton{}`

  Son los elementos que estan dentro del elemento principal y que se van a diferenciar con guiones bajos "\_\_"

- Modifier

  `.card__boton--activo`

  Segun la condicion en la que se encuentra, asi se describe el modificador, para el ejemplo anterior el boton esta activo

#### Utility First

Una propiedad con un valor de la clase, describiendo lo que esa clase afectara en el html

`.text-center {}`

`.color_red-100 {}`

`bg-blue-200 {}`

`p-2 {}` // padding

`m-2 {}` //margin

#### Modulos

se define segun la descripcion de la propiedad, acompañada por el etiqueta
`.card {}`

`.card h2 {}`

`.card img {}`

`.card a {}`

### Responsive Design

Adaptabilidad a las resoluciones segun donde se navegue con media querys. La condicion que se acepta es la definida en _px_ desde alli, habra una modificacion para la resolucion de la pantalla

- ```css
  @media (min-width: 768px) {
  }
  ```

- ```css
  @media (min-width: 992px) {
  }
  ```

Creando un snippet para los media querys

```json
'crea un media query': {
  "prefix":"mq",
  "body": '@media (min-width: $1) {\n   $2\n}';
}
```

#### Box Model CSS

Es lo que limita a un elemento teniendo 4 consideraciones:

- tamaño del contenido
- tamaño del relleno (padding)
- tamaño del borde
- margen

Lo anterior marca una tarea mas compleja para la colocacion de los elementos porque se debe estar sumando o restando cualesquiera de los elementos, por ello se tiene una alternativa para reajustar dichos paramentros, [Box-sizing: Border-Box](https://www.paulirish.com/2012/box-sizing-border-box-ftw/), permite sustraer pixeles del _width_ original para que no se expanda

```css
html {
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}
```

Los (\*) selecciona todos los elementos del html, de manera universal. A todos los elemtos le aplica l box sizing border box; por ello cuando se maneja los diferentes medidas para los elementos no seran afectados

#### Posicionamiento Relativa y absoluta

La posicion exacta de los elementos lo ideal es usar posicion absoluta y relativa, donde el padre tiene que estar con posicion _Relativa_ y al hijo posicion _absoluta_, porque de es manera se van manejando sus condicionantes. Tambien se debe tomar en cuenta que siempre esta presente top, rigth, bottom y left como parte del formato de posicionamiento

![Relativa y absoluta](img/relative.png 'Description')

Con el codigo se manajera los siguiente

```css
.hero {
  /* Contenedor padre*/
  position: relative;
}

.contenido-hero {
  /*Contenedor hijo*/
  position: absolute;
}
```

#### Degradados cap 43

Codigo en css para que las paginas tengan un diferenciador en el color de fondo(comunmente aplicado) siempre en el _body_ del css y se va manejando para lo que se considere el gradiente

```css
body {
  background-image: linear-gradient(
    to top,
    /*desde terminara*/ var(--grisClaro 0%, var(--blanco) 100%)
  );
}
```

#### Sombras

Para la aplicacion de sombras se recomienda [cssmatic](https://www.cssmatic.com/box-shadow) para que el codigo que esta pagina genere, trasladarlo al css principal

#### CSS GRID

Permite definir la ubicacion y el tamaño de los elementos en 2 dimensiones la funcion del sistema _GRid_, se asemeja a un tabla con la colocacion de los objetos intercalando arriba/abajo y derecha/izquierda [guia online](https://www.tutorjoes.in/css_tutorial/grid_introduction_in_css)

![Grid](img/flex-vs-grid.png)

para ingresar a esas dimensiones con

- _grid-template-columns_
- _grid_template-rows_
- _grid: 200px 800px / 300px 300px_ row es la primera definida y despues de la "/" se define la columna, las 2 opciones presentadas son ya desfazadas

Consideraciones

1. Usar Flexbox: Alineacion y distribucion de elementos que estan **dentro** de contenedores, esos pueden ser _nav_

2. Usar Grid: **Layout** que contienen la pagina web porque se pueden distribuir segun las necesidades

3. Para el formulario se trabajan los campos detallando las condiciones que se adapataran desde la visualizacion en un movil y otros dispositivos

4. Unas de las nuevas caracteristicas que da mejor visualizacion, el scroll se detiene en cada area de la web

5. Para ver la web terminada visita [example-freelance](https://example-freelance.netlify.app/)

---

[:leftwards_arrow_with_hook: menu principal](/README.md)
