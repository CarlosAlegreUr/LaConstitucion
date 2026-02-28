---
description: "Crea archivos markdown detallados para cada concepto del grafo"
---

# IMPORTANTE: Si el contexto se ha comprimido

Lee primero:
1. `PLAN-SISTEMA-AGENTES.md` (plan maestro del sistema)
2. `/obra-constitucion-democratica/conceptos/grafo.json` (debe existir ya)

---

# Comando: Descripción de Conceptos

## Tu Tarea

Para cada concepto en el grafo, crear un archivo markdown detallado basándote en las notas originales.

## Input (archivos a leer)

1. `/obra-constitucion-democratica/conceptos/grafo.json`
2. Todas las notas en `/constitucion-notas/*.md`
3. `PLAN-SISTEMA-AGENTES.md` (para contexto)

## Proceso

Para cada concepto en el grafo:

1. **Lee el concepto** del grafo.json (title, dependencies, etc.)
2. **Busca todas las referencias** en las notas (usa source_notes como guía)
3. **Prioriza información de notas recientes:** nota-6 > nota-5 > ... > nota-0
4. **Extrae información relevante:**
   - Definición del concepto
   - Por qué es importante
   - Ejemplos concretos
   - Citas del usuario
   - Casos históricos (si los hay)
5. **Escribe markdown detallado** siguiendo el formato especificado

## Output

Crea archivos en: `/obra-constitucion-democratica/conceptos/md/[id-concepto].md`

Ejemplo: `/obra-constitucion-democratica/conceptos/md/separacion-poderes.md`

**Formato de cada archivo:**

```markdown
# [Título del Concepto]

## Definición

[Definición clara y concisa del concepto en 1-3 párrafos]

[Si es concepto fundamental: explica desde primeros principios]
[Si es mecanismo: explica qué problema resuelve]
[Si es ejemplo: explica el caso concreto]

## Contexto e Importancia

[Por qué este concepto es necesario en una constitución democrática]
[Qué pasaría sin este concepto]
[Cómo se relaciona con el objetivo de democracia real]

## Detalles desde las Notas

### [Subtema 1]

[Información detallada extraída de las notas]
[Puede incluir sub-secciones según sea necesario]

### [Subtema 2]

[...]

### [Si hay casos históricos]

**[País/Caso]:** [Descripción breve de cómo se aplicó o falló]

## Citas Relevantes del Usuario

> "Cita textual importante del usuario"
> — Notas de Sesión X

[Incluye 2-5 citas cuando refuercen el concepto]

## Relaciones con Otros Conceptos

**Depende de:**
- [[concepto-1]]: [Breve explicación de por qué]
- [[concepto-2]]: [...]

**Usado en:**
- Parte 1: [Contexto de uso]
- Parte 3: [Contexto de uso]

**Relacionado con:**
- [[concepto-relacionado-1]]: [Cómo se relacionan]
- [[concepto-relacionado-2]]: [...]

## Fuentes

- Notas de Sesión 2 (sección X)
- Notas de Sesión 6 (sección Y)

---

*Última actualización: [fecha]*
```

## Estilo de Escritura

- **Español de España:** Castellano peninsular
- **Tono:** Profesional pero accesible
- **Párrafos cortos:** 3-5 líneas máximo
- **Lenguaje directo:** Sin jerga innecesaria
- **Usa listas** cuando clarifica
- **Negritas para énfasis**, no cursivas
- **Citas del usuario:** Usa > para citarle textualmente cuando refuerza el punto

## Conceptos Prioritarios (asegúrate de que estén bien detallados)

Estos conceptos son fundamentales y deben tener especial atención:

- Soberanía popular
- Separación de poderes
- Jerarquía de legitimidad
- Autodestrucción mutua
- Override popular
- Cláusulas pétreas
- Bootstrap democrático
- Semipresidencialismo
- Estados de excepción

## Validación

Antes de entregar, verifica:

- [ ] Creé un archivo .md por cada concepto del grafo
- [ ] Cada archivo tiene todas las secciones del formato
- [ ] Prioricé información de nota-6 cuando había conflictos
- [ ] Incluí citas del usuario cuando refuerzan el concepto
- [ ] Documenté las relaciones (dependencies, related)
- [ ] Expliqué POR QUÉ cada concepto es importante, no solo QUÉ es

## Estrategia de Ejecución

**Si hay muchos conceptos (>30):**

1. Primero crea los fundamentales (level="fundamental")
2. Luego los mecanismos (level="mecanismo")
3. Luego ejemplos y detalles

Esto permite que los conceptos que dependen de otros ya tengan referencias disponibles.

## Notas Importantes

- **Sé generoso con la información:** Es mejor tener más contenido y editar después que quedarse corto
- **Cita textualmente:** Cuando el usuario dijo algo importante, cítalo literalmente
- **Contexto histórico:** Si las notas mencionan casos reales (Hungría, Weimar, etc.), inclúyelos
- **Trade-offs:** Si el usuario mencionó pros/cons de este concepto, documéntalos

---

Una vez termines, el usuario revisará por muestreo (5-10 conceptos aleatorios) antes de continuar con la Fase 4 (plan de Parte 1).
