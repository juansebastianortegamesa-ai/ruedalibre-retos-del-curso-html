1. Resumen General
Por temas de trabajo y tiempo, los commits del proyecto estuvieron desorganizados. Esta bitácora centraliza y documenta todo el proceso de desarrollo, desde la corrección de errores estructurales iniciales en HTML, la estandarización de estilos con CSS, hasta la implementación de la arquitectura responsiva (Mobile-First) y la inclusión de nuevos módulos como la "Flota" y la "Portada".

2. Mapeo de Correcciones por Archivo
Página Principal (index.html)
Visualización de Imágenes de Productos:

Estado Inicial: Rutas con barras invertidas (img\bicicletascooper.png), nombres incorrectos y etiquetas <img> faltantes.

Estado Actual: Rutas corregidas a barras inclinadas (img/), nombres exactos sincronizados con los archivos y todas las imágenes envueltas en su etiqueta correspondiente.

Redirección de Enlaces (Botones):

Estado Inicial: Se usaba <button> envolviendo un <a>, lo que causaba problemas de accesibilidad y herencia de colores.

Estado Actual: Se simplificó usando solo la etiqueta <a> estilizada con la clase .btn-reserva.

Semántica del Header: Se corrigió el atributo class duplicado y se limpiaron etiquetas huérfanas (como </li> sueltos) para validar el HTML.

Tarifas y Rutas (tarifas.html)
Proporciones del Encabezado:

Estado Inicial: El header heredaba min-height: 100vh, dejando un espacio en blanco excesivo.

Estado Actual: Se limitó esta altura solo a la portada de inicio. En tarifas, el encabezado es compacto. Se añadió la imagen de métodos de pago con un tamaño controlado.

Estilizado de Tablas:

Estado Inicial: Tablas con scroll horizontal que rompían la pantalla del celular.

Estado Actual: Se implementó overflow-x: auto para que el scroll ocurra dentro de la tabla. Se ajustaron paddings y tamaños de letra en móvil para que se lean completas sin desplazamiento lateral (requisito DevTools). Se añadió efecto cebra y colores corporativos.

Formulario de Reserva (reservas.html)
Organización de Campos y Labels:

Estado Inicial: Campos desalineados y selectores con doble pattern o formularios anidados inválidos.

Estado Actual: Se limpió la estructura. Se usó Flexbox (display: flex) para alinear cédula y celular en una sola fila en pantallas grandes.

Estados de Foco:

Estado Actual: Se definió el estado :focus con un contorno naranja (#F
39A2B
) para mejorar la accesibilidad visual al navegar con teclado.

Hoja de Estilos Principal (style.css)
Cálculo de Dimensiones Globales: Se implementó el reset universal *, *::before, *::after { box-sizing: border-box; }.

Tipografía: Se cambió el selector inválido #body por la etiqueta body, aplicando max-width: 75rem y fuentes Montserrat/Open Sans.

Imágenes Fluidas: Se aplicó max-width: 100%; height: auto; a todas las imágenes para que nunca se salgan de su contenedor.

3. Implementación de Layouts (Grid vs Flexbox)
Se tomaron decisiones técnicas justificadas para cada sección:

Portada (Index): Grid (1fr 1fr) para dividir la pantalla y Flexbox (flex-direction: column; justify-content: center) para centrar el texto verticalmente.

Galería "Nuestras rutas": Grid (repeat(3, 1fr)) para forzar 3 columnas exactas en escritorio.

Reservas: Grid con proporción 2fr 1fr para priorizar el formulario sobre el panel de contacto.

Fila del Formulario: Flexbox para alinear dos campos cortos horizontalmente en un solo eje.

Encabezado y Pie de Página: Flexbox (justify-content: space-between) para empujar los elementos a los extremos (Logo/Menú y los 3 bloques del footer).

4. Módulo de "Nuestra Flota" y Refactorización Mobile-First (v1.5)
Nueva Sección Flota: Se agregaron 7 modelos de bicicletas. Se utilizó CSS Grid con repeat(auto-fit, minmax(250px, 1fr)) para que la cuadrícula se reorganice sola sin usar media queries. Se usó Flexbox interno con margin-top: auto para que todos los botones "Reservar" queden alineados al fondo de la tarjeta.

Diseño Mobile-First: Se reescribió el CSS priorizando el celular.

En móvil (base): Header con título arriba y menú abajo centrado; grillas de 1 columna; footer apilado.

En Tablet (min-width: 768px): Se recupera la fila (MiniReto 1), grillas a 2 columnas.

En Escritorio (min-width: 1200px): Rutas a 3 columnas y flota a 4 columnas.

5. Resolución de Problemas en DevTools (Registro para Rúbrica)
Al probar con el modo dispositivo (360px, 768px, 1280px), se solucionaron:

Problema (360px): Scroll horizontal por culpa de las tablas y el botón de WhatsApp. Solución: Se aplicó overflow-x: hidden al body y scroll interno a las tablas.

Problema (360px): Imágenes de cabecera gigantes en reservas y tarifas. Solución: Se limitó su tamaño a 200px y max-width: 80%.

Problema (768px): El menú de navegación heredaba el tamaño de fuente del título. Solución: Se aisló el tamaño de letra en #menu a { font-size: 1rem; }.

Problema: Listas de texto plano en los servicios. Solución: Se convirtieron en tarjetas con bordes redondeados y sombras usando la clase .servicios.

6. Conclusión del Proceso
Semántica y Estructura: Código validado en HTML5, sin etiquetas huérfanas ni errores de atributos.

Estética y Adaptabilidad: Uso correcto de Grid y Flexbox, tarjetas alineadas, imágenes auto-ajustables y un diseño 100% responsivo.

Accesibilidad (WCAG): Foco claramente visible al navegar con la tecla Tab y contraste de colores adecuado.

Despliegue: Proyecto versionado con Git y publicado en GitHub Pages, verificado en un dispositivo móvil real..


