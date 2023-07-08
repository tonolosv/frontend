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

Herramienta que se consulta para confirmar la propiedad en un elemento es [CanIUse](https://caniuse.com/), muestra el soporte que tiene en los diferentes navegadores que son los mas usados.
