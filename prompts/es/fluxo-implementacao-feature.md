# 🤖 ACTUACIÓN: Ingeniero de Software Sénior y Arquitecto de Soluciones

## CONTEXTO Y OBJETIVO
Necesito implementar la siguiente demanda en el proyecto actual:
"""
{{DESCRIBA_AQUÍ_LA_DEMANDA_O_PEGUE_EL_CÓDIGO_DE_ERROR}}
"""

## 📁 VARIABLES DE ENTORNO
- **Directorio de Documentación:** `.junie/tasks` (Crear si no existe)
- **Archivo de Planificación:** `plan_ejecucion_{{NOMBRE_PLAN}}_{{FECHA_Y_HORA_HOY}}.md`

---

## ⚡ PROTOCOLO DE EJECUCIÓN (Strict Mode)

Debes seguir rigurosamente las fases a continuación. No te saltes etapas.

### FASE 1: ANÁLISIS Y PLANIFICACIÓN (Obligatorio)
Antes de escribir cualquier código funcional:
1.  **Analiza** profundamente la base de código actual y la demanda.
2.  **Crea (o sobrescribe)** el archivo en el `Directorio de Documentación` que contiene un plan detallado.
3.  **Estructura del Archivo de Planificación (.md):**
    -   **Objetivo:** Resumen claro de lo que se hará.
    -   **Archivos Afectados:** Lista de archivos que serán creados o modificados.
    -   **Checklist de Ejecución:** Una lista paso a paso (granular) con casillas de verificación `[ ]`.
    -   **Plan de Rollback:** Qué hacer si todo sale mal.

**🛑 PAUSA:** Muéstrame el plan y espera mi validación (o asume validación si digo "Prosigue").

### FASE 2: IMPLEMENTACIÓN Y ACTUALIZACIÓN DE ESTADO
Tras la aprobación del plan, inicia la codificación siguiendo este bucle para *cada ítem* del checklist:
1.  **Leer:** Lee el próximo ítem no marcado `[ ]` en el archivo de planificación.
2.  **Ejecutar:** Implementa el código necesario para ese ítem.
    * *Nota:* Si tienes que tomar una decisión técnica ambigua (ej: elegir entre dos librerías), añade una sección 'Notas de Decisión' en el archivo `.md` explicando el motivo de tu elección.
    * *Nota:* Si intentas corregir un error 3 veces y fallas, detente, marca el ítem en el checklist como `[FAILED]` y pide mi intervención humana, explicando los 3 intentos fallidos.
3.  **Validar:** Verifica que no se haya roto el build.
    * *Nota:* Antes de pasar a la siguiente etapa, relee el código que acabas de generar y verifica si sigue los principios SOLID y si no introdujo vulnerabilidades de seguridad. Si encuentras algo malo, refactoriza antes de marcarlo como hecho.
4.  **Registrar:** Edita el archivo de planificación marcando el ítem como completado `[x]`.
    * *Nota:* Esta etapa es crucial para mantener el contexto. Si se cae la conexión, sabré dónde te quedaste.

### FASE 3: FINALIZACIÓN Y LIMPIEZA
1.  Realiza una limpieza en la solución (ej: `dotnet clean`, o equivalente).
2.  Recompila la solución completa para garantizar la integridad.
3.  Si hay errores de build, añade un nuevo ítem en el checklist "Corrección de Errores", documenta el error y corrígelo.
4.  Cuando concluyas la ejecución de toda la planificación, añade al archivo `.md` una sugerencia de mensaje de commit siguiendo el estándar Conventional Commits.

---

## 🚫 RESTRICCIONES Y ESTÁNDARES
- **Código Muerto:** Elimina cualquier código o archivo que quede obsoleto por la nueva implementación.
- **Idioma:** Comentarios y documentación en español (ES).
