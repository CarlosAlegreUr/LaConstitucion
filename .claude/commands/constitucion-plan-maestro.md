---
description: "Crea el Plan Maestro analizando todas las notas y definiendo estructura de las 4 partes"
---

# IMPORTANTE: Si el contexto se ha comprimido

Lee primero:
1. `PLAN-SISTEMA-AGENTES.md` (fuente de verdad del sistema)
2. Las notas en `/constitucion-notas/` (especialmente la-constitucion-notas-6.md)

---

# Comando: Plan Maestro

## Tu Tarea

Crear el plan maestro de la obra "La Constitución Democrática" analizando las 7 notas de estudio.

## Input

1. Todas las notas en `/constitucion-notas/`:
   - `la-constitución-0.md` (primera sesión)
   - `la-constitucion-1.md`
   - `la-constitucion-notas-2.md`
   - `la-constitucion-notas-3.md`
   - `la-constitucion-notas-4.md`
   - `la-constitucion-notas-5.md`
   - `la-constitucion-notas-6.md` (más reciente, prioridad máxima)

2. `PLAN-SISTEMA-AGENTES.md` (estructura deseada de las 4 partes)

## Proceso

1. **Lee TODAS las notas en orden cronológico** (0 → 6)
2. **Identifica evolución de ideas:** Cómo cambiaron conceptos clave
3. **Resuelve contradicciones:** Priorizar nota 6 > 5 > ... > 0
4. **Identifica conceptos principales:** ~40-50 conceptos (ya extraídos en grafo.json, puedes leerlo)
5. **Crea outline de las 4 partes:**
   - **Parte 1:** Texto constitucional con estructura de títulos y artículos
   - **Parte 2:** Explicación del texto (capítulos)
   - **Parte 3:** Implementación España (capítulos)
   - **Parte 4:** Razonamiento implementación (capítulos)

## Output

Escribe: `/obra-constitucion-democratica/planes/plan-maestro.md`

**Formato:**

```markdown
# Plan Maestro - La Constitución Democrática

**Fecha:** 2026-01-06
**Autor:** Charles
**Objetivo:** Diseño constitucional completo para democracia real

---

## Análisis de Notas

### Evolución de Ideas (Nota 0 → Nota 6)

[Describe cómo evolucionaron conceptos clave]

### Conceptos Principales Identificados

[Lista de ~42 conceptos del grafo.json con breve descripción]

### Contradicciones Resueltas

[Documenta qué contradicciones encontraste y cómo las resolviste]

---

## Estructura de las 4 Partes

### Parte 1: La Constitución Democrática (Texto Constitucional)

**Objetivo:** Producir texto constitucional completo con artículos numerados

**Estructura propuesta:**

- **Título I: Fundamentos** (Arts. estimados: X-Y)
  - Soberanía Popular
  - Sufragio Universal
  - Representación Responsable
  - Jerarquía de Legitimidad

- **Título II: Organización de Poderes** (Arts. estimados: X-Y)
  - Poder Legislativo
  - Poder Ejecutivo
  - Bootstrap Democrático (primera legislatura)
  - Poder Judicial

- **Título III: Control Constitucional** (Arts. estimados: X-Y)
  - Sistema en capas
  - Override Popular

- **Título IV: Protecciones Fundamentales** (Arts. estimados: X-Y)
  - Cláusulas Pétreas
  - Procedimiento de Reforma
  - Cosa Juzgada

- **Título V: Estados de Excepción** (Arts. estimados: X-Y)
  - Tipos y límites obligatorios
  - Núcleo intangible

[Ajusta títulos según veas necesario basándote en las notas]

**Páginas estimadas:** X-Y (articulado constitucional)

---

### Parte 2: Explicación del Texto Constitucional

**Objetivo:** Explicar por qué cada artículo está escrito así

**Capítulos propuestos:**

1. [Capítulo que explica Título I]
2. [Capítulo que explica Título II]
3. [etc.]

**Páginas estimadas:** X-Y

---

### Parte 3: Ejemplo de Implementación (España)

**Objetivo:** Cómo se implementaría en contexto español

**Capítulos propuestos:**

1. Bootstrap Democrático en España
2. [Otros capítulos según veas necesario]

**Páginas estimadas:** X-Y

---

### Parte 4: Razonamiento de Elecciones de Implementación

**Objetivo:** Justificar cada elección específica de Parte 3

**Capítulos propuestos:**

1. [Según decisiones de Parte 3]

**Páginas estimadas:** X-Y

---

## Estimación Global

- **Conceptos identificados:** 42 (ya en grafo.json)
- **Artículos estimados Parte 1:** 50-80
- **Páginas totales estimadas:** 150-250
- **Distribución por parte:** [X, Y, Z, W]

---

## Filosofía del Usuario (Resumen de Notas)

[Resume la filosofía identificada en las notas:
- Pragmatismo sobre postureo
- Jerarquía de legitimidad
- Balance eficiencia-democracia
- Influencia Trevijano
- Desconfianza sistemas actuales
- Enfoque hacker (diseñar pensando en peor caso)]

---

## Validación

- [ ] Leí las 7 notas completas
- [ ] Identifiqué evolución de ideas
- [ ] Resolví contradicciones (prioridad nota 6)
- [ ] Propuse estructura coherente de Parte 1 (títulos del articulado)
- [ ] Propuse outlines de Partes 2, 3, 4
- [ ] Documenté filosofía del usuario

---

**Última actualización:** 2026-01-06
```

## Consideraciones Importantes

1. **Parte 1 es TEXTO CONSTITUCIONAL:** No es narrativa explicativa, son artículos con números
2. **Priorizar nota 6:** Si hay conflicto entre notas, usa la más reciente
3. **Usar grafo.json:** Ya tiene los 42 conceptos extraídos, puedes leerlo como referencia
4. **Ser específico en estructura:** Define cuántos títulos tiene Parte 1 y qué cubre cada uno

---

El usuario revisará este plan antes de proceder a FASE 2 (que ya está hecha: grafo + conceptos).
