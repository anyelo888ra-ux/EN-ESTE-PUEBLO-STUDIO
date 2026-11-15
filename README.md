# EN ESTE PUEBLO STUDIO v1.0

Demo local independiente en HTML + JavaScript + Three.js.

## Abrir
1. Extrae el ZIP.
2. Abre `index.html` en Chrome, Edge u Opera.
3. Necesitas conexión a Internet para cargar Three.js desde jsDelivr y consultar los endpoints públicos de Roblox.

Si el navegador bloquea módulos al abrir `file://`, inicia un servidor local en esta carpeta:
- Python: `python -m http.server 8000`
- Abre `http://localhost:8000`

## Incluye
- Tema y nombre del pueblo.
- Guion `Personaje> diálogo`.
- Detección de NPC y protagonista.
- Pueblo 3D procedural con personajes de bloques R6/R15 aproximados.
- Búsqueda de usuario/ID Roblox y miniatura pública del avatar.
- Importación de modelos GLB/GLTF propios.
- Voces de navegador por personaje.
- Campo de Voice ID y configuración Fish Audio (integración real pendiente).
- Guardar/cargar proyecto JSON.
- Grabación de canvas 3D a WebM cuando el navegador lo admite.

## Limitaciones importantes de esta v1.0
- El avatar Roblox se consulta para obtener su miniatura; no se descarga la malla oficial completa. El protagonista se representa con un rig de bloques aproximado.
- Los NPC son generados por el guion, pero el modelo de alcalde personalizado debe importarse como GLB/GLTF.
- Fish Audio está preparado como configuración, pero no se llama directamente desde el navegador. Para producción se necesita backend y guardar la API key como secreto.
- La grabación WebM captura el canvas 3D, no incorpora todavía las voces del navegador ni los subtítulos HTML.
- No es un editor oficial de Roblox ni usa assets de Roblox protegidos.

## Siguiente etapa
Implementar un compositor de vídeo que dibuje subtítulos dentro del canvas, mezcle audio generado y permita MP4 mediante un proceso de conversión local o backend.


## v1.1 — Exportación y conversión
- La grabación integra el título y los subtítulos dentro del vídeo (no dependen de la interfaz del editor).
- Tamaños de salida exactos: vertical 720×1280 / 1080×1920, horizontal 1280×720 / 1920×1080 y cuadrado 720×720 / 1080×1080.
- El vídeo se graba como WebM desde el navegador.
- La página `convertir-a-mp4-tu-video.html` convierte WebM a MP4 H.264 con FFmpeg WebAssembly en el propio navegador.
- La conversión carga un motor de varias decenas de MB y puede tardar bastante en equipos con poca RAM o CPU.
- La voz generada por SpeechSynthesis todavía no se incorpora al audio del vídeo exportado.
- La cámara ahora puede seguir al personaje del diálogo y los NPC añadidos manualmente se conservan al regenerar el reparto.

## Conversor
Abre `convertir-a-mp4-tu-video.html` desde GitHub Pages. Selecciona un WebM, pulsa Convertir y luego Descargar MP4. La primera vez requiere conexión para descargar FFmpeg desde jsDelivr.
