Aquí tienes una propuesta de bitácora detallada para tu proyecto, cumpliendo con los requisitos que mencionaste (tiempo de 1 hora y descripción de lo realizado).

***

# Bitácora de Desarrollo: Catálogo en Bootstrap 5.3

**Fecha:**11 de noviembre del 2026
**Tiempo invertido:** 1 hora
**Archivo generado:** `pruebas/catalogo-bootstrap.html`

##  Objetivo de la sesión
Recrear la sección de "Nuestra flota" (catálogo de bicicletas) del archivo `index.html`, integrándole un *header* y un *footer* similares a los originales. La regla principal fue **no utilizar CSS propio** (ni `styles.css` ni etiquetas `<style>`), logrando toda la maquetación y los estilos visuales exclusivamente con clases de utilidad y componentes de Bootstrap 5.3.

##  ¿Qué se hizo? (Paso a paso)

1. **Estructura general (Sticky Footer):**
   * Se configuró la etiqueta `<body>` con las clases `d-flex flex-column min-vh-100`. Esto asegura que, sin importar el tamaño de la pantalla, el footer siempre se mantenga pegado a la parte inferior de la ventana.
   * Se le asignó `flex-grow-1` a la etiqueta `<main>` para que ocupe todo el espacio disponible y empuje el footer hacia abajo.

2. **Header (Navbar):**
   * Se implementó el componente `navbar` de Bootstrap con la clase `navbar-expand-lg`. Se optó por un fondo blanco (`navbar-white`) 
    para mantener una estética limpia.
   * Se utilizó el botón "hamburguesa" (`navbar-toggler`) para que el menú colapse automáticamente en dispositivos móviles, demostrando la capacidad *responsive* de Bootstrap sin código extra.
   * Se ajustaron las rutas del menú para que apunten correctamente al `../index.html` y a las páginas internas.

3. **Catálogo de Bicicletas (El núcleo):**
   * **Grilla Responsiva:** Se utilizó la clase `row g-4` para crear la cuadrícula con separación (gutters). Cada tarjeta se envolvió en un `div` con las clases `col-12 col-sm-6 col-lg-4 col-xl-3`, logrando exactamente lo pedido: 1 columna en celulares, 2 en tablets (`sm`), 3 en pantallas medianas (`lg`) y 4 en pantallas grandes (`xl`).
   * **Tarjetas (Cards):** Se usó el componente `card` con utilidades como `h-100` (para que todas tengan la misma altura), `p-4`, `border`, `rounded`, `bg-light` y `shadow-sm` para darles el aspecto visual del index original.
   * **Imágenes:** Se utilizó la clase `ratio ratio-4x3` para mantener una proporción exacta y evitar que las imágenes se deformen, combinándolo con `object-fit-cover`.
   * **Botones y Alineación:** Se usó `btn btn-success` para simular los botones verdes de reserva del index. Para que todos los botones quedaran alineados al fondo de la tarjeta (sin importar cuánto texto tuviera encima), se aplicó `flex-grow-1` al párrafo descriptivo y `mt-auto` al botón.
   * Se ajustaron las rutas de las imágenes a la carpeta local (`../img/...`).

4. **Footer:**
   * Se construyó con un fondo claro (`bg-white`), texto negro y un borde superior sutil.
   * Se usó la grilla (`row` y `col-12 col-md-4`) para dividir la información de contacto, horarios y descripción en tres columnas en pantallas grandes, apilándose en móviles.
   * Se adaptó el botón de WhatsApp usando `btn btn-success` y se centró, dándole un toque visual idéntico al original.

## 💡 Aprendizajes y Conclusiones

* **Poder de las utilidades:** Descubrí que clases como `d-flex`, `flex-column`, `mt-auto` y `h-100` son muy utiles para resolver  los problemas iniciales que tenia de  alineación vertical , aparte aveses es mucho mas rapido que crear cada clase para cada cosa en el css 
* **Consistencia visual:** Aunque no usamos las tipografías personalizadas ni los colores exactos en hexadecimal del `index`, el uso de la paleta de Bootstrap (como `bg-light`, `text-secondary` y `btn-success`) logró un resultado visualmente coherente y muy profesional.
* **Cero deuda técnica:** Al usar solo Bootstrap, la página es ya es responsive y fácil de mantener (ya que es solo la seccion del catalogo). pero por ejemplo  Si se necesita cambiar un color, solo se cambia la clase y no hay que buscar en archivos CSS externos.



---

### 1. Enfoque con CSS Propio (`index.html` + `style.css`)

**Ventajas:**
* **Control absoluto y precisión:** Tienes el control exacto de cada píxel. Los colores son exactamente los de tu paleta (`--color-verde-ruta: #1e7a4f`), las tipografías son las que definiste (Montserrat y Open Sans) y los efectos `hover` o las sombras son únicas.
* **Identidad visual única:** La página no se ve como una plantilla genérica. Tiene la personalidad de la marca "Rueda Libre".

* **Curva de aprendizaje nativa:** No dependes de recordar las clases de un framework (como `col-md-6` o `d-flex`). Escribes CSS puro, lo cual es una habilidad fundamental y universal.

**Desventajas:**
* **Mayor tiempo de desarrollo:** Tienes que escribir manualmente las Media Queries (ej. `@media (min-width: 768px)`), definir los contenedores Flexbox/Grid y calcular los espaciados uno por uno.
* **Mantenimiento a escala:** A medida que el sitio crece, el archivo CSS se vuelve un "monstruo". Requiere mucha disciplina (usar metodologías como BEM) para evitar que los estilos de una sección rompan otra.
* **Componentes interactivos desde cero:** Si quisieras hacer el menú hamburguesa para móviles, tendrías que agregar JavaScript propio. Bootstrap ya lo trae hecho.
* **Propenso a errores visuales:** Al hacer la responsividad manual, es fácil olvidar probar en algún tamaño de pantalla intermedio y que el diseño se rompa.

---

### 2. Enfoque con Bootstrap (`catalogo-bootstrap.html`)

**Ventajas:**
* **Velocidad de desarrollo brutal:** Lo que en CSS propio te tomaba 30 minutos de maquetación, en Bootstrap se resuelve con una línea de clases: `col-12 col-sm-6 col-lg-4 col-xl-3`. La grilla ya está hecha y probada.
* **Responsive "Out of the box":** Bootstrap está diseñado bajo la filosofía *Mobile-First*. Los puntos de quiebre (breakpoints) están estandarizados y probados en miles de dispositivos. No tienes que programar Media Queries.
* **Componentes listos para usar:** El menú de navegación (`navbar`) colapsable, las tarjetas (`card`), los botones (`btn`), las alertas, etc., vienen preconstruidos con su propio JavaScript (vía el bundle). Ganaste un menú móvil funcional sin escribir una línea de JS.
* **Consistencia visual:** Utilidades como `mt-auto`, `g-4` o `p-4` aseguran que los espacios y márgenes sean siempre coherentes en todo el sitio.

**Desventajas:**

* **"Look" genérico (Bootstrap-izado):** Si no lo personalizas, todo el mundo notará que usaste Bootstrap. Los colores (`btn-success`) y las fuentes por defecto son las del framework, no las de tu marca (perdiste la fuente Montserrat y el verde exacto de tu paleta).
* **Dificultad para personalizar a fondo:** Si quieres que un botón de Bootstrap tenga un borde de un color específico que no está en sus utilidades, terminarás escribiendo CSS propio para sobrescribir Bootstrap (usando `!important` en muchos casos), lo cual es una mala práctica.
* **Dependencia de Terceros:** Si el CDN de Bootstrap falla o hay un problema de red, tu página perderá todos los estilos y estructura.

---

###  Conclusión: cual usaria?

* **Usaria css  Propio si:** Es un proyecto pequeño/mediano, necesitas una **identidad de marca muy estricta** (colores exactos, tipografías específicas), o quieres demostrar dominio avanzado de CSS nativo, Grid y Flexbox.
* **Usa Bootstrap si:** Necesitas un **prototipo rápido**, el proyecto va a crecer mucho y necesitas estandarización, o si el equipo de desarrollo es grande y todos deben hablar el "mismo idioma" de clases.
.



# Bitácora de Migración: Rueda Libre v1.5 a v2.0-beta

## 1. Resumen del Proyecto
El objetivo de esta migración fue refactorizar el sitio web de "Rueda Libre" para eliminar el CSS de distribución personalizado y adoptar el sistema de cuadrícula (Grid) y las utilidades de Bootstrap 5.3. Se priorizó la semántica, la responsividad (360px, 768px, 1280px), la limpieza del código (cero `!important`, cero estilos en línea) y la conservación de la identidad visual de la marca.

## 2. Comparativa de Código (`styles.css`)
*   **Versión v1.5 (Código Original):** 285 líneas de código.
*   **Versión v2.0-beta (Actual):** 98 líneas de código.
*   **Reducción:** **187 líneas menos (una reducción del 65.6%)**.

*El CSS ahora solo contiene variables de color, tipografía, bordes, sombras y estados de foco. Toda la distribución (`display: flex`, `grid`, `margin: auto`) fue eliminada y delegada a Bootstrap.*

## 3. Tiempo Invertido en la Migración
*   **Análisis inicial y detección de conflictos (DevTools):** 30 minutos.
*   **Refactorización de los 3 archivos HTML (aplicación de grid y utilidades):** 1 hora 30 minutos.
*   **Limpieza profunda de `style.css` y ajuste de variables en `:root`:** 1 hora.
*   **Pruebas responsivas cruzadas (360px, 768px, 1280px):** 30 minutos.
*   **Tiempo total:** **3 horas 30 minutos.**

## 4. Ventajas y Desventajas Observadas

### Ventajas
1.  **Mantenibilidad Extrema:** El CSS se redujo más de la mitad. Si se requiere mover un elemento, solo se modifican las clases en el HTML (`col-md-8`), sin tocar el CSS.
2.  **Responsividad Nativa:** Las tablas y el formulario son proporcionales en todos los dispositivos. El uso de `table-responsive` solucionó de raíz los desbordamientos en móviles.
3.  **Accesibilidad y Consistencia:** Los formularios ahora tienen estados de foco estandarizados y accesibles (`form-control`, `form-select`).
4.  **Cascada Limpia:** Al cargar Bootstrap primero (CDN) y nuestro `style.css` después, las reglas de la marca se aplican sin necesidad de recurrir a `!important`.

### Desventajas
1.  **HTML más "Verboso":** Las etiquetas ahora contienen múltiples clases utilitarias (ej. `d-flex flex-column flex-md-row align-items-center gap-3`), lo que puede hacer que el archivo HTML se vea más denso a primera vista.
2.  **Curva de Aprendizaje:** Requiere memorizar la nomenclatura de los breakpoints de Bootstrap (`md`, `lg`) y las utilidades de flexbox para no volver a caer en la tentación de escribir CSS de layout personalizado.
3.  **Dependencia de CDN:** La página depende de una conexión a internet para cargar los estilos y scripts de Bootstrap.

## 5. Conclusión
La migración a **Bootstrap 5.3 (v2.0-beta)** ha sido un éxito total. Se logró el objetivo principal: **delegar toda la responsividad y distribución al framework, dejando el CSS propio exclusivamente para la identidad visual** (colores, tipografía, bordes y sombras). Las páginas de Inicio, Tarifas y Reservas se adaptan perfectamente a los tres anchos solicitados (360px, 768px y 1280px). El código es ahora escalable, semántico, libre de malas prácticas (sin `<span>` innecesarios, sin `style=""`, sin `!important`) y está listo para ser desplegado en GitHub Pages.


-------------------------------------

# Bitácora de Desarrollo - Proyecto Rueda Libre (v2.0)

**Pequeño Resumen Ejecutivo:** 
Este documento detalla la evolución técnica del proyecto "Rueda Libre", desde su estructura inicial hasta la implementación de la versión 2.0. El objetivo principal fue personalizar profundamente Bootstrap 5.3.3 para alinearlo con la identidad visual de la marca (Verde Ruta, Naranja Pedal, Azul Noche), garantizando al mismo tiempo el cumplimiento estricto de las normas de accesibilidad, la semántica HTML y las buenas prácticas de desarrollo, todo sin modificar los archivos originales del framework.

---

## 1. Correcciones en `style.css` y Variables Globales
*   **Corrección de sintaxis raíz:** Se eliminó el selector erróneo `*:root` y se reemplazó por el correcto `:root` para que las variables globales de CSS se apliquen adecuadamente.
*   **Sobreescritura de variables de Bootstrap:** Se definieron las variables `--bs-primary`, `--bs-primary-rgb`, `--bs-link-color`, `--bs-link-hover-color`, `--bs-border-radius`, `--bs-body-font-family`, `--bs-body-color` y `--bs-body-bg` para alinear el framework con los colores y fuentes de la marca.
*   **Tipografía:** Se aplicó la fuente Montserrat a los títulos y Open Sans a los textos. Se corrigió la asignación de los encabezados (`h1`, `h2`, `h3`) para usar la variable nativa `--bs-heading-color` y se forzó el grosor mediante una variable personalizada `--bs-heading-font-weight: 700`.
*   **Eliminación de malas prácticas:** Se eliminó cualquier uso de `!important` en el archivo, logrando la personalización mediante la especificidad correcta del CSS y el uso de las variables nativas de Bootstrap.

## 2. Botones y Clases Propias
*   **Botón Principal (`btn-primary`):** Se personalizó usando las variables `--bs-btn-*` de Bootstrap para que el estado normal sea Verde Ruta y el `:hover` / `:active` sea Naranja Pedal con texto Azul Noche, asegurando el contraste.
*   **Nuevo Botón Naranja (`.btn-naranja`):** Se creó esta variante con sus respectivos estados (fondo Naranja, hover Verde) para el llamado a la acción principal (CTA) del inicio.
*   **Botón Outline (`.btn-outline-primary`):** Se ajustó para mantener la coherencia con los colores de la marca.
*   **Creación de más de 3 clases propias:** Se implementaron clases complementarias a Bootstrap: `.titulo-seccion`, `.tarjeta-beneficio` (con efecto hover), `.precio-tarjeta`, `.nivel-facil`, `.nivel-dificil`, `.imagen-banner`, `.card-img-uniform` y `.boton-whatsapp`.

## 3. Cambios Semánticos y Estructurales en el HTML
*   **Etiqueta Header:** Se delimitó correctamente la cabecera de todas las páginas utilizando la etiqueta semántica `<header>` que envuelve al `<nav>`.
*   **Navbar con Iconos:** Se integró **Bootstrap Icons** (vía CDN) en el menú de navegación. Se agregaron iconos a cada enlace y se configuró el color de hover a Verde Ruta mediante las variables `--bs-navbar-hover-color` y reglas CSS específicas.
*   **Unificación de Botones:** Se reemplazaron los botones antiguos que usaban `btn-success` por el nuevo `.btn-primary` personalizado para mantener la identidad visual estricta.
*   **Estructura en Grillas:** Se estandarizó la estructura de las secciones para que sigan estrictamente el patrón de Bootstrap: `container > row > col`. Esto se aplicó en productos, rutas, flota y la nueva sección de servicios.
*   **Rediseño de "Nuestros Servicios":** Se cambió la lista ordenada (`<ol>`) de la versión original por un diseño de tarjetas (usando la clase `.tarjeta-beneficio` con iconos representativos), logrando una interfaz mucho más visual y coherente con la sección "¿Por qué elegir Rueda Libre?".
*   **Uso correcto de Tablas:** Se aseguró de que la clase `.table-responsive` se aplicara única y exclusivamente a los contenedores de tablas (Horarios en `reservas.html` y Tarifas en `tarifas.html`), manteniendo el formulario adaptado mediante las columnas de la grilla de Bootstrap.

## 4. Accesibilidad y Buenas Prácticas
*   **Iconos Accesibles:** Se agregó el atributo `aria-hidden="true"` a todos los iconos de Bootstrap Icons que son meramente decorativos.
*   **Botones con `aria-label`:** Se añadieron etiquetas `aria-label` a botones que solo contienen iconos (como el botón de cerrar de las alertas/modales, los controles del carrusel y el botón flotante de WhatsApp) para que los lectores de pantalla sepan qué hacen.
*   **Contraste:** Se verificó que la combinación de colores (texto blanco sobre fondo verde oscuro, y texto azul noche sobre fondo naranja) cumpla con la relación de contraste mínima de 4.5:1 exigida por las normas de accesibilidad.
*   **Semántica HTML:** Se reemplazaron elementos genéricos por etiquetas semánticas, como usar `<article>` para las tarjetas, `<section>` para los bloques temáticos, `<aside>` para información complementaria y un enlace de "Saltar al contenido" (`visually-hidden-focusable`) para la navegación por teclado.

## 5. Checklist de Cumplimiento (Rúbrica)
*   [x] Variables de Bootstrap sobreescritas sin tocar el archivo original del CDN.
*   [x] Uso de variables `--bs-btn-*` para los botones.
*   [x] Creación de más de 3 clases propias complementarias.
*   [x] Integración de Bootstrap Icons con accesibilidad (`aria-hidden`, `aria-label`).
*   [x] Código estructurado estrictamente en `container > row > col`.
*   [x] Cero uso de `!important` y cero etiquetas `<span>`.
*   [x] Archivo `style.css` limpio y cargado después de Bootstrap.
*   [x] Diseño completamente adaptable a móvil, tablet y escritorio.

## 6. Conclusión y Aprendizajes
A lo largo de este proyecto, se consolidaron aprendizajes fundamentales sobre el desarrollo frontend moderno:

1.  **Personalización Profunda de Frameworks:** Se comprendió cómo extender y adaptar Bootstrap sin necesidad de modificar sus archivos fuente, aprovechando al máximo su arquitectura de variables CSS (`--bs-*`). Esto garantiza que el código sea fácil de mantener y actualizar en el futuro.
2.  **La Importancia de la Semántica y Accesibilidad:** Se evidenció que una página no solo debe verse bien, sino ser comprensible para todos. El uso correcto de etiquetas HTML5 (`<header>`, `<main>`, `<section>`, `<article>`) y atributos de accesibilidad (`aria-label`, `aria-hidden`) son pilares no negociables en el desarrollo web profesional.
3.  **Buenas Prácticas CSS:** Se reforzó la idea de evitar malas prácticas como el uso de `!important` o estilos en línea. Al entender la especificidad y la cascada de CSS, se logró un código más limpio, escalable y predecible.
4.  **Diseño Responsivo Estructurado:** Se dominó el sistema de cuadrícula de Bootstrap (`container > row > col`) para crear interfaces que se adaptan perfectamente a cualquier dispositivo, entendiendo la responsabilidad de cada clase utilitaria.








