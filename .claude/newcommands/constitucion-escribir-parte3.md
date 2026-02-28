---
description: "Escribe Parte 3: Ejemplo de Implementación (con números concretos)"
---

# IMPORTANTE: Si el contexto se ha comprimido

Lee primero:
1. `PLAN-SISTEMA-AGENTES.md`
2. `/obra-constitucion-democratica/planes/plan-parte-3.md` (APROBADO)
3. Partes 1 y 2 (para coherencia)

---

# Comando: Escribir Parte 3

## Tu Tarea

Escribir **Parte 3: Ejemplo de Implementación** con propuestas específicas y números concretos.

## Input

1. Plan de Parte 3 (aprobado)
2. Partes 1 y 2 escritas
3. Archivos md de conceptos
4. **Notas (especialmente nota-6)** - contiene las decisiones de implementación
5. PLAN-SISTEMA-AGENTES.md

## Enfoque de Esta Parte

**Implementación CONCRETA que respeta los principios de Parte 1.**

**Ahora SÍ incluyes:**
- Porcentajes específicos (75%, 95%, 66%, etc.)
- Plazos (2 años, 20 años, 6 meses, etc.)
- Números concretos (participación mínima 40%, etc.)
- Estructura detallada de instituciones
- Procedimientos paso a paso

**Dos fases críticas:**
1. **Bootstrap:** Primera legislatura con reglas especiales
2. **Operación Normal:** Legislaturas posteriores

**DEBE quedar CRISTALINO** cuándo termina bootstrap y empieza normal.

## Output

Escribe: `/obra-constitucion-democratica/partes/parte-3-implementacion.md`

## Estilo de Escritura

**Hereda convenciones de Partes 1-2:**
- Español de España
- Profesional pero accesible
- Párrafos cortos

**Específico de Parte 3:**
- **Precisión:** Números exactos, no rangos vagos
- **Claridad:** Cada procedimiento debe ser ejecutable
- **Justificación breve:** Para cada número, 1-2 líneas de por qué
  (La justificación completa irá en Parte 4)

## Formato de Decisiones de Implementación

Cuando especifiques una decisión numérica:

```markdown
**[Nombre de la decisión]**

**Valor:** [número concreto]

**Justificación:** [1-2 líneas de por qué este número]

**Procedimiento:** [Si aplica, pasos concretos]
```

**Ejemplo:**

```markdown
**Override Popular: Participación Mínima**

**Valor:** 40% del censo electoral

**Justificación:** Balance entre acceso (no tan alto que sea inalcanzable)
y legitimidad (suficientemente alto para demostrar interés real).

**Procedimiento:**
1. Ciudadano o grupo de ciudadanos convoca votación vía blockchain
2. Periodo de firmas: 2% del censo en 60 días
3. Si se alcanza, se convoca votación oficial
4. Participación mínima 40%, mayoría 66% para override
```

## Bootstrap vs Operación Normal

**Sección dedicada al inicio:**

```markdown
## Capítulo 1: El Bootstrap Democrático

### Sección 1.1: ¿Qué es el Bootstrap?

[Explicación de la fase especial - 2-3 páginas]

El bootstrap es la primera legislatura tras la aprobación de esta constitución.
Tiene características especiales porque su mandato es implementar los principios
constitucionales en forma de leyes concretas.

**Duración del bootstrap:** [X años - especificar]

**Diferencias con operación normal:**

| Aspecto | Bootstrap | Operación Normal |
|---------|-----------|------------------|
| Mandato | Implementar principios constitucionales | Gobernar según leyes ya establecidas |
| Override popular | 75% discrepancia invierte voto | No aplica (solo para constitucionalidad) |
| Revocación | [Especificar si aplica diferente] | [Reglas estándares] |
| [etc.] | [...] | [...] |

### Sección 1.2: Mecanismo de Override 75%

**Cómo funciona:**

Durante el bootstrap, el pueblo puede revisar cada decisión del representante.

1. Representante vota implementación de [tema X]
2. Publicación obligatoria: texto completo + argumentos
3. Periodo de revisión: [Y días]
4. Votación popular:
   - Si 75%+ discrepancia → voto se invierte automáticamente
   - Si <75% discrepancia → voto original se mantiene

**Ejemplo concreto:** [Dar un ejemplo hipotético de cómo funcionaría]

### Sección 1.3: Transición a Operación Normal

**Cuándo termina el bootstrap:**

Al finalizar el mandato de la primera legislatura ([X años]), el sistema
transiciona a operación normal. A partir de ese momento:

- Ya no aplica override 75%
- Override popular solo para constitucionalidad de leyes
- Todas las implementaciones del bootstrap se convierten en leyes ordinarias
  (modificables con mayorías especificadas en la constitución)

[...]
```

## Referencias a Partes Anteriores

Usa liberalmente:

> "Como establecimos en Parte 1, Artículo 5, debe existir mecanismo de
> revocación de representantes. Aquí especificamos cómo implementarlo..."

> "La fundamentación teórica de esta decisión se encuentra en Parte 2, Capítulo 3.
> Ahora damos los números concretos..."

## Estructura de Artículos Implementados

Cuando propongas un artículo de ley específico:

```markdown
**Artículo de Implementación X: [Título]**

[Texto legal preciso]

**Parámetros:**
- [Parámetro 1]: [valor]
- [Parámetro 2]: [valor]

**Notas:**
- [Aclaración técnica si necesaria]
```

## Tablas Comparativas

Usa tablas para claridad:

**Ejemplo: Mayorías requeridas**

| Tipo de Decisión | Mayoría Requerida | Observaciones |
|------------------|-------------------|---------------|
| Ley ordinaria | 50% + 1 | Mayoría simple |
| Ley orgánica | 60% | Materias sensibles |
| Reforma constitucional | 66% | Primera votación |
| Reforma cláusula pétrea | 95% + proceso especial | Excepcional |

## Validación Continua

Mientras escribes:

- [ ] ¿Especifiqué números concretos?
- [ ] ¿Diferencié claramente bootstrap vs normal?
- [ ] ¿Cada decisión respeta principios de Parte 1?
- [ ] ¿Di justificación breve (1-2 líneas) de cada número?
- [ ] ¿Los procedimientos son ejecutables?

## Estructura del Documento

```markdown
# Parte 3: Ejemplo de Implementación

## Introducción

[Esta parte propone implementación específica]
[Explicación de bootstrap vs operación normal]
[3-4 páginas]

---

## Capítulo 1: El Bootstrap Democrático

[Explicación detallada de la fase bootstrap]

---

## Capítulo 2: Poder Ejecutivo

### Sección 2.1: Semipresidencialismo

**Presidente:**
- Elección: [directa, método específico]
- Mandato: [X años]
- Reelección: [sí/no, cuántas veces]
- [etc.]

**Primer Ministro:**
- Elección: [por parlamento, procedimiento]
- Mandato: [mientras tenga confianza del parlamento]
- [etc.]

### Sección 2.2: Autodestrucción Mutua

**Cooldown inicial:** [6-12 meses]

**Procedimiento:**
1. [Paso 1]
2. [Paso 2]
[...]

---

[Más capítulos según plan]

---

## Conclusión

[Síntesis de la implementación propuesta]
[Transición a Parte 4: ahora viene la justificación detallada]
[2 páginas]

---

*Parte 3 de 4 de "La Constitución Democrática"*
*Siguiente: Parte 4 - Razonamiento de Elecciones*
```

## Estimación de Longitud

**Total esperado:** 50-70 páginas

(La más larga de las 4 partes debido al detalle)

## Validación Final

- [ ] Seguí el plan aprobado
- [ ] Especifiqué todos los números concretos de las notas
- [ ] Bootstrap está claramente diferenciado
- [ ] Cada decisión tiene justificación breve
- [ ] Procedimientos son claros y ejecutables
- [ ] Respeta principios de Parte 1
- [ ] Referencias a Partes 1-2 son claras
- [ ] Español de España correcto

---

Una vez termines, el usuario revisará Parte 3 antes de continuar con `/constitucion-plan-parte4`.

**IMPORTANTE:** Esta es la parte más técnica. Sé preciso con los números y procedimientos.
