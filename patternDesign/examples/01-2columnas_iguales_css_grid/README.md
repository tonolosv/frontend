# 2 columnas iguales con CSS GRID

- Esto es aplicable eN dispositivos tablet a pc, porque en dispositivos moviles los coloca uno debajo del otro
- Para ello se empezara a usar un media query de 768px (tablet) como medida estandar
- Para aplicar el CSS GRId, es importante que el contenedor de los layout sea el **_padre_**

> ```html
> <div class="contenedor dos-columnas">
>   <!--describe lo que se realizara-->
>   <article class="entrada-blog">
>     <h1>Titulo Entrada Blog</h1>
>   </article>
> </div>
> ```

> ```css
> @media (min-width: 768px) {
>   .dos-columnas {
>     /*se denomino asi al padre*/
>     display: grid;
>   }
> }
> ```

- La separacion entre elementos (recordanddo que son del mismo padre), se debe usar _`gap`_ en rem, para tener ese efecto.

- la propiedad que divide las columnas en el numero deseado en este caso 2, es `grid-template-columns`, existen varias formas de aplicarlo

> ```css
> grid-template-columns: 50% 50%;
> grid-template-columns: repeat(2, 50%);
> grid-template-columns: 1fr 1fr;
> grid-template-columns: repeat (2, 1fr);
> ```

Resultado final

![2 columnas](/patternDesign/examples/01-2columnas_iguales_css_grid/img/d-columns-grid.png)
