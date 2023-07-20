# Column Drop | Colocacion de columnas

Es una reposicion de columnas, las cuales se van "recolocando" con una fluidez una sobre otra, dependiendo el tamaño y cantidad de columnas. Esto puede funcionar de mejor manera en dispositivos moviles o de menor tamaño.

### Dispositivos moviles

- Se debe crear una clase en el div padre para habilitar las propiedades del `grid`
- Los hijos en este caso son `aside`, seran las que tendran la reposicion dentro de la web
- Se comienza con dispositivos de menor pixeles, esto para ir determinando la posicion que estaran cada columna

  ![480 pixeles](/patternDesign/examples/07-column_drop_css_grid/img/480px.png)

- La tercera columna ocupara todo el row inferior para una mejor vista, pero a medida que va disminuyendo el espacio visual. Este se contraera hasta tener una columna sobre la otra

  ![480 pixeles](/patternDesign/examples/07-column_drop_css_grid/img/480px2.png)

- Visualmente quedaría de esta manera, cuando se visita la pagina desde un dispositivo movil

  ![480 pixeles](/patternDesign/examples/07-column_drop_css_grid/img/480px3.png)

  ```css
  @media (min-width: 480px) {
    .column-drop-css {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 2rem;
    }
    .segunda {
      grid-column: 1/3;
    }
  }
  ```

### Dispositivos de mayor escala

- Se manejan de igual forma padre e hijos, la diferencia en este ejemplo se utilizara todo el espacio disponible para su visualizacion, creando 3 columnas

![768 pixeles](/patternDesign/examples/07-column_drop_css_grid/img/768px1.png)

- El codigo `css` queda de la siguiente manera

  ```css
  @media (min-width: 768px) {
    .column-drop-css {
      grid-template-columns: repeat(3, 1fr);
    }
    .segunda {
      grid-column: 3/4;
    }
  }
  ```

### Un cambio de posicion en las columnas

Se muestra como puede cambiar la posicion de las columnas (Notar en el encabezado) que el orden ha cambiado cuando va de mayor a menor.

```css
@media (min-width: 480px) {
  .column-drop-css {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }
  .primera {
    grid-column: 1/3;
    grid-row: 2/3;
  }
  .segunda {
    grid-column: 2/3;
    grid-row: 1/3;
  }
}

@media (min-width: 768px) {
  .column-drop-css {
    grid-template-columns: repeat(3, 1fr);
  }
  .primera {
    grid-column: 2/3;
    grid-row: unset; /*Resetea el grid row*/
  }
  .segunda {
    grid-column: 3/4;
    grid-row: unset; /*Resetea el grid row*/
  }
}
```

- Dispositivo mayor a 768px

  ![Large](/patternDesign/examples/07-column_drop_css_grid/img/Medium-Screen-1024x800.png)

- Dispositivo menor a 480px

  ![Medium](/patternDesign/examples/07-column_drop_css_grid/img/Large-Screen-688x1031.png)
