# 3 Columnas iguales CSS GRID

- :heavy_exclamation_mark: Los elementos a separar deben de coexistir en un elmento unico llamado _**contenedor Padre**_

  ```html
  <div class="contenedor tres-columnas">
    <!--Nombre que se escoge para la division-->
    <article class="entrada-blog">---</article>
    <article class="entrada-blog">---</article>
    <article class="entrada-blog">---</article>
  </div>
  ```

- En CSS usamos la propiedad `display: grid;`, de esta manera tenemos a nuestra disposicion la variedad de opciones de Grid. Para nuestro ejercicio, se hace desde dispositivos mayores a 768px, usando un media query

```css
@media (min-width: 768px) {
  .tres-columnas {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
}
```

- otras opciones para `grid-template-columns`

  `grid-template-columns: 33.3% 33.3% 33.3%;`

  `grid-template-columns: 1fr 1fr 1fr;`

Resultado

![3 columnas GRID](/patternDesign/examples/03-3columnas_iguales_css_grid/img/tres-columnas-grid.png)

---

[:leftwards_arrow_with_hook: volver a menu](/patternDesign/)
