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
