# Guía 1 - Motricidad

Proyecto web interactiva construida en Astro para el desarrollo de la motricidad fina y la coordinación visomotora en niños de 3 a 4 años.

## 📌 Objetivo del proyecto

- Crear una plataforma con actividades pedagógicas guiadas.
- Trabajar conceptos de espacio gráfico, orden de trazos y uso de herramientas básicas.
- Usar contenido dinámico con JSON local para mantener el sitio modular.

## 🚧 Estado actual del proyecto

- Infraestructura lista en Astro con Node.js v22.12.0 o superior (ver package.json).
- Componentes principales implementados: `Pizarra.astro`, `Pizarrapregra.astro`, `Pizarrapuntoa.astro` y `Barraplegado.astro`.
- Layouts configurados: `PaginaMaestra1.astro` y `PaginaMaestrapuntoa.astro`.
- Sección A (Punto de Partida): página introductoria `puntoa-a.astro` completada.
- Sección B (Motricidad Fina): 12 actividades parcialmente implementadas.
  - `modelado1-1` a `modelado1-4`
  - `plegado3-1` a `plegado3-4`
  - `recortado2-1` a `recortado2-4`
  - Coloreado: 4 actividades — estructura implementada; contenido pendiente de completar.
- Sección C (Pregraficos): `trazos1.astro` implementada; números y vocales en preparación.
- Datos configurados en `tablavideos.json` y `tablatutorial.json`.

## 🧩 Arquitectura

- `src/pages/`: páginas y rutas del sitio.
- `src/components/`: componentes reutilizables.
- `public/`: activos estáticos como imágenes, fuentes y videos.
- JSON locales para mantener ejercicios y tutoriales separados de la UI.

## ⚙️ Comandos útiles

| Comando                   | Acción                                              |
| :------------------------ | :-------------------------------------------------- |
| `npm install`             | Instala dependencias                                 |
| `npm run dev`             | Inicia servidor local                                |
| `npm run build`           | Genera el sitio de producción                        |
| `npm run preview`         | Previsualiza el build local                          |

## 📍 Notas adicionales

- El estado detallado del proyecto también está documentado en `agents.md`.
- Ejemplo de estructura para `tablavideos.json`:
  - Cada objeto de ejercicio sigue este formato:

```
{
  "id": "modelado1-1",
  "ruta": "/videos/modelado1-1.webm",
  "titulo": "Modelado 1-1",
  "instrucciones": "<p>Instrucciones HTML aquí</p>"
}
```

- Recomendaciones de archivos públicos:
  - Usar siempre nombres en minúsculas en `public/`.
  - Referenciar activos con rutas absolutas (ej. `/videos/nombre.webm`).

- Para publicar cambios:
  1. `git add .`
  2. `git commit -m "Actualiza documentación y estado del proyecto"`
  3. `git push origin main`

## 🤝 Contribución

- Fork y PR para cambios importantes.
- Abrir issues para bugs o mejoras pequeñas.

## 📝 Licencia

- Añadir archivo LICENSE en el repo con la licencia del proyecto (p. ej., MIT).
