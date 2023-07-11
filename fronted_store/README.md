# FRONTEND STORE

Simulacion de una store diseñada con html y CSS, que a su vez tiene la caracteristicas de estar construida con los principios de BEM.
Una buena practica para la elaboracion de sitios web, es formatear el documento en el css

- custom properties definir los colores, tipo de fuente a utilizar, etc
- Restructurar la pagina con box sizing para no tener dificultades en los tamaños de los elementos
- Definir los condiciones globales a aplicar a los elementos que mas se utilizan por ejemplo los encabezados, parrafos, enlaces junto a los colores y tamaños

El archivo _html_ se deben linkear los estilos css (normalize y style), de la misma manera si se utiliza google fonts

---

## BLOCK ELEMENT MODIFIER | [BEM](https://getbem.com/ 'sitio web oficial')

Metodologia para crear archivos `CSS` de manera reutilizable y ordenada; se deben seguir las convenciones de escritura para evitar colisiones de nombres

- Block: sera aquella seccion que no requiere de otras secciones y es significativa, se podria establecer como el padre y los elementos internos hijos del mismo

  > html `<div class="cliente">...</div>`

  > css `.cliente {...}`

- Element: Hijos del bloque que dependen de la generalidad que se vaya a construir, este debe ir con el nombre del bloque seguido de dos guiones bajos "\_\_"

  > hmtl `<p class="cliente__nombre">...</p>`

  > css `.cliente__nombre{...}`

- Modifier: Identifica que un elemento o un bloque tendra un diseño diferente por ello se modificara utilizando una bandera. Despues del _element_ se deben escribir lo modificadores con dos guiones medios "--"

  > hmtl `<p class="cliente__nombre--ceo">...</p>`

  > css `.cliente__nombre--ceo{...}`

---

Herramienta que se consulta para confirmar si la propiedad utilizad en un elemento es [CanIUse](https://caniuse.com/), es soportada por los navegadores que hay en el mercado
Cuando se desea mostrar diferentes productos y que puedan adapatarse al dispositivo, lo mejor es usar `grid`, ya que este permite posicionar segun convenga en columnas o filas. El siguiente codigo es clave para trabajar esta opcion

```css
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /*2 columnas*/
  gap: 2rem;
}
@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(3, 1fr); /*3 columnas*/
  }
}
```

---

Se pueden insertar imagenes desde el `CSS`, utilizando las propiedades de `background-image: url(../img/imagen.jpg);`

---

Conocer mas acerca de los formularios y sus atributos para mejorar su desempeño

---

Para ver el proyecto terminado visita [frontend Store](https://store-frontend-test.netlify.app/)

