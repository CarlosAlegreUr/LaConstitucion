---
description: "Crea el plan detallado de Parte 1 (texto constitucional con artículos específicos)"
---

# IMPORTANTE: Si el contexto se ha comprimido

Lee primero:
1. `PLAN-SISTEMA-AGENTES.md`
2. `/obra-constitucion-democratica/planes/plan-maestro.md`
3. `/obra-constitucion-democratica/conceptos/grafo.json`

---

# Comando: Plan Parte 1

## Tu Tarea

Crear plan detallado de Parte 1: El Texto Constitucional con estructura de artículos específicos.

## Input

1. Plan maestro (estructura de 8 títulos ya definida)
2. Grafo de conceptos (42 conceptos con info sobre cuáles van en Parte 1)
3. Conceptos .md (para detalles de cada concepto)

## Proceso

1. **Toma la estructura del plan maestro** (8 títulos, 85 artículos estimados)
2. **Para cada título, detalla artículo por artículo:**
   - Número de artículo
   - Título/tema del artículo
   - Qué concepto(s) del grafo cubre
   - Contenido normativo específico (con números cuando corresponda)
   - Relaciones con otros artículos

3. **Verifica coherencia:**
   - Numeración consecutiva
   - Referencias cruzadas claras
   - No duplicación de conceptos
   - Cobertura completa de conceptos fundamentales y mecanismos

## Output

Escribe: `/obra-constitucion-democratica/planes/plan-parte-1.md`

**Formato:**

```markdown
# Plan Detallado - Parte 1: La Constitución Democrática (Texto Constitucional)

**Fecha:** 2026-01-06
**Objetivo:** Articulado constitucional completo y operativo

---

## Principios de Redacción

- Formato: "Artículo X: [Contenido normativo]"
- Lenguaje jurídico claro (no pomposo, no arcaico)
- Incluir números explícitos (75%, 21 años, 40%, 66%, etc.)
- Cada artículo = idea completa y autocontenida
- Referencias cruzadas cuando necesario

---

## Estructura Global

**Total:** 85 artículos en 8 títulos
**Páginas estimadas:** 40-60

---

## TÍTULO I: FUNDAMENTOS (Arts. 1-12)

### Artículo 1: Soberanía Popular

**Concepto:** [[soberania-popular]]

**Contenido normativo:**
- La soberanía reside originaria y permanentemente en el pueblo
- No es delegable de forma irrevocable
- Se ejerce mediante mecanismos directos e indirectos establecidos en esta Constitución

**Referencias:** Art. 2 (jerarquía de legitimidad), Arts. 5-7 (representación)

---

### Artículo 2: Jerarquía de Legitimidad

**Concepto:** [[jerarquia-legitimidad]]

**Contenido normativo:**
- Establece jerarquía: Judicial < Legislativo < Popular
- Cada nivel de mayor legitimidad puede anular decisiones del inferior
- Se operacionaliza mediante override (Art. 47-50)

**Referencias:** Art. 1 (soberanía), Arts. 47-50 (override popular)

---

### Artículo 3: Sufragio Universal

**Concepto:** [[sufragio-universal]]

**Contenido normativo:**
- Todo ciudadano mayor de edad tiene derecho al voto
- Igualdad electoral: un ciudadano, un voto
- No puede restringirse salvo incapacidad legal declarada judicialmente

**Referencias:** Art. 53 (cláusula pétrea)

---

### Artículo 4: Secreto y Verificabilidad del Voto

**Concepto:** [[sufragio-universal]] (continuación)

**Contenido normativo:**
- El voto es secreto (nadie puede saber cómo votó cada persona)
- El voto es verificable (cada votante puede comprobar que su voto fue contado)
- Auditoría pública del proceso electoral

**Referencias:** Arts. 81-85 (transparencia blockchain)

---

### Artículo 5: Representación por Distritos Territoriales

**Concepto:** [[representacion-responsable]]

**Contenido normativo:**
- Representantes electos por distritos territoriales
- Un representante por distrito
- Vínculo territorial con ciudadanos del distrito

**Referencias:** Art. 10 (delimitación distritos), Arts. 6-7 (revocación)

---

### Artículo 6: Revocabilidad de Representantes

**Concepto:** [[representacion-responsable]], [[revocacion-umbral-75]]

**Contenido normativo:**
- Los representantes son revocables directamente por el pueblo del distrito
- Umbral de revocación: 75% de votos válidos en el distrito
- Sin causas legales previas (umbral matemático puro)

**Referencias:** Art. 7 (procedimiento revocación)

---

### Artículo 7: Procedimiento de Revocación

**Concepto:** [[revocacion-umbral-75]] (continuación)

**Contenido normativo:**
- Convocatoria: 2% del censo del distrito en 60 días
- Votación oficial: participación abierta a todo el distrito
- Si alcanza 75% → mandato extinguido, nueva elección en 90 días
- Cooldown: no puede convocarse nueva revocación contra sucesor antes de 6 meses

**Referencias:** Art. 6 (principio revocación)

---

### Artículo 8: Sistema de Doble Vuelta Electoral

**Concepto:** [[doble-vuelta-electoral]]

**Contenido normativo:**
- Primera vuelta: si candidato supera 51% → gana directamente
- Segunda vuelta: si nadie supera 51% → los 2 más votados compiten
- Garantiza mayoría real, no solo pluralidad

**Referencias:** Art. 5 (representación por distrito)

---

### Artículo 9: Tamaño de Distritos

**Concepto:** [[optimizacion-distritos-corrupcion]]

**Contenido normativo:**
- Tamaño objetivo: 95.000 - 120.000 habitantes por distrito
- Basado en optimización por coste de corrupción (maximizar P25)
- Constraints: continuidad geográfica, coherencia histórico-cultural

**Referencias:** Art. 10 (actualización periódica)

---

### Artículo 10: Actualización Distrital Periódica

**Concepto:** [[actualizacion-distrital-21-anos]]

**Contenido normativo:**
- Los distritos se actualizan cada 21 años (maduración cerebral)
- Algoritmo de optimización basado en percentil 25 de renta (proxy coste corrupción)
- Primera actualización: año X + 21
- Ejecutado por comisión técnica independiente, ratificado por referéndum

**Referencias:** Art. 9 (tamaño distritos)

---

### Artículo 11: Financiación Electoral Pública

**Concepto:** [implicado en sufragio-universal y representacion-responsable]

**Contenido normativo:**
- Financiación pública de campañas electorales
- Límites estrictos a donaciones privadas
- Transparencia total de financiación (blockchain público)

**Referencias:** Arts. 81-85 (transparencia)

---

### Artículo 12: Voto Remoto Verificable

**Concepto:** [[sufragio-universal]], [[transparencia-blockchain]]

**Contenido normativo:**
- El voto puede ejercerse remotamente mediante sistema verificable criptográficamente
- Garantías: secreto + verificabilidad individual + auditoría pública
- No prescribe tecnología específica (principio de capacidad del proceso)

**Referencias:** Art. 84 (tecnología habilitadora)

---

[Continúa con TÍTULO II, III, IV, V, VI, VII, VIII de forma similar, detallando cada artículo]

## TÍTULO II: ORGANIZACIÓN DE PODERES (Arts. 13-35)

[Detalle de Arts. 13-35]

## TÍTULO III: BOOTSTRAP DEMOCRÁTICO (Arts. 36-41)

[Detalle de Arts. 36-41]

## TÍTULO IV: CONTROL CONSTITUCIONAL (Arts. 42-50)

[Detalle de Arts. 42-50]

## TÍTULO V: PROTECCIONES FUNDAMENTALES (Arts. 51-60)

[Detalle de Arts. 51-60]

## TÍTULO VI: ESTADOS DE EXCEPCIÓN (Arts. 61-72)

[Detalle de Arts. 61-72]

## TÍTULO VII: CONTROL DE FUERZAS ARMADAS (Arts. 73-80)

[Detalle de Arts. 73-80]

## TÍTULO VIII: TRANSPARENCIA Y TECNOLOGÍA (Arts. 81-85)

[Detalle de Arts. 81-85]

---

## Mapa Conceptos → Artículos

[Tabla que muestra qué artículos cubren cada concepto del grafo]

---

## Validación

- [ ] 85 artículos planificados (puede variar ligeramente)
- [ ] Numeración consecutiva 1-85
- [ ] Cada concepto fundamental tiene al menos 1 artículo
- [ ] Referencias cruzadas identificadas
- [ ] Números concretos especificados donde corresponde
- [ ] Balance entre principios (qué) y mecanismos (cómo)

---

**Última actualización:** 2026-01-06
**Estado:** LISTO PARA REVISIÓN → Si aprobado, proceder a escritura por títulos
```

## Consideraciones

1. **Detalla TODOS los artículos:** No solo los primeros, completa los 85
2. **Especifica números:** Cuando el concepto tiene números (75%, 21 años, 66%, etc.), inclúyelos
3. **Referencias cruzadas:** Identifica qué artículos se relacionan
4. **Conceptos del grafo:** Usa [[nombre-concepto]] para linkear

---

El usuario revisará este plan antes de proceder a escritura del Título I.
