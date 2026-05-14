Contexto del Proyecto: Guía 1 - Motricidad
Objetivo
Plataforma web interactiva diseñada para el desarrollo de la motricidad fina y coordinación visomotora en niños.

Enfoque principal en actividades de modelado y trazos progresivos.

Objetivos Pedagógicos
Población objetivo: Niños de 3 a 4 años.

Alcance: Esta es la primera de un total de tres guías planificadas para el aprendizaje progresivo.

Propósito: Fortalecer las bases de la motricidad fina y la organización del espacio gráfico (arriba-abajo, izquierda-derecha).

Metodología: Fomentar hábitos de trabajo ordenado y autonomía mediante procedimientos paso a paso.

Stack Tecnológico
Framework: Astro (Static Output).

Entorno: Node.js v22.12.0 o superior (Configurado en package.json).

Despliegue: Vercel (Sensible a mayúsculas/minúsculas en nombres de archivos).

Librerías Clave: Swiper.js (Modo CSS) para carruseles de información.

Gestión de Datos: Archivos JSON locales (`tablavideos.json`, `tablatutorial.json`) para contenido dinámico.

Arquitectura y Reglas de Código
Organización de Archivos:

- Los componentes reutilizables (como Pizarra.astro) deben residir en src/components/.
- No colocar componentes en src/pages/ para evitar errores de renderizado de rutas estáticas.

Componente Pizarra.astro (Núcleo de Actividades):

- Funciona como un contenedor inteligente que recibe el objeto `miejercicio` como prop.
- Encapsula su propio CSS y lógica de control de video (Play/Pausa, Replay).
- Utiliza `set:html` para renderizar las instrucciones, permitiendo el uso de etiquetas HTML (ej. `<br>`) desde el JSON.
- Incluye una validación de seguridad: si no recibe datos, redirige al inicio para evitar errores de compilación.

Componente Barraplegado.astro (Navegación):
- Funciona como una barra de navegación interactiva integrada mediante un SVG complejo.
- Utiliza etiquetas de anclaje (`<a>`) dentro del SVG para vincular las secciones principales (A, B y C).
- Contiene botones visuales específicos para las sub-actividades: Modelado, Recortado, Plegado y Coloreado, facilitando el acceso directo a cada categoría.

Tipografía y Estilos:

- Fuentes principales: Coiny y Fredoka, declaradas vía @font-face en el layout global.
- Alineación: Uso de text-align: left y white-space: pre-line para textos de JSON cuando sea necesario.
- Bordes: Uso de box-shadow múltiple para efectos visuales premium en la interfaz.

Nomenclatura y Rutas:

- Uso estricto de minúsculas para archivos en public/.
- Referencias a activos mediante rutas absolutas (ej. /videos/nombre.webm).

Lógica de Componentes Dinámicos
Estructura de Contenido (Secciones):

- Punto de partida: Introducción y bases del aprendizaje.
- Motricidad Fina: Actividades de modelado y pinza (Sección B).
- Pregraficos simples: Trazos iniciales (Sección C).

Gestión de Datos:

- `tablavideos.json`: Contiene objetos de ejercicio con campos: id, ruta, titulo, instrucciones. Ejemplo:

```
{
  "id": "modelado1-1",
  "ruta": "/videos/modelado1-1.webm",
  "titulo": "Modelado 1-1",
  "instrucciones": "<p>Instrucciones HTML</p>"
}
```

- Las páginas de ejercicios buscan su respectivo objeto mediante el ID (ej. `tablavideos.find(i => i.id === 'modelado1-1')`).

Reglas de Renderizado:

- Validaciones obligatorias de propiedades en carruseles para evitar errores de undefined.
- Continuidad lógica: En carruseles, si falta contenido en una página intermedia, las siguientes no se muestran para mantener la coherencia.

Estado Actual del Proyecto
Infraestructura: Migración a Node 22 completada y repositorio vinculado a GitHub.

Desarrollo:
- Componente `Pizarra.astro` totalmente modularizado y funcional.
- Componentes `Pizarrapregra.astro` y `Pizarrapuntoa.astro` implementados.
- Layouts `PaginaMaestra1.astro` y `PaginaMaestrapuntoa.astro` configurados.
- Componente `Barraplegado.astro` para navegación visual implementado.
- Limpieza de código completada: se eliminaron redundancias de CSS y JS en las páginas de ejercicios individuales.
- Lógica de video estabilizada con soporte para reinicio y control de estado.

Contenido Implementado:
- Sección A (Punto de Partida): Página introductoria `puntoa-a.astro` con tutorial completo implementada.
- Sección B (Motricidad Fina): 12 actividades completamente implementadas:
  - Modelado 1: 4 actividades (modelado1-1 a modelado1-4)
  - Plegado 3: 4 actividades (plegado3-1 a plegado3-4)
  - Recortado 2: 4 actividades (recortado2-1 a recortado2-4)
  - Coloreado: 4 actividades — estructura implementada; contenido pendiente de completar.
- Sección C (Pregraficos): 
  - Trazos: 1 actividad implementada (trazos1.astro)
  - Números y Vocales: Estructuras preparadas (pendientes de implementación)

Datos: 
- `tablavideos.json`: Contiene datos para actividades de modelado, plegado y recortado.
- `tablatutorial.json`: Contiene contenido tutorial para la introducción.

Incidencias Técnicas:
- Error intermitente detectado: `fatal: unable to access ...`. Generalmente asociado a problemas temporales de DNS o conexión a internet.
- Resuelto: Problema de duplicidad de estilos y scripts en el componente Pizarra que causaba comportamientos erráticos.

Chuleta para subir los cambios a Github
1. git status (opcional).
2. git add .
3. git commit -m "mensaje"
4. git push origin main