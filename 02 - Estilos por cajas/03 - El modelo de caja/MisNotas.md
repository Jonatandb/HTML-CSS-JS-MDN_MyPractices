## ¿Qué es el modelo de cajas CSS?

El modelo de cajas CSS completo se aplica a cajas que presentan comportamiento en bloque; las cajas con comportamiento en línea solo usan una parte del comportamiento definido en el modelo de cajas. El modelo define cómo funcionan juntas las diferentes partes de una caja (margen, borde, relleno y contenido) para crear una caja que puedas ver en tu página. Para complicarlo un poco más, hay un modelo de cajas estándar y un modelo de cajas alternativo.

## El modelo de cajas CSS estándar

En el modelo de cajas estándar, cuando estableces los atributos width y height para una caja, defines el ancho y el alto del contenido de la caja. Cualquier área de relleno y borde se añade a ese ancho y alto para obtener el tamaño total que ocupa la caja.

## El modelo de cajas CSS alternativo

Podrías pensar que es más bien incómodo tener que sumar el borde y el área de relleno para obtener el tamaño real de la caja, ¡y tienes razón! Por este motivo, CSS introdujo un modelo de caja alternativo algún tiempo después del modelo de cajas estándar. Con este modelo, cualquier ancho es el ancho de la caja visible en la página, por lo tanto, el ancho del área de contenido es ese ancho menos el ancho para el relleno y el borde.

##### Si quieres que todos tus elementos usen el modelo de cajas alternativo (opción común entre los desarrolladores) debes establecer la propiedad box-sizing en el elemento _**html**_. Luego debes configurar todos los demás elementos para que hereden ese valor, como se ve en el fragmento de código siguiente. Si deseas comprender qué hay detrás, consulta el [artículo de CSS-Tricks sobre el tamaño de las cajas.](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/)

        html {
          box-sizing: border-box;
        }
        *, *::before, *::after {
          box-sizing: inherit;
        }

## Margen

El margen es un espacio invisible que hay alrededor de la caja. Aleja el resto de elementos de la caja. _**Los márgenes pueden tener valores positivos o negativos**_. Establecer un margen negativo para un lado de tu caja puede hacer que se superponga con otros elementos de la página. Tanto si utilizas el modelo de cajas estándar como el alternativo, el margen siempre se añade después de haber calculado el tamaño de la caja que se ve.

#### Colapso del margen

Un punto clave a la hora de entender los márgenes es el concepto de colapso del margen. Si tienes dos elementos cuyos márgenes se tocan, esos márgenes se combinan para convertirse en un solo margen, cuyo tamaño es el del margen más grande.

Hay una serie de reglas que establecen cuándo los márgenes colapsan y cuándo no. Para obtener más información, [consulta la página web sobre entender el colapso de márgenes](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing). Por ahora solo debes recordar que el colapso de los márgenes es algo que puede suceder. Si creas un espacio con márgenes y no obtienes el espacio que esperas, probablemente es que se haya producido algún colapso de márgenes.

## Bordes

El borde se dibuja entre el margen y el área de relleno de una caja. Si utilizas el modelo de cajas estándar, el tamaño del borde se añade a los elementos width y height que establecen el alto y el ancho de la caja. Si utilizas el modelo de cajas alternativo, el tamaño del borde reduce el tamaño de la caja de contenido, porque ocupa una parte del alto y el ancho disponibles.

## Relleno

El relleno se encuentra entre el borde y el área de contenido. A diferencia de los márgenes, _**el relleno no puede tomar valores negativos**_, por lo que el valor debe ser 0 o positivo.

## El modelo de cajas y las cajas en línea

Todo lo anterior se aplica por completo a las cajas en bloque. Algunas de las propiedades también pueden aplicarse a las cajas en línea, como las que crea un elemento _**span**_.

## El uso de display: inline-block

Hay un valor especial de display que proporciona un punto medio entre inline y block. Esto es útil para situaciones en las que no deseas que un elemento fuerce un salto de línea, pero sí deseas que se respeten las propiedades width y height para evitar superposiciones como la que se ve arriba.

Un elemento con display: _inline-block_ conforma un subconjunto de los elementos en bloque que ya conocemos:

- Se respetan las propiedades de ancho y alto.
- El relleno, el margen y el borde mantienen los otros elementos alejados de la caja.

Sin embargo, no se fuerza un salto de línea, y solo se hace más grande que su contenido si añades las propiedades width y height explícitamente.

Esto puede ser útil cuando deseas dar a un enlace un área de impacto más grande añadiendo padding. _**a**_ es un elemento en línea como _**span**_; puedes usar display: inline-block para configurar el área de relleno para facilitar al usuario hacer clic en el enlace.
