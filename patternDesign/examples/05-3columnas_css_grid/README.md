Anteriormente se ha trabajado con columnas de igual tamaño, pero en el caso que el requerimiento se necesita 2 iguales, pero el tercero debe tener un mayor espacio que destaque; con `grid` se pueden elaborar este tipo de columnas.

Lo que se vera a continuacion en su primer aporte, es el trabajo de la forma numerica con los atributos conocidos. Luego se tendra la facilidad de identificacion con caracteristicas, que describan donde estara cada elemento.

---

### HTML

- El contenido principal deberá estar dentro de 2 clases, una padre que tendra la garantía que desde alli, se aplicará la propiedad `grid` y la otra que tendra la propiedad `grid-template-areas`
- los elementos que acompañan al contenido principal, deben ser identificados como `sidebar` 1/2 respectivamente

### CSS

- Despues de aplicar la propieda `grid`, de manera consecutiva debemos de dar el tamaño que tendran dichas columnas

  ```css
  grid-template-columns: 20% 60% 20%;
  ```

  El detalle que estas condiciones las aplica de manera indiferente, ignorando cual es el `main` o cuales son los `sidebar`

  ![ubicacion grid](/patternDesign/examples/05-3columnas_css_grid/img/grid-google.png)

  La ventaja que presenta la herramienta de <u>inspeccion</u> de google `grid`, se puede monitorear en que columna esta posicionada cada elemento, de tal manera que podemos moverlos segun convenga.

  ```css
  .contenido-principal {
    grid-column: 2/3;
  }
  ```

  La porcion de codigo anterior, ha movido el contenido principal hacia el centro, porque se delimito con `grid-column` que ocupe desde la posicion 2 a la 3, sin embargo sucede que uno de los aside fue colocado en la parte inferior.

  ![aside debajo](/patternDesign/examples/05-3columnas_css_grid/img/aside_abajo.png)

  Se podría colocar un aside desde la posicion `grid column: 1/2`, pero esto hara que salte a un nuevo `row`, ejemplificado en la siguiente imagen.
  Esto se da por el conflicto de _<u>colocacion automatica de la cuadricula</u>_; su acomodo es automatico.

  ```css
  .sidebar-1 {
    grid-column: 1/2;
  }
  ```

  ![aside mal](/patternDesign/examples/05-3columnas_css_grid/img/aside-mal.png)

  La manera apropiada para que las columnas se desplacen de manera correcta, es desde el elemento padre utilizar la propiedad `grid-auto-flow: column`, siendo corregido el diseño que se posicionaban abajo los aside

  ```css
  .contenedor-grid {
    display: grid;
    grid-template-columns: 20% 60% 20%;
    column-gap: 2rem;
    grid-auto-flow: column; /*propiedad flow*/
  }
  ```

  ![correccion de aside](/patternDesign/examples/05-3columnas_css_grid/img/grid-auto-colum.png)

  El codigo completo para la posicion de columnas con diferentes tamaños.

  ```css
  @media (min-width: 768px) {
    .contenedor-grid {
      display: grid;
      grid-template-columns: 20% 60% 20%;
      column-gap: 2rem;
      grid-auto-flow: column;
    }
    .contenido-principal {
      grid-column: 2/3;
    }
    .sidebar-1 {
      grid-column: 1/2;
    }
  }
  ```

  Si no se desea trabajar con porcentajes en `grid-template-columns`, existe una opcion que es manejada por fracciones, ademas asignar un nombre que identifique las columnas segun como sea su posicionamiento. Ver el siguiente codigo

  ```css
  @media (min-width: 768px) {
    .contenedor-grid {
      display: grid;
      grid-template-areas: 'izquierda contenido derecha';
      grid-template-columns: 1fr 3fr 1fr;
      column-gap: 2rem;
    }
    .contenido-principal {
      grid-area: contenido;
    }
    .sidebar-1 {
      grid-area: izquierda;
    }
  }
  ```

  ![Posicionamiento final](/patternDesign/examples/05-3columnas_css_grid/img/final.png)

  ---
  [:leftwards_arrow_with_hook: volver a menu](/patternDesign/)
