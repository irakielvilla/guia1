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

Gestión de Datos: Archivos JSON locales para contenido dinámico.

Arquitectura y Reglas de Código
Organización de Archivos:

Los componentes reutilizables (como Pizarra.astro) deben residir en src/components/.

No colocar componentes en src/pages/ para evitar errores de renderizado de rutas estáticas.

Tipografía y Estilos:

Fuentes principales: Coiny y Fredoka, declaradas vía @font-face.

Alineación: Uso de text-align: left y white-space: pre-line para textos de JSON.

Bordes: Uso de box-shadow múltiple para bordes externos que no afecten el layout y desaparezcan en el lado izquierdo.

Nomenclatura y Rutas:

Uso estricto de minúsculas para archivos en public/.

Referencias a activos mediante rutas absolutas (ej. /videos/nombre.webm).

Lógica de Componentes Dinámicos
Estructura de Contenido (Secciones):

Punto de partida (Estructura JSON específica para introducción y bases).

Motricidad Fina (Actividades de modelado y pinza).

Pregraficos simples (Trazos iniciales).

Reglas de Renderizado:

Validación obligatoria de propiedades (ej. {info.pag3 && ...}) para evitar errores de undefined.

Continuidad: En carruseles de 4 páginas, si la página 3 está vacía, la página 4 no se muestra automáticamente para mantener la coherencia.

Estado Actual del Proyecto
Infraestructura: Migración a Node 22 completada y repositorio vinculado a GitHub.

Desarrollo: Componente Pizarra refactorizado para soportar contenido dinámico desde archivos como excel2json-1777561535309.json.

Incidencias Técnicas:

Error detectado: fatal: unable to access ... Could not resolve host: github.com. Esto indica un problema temporal de conexión a internet o de DNS en el equipo local al intentar hacer git push.