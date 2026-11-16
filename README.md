#  Rueda Libre – Retos del Curso HTML

Este repositorio contiene el desarrollo de **Rueda Libre**, un sitio web estático para una empresa ficticia de alquiler de bicicletas en Medellín. El proyecto forma parte de los retos del curso de HTML y está construido principalmente con **Bootstrap, HTML y CSS**.

##  Descripción del Proyecto

Rueda Libre es una página web informativa y transaccional que permite a los usuarios:

- Conocer los servicios de alquiler de bicicletas.
- Explorar el catálogo de productos (bicicletas urbanas, de montaña, eléctricas, accesorios, etc.).
- Consultar tarifas y rutas disponibles.
- Realizar reservas mediante un formulario con validaciones.

El sitio está diseñado para ser responsivo y utilizar componentes de Bootstrap para agilizar el desarrollo de la interfaz.

## 🛠️ Tecnologías Utilizadas

| Tecnología | Uso en el proyecto |
|------------|-------------------|
| **HTML5** | Estructura semántica de todas las páginas (`index.html`, `reservas.html`, `tarifas.html`, etc.). |
| **CSS3** | Estilos personalizados, variables de marca y sobreescritura de estilos de Bootstrap en `css/style.css`. |
| **Bootstrap 5** | Framework principal para el diseño responsivo, componentes (navbar, cards, formularios, botones, modales) y sistema de grid. |
| **JavaScript** | Validación de formularios y manipulación básica del DOM (mencionado en `bitacoras.txt`). |
| **Git / GitHub** | Control de versiones y alojamiento del repositorio. |

> **Nota:** El proyecto no utiliza frameworks de JavaScript avanzados ni preprocesadores CSS; es un sitio estático que se puede abrir directamente en el navegador.

## 📁 Estructura del Proyecto

La organización de carpetas y archivos es la siguiente:

```
ruedalibre-retos-del-curso-html/
│
├── css/
│   └── style.css               # Hoja de estilos principal (variables, overrides de Bootstrap, estilos propios)
│
├── img/                        # Imágenes y recursos gráficos
│   ├── antes y despues rueda libre 2.0/   # (subcarpeta con imágenes comparativas)
│   ├── LogotipocircularRuedaLibre.png
│   ├── accesorios-bicicleta.png
│   ├── bicicleta-scoop.png
│   ├── bicicleta.png
│   ├── bicicletaelectrica.png
│   ├── bicicletas-competicion.png
│   └── ... (otras imágenes de productos y promociones)
│
├── paginas/                    # Páginas secundarias del sitio
│   ├── reservas.html           # Formulario de reserva con validaciones
│   └── tarifas.html            # Información de tarifas y rutas
│
├── pruebas/                    # Archivos de práctica y versiones de prueba
│   ├── bitacora.md             # Notas de aprendizaje y pruebas
│   └── catalogo-boostrap.html  # Catálogo de bicicletas usando componentes de Bootstrap
│
├── bitacoras.txt               # Registro de conceptos técnicos (HTTP, rutas, semántica, etc.)
├── index.html                  # Página principal del sitio
└── README.md                   # Este archivo
```

### 🔍 Detalle de los archivos principales

- **`index.html`**  
  Es la página de inicio. Contiene la barra de navegación, secciones de "¿Quiénes somos?", "Nuestros servicios", "Nuestros productos" (con tarjetas de bicicletas y accesorios) y el pie de página. Utiliza clases de Bootstrap para el layout y los componentes.

- **`css/style.css`**  
  Define las variables de marca (colores, tipografías) y sobreescribe las variables de Bootstrap (`--bs-primary`, `--bs-warning`, etc.) para adaptar el tema visual. También incluye estilos para la navbar, botones, formularios y utilidades de accesibilidad (focus visible).

- **`paginas/reservas.html`**  
  Formulario de reserva con campos validados (nombre, apellido, email, cédula, teléfono, cantidad de bicicletas, tipo, duración, fecha, términos y condiciones). Incluye mensajes de error y un modal de políticas de alquiler.

- **`paginas/tarifas.html`**  
  Página destinada a mostrar las tarifas y rutas disponibles (no se detalla en este análisis, pero forma parte del flujo de navegación).

- **`pruebas/catalogo-boostrap.html`**  
  Versión de prueba del catálogo que utiliza componentes de Bootstrap (cards, botones) para listar la flota de bicicletas con precios por hora.

- **`bitacoras.txt`**  
  Archivo de texto que documenta conceptos aprendidos: códigos de estado HTTP (304, 404), rutas relativas, esquemas de regiones semánticas y la función de HTML, CSS y JavaScript en el proyecto.

##  Cómo visualizar el proyecto

1. Clona el repositorio:
   ```bash
   git clone https://github.com/juansebastianortegamesa-ai/ruedalibre-retos-del-curso-html.git
   ```
2. Abre el archivo `index.html` en tu navegador.
3. Navega entre las páginas usando los enlaces del menú.

> **Recomendación:** para abrir mejor el archivo desde visual usaar  la extensión **Live Server** de VS Code o cualquier servidor local estático.

## 🎯 Objetivo del Proyecto

Este repositorio refleja el aprendizaje y la aplicación práctica de:

- Estructura semántica de HTML5.
- Estilos con CSS3 y personalización de Bootstrap.
- Diseño responsivo con el sistema de grid y componentes de Bootstrap.
- Validación básica de formularios con JavaScript.
- Organización de archivos y carpetas en un proyecto web estático.

## 📝 Notas

- El proyecto está en constante evolución; la carpeta `pruebas/` contiene versiones experimentales y apuntes de clase.
- El archivo `bitacoras.txt` sirve como bitácora técnica y puede ser útil para comprender la lógica detrás de las rutas y la semántica empleada.

---

**Autor:** Juan Sebastián Ortega Mesa  
**Curso:** curso html  y css  – Riwi  
**Año:** 2026
