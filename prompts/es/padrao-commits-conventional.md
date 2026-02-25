Genere UN mensaje de commit claro, específico e informativo basado en el diff proporcionado. Siga *Conventional Commits* y escriba en **español**.

OBJETIVO
- Reflejar fielmente TODO lo que se cambió (cuando haya múltiples cambios).
- Título conciso (<= 100 caracteres). Cuerpo solo si agrega valor, con saltos a 100 caracteres.
- Nada de bloques de código, emojis o comillas externas.

FORMATO
<tipo>(<escopo>): <descripción>
[líneas de cuerpo opcionales, con saltos a 100 caracteres]
[pies de página opcionales]

TIPOS (elija con precisión; si hay más de un tipo relevante, enumere hasta 2 separados por una coma dinámica, por orden de importancia)
- feat: nueva funcionalidad (visible o comportamiento nuevo)
- fix: corrección de error (bug)
- refactor: cambio de código que no corrige un error ni añade una funcionalidad
- perf: mejora de rendimiento
- docs: documentación/comentarios/XMLDoc
- style: formato, lint, nombres (sin impacto funcional)
- test: adición/ajuste de pruebas
- chore: mantenimiento, dependencias, build, CI/CD, configuraciones
- build: cambios en el empaquetado/build
- ci: pipeline/automatizaciones

ALCANCE (SCOPE)
- Sustantivo corto que identifique el área primaria impactada.
- Preferir el directorio o módulo dominante del diff (ej.: core, api, httpclient, middleware, config, infra, auth, swagger, db, ci, build).
- Si hay múltiples áreas y ninguna es dominante, use un término agregador como: global, app, multi.

DESCRIPCIÓN (TÍTULO)
- Voz activa y tiempo presente: "añade", "corrige", "refactoriza"...
- Comience con letra minúscula, sin punto final.
- Envuelva nombres de archivos, símbolos y números entre comillas invertidas (`).
- Debe decir qué se hizo + el enfoque principal. <= 100 caracteres.

CUERPO (OPCIONAL, PERO RECOMENDADO SI HAY MÚLTIPLES CAMBIOS)
- Liste ítems objetivos, agrupando por área/tema. Use viñetas con "- ".
- Explique qué cambió, por qué e impacto (compatibilidad/comportamiento).
- Salte de línea cada 100 caracteres.
- Si hay cambios de distinta naturaleza, refléjelos TODOS en viñetas separadas.
- Use identificadores concretos: nombres de clases, métodos, archivos y claves de configuración. Evite frases genéricas.

REGLAS ESPECIALES PARA COMMITS MIXTOS
1) Si el diff contiene cambios de distinta naturaleza:
   - Elija hasta DOS tipos (ej.: "feat,refactor" o "refactor,fix").
   - Use un alcance agregador (ej.: "core" o "global") O el alcance dominante.
   - En el cuerpo, cree viñetas por TEMA.
2) Si hay un cambio potencial de ruptura (breaking change), incluya en el pie:
   - BREAKING CHANGE: <descripción corta>
3) Si el diff menciona issues/PRs, incluya en el pie:
   - Refs: #123, #456
   - Closes: #789

ALGORITMO DE DECISIÓN (RESUMEN)
- Detecte temas por el contenido del diff.
- Defina el TÍTULO por el impacto más relevante para el usuario/sistema.
- En el CUERPO, cubra todos los demás cambios en viñetas cortas y técnicas.

SALIDA
- Produzca el mensaje final de commit siguiendo las reglas anteriores.
- Un único mensaje, sin bloques de código.
- Título <= 100 caracteres. Cuerpo con saltos a 100 caracteres.
- En español.

DIFERENCIA (git diff --staged)
{diff}

EJEMPLOS ILUSTRATIVOS (NO COPIAR AL PIE DE LA LETRA; SOLO GUÍA)
1)
refactor,fix(global): mejora la robustez de json y el tratamiento de errores
- añade conversores para `decimal` y `decimal?` con soporte para strings y comas
- configura `AddJsonOptions` y registra conversores globalmente
- ajusta el orden de los middlewares en `Program.cs` para una captura consistente
- mejora `ErrorHandlerMiddleware` (mapeo de estados, traceId, logs)
- refuerza `LojaConceitoHttpClient` (content-type, payload bruto, ruta de error)

2)
feat(core): soporte para conversores decimales flexibles y json global
- registra conversores para `decimal`/`decimal?` y `AllowReadingFromString`
- documenta y aplica saltos de 72 columnas en los mensajes de error
- reorganiza middlewares y ubica `UseErrorHandlerMiddleware` pronto en el pipeline
- mejora el diagnóstico y las respuestas del httpclient `XPTO`
