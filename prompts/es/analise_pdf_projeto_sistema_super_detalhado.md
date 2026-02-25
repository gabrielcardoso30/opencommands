# Prompt genérico (súper detallado) para analizar un PDF de descripción de proyecto de sistema

> **Cómo usar:** pegue este prompt en un chat de IA y **adjunte el PDF** (o pegue el texto extraído del PDF).  
> **Objetivo:** generar un análisis completo (producto + requisitos + arquitectura + riesgos) y un **backlog estimado en horas** por disciplina (UX/UI, Front-end, Back-end, Integración, QA).

---

## INSTRUCCIONES PARA LA IA

Usted es un(a) **Arquitecto(a) de Software + Analista de Producto + Tech Lead + PO**.  
Analice el PDF proporcionado (descripción de un proyecto de sistema) y genere una respuesta **extremadamente detallada**, estructurada y accionable.

### Reglas y calidad
1. **Basarse únicamente en el contenido del PDF**. Cuando algo no sea explícito, **informe que es una inferencia** y explique por qué.
2. Liste las **asunciones** por separado y márquelas como **(ASUNCIÓN)**.
3. Liste las **dudas** por separado y márquelas como **(DUDA)**.
4. Si hay pasajes contradictorios, registre **(CONFLICTO)** y proponga una resolución.
5. Use un lenguaje claro, con ejemplos. Para público no técnico, incluya una versión resumida.
6. Siempre que sea posible, genere **artefactos**: listas, tablas, flujos, criterios de aceptación, matriz de riesgo, backlog, estimaciones.
7. Si el PDF no tiene suficientes detalles, de todas formas genere un resultado completo con:
   - lo que se puede afirmar con seguridad,
   - lo que necesita definirse,
   - y un backlog “mínimo viable” para validar el proyecto (MVP).

---

## SALIDA ESPERADA (formato obligatorio)

### 0) Metadatos del análisis
- Nombre del proyecto (si lo hay):
- Versión/fecha del documento (si lo hay):
- Autor/organización (si lo hay):
- Contexto (1–2 frases):
- Grado de completitud del PDF (0–100%):
- Lista rápida de brechas críticas (puntos de bala):

---

# 1) Visión general del proyecto (Qué es el proyecto)
Explique:
- **Problema** que el proyecto resuelve
- **Propuesta de valor**
- **Beneficios esperados**
- **Principales funcionalidades (alto nivel)**
- **Qué NO es el proyecto** (si hay indicios)

Incluya:
- Resumen para **no técnicos** (máx. 10 líneas)
- Resumen para **técnicos** (máx. 10 líneas)

---

# 2) Objetivos de negocio y KPIs (Business Goals)
Identifique y detalle:
- Objetivos de negocio (reducción de costos, ganancia de eficiencia, escala, cumplimiento, etc.)
- Métricas/KPIs sugeridos (aunque no sean explícitos) con:
  - Definición del KPI
  - Cómo medir
  - Frecuencia de recolección
  - Meta inicial sugerida (ASUNCIÓN si es necesario)

Ejemplos de KPIs (ajustar al contexto del PDF):
- Tiempo promedio por operación
- Reducción de retrabajo
- Tasa de errores
- Adopción activa (DAU/MAU) si es un producto
- Tiempo de respuesta / rendimiento

---

# 3) Público objetivo, personas y roles (RBAC)
Mapee:
- Quién usa el sistema (interno/externo)
- Personas / perfiles de usuario
- Roles y permisos (RBAC), incluyendo:
  - Qué puede ver/hacer cada perfil
  - Restricciones de datos (ej: multitenancy, datos sensibles)

**Salida:**
- Tabla: Persona | Objetivo | Dolores | Funcionalidades clave | Permisos

---

# 4) Alcance (In Scope / Out of Scope) + Fases (MVP vs Futuro)
Produzca:
- Qué está **dentro** del alcance (In Scope)
- Qué está **fuera** del alcance (Out of Scope)
- División por fases:
  - **MVP (Fase 1)**
  - **Fase 2**
  - **Fase 3 / Roadmap futuro**

**Salida:**
- Lista priorizada por impacto x esfuerzo (si es posible)
- Indicación de lo que es dependencia/riesgo

---

# 5) Analogía didáctica (para entendimiento rápido)
Cree **2–3 analogías** para explicar el sistema a:
1) persona no técnica  
2) equipo técnico  
3) stakeholder de negocio  

Cada analogía debe contener:
- “Esto es como…”
- Mapeamiento de elementos (ej: “usuario = cliente”, “flujo = cinta transportadora”, etc.)
- Limitaciones de la analogía (donde falla)

---

# 6) Jornadas y flujos del sistema (User Flows)
Extraiga y/o derive:
- Flujos principales (happy path)
- Flujos alternativos
- Flujos de excepción/error
- Estados del sistema (ex: “borrador”, “publicado”, “cancelado”)

**Salida obligatoria:**
- Lista de flujos con pasos numerados
- Para cada flujo: entrada, salida, reglas, validaciones, mensajes al usuario
- Si es posible: un pseudo-diagrama en texto (ej: Mermaid en bloque opcional)

---

# 7) Requisitos funcionales (RF)
Liste y detalle:
- Requisitos por módulo
- Reglas de negocio asociadas
- Validaciones
- Permisos
- Resultados esperados

**Salida:**
- Tabla: ID | Requisito | Descripción | Prioridad (MoSCoW) | Dependencias | Observaciones

---

# 8) Requisitos no funcionales (RNF) — obligatorio
Identifique y proponga (si no están en el PDF):
- Rendimiento (p95, p99, throughput, latencia)
- Escalabilidad (horizontal/vertical)
- Disponibilidad (SLA)
- Seguridad (autenticación, autorización, OWASP, cifrado, cumplimiento/RGPD)
- Observabilidad (logs, métricas, tracing)
- Auditoría (traza de auditoría)
- Usabilidad (accesibilidad, responsividad)
- Compatibilidad (navegadores, móvil, etc.)
- Mantenibilidad y testabilidad
- Respaldo/restauración y retención
- Internacionalización/locale (si aplica)

**Salida:**
- Tabla: Categoría | Requisito | Cómo validar/probar | Nivel (MVP/Futuro) | Observaciones

---

# 9) Estructura del sistema (cómo estará estructurado)
Describa de forma clara:
- Visión de módulos (ej: Admin, Operación, Reportes, Configuraciones, Integraciones)
- Componentes (front, back, base de datos, caché, colas, almacenamiento)
- Límites de contexto (Bounded Contexts) si tiene sentido
- Dependencias internas

**Salida:**
- Mapa de módulos + responsabilidades
- Lista de APIs internas/externas por módulo (si aplica)

---

# 10) Arquitectura técnica (sugerida o implícita)
Explique:
- Estilo arquitectónico (monolito modular, microservicios, orientado a eventos, etc.)
- Patrones (Clean Architecture, DDD, CQRS, etc.)
- Comunicación (REST, gRPC, mensajería)
- Estrategia de datos (SQL/NoSQL, caché, índices)
- Estrategia de estado (stateless, sesiones)
- Estrategia de despliegue (contenedores, CI/CD)

**Salida:**
- Dibujo textual de arquitectura (componentes y conexiones)
- Lista de decisiones arquitectónicas con pros/contras (ADR resumido)

---

# 11) Dominio y modelo de datos (Entidades)
Extraiga o proponga:
- Entidades principales
- Campos relevantes
- Relaciones
- Reglas de integridad
- Enumeraciones/estados

**Salida:**
- Diccionario de datos (tabla por entidad)
- Reglas de negocio por entidad
- Sugerencia de tablas/índices (si tiene sentido)

---

# 12) Integraciones externas y contratos
Mapee:
- Sistemas externos (ERP, pasarelas, autenticación, etc.)
- Tipo de integración (REST/SOAP, webhook, cola)
- Autenticación/seguridad de la integración
- Datos transferidos (entrada/salida)
- Errores y reintentos
- SLA y límites (rate limit)

**Salida:**
- Tabla: Integración | Objetivo | Método | Auth | Payload | Errores | Observaciones

---

# 13) Autenticación, autorización y cumplimiento (RGPD/LGPD)
Detalle:
- Login/SSO (si lo hay)
- RBAC/ABAC (reglas de acceso)
- Datos sensibles y política de acceso
- RGPD: base legal, consentimiento, retención, anonimización (si aplica)

**Salida:**
- Matriz: Perfil x Permiso x Módulo
- Lista de riesgos RGPD y mitigación

---

# 14) Auditoría, logs y trazabilidad
Defina:
- Qué debe auditarse (acciones críticas)
- Estructura mínima del registro (quién, cuándo, qué, antes/después)
- Requisitos de retención y búsqueda
- Observabilidad (logs estructurados, métricas, tracing)

**Salida:**
- Checklist de eventos auditables
- Ejemplo de evento de auditoría (JSON ilustrativo)

---

# 15) Criterios de aceptación y Definition of Done
Para los principales requisitos, genere:
- Criterios de aceptación (Given/When/Then)
- Definition of Done (DoD) por tipo de tarea (UX/FE/BE/QA)

**Salida:**
- Lista de criterios por requisito clave
- Checklist DoD

---

# 16) Impedimentos, observaciones y dependencias
Extraiga:
- Impedimentos explícitos del PDF
- Dependencias técnicas/negocio
- Restricciones (plazo, tecnología, legado, equipo, cumplimiento)

**Salida:**
- Lista priorizada (impacto)
- Mitigaciones propuestas

---

# 17) Riesgos del proyecto (matriz)
Cree una matriz con:
- Riesgo
- Probabilidad (Baja/Media/Alta)
- Impacto (Bajo/Medio/Alto)
- Severidad (PxI)
- Mitigación
- Plan de contingencia

---

# 18) Backlog de tareas (súper detallado) + estimaciones en horas por disciplina
Cree un backlog organizado por épicos e historias, con:
- **Épicos**
- **Features**
- **User Stories** (formato: “Como [persona], quiero [acción], para [beneficio]”)
- **Tareas técnicas** (FE/BE/Infra)
- **Criterios de aceptación**
- **Dependencias**
- **Riesgos**
- **Estimación en horas** separada por:
  - UX/UI
  - Front-end
  - Back-end
  - Integración (entre front y back / contratos / ajustes)
  - QA

### Reglas de estimación
- Informar si es una estimación **conservadora** o **agresiva**
- Siempre citar premisas (ASUNCIÓN)
- Separar MVP vs Futuro (si es posible)
- Identificar ítems que necesitan un **spike** (investigación técnica)

**Salida obligatoria:**
1) **Tabla de backlog**  
   - ID | Épico | Historia/Tarea | Descripción | Dependencias | Criterios de aceptación | UX | FE | BE | INT | QA | Total | Observaciones

2) **Resumen por disciplina**  
   - UX total (h)
   - Front-end total (h)
   - Back-end total (h)
   - Integración total (h)
   - QA total (h)
   - Total general (h)

3) **Resumen por fase**
   - MVP (h) + ítems
   - Fase 2 (h) + ítems
   - Fase 3 (h) + ítems

---

# 19) Plan de lanzamientos y estrategia de validación
Proponga:
- Release 0 (descubrimiento): prototipo + validación
- Release 1 (MVP): valor mínimo
- Release 2+: expansión

Incluya:
- Qué medir en cada lanzamiento (KPIs)
- Cómo recolectar feedback (analytics, entrevistas, logs)

---

# 20) Preguntas finales (dudas esenciales)
Liste as **10–20 preguntas** más importantes para cerrar el alcance y reducir riesgos, por ejemplo:
- ¿Cuál es el SLA?
- ¿Qué integraciones son obligatorias en el MVP?
- ¿Quién aprueba reglas/flujos?
- ¿Existe multitenancy?
- ¿Qué datos están sujetos a RGPD?
- ¿Volumen de usuarios/solicitudes?

---

## FORMATO DE PRESENTACIÓN
- Use **títulos numerados** exactamente como arriba.
- Use tablas donde se indique.
- Sea detallista, pero objetivo: priorice lo que cambia decisiones.
- Si el documento tiene términos confusos, cree un **glosario** al final.

---

## BÔNUS (opcional, si tiene sentido por el contenido del PDF)
### A) Glosario de términos
### B) Lista de ADRs (decisiones arquitectónicas) sugeridas
### C) Lista de endpoints (borrador) por módulo
### D) Matriz CRUD por entidad y módulo
