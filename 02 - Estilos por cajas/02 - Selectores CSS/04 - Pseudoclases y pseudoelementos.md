### [Las pseudoclases](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements#las_pseudoclases):

- Una pseudoclase es un selector que marca los elementos que están en un estado específico, por ejemplo, los que son el primer elemento de su tipo, o aquellos por los que el cursor les pasa por encima.
- Aplican estilo a ciertos estados de un elemento.
- Por ejemplo, selecciona un elemento solo cuando se le pasa el ratón por encima.

      a: hover {}

---

### [Los pseudoelementos](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements#pseudoelementos):

- Los pseudoelementos se comportan de manera similar a las pseudoclases. Sin embargo, actúan como si hubieras añadido un elemento HTML totalmente nuevo en el marcado, en lugar de haber aplicado una clase nueva a los elementos presentes. Los pseudoelementos empiezan con un doble signo de dos puntos ::.
- Seleccionan una parte determinada de un elemento en vez del elemento en sí.
- Por ejemplo, _::first-line_ siempre selecciona la primera línea del texto que se encuentra dentro de un elemento (_p_ por ejemplo), y actúa como si un elemento _span_ hubiera delimitado la primera línea.

        p::first-line { }

---
