# Plan del Sistema de Agentes para Creación de la Obra

**Fecha:** 2026-01-06
**Objetivo:** Crear sistema de slash commands que genere "La Constitución Democrática" basándose en notas de estudio.

---

## IMPORTANTE: Re-lectura tras Compresión de Contexto

**Si el contexto de esta conversación se comprime o se pierde información:**

1. Vuelve a leer este archivo completo (`PLAN-SISTEMA-AGENTES.md`)
2. Lee las notas en `/constitucion-notas/` (especialmente la-constitucion-notas-6.md)
3. Revisa qué fase del proceso se está ejecutando
4. Continúa desde ahí con la información actualizada

**Este documento es la fuente de verdad del sistema. Siempre consultar si hay dudas.**

---

## Contexto

### Notas de Entrada (Input)

Ubicación: `/constitucion-notas/`

Archivos (en orden cronológico):
- `la-constitución-0.md` (primera sesión)
- `la-constitucion-notas-2.md`
- `la-constitucion-notas-3.md`
- `la-constitucion-notas-4.md`
- `la-constitucion-notas-5.md` (usuario la creó renombrando)
- `la-constitucion-notas-6.md` (última sesión, más actualizada)

**IMPORTANTE:** Las notas están en orden cronológico. Las ideas evolucionaron. **La nota 6 es la más actualizada y tiene prioridad cuando hay contradicciones.**

---

## Estructura de la Obra (Output Final)

La obra tiene 4 partes:

**1. LA CONSTITUCIÓN DEMOCRÁTICA (TEXTO CONSTITUCIONAL)**
- Texto constitucional literal en forma de artículos
- CON números, porcentajes, plazos específicos
- Formato: "Artículo X: [contenido normativo]"
- Incluye TODO lo necesario: principios + mecanismos + números
- Redacción jurídica clara y directa
- Aplicable universalmente (no específico de España)

**2. EXPLICACIÓN DEL TEXTO CONSTITUCIONAL**
- Por qué cada artículo está escrito así
- Fundamentos teóricos y filosóficos
- Qué problema resuelve cada artículo
- Base empírica e histórica
- Referencias a casos de éxito/fracaso
- Puede referenciar artículos de Parte 1

**3. EJEMPLO DE IMPLEMENTACIÓN (ESPAÑA)**
- Cómo se implementaría en contexto español específico
- Bootstrap democrático + Operación normal
- Adaptaciones culturales/históricas necesarias
- Estructura concreta de instituciones
- Diferencia clara entre bootstrap y régimen permanente
- Respeta siempre los artículos de Parte 1

**4. RAZONAMIENTO DE ELECCIONES DE IMPLEMENTACIÓN**
- Por qué España como ejemplo
- Por qué estas adaptaciones específicas
- Trade-offs en la implementación española
- Qué funcionaría diferente en otros contextos
- Limitaciones reconocidas

**Idioma:** Español de España (castellano peninsular)

---

## Arquitectura del Sistema

### Principio: Grafo de Conceptos

Similar al sistema de `.claude/study-goals/` de Little Cheerful:
- Un grafo JSON define relaciones entre conceptos
- Cada concepto tiene su propio markdown detallado
- Los agentes navegan el grafo para escribir coherentemente
- Permite referencias cruzadas precisas

---

## Estructura de Directorios (Output)

```
/obra-constitucion-democratica/

  /conceptos/
    grafo.json                          # Relaciones entre todos los conceptos
    /md/
      separacion-poderes.md
      clausulas-petreas.md
      autodestruccion-mutua.md
      override-popular.md
      semipresidencialismo.md
      estados-excepcion.md
      ... (todos los conceptos identificados)

  /partes/
    parte-1-constitucion.md             # LA CONSTITUCIÓN DEMOCRÁTICA
    parte-2-argumentacion.md            # PRINCIPIOS HUMANOS Y ARGUMENTACIÓN
    parte-3-implementacion.md           # EJEMPLO DE IMPLEMENTACIÓN
    parte-4-razonamiento.md             # RAZONAMIENTO DE ELECCIONES

  /planes/
    plan-maestro.md                     # Plan general de la obra
    plan-parte-1.md                     # Plan detallado Parte 1
    plan-parte-2.md                     # Plan detallado Parte 2
    plan-parte-3.md                     # Plan detallado Parte 3
    plan-parte-4.md                     # Plan detallado Parte 4
```

---

## Schema del grafo.json (SOLO EJEMPLO)

**IMPORTANTE:** Este es un ejemplo ilustrativo. El agente que cree el grafo decidirá la estructura óptima basándose en las notas. No está obligado a usar estos campos exactos.

**Ejemplo posible:**

```json
{
  "metadata": {
    "created": "2026-01-06",
    "total_concepts": 0,
    "last_updated": "2026-01-06"
  },
  "concepts": {
    "separacion-poderes": {
      "title": "Separación de Poderes",
      "level": "fundamental",
      "dependencies": [],
      "used_in_parts": [1, 2],
      "related": ["checks-and-balances", "autodestruccion-mutua"],
      "source_notes": ["notas-2", "notas-6"]
    }
  }
}
```

**El agente puede:**
- Añadir campos que considere útiles
- Cambiar nombres de campos
- Usar estructura diferente si es más apropiada
- Lo importante es que capture las relaciones entre conceptos y sea navegable

---

## Flujo de Trabajo (11 Fases)

### FASE 0: Preparación Manual
- Usuario crea `/obra-constitucion-democratica/` y subdirectorios
- O el primer comando lo hace automáticamente

---

### FASE 1: Plan Maestro

**Comando:** `/constitucion-plan-maestro`

**Input:**
- Todas las notas en `/constitucion-notas/` (0-6)
- Este documento (PLAN-SISTEMA-AGENTES.md)

**Tarea:**
1. Leer TODAS las notas en orden cronológico
2. Identificar estructura de la obra (4 partes)
3. Identificar temas principales y su distribución en las partes
4. Identificar posibles contradicciones entre notas (priorizar nota 6)
5. Crear outline general de cada parte

**Output:** `/obra-constitucion-democratica/planes/plan-maestro.md`

**Formato del plan maestro:**
```markdown
# Plan Maestro - La Constitución Democrática

## Análisis de Notas

### Evolución de Ideas
[Cómo evolucionaron conceptos clave del 0 al 6]

### Conceptos Principales Identificados
[Lista de ~30-50 conceptos principales]

### Posibles Contradicciones Resueltas
[Si nota 2 dice X pero nota 6 dice Y, usamos Y]

## Estructura de las 4 Partes

### Parte 1: La Constitución Democrática (Texto Constitucional)
- Outline de títulos del articulado
- Estimación de artículos por título
- Conceptos que aportan información para los artículos
- Ej: Título I (Fundamentos): Arts. 1-10, Título II (Poderes): Arts. 11-35, etc.

### Parte 2: Explicación del Texto Constitucional
[Outline de capítulos que explican los artículos de Parte 1]

### Parte 3: Ejemplo de Implementación (España)
[Outline de capítulos de implementación específica]

### Parte 4: Razonamiento de Elecciones de Implementación
[Outline de capítulos justificando elecciones de Parte 3]

## Estimación
- Conceptos identificados: ~42
- Artículos estimados Parte 1: ~50-80
- Páginas estimadas por parte: [X, Y, Z, W]
```

**Usuario revisa y aprueba antes de continuar.**

---

### FASE 2: Creación del Grafo

**Comando:** `/constitucion-grafo`

**Input:**
- Plan maestro (aprobado)
- Notas originales

**Tarea:**
1. Extraer TODOS los conceptos del plan maestro
2. Identificar relaciones de dependencia entre conceptos
3. Clasificar por nivel (fundamental, mecanismo, ejemplo, detalle)
4. Determinar en qué partes se usa cada concepto
5. Identificar conceptos relacionados (pero no dependencias estrictas)
6. Mapear a qué notas pertenece cada concepto

**Output:** `/obra-constitucion-democratica/conceptos/grafo.json`

**Validaciones automáticas:**
- No debe haber ciclos en dependencias
- Conceptos fundamentales no pueden depender de mecanismos
- Cada concepto debe aparecer en al menos 1 parte

**Usuario revisa grafo (estructura, no contenido aún).**

---

### FASE 3: Descripción de Conceptos

**Comando:** `/constitucion-conceptos`

**Input:**
- Grafo aprobado
- Notas originales

**Tarea:**
Para cada concepto en el grafo:
1. Buscar todas las referencias en las notas
2. Priorizar información de notas más recientes (6 > 5 > ... > 0)
3. Crear markdown detallado con:
   - Definición clara
   - Contexto de por qué es importante
   - Ejemplos de las notas
   - Relación con conceptos dependientes
   - Citas textuales del usuario cuando relevante

**Output:** `/obra-constitucion-democratica/conceptos/md/*.md` (uno por concepto)

**Formato de cada concepto:**
```markdown
# [Título del Concepto]

## Definición

[Definición clara en 1-3 párrafos]

## Contexto e Importancia

[Por qué este concepto es necesario en una constitución democrática]

## Detalles desde las Notas

### [Subtema 1]
[Información detallada]

### [Subtema 2]
[Información detallada]

## Citas Relevantes del Usuario

> "Cita textual importante"
> — Notas de Sesión X

## Relaciones

**Depende de:** [lista de conceptos]
**Usado en:** Partes [X, Y]
**Relacionado con:** [lista de conceptos]

## Fuentes

- Notas de Sesión X (página/sección)
- Notas de Sesión Y (página/sección)
```

**Usuario revisa por muestreo (5-10 conceptos aleatorios).**

---

### FASE 4: Plan Parte 1

**Comando:** `/constitucion-plan-parte1`

**Input:**
- Plan maestro
- Grafo + conceptos (todos los md)

**Tarea:**
1. Del plan maestro, tomar el outline de Parte 1
2. Expandir cada sección/capítulo con artículos constitucionales específicos
3. Definir estructura de articulado (numeración, agrupación temática)
4. Identificar qué conceptos del grafo aportan info para cada artículo
5. Planificar redacción: principios + mecanismos + números concretos

**Output:** `/obra-constitucion-democratica/planes/plan-parte-1.md`

**Formato:**
```markdown
# Plan Detallado - Parte 1: La Constitución Democrática (Texto Constitucional)

## Objetivo de esta Parte
Producir texto constitucional completo y operativo con artículos numerados

## Estructura del Articulado

### Título I: Fundamentos
- Artículo 1: Soberanía Popular
- Artículo 2: Sufragio Universal
- Artículo 3: Representación Responsable
- ...

### Título II: Organización de Poderes
- Artículo X: Poder Legislativo
- Artículo Y: Poder Ejecutivo
  - Subtítulo: Bootstrap Democrático (primera legislatura)
- Artículo Z: Poder Judicial
- ...

### Título III: Control Constitucional
...

### Título IV: Protecciones Fundamentales (Cláusulas Pétreas)
...

### Título V: Estados de Excepción
...

## Principios de Redacción

- [ ] Formato de artículos: "Artículo X: [Contenido normativo]"
- [ ] Incluir números concretos (75%, 40%, 66%, 21 años, etc.)
- [ ] Lenguaje jurídico claro (no pomposo)
- [ ] Orden lógico: fundamentos → mecanismos → protecciones
- [ ] Universal (no específico de España, eso va en Parte 3)

## Mapa Conceptos → Artículos

[Qué conceptos del grafo se usan en cada artículo]
```

**Usuario revisa plan antes de escribir.**

---

### FASE 5: Escribir Parte 1 (Título por Título)

**Estrategia:** Escribir cada título del articulado por separado, revisando antes de continuar.

**Ventajas:**
- Chunks manejables temáticamente cohesivos
- Feedback progresivo del usuario
- Referencias coherentes entre títulos
- Mejor calidad por sección
- Si algo no gusta, solo se reescribe ese título
- Control de costes (generación incremental)

---

#### FASE 5.X: Escribir Cada Título del Articulado

**NOTA:** El número exacto de comandos dependerá del plan-parte-1.md (cuántos títulos tenga el articulado). Estructura genérica:

**Comando:** `/constitucion-escribir-parte1-titulo[N]`

**Input:**
- Plan Parte 1 (sección del Título N)
- Conceptos.md relevantes para ese título
- Títulos anteriores ya escritos (para continuidad y referencias entre artículos)

**Tarea:**
1. Leer plan detallado del Título N
2. Leer conceptos del grafo que se usan en los artículos de este título
3. Escribir artículos del Título N en formato constitucional
4. Numerar artículos consecutivamente
5. Referencias cruzadas a artículos anteriores cuando corresponda

**Output:** `/obra-constitucion-democratica/partes/parte-1-titulo-[N].md`

**Usuario revisa antes de continuar.**

---

#### FASE 5.FINAL: Compilar Parte 1 Completa

**Comando:** `/constitucion-compilar-parte1`

**Input:**
- Todos los títulos escritos

**Tarea:**
1. Concatenar todos los títulos en orden
2. Añadir preámbulo constitucional (opcional)
3. Verificar numeración consecutiva de artículos
4. Verificar referencias cruzadas entre artículos
5. Añadir índice de artículos por tema

**Output:** `/obra-constitucion-democratica/partes/parte-1-constitucion.md`

**Usuario revisa Parte 1 completa.**

---

**Estilo de escritura (aplica a todos los artículos):**
- Formato: "Artículo X: [Contenido normativo]"
- Lenguaje jurídico claro (no pomposo, no arcaico)
- Frases cortas y directas
- Números explícitos (75%, 21 años, etc.)
- Evitar ambigüedades
- Cada artículo = idea completa y autocontenida

---

### FASE 6: Plan Parte 2

**Comando:** `/constitucion-plan-parte2`

**Input:**
- Plan maestro
- Grafo + conceptos
- **Parte 1 ya escrita** (para referencias)

**Tarea:**
Similar a Fase 4, pero:
- Puede referenciar lo escrito en Parte 1
- Enfoque en ARGUMENTACIÓN de por qué estos principios

**Output:** `/obra-constitucion-democratica/planes/plan-parte-2.md`

**Usuario revisa plan.**

---

### FASE 7: Escribir Parte 2

**Comando:** `/constitucion-escribir-parte2`

**Input:**
- Plan Parte 2
- Conceptos relevantes
- **Parte 1 escrita** (para referencias)

**Tarea:**
- Escribir argumentación teórica
- Puede decir "Como vimos en Parte 1, Sección X..."
- Enfoque filosófico/empírico

**Output:** `/obra-constitucion-democratica/partes/parte-2-argumentacion.md`

**Usuario revisa Parte 2.**

---

### FASE 8: Plan Parte 3

**Comando:** `/constitucion-plan-parte3`

**Input:**
- Plan maestro
- Grafo + conceptos
- Partes 1 y 2 escritas

**Tarea:**
- Plan detallado de IMPLEMENTACIÓN
- Asegurar que respeta principios de Parte 1
- Definir bootstrap vs ejecución normal

**Output:** `/obra-constitucion-democratica/planes/plan-parte-3.md`

**Usuario revisa plan.**

---

### FASE 9: Escribir Parte 3

**Comando:** `/constitucion-escribir-parte3`

**Input:**
- Plan Parte 3
- Conceptos
- Partes 1 y 2 escritas

**Tarea:**
- Escribir implementación específica
- Diferenciar claramente bootstrap de operación normal
- Dar números concretos (%, días, umbrales)
- Justificar cada decisión brevemente

**Output:** `/obra-constitucion-democratica/partes/parte-3-implementacion.md`

**Usuario revisa Parte 3.**

---

### FASE 10: Plan Parte 4

**Comando:** `/constitucion-plan-parte4`

**Input:**
- Plan maestro
- Grafo + conceptos
- Partes 1, 2, 3 escritas

**Tarea:**
- Plan de razonamiento de CADA decisión de implementación
- Identificar trade-offs explicados en Parte 3
- Estructurar por tipo de decisión

**Output:** `/obra-constitucion-democratica/planes/plan-parte-4.md`

**Usuario revisa plan.**

---

### FASE 11: Escribir Parte 4

**Comando:** `/constitucion-escribir-parte4`

**Input:**
- Plan Parte 4
- Conceptos
- Partes 1, 2, 3 escritas

**Tarea:**
- Para cada decisión de implementación de Parte 3
- Explicar: por qué este número, qué trade-offs, qué alternativas se descartaron
- Tono: transparente, honesto sobre limitaciones

**Output:** `/obra-constitucion-democratica/partes/parte-4-razonamiento.md`

**Usuario revisa Parte 4.**

---

## FASE 12+: Edición (A Definir)

Después de tener las 4 partes escritas, el usuario decidirá qué tipo de edición necesita:
- Corrección de estilo
- Unificación de terminología
- Referencias cruzadas más precisas
- Etc.

**Se definirán comandos adicionales según necesidad.**

---

## Ubicación de Slash Commands

Los comandos se crearán en `.claude/commands/`:

```
# Preparación (3 comandos)
constitucion-plan-maestro.md
constitucion-grafo.md
constitucion-conceptos.md

# Parte 1: Texto Constitucional (variable según títulos)
constitucion-plan-parte1.md
constitucion-escribir-parte1-titulo1.md        # Ej: Fundamentos
constitucion-escribir-parte1-titulo2.md        # Ej: Organización de Poderes
constitucion-escribir-parte1-titulo3.md        # Ej: Control Constitucional
constitucion-escribir-parte1-titulo4.md        # Ej: Protecciones Fundamentales
constitucion-escribir-parte1-titulo5.md        # Ej: Estados de Excepción
constitucion-escribir-parte1-titulo[N].md      # Según plan
constitucion-compilar-parte1.md

# Parte 2: Explicación del Texto (estructura según plan-parte-2)
constitucion-plan-parte2.md
constitucion-escribir-parte2-capitulo*.md (según plan)
constitucion-compilar-parte2.md

# Parte 3: Implementación España (estructura según plan-parte-3)
constitucion-plan-parte3.md
constitucion-escribir-parte3-capitulo*.md (según plan)
constitucion-compilar-parte3.md

# Parte 4: Razonamiento Implementación (estructura según plan-parte-4)
constitucion-plan-parte4.md
constitucion-escribir-parte4-capitulo*.md (según plan)
constitucion-compilar-parte4.md
```

**Nota:** Cada comando debe empezar con una instrucción de re-lectura:
```
Si el contexto se ha comprimido, lee primero:
1. PLAN-SISTEMA-AGENTES.md (este plan maestro)
2. Las notas más recientes en /constitucion-notas/
```

---

## Convenciones de Escritura

### Español de España

- Usar "vosotros" no "ustedes"
- "Ordenador" no "computadora"
- "Móvil" no "celular"
- Gerundio correcto: "estando" no construcciones latinoamericanas

### Tono

- Profesional pero accesible
- Serio sin ser pomposo
- Directo sin ser simplista
- Usar ejemplos concretos
- Evitar: "cabe destacar", "es menester", "en aras de"
- Preferir: "es importante", "debemos", "para lograr"

### Formato

- Títulos en `#` markdown
- Listas numeradas para secuencias
- Listas con `-` para enumeraciones
- Negritas para énfasis
- Bloques de código para artículos constitucionales propuestos
- Citas `>` para textos del usuario

### Referencias

Cuando se referencia a otra parte:
- "Como se establece en Parte 1, Sección 2.3..."
- "Véase el análisis detallado en Parte 2..."
- No usar notas al pie, usar referencias inline

---

## Consideraciones Técnicas

### Manejo de Contradicciones en Notas

Si hay información contradictoria entre notas:
1. Priorizar nota 6 (más reciente)
2. Si no está en nota 6, usar nota 5
3. Y así sucesivamente
4. Documentar en plan maestro qué contradicciones se resolvieron

### Límites de Contexto

- Cada comando debe ser autocontenido
- Leer solo archivos necesarios (no todo siempre)
- Plan maestro sirve como resumen para comandos posteriores

### Validación

Cada output debe incluir sección final:
```markdown
## Validación

- [ ] Checklist item 1
- [ ] Checklist item 2
```

Para que el usuario pueda verificar rápidamente.

---

## Próximos Pasos

1. Usuario revisa este plan maestro
2. Crear los 11 archivos de slash commands en `.claude/commands/constitucion/`
3. Usuario ejecuta `/constitucion-plan-maestro`
4. Usuario revisa y aprueba
5. Continuar fase por fase

---

## Notas Adicionales

### Filosofía del Usuario (de las notas)

**Pragmatismo sobre idealismo:**
- Rechaza "postureo" (cosas que suenan bien pero no funcionan)
- Acepta trade-offs explícitos
- Prefiere diseño emergente a reglas exhaustivas

**Jerarquía de legitimidad:**
- Judicial < Legislativo < Popular
- Cada nivel puede anular al inferior

**Balance eficiencia-democracia:**
- No es binario, es espectro
- Default eficiente, override democrático cuando importa

**Influencia de Trevijano:**
- Autodestrucción mutua
- Elección corporativa de jueces (aunque flexible)
- Distinción democracia real vs oligarquías electivas

**Desconfianza en sistemas actuales:**
- "Democracias" actuales como oligarquías disfrazadas
- Necesidad de contrapesos efectivos, no solo formales

---

**Última actualización:** 2026-01-06
