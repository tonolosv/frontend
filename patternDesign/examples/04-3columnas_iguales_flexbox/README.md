# 3 Columnas iguales Flexbox

- :heavy\*exclamation_mark: Los elementos a separar deben de coexistir en un elmento unico llamado **\*contenedor Padre**\_

  ```html
  <div class="contenedor tres-columnas">
    <!--Nombre que se escoge para la division-->
    <article class="entrada-blog">---</article>
    <article class="entrada-blog">---</article>
    <article class="entrada-blog">---</article>
  </div>
  ```

- En CSS usamos la propiedad `display: flexbox;` para obtener las caracteristicas que ofrece Flexbox

```css
@media (min-width: 768px) {
  .tres-columnas {
    display: flex;
    gap: 2rem;
  }
}
```

- En su momento el soporte para `gap`, no estaba disponible para firefox por esa razon se trabajaba de la siguiente manera el codigo

  ```css
  @media (min-width: 768px) {
  .tres-columnas {
    display: flex;
  }
  .entrada-blog{
    flex: 0 0 calc(33.3% - 1 rem)
    }
  }

  `.entrada_blog` es la clase que tienen los elementos hijos de la clase `.tres-columas`
  ```

- Para el 2023 el uso del gap directamente asociado al selector padre, esta vigente para todos los navegadores.

![Gap](/patternDesign/examples/04-3columnas_iguales_flexbox/img/gap.png)

Resultado del tratamiento del Flexbox

![3 columnas GRID](/patternDesign/examples/04-3columnas_iguales_flexbox/img/columnas_flexbox.png)

---

[:leftwards_arrow_with_hook: volver a menu](/patternDesign/)

```

```
