# Bitácora de Cambios y Optimizaciones del Proyecto
**Proyecto:** Rueda Libre — Alquiler de Bicicletas en Medellín
## 1. Resumen General
POR TEMAS DE TRABAJO Y EL TIEMPO MIS COMMITS ESTABAN DESORGANIZADOS POR LO QUE ESTA VITACORA ABARCA TODO LO QUE SE HIZO DESDE EL 24 DE OCTUBRE HASTA LA FECHA ACTUAL QUE ES 2 DE NOVIEMBRE

Esta bitácora documenta las correcciones, ajustes de accesibilidad, optimizaciones estructurales en HTML y estandarizaciones de diseño mediante CSS realizadas a lo largo del desarrollo del sitio web para "Rueda Libre".

## 2. Mapeo de Correcciones por Archivo

### Página Principal (index.html)

* **Visualización de Imágenes de Productos:**

  * *Estado Inicial:* Las rutas utilizaban barras invertidas (`img\bicicletascooper.png`) y nombres que no coincidían con los archivos en disco (`bicicletas-bmx.png`, `bicicletascooper.png`), además de faltar la etiqueta `<img>` en las bicicletas de competición.

  * *Estado Actual:* Se corrigieron las rutas a barras inclinadas directas (`img/`) y se mapearon los nombres exactos: `img/bicicleta-scoop.png`, `img/bmx.png`, `img/bicicletas-competicion.png`, `img/cascos-bicicleta.png`, `img/accesorios-bicicleta.png` y `img/kit-limpieza-bicicleta.png`.

* **Redirección de Enlaces:**

  * *Estado Inicial:* Se tenía un elemento `<button>` envolviendo una etiqueta `<a>` (`<button id="button"><a href="...">...</a></button>`). Esto provocaba que el texto apareciera de color azul de enlace predeterminado y generaba problemas de accesibilidad.

  * *Estado Actual:* Se simplificó utilizando la etiqueta `<a>` estilizada visualmente como botón mediante la clase `.btn-reserva`.

### Tarifas y Rutas (tarifas.html)

* **Proporciones del Encabezado (`#header`):**

  * *Estado Inicial:* El header heredaba `min-height: 100vh` globalmente, provocando un espacio en blanco excesivo antes de poder visualizar las tablas de precios y recorridos.

  * *Estado Actual:* Se desacopló la regla `min-height: 100vh` del selector general `#header` y se asignó exclusivamente a la portada del inicio mediante una clase específica (`.portada-inicio`), dejando en `tarifas.html` un relleno vertical proportional (`padding: 2rem 1rem`).

* **Estilizado de Tablas:**

  * *Estado Inicial:* Estilos de tabla básicos o incoherentes.

  * *Estado Actual:* Se implementó `border-collapse: collapse`, relleno adecuado en celdas (`th`, `td`), encabezados con color verde de marca (`#1E7A4F`) con texto en blanco de alto contraste y filas intercaladas (efecto cebra).

### Formulario de Reserva (reservas.html)

* **Organización de Campos y Labels:**

  * *Estado Inicial:* Campos desalineados respecto a sus etiquetas correspondientes y sin ancho consistente.

  * *Estado Actual:* Se configuraron los `<label>` con `display: block` sobre cada campo y los `<input>` / `<select>` a todo el ancho disponible (`width: 100%`) dentro de sus respectivos `<fieldset>`.

* **Estados de Foco y Accesibilidad:**

  * *Estado Inicial:* Borde azul genérico del navegador al interactuar con el teclado o mouse.

  * *Estado Actual:* Definición del estado `:focus` con contorno de resalte (`outline`) usando el color de marca naranja pedal (`#F39A2B`) y resplandor sutil.

### Hoja de Estilos Principal (style.css)

* **Cálculo de Dimensiones Globales (`box-sizing`):**

  * *Estado Inicial:* Los anchos de los elementos se calculaban por fuera del padding y el borde, desalineando componentes.

  * *Estado Actual:* Inclusión de la regla universal:

    ```css
    *, *::before, *::after {
        box-sizing: border-box;
    }
    ```

* **Tipografía y Heredabilidad:**

  * *Estado Inicial:* Existía una regla `#body` (con selector de ID no existente) que impedía que los estilos globales de fuente y márgenes se aplicaran correctamente.

  * *Estado Actual:* Corrección a la etiqueta `body`, estableciendo ancho máximo (`max-width: 75rem; margin: 0 auto;`) y tipografías corporativas (`Montserrat` para títulos y `Open Sans` para párrafos).

* **Control de Imágenes y Cuadrícula de Tarjetas:**

  * *Estado Inicial:* Imágenes de tamaño excesivo y tarjetas desproporcionadas en filas con pocos elementos.

  * *Estado Actual:*

    * Regla universal de fluidez para imágenes: `img { max-width: 100%; height: auto; display: block; }`.

    * Configuración de la retícula de tarjetas con CSS Grid (`grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));`) y centrado horizontal (`justify-content: center;`).

* **Navegación Horizontal (`#menu`):**

  * *Estado Inicial:* Enlaces desordenados.

  * *Estado Actual:* Flexbox aplicado en `#menu` (`display: flex; gap: 1.5rem; justify-content: center;`) para distribuir el menú en una sola fila.

## 3. Medición en DevTools: Cambio en `box-sizing` (Punto 7)

| Elemento Analizado | Con `box-sizing: content-box` (Inicial) | Con `box-sizing: border-box` (Actual) | Impacto |
| ----- | ----- | ----- | ----- |
| **Tarjeta de Producto** (`article.Bicicleta li`) | Ancho base + 32px (padding) + 2px (border) = **Mayor al valor asignado** | Ancho total fijo exacto incluyendo relleno y borde | Evita desbordamientos y descuadres en la cuadrícula de la página |

## 4. Estado Actual del Sitio

1. **Semántica y Estructura:** Código validado en HTML5, sin etiquetas inventadas y con buen uso de etiquetas accesibles.
2. **Estética y Adaptabilidad:** Tarjetas alineadas, imágenes auto-ajustables y encabezados proporcionales a cada sección.
3. **Accesibilidad (WCAG):** Foco claramente visible al navegar con la tecla `Tab` tanto en links como en formularios.