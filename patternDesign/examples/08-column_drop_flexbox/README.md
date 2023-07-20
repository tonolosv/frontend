# Column Drop Flexbox

Una nueva alternativa para la recolocacion de las columnas, es usar Flexbox. Para ello se tendra un elemento padre que contiene `display: flex`; para que habilite todas las caracteristicas de los elementos.
A diferencia de Grid, se añade una nueva clase al contenedor main para moverlo a cualquier lado que se requiera, y los aside ".primera y .segunda" son los que se posicionaran dependiendo del lugar.
Las condiciones de trabajo que se realizaron anteriormente son identicas en este posicionamiento, porque es segun el espacio disponible.

```css
@media (min-width: 480px) {
  .column-drop-flex {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
  .contenido-principal,
  .primera {
    flex-basis: calc(50% - 1rem);
  }
}

@media (min-width: 768px) {
  .contenido-principal,
  .primera,
  .segunda {
    flex: 0 0 calc(33.3% - 2rem);
  }
}
```

- Muestra en dispositivo con pantalla normal

  ![Large](/patternDesign/examples/08-column_drop_flexbox/img/large.png)

- Dispositivos tipo tablet

  ![Medium](/patternDesign/examples/08-column_drop_flexbox/img/medium.png)

- Dispositivos Moviles

  ![](/patternDesign/examples/08-column_drop_flexbox/img/movil.png)

---

[:leftwards_arrow_with_hook: volver a menu](/patternDesign/)
