Se hara el ejercicio anterior, donde 3 columnas deben coexistir cuando una de ellas es la principal por ende la de mayor tamaño.

El uso de `display:flexbox` nos permitira tener a disposicion las caracteristica de `flex-basis` donde calculamos su tamaño dentro del espacio de trabajo.

### HTML

- Para el elemento padre siempre debe asignarse su clase, para que se añada la caracteristica `flex`, en el primer elemento hijo se crea una clase `flex-basis` para determinar su tamaño.

Los aside tendran 2 clases, una para aplicar `flex-basis` y una de ellas porque son iguales, tendra la propieda `order`

```css
@media (min-width: 768px) {
  .contenedor-flex {
    display: flex;
    justify-content: space-between;
    gap: 2rem;
  }
  .contenedor-principal {
    flex-basis: calc(60% -1rem);
  }
  .sidebar {
    flex-basis: calc(20% - 1rem);
  }
  .sidebar-1 {
    order: -1;
  }
}
```

---

![columnas flexbox](/patternDesign/examples/06-3columnas_flexbox/img/flexbox.png)
