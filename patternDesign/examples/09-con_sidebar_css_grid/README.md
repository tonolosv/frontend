# Sidebar Grid

Este patron de diseño esta enfocado para blogs o tiendas virtuales, donde el contenido principal tiene la mayor espacio y `aside` que estara en cualquiera de los lados.
En un dispositivo movil, lo mostrara uno debajo del otro

- Al tener un elemento principal, en este caso solo llevara una clase `.con-sidebar` se asignado al div principal.
- Se le atribuye `display-grid` y como será la distribucion de las columnas con `grid-template-columns:(1fr 3fr)`.
- Para este ejemplo va acompañado por un `aside` y un `article` sin embargo no llevan clases, para la recolocacion en CSS, se le asignara un lugar segun las propiedades de Grid.
- Una nueva propiedad que se uso para la posicion correcta del aside y del article es `grid-auto-flow: column`; controla como funciona el algoritmo de colocacion y automaticamente los elementos fluyen dependiendo del espacio disponible, en este caso fue en columna

```css
@media (min-width: 768px) {
  .con-sidebar {
    display: grid;
    grid-template-columns: 1fr 3fr;
    column-gap: 4rem;
    grid-auto-flow: column;
  }
  aside {
    grid-column: 1/2;
    grid-row: 1/2;
  }
}
```

- Pc y laptop

  ![Dispositivo Large](/patternDesign/examples/09-con_sidebar_css_grid/img/large.png)

- Dispositivos moviles

  ![Moviles](/patternDesign/examples/09-con_sidebar_css_grid/img/movil.png)

Si se desea cambiar la posicion del aside y del article, solo se debe intercalar el posicionamiento en el CSS.

```css
@media (min-width: 768px) {
  .con-sidebar {
    display: grid;
    grid-template-columns: 3fr 1fr;
    column-gap: 4rem;
    grid-auto-flow: column;
  }
  aside {
    grid-column: 2/3;
  }
}
```

Imagen de referencia

## ![sidebar invertido](/patternDesign/examples/09-con_sidebar_css_grid/img/large-inverso.png)

[:leftwards_arrow_with_hook: volver a menu](/patternDesign/)
