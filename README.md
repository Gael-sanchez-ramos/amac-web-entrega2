# Bolsa de Trabajo AMAC — Entrega 2

Maquetación estática en HTML y CSS para personas adultas mayores, basada en el [prototipo de Figma](https://www.figma.com/design/3BkOcgQYNTJxL8vdlkGdiC/Bolsa-de-Trabajo-AMAC?node-id=0-1).

## Abrir el proyecto

Abre `index.html` en un navegador o usa Live Server desde esta carpeta. No requiere instalación, frameworks ni JavaScript.

## Páginas y navegación

- `index.html`: buscador y filtros visuales, seis vacantes y enlaces a su detalle.
- `vacante.html`: detalle de Auxiliar de atención. Las otras cinco tarjetas tienen sus propios archivos `vacante-*.html` con la misma estructura.
- `login.html`: formulario visual de acceso y enlaces a registro y solicitudes.
- `registro-candidato.html`: datos personales, dirección, contacto, experiencia, habilidades y consentimientos.
- `mis-solicitudes.html`: tres solicitudes con estados Pendiente, Aceptada y Rechazada. El botón Cancelar solo está activo en la Pendiente; en las resueltas aparece deshabilitado con una explicación (RF-006).
- `empresa-vacantes.html`: panel de la empresa, acciones visuales y dos solicitudes de ejemplo.

Flujo de demostración: Buscar empleo → Ver vacante → Postularme → Iniciar sesión → Mis solicitudes. El enlace de acceso muestra la pantalla de ejemplo; no autentica a una persona.

Además de las seis páginas obligatorias hay cinco detalles de vacante (`vacante-*.html`), uno por cada tarjeta del listado.

## Estructura CSS

- `css/variables.css`: colores, fuentes, tamaños, espaciados, bordes y radios del diseño.
- `css/base.css`: fuentes locales, reset, tipografía, controles y foco visible.
- `css/layout.css`: contenedor, distribución mobile-first y media queries a 48rem y 64rem.
- `css/componentes.css`: navegación, botones, tarjetas, formularios, estados y ayuda.

Las páginas cargan directamente los cuatro archivos.

## Paleta y tipografías

| Token | Valor | Uso |
| --- | --- | --- |
| `--color-azul` | `#202945` | Texto, cabeceras y botones primarios |
| `--color-coral` | `#ff815c` | Presentación, botones y bordes |
| `--color-celeste` | `#cae4ef` | Filtros y paneles de apoyo |
| `--color-fondo` | `#ffffff` | Fondo y texto sobre azul |
| `--color-gris` | `#586079` | Placeholders y botones deshabilitados |
| `--color-pendiente` | `#ffdaa6` | Estado Pendiente |
| `--color-aceptada` | `#d9efdf` | Estado Aceptada |
| `--color-rechazada` | `#f8dce0` | Estado Rechazada |

Work Sans 400/600 para texto y controles; Baskervville 600 para títulos principales. Archivos locales en `fonts/` con sus licencias OFL. Texto base de `1.125rem`, interlineado 1.45 y controles de al menos 44px. El texto sobre coral usa azul para mantener el contraste.

## Componentes reutilizables para la Entrega 3

`Encabezado`, `Navegacion`, `Pie`, `AyudaAmac`, `CabeceraEditorial`, `Boton`, `TarjetaVacante`, `TarjetaSolicitud`, `TarjetaEmpresa`, `EtiquetaEstatus`, `CampoFormulario`, `FormularioAcceso` y `FormularioRegistro`.

## Adaptaciones respecto de Figma

- Se mantienen los colores, las fuentes, las imágenes originales, la presentación coral y los paneles azules y celestes.
- Se reemplazan las medidas rígidas del lienzo por contenedores fluidos, alturas naturales y columnas que se apilan en celular.
- El listado pasa de tres a seis vacantes y las solicitudes de dos pendientes a tres estados diferentes para cumplir la rúbrica. Los registros adicionales son ficticios.
- Encabezado y pie comunes en todas las páginas, incluido el acceso. La navegación permite llegar también al panel de empresa.
- Se añaden etiquetas visibles, encabezados semánticos, enlace para saltar al contenido y ayuda desplegable.
- El logo y la ilustración decorativa proceden del Figma; se guardan en `img/` y no dependen de enlaces temporales.

## Alcance estático y datos pendientes

No hay autenticación, envío de formularios, almacenamiento, filtrado, publicación de vacantes ni cancelación real de solicitudes. Los campos se pueden editar. Acceso y registro utilizan validación nativa del navegador y después navegan a la siguiente pantalla. Sus controles tienen ID y etiquetas, pero omiten deliberadamente `name` para que el navegador no incluya información personal ni contraseñas en la URL. El registro no crea cuentas: lo indica expresamente en la pantalla siguiente. Los botones de gestión de vacantes y cancelación son visuales, como permite la entrega. No introduzcas información personal real. Los términos y el aviso de privacidad definitivos deben ser entregados por AMAC: no se inventaron documentos legales.

Los teléfonos son **números de ejemplo** (AMAC: 81 0000 0000; empresa de la vacante `vacante.html`: 81 0000 0001). El botón "Llamar a AMAC" está en la ayuda de todas las páginas (RF-052) y el botón "Llamar" solo aparece en `vacante.html` (RF-051); ambos son enlaces `tel:`. Cuando AMAC y la empresa confirmen sus números reales, hay que cambiar el texto y el `href` de esos enlaces. La ayuda desplegable ya está disponible.

## Equipo

Completar con los integrantes reales y sus aportaciones. No se generaron commits atribuidos a otras personas.

| Integrante | Aportación |
| --- | --- |
| Rossbel Rodríguez Rubio | Maquetación de inicio de sesión (`login.html`) y formulario accesible de registro de candidato (`registro-candidato.html`) con validaciones y agrupación semántica. |
| Gael Sánchez Ramos | Configuración base del repositorio, hojas de estilo compartidas (`css/`), tipografías y recursos (`fonts/`, `img/`), página principal de listado con buscador/filtros (`index.html`), vistas de detalle de vacantes (`vacante.html` y `vacante-*.html`) y documentación (`README.md`). |
| Ivanna Treviño Pérez | Maquetación del panel de solicitudes del candidato con estados y cancelación (`mis-solicitudes.html`) y panel de vacantes y solicitudes recibidas de la empresa (`empresa-vacantes.html`). |


## Comprobaciones y evidencias

Las comprobaciones locales se documentan en `VERIFICACION.md`. Estado actual:

- [x] Revisar las páginas a 320, 768, 1024 y 1440px sin desplazamiento horizontal.
- [x] Recorrer todos los controles con Tab y comprobar el foco.
- [x] Verificar el zoom al 200 % sin desplazamiento horizontal (equivale a 720 y 384px de ancho).
- [ ] Validar cada página con W3C: cero errores.
- [ ] Ejecutar Lighthouse Accessibility en `index.html`: al menos 90 puntos; guardar la captura en `img/`.
- [x] Añadir capturas de `index.html` en celular y escritorio (abajo).
- [ ] Revisar a mano con Shift+Tab y Enter, y el zoom al 200 % en el navegador real.

### Capturas de `index.html`

Escritorio (1440px):

![Listado de vacantes en escritorio](img/captura-index-escritorio.png)

Celular (375px):

![Listado de vacantes en celular](img/captura-index-celular.png)

## Publicación

Pendientes la URL del repositorio y la URL pública. Para Vercel: importar el repositorio, usar preset Other y seleccionar `Proyecto_Final` como Root Directory si el repositorio incluye las demás carpetas de ejercicios. Si se publica solo esta carpeta como repositorio independiente, la raíz ya es la correcta. No requiere comando de compilación. La configuración de GitHub y Vercel no forma parte de los archivos HTML/CSS ni se realizó automáticamente.

### Estado de sesión en la maqueta

Las páginas públicas muestran “Iniciar sesión”. En login se oculta ese enlace; en registro se muestra “Volver a iniciar sesión”. Los paneles de solicitudes y empresa muestran “Cerrar sesión”, que vuelve a `index.html`. Estos estados son estáticos y no representan autenticación real.
