# 2 Columnas iguales con Flexbox

- Para aplicar el Flexbox, es importante que los elementos a modificar pertenezcan a un contenedor _**Padre**_.

- Iniciar Flexbox con: `display: flex`, de esta manera nos da apertura a todas las propiedades de flexbox

  > ```html
  > <div class="contenedor dos-columnas">
  >   <article class="entrada-blog">
  >     <h1>Titulo Entrada Blog</h1>
  > </div>
  > ```

  > ```css
  > @media (min-width: 768px) {
  >   .dos-columnas {
  >     display: flex;
  >     justify-content: space-between;
  >     gap: 2rem;
  >   }
  > }
  > ```

- > [!NOTE]
  >
  > Al aplicar flexbox, todos los elementos hijos los justifica de izquierda a derecha.

- En versiones anteriores, hay maneras para hacer 2 columnas; previamente se aplico `justify-content`

  - Al elemento hijo (que deben llamarse de igual manera), se tiene que añadir una nueva clase

  ```html
  <article class="entrada-blog">
    <!--asi se asigno la nueva clase-->
    <h1>Titulo Entrada Blog</h1>
  </article>
  <article class="entrada-blog">
    <h1>Titulo Entrada Blog</h1>
  </article>
  ```

  - luego utilizar la propiedad `flex-basis`

    ```css
    flex-basis: calc(50% -1rem); //divide en 2 pero coloca un espacio de 1 rem
    flex: 0 0 calc(50% - 1rem); // 0 factor de crecimiento, 0 factor mas pequeño y calc es tamaño base
    ```

- Actualmente `gap` es la manera idonea y menos codigo para separacion de columnas
