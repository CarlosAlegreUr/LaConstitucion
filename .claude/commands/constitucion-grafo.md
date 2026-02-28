---
description: "Crea el grafo JSON de relaciones entre conceptos de la obra"
---

# IMPORTANTE: Si el contexto se ha comprimido

Lee primero:
1. `PLAN-SISTEMA-AGENTES.md` (plan maestro del sistema)
2. `/obra-constitucion-democratica/planes/plan-maestro.md` (debe existir ya)

---

# Comando: Grafo de Conceptos

## Tu Tarea

Crear un grafo JSON que capture todos los conceptos de la obra y sus relaciones.

## Input (archivos a leer)

1. `PLAN-SISTEMA-AGENTES.md`
2. `/obra-constitucion-democratica/planes/plan-maestro.md` (creado en fase anterior)
3. `/constitucion-notas/*.md` (para referencia si necesitas más detalles)

## Proceso

1. **Extrae todos los conceptos** del plan maestro
2. **Identifica relaciones de dependencia:** ¿Qué conceptos deben entenderse antes de otros?
3. **Clasifica por nivel:** fundamental, mecanismo, ejemplo, detalle
4. **Determina en qué partes** se usa cada concepto [1, 2, 3, 4]
5. **Identifica conceptos relacionados** (no dependencias estrictas, sino conexiones útiles)
6. **Mapea a fuentes:** ¿De qué notas viene cada concepto?

## Output

Escribe el archivo: `/obra-constitucion-democratica/conceptos/grafo.json`

**Estructura del JSON:**

**NOTA:** Puedes ajustar esta estructura si consideras que otra es más útil. Lo importante es capturar:
- Todos los conceptos
- Sus relaciones de dependencia
- En qué partes se usan
- Navegabilidad clara

```json
{
  "metadata": {
    "created": "YYYY-MM-DD",
    "total_concepts": 0,
    "last_updated": "YYYY-MM-DD"
  },
  "concepts": {
    "id-concepto": {
      "title": "Título legible del concepto",
      "level": "fundamental | mecanismo | ejemplo | detalle",
      "dependencies": ["conceptos que deben entenderse antes"],
      "used_in_parts": [1, 2, 3, 4],
      "related": ["conceptos relacionados pero no dependencias"],
      "source_notes": ["nota-2", "nota-6"]
    }
  }
}
```

**Ejemplo:**

```json
{
  "metadata": {
    "created": "2026-01-06",
    "total_concepts": 42,
    "last_updated": "2026-01-06"
  },
  "concepts": {
    "separacion-poderes": {
      "title": "Separación de Poderes",
      "level": "fundamental",
      "dependencies": [],
      "used_in_parts": [1, 2],
      "related": ["checks-and-balances", "autodestruccion-mutua"],
      "source_notes": ["nota-2", "nota-6"]
    },
    "autodestruccion-mutua": {
      "title": "Autodestrucción Mutua (Modelo Trevijano)",
      "level": "mecanismo",
      "dependencies": ["separacion-poderes", "semipresidencialismo"],
      "used_in_parts": [1, 3, 4],
      "related": ["resolucion-conflictos"],
      "source_notes": ["nota-2", "nota-6"]
    },
    "override-popular": {
      "title": "Override Popular vía Blockchain",
      "level": "mecanismo",
      "dependencies": ["tribunal-constitucional", "jerarquia-legitimidad"],
      "used_in_parts": [1, 3, 4],
      "related": ["control-constitucional", "blockchain"],
      "source_notes": ["nota-6"]
    }
  }
}
```

## Validaciones Automáticas

Antes de entregar, verifica:

- [ ] **No hay ciclos en dependencias:** Si A depende de B, B NO puede depender de A (directa o indirectamente)
- [ ] **Conceptos fundamentales primero:** Los de level="fundamental" no pueden depender de level="mecanismo" o "ejemplo"
- [ ] **Cada concepto usado al menos una vez:** Todos los conceptos deben aparecer en al menos 1 parte
- [ ] **Metadata correcto:** total_concepts coincide con el número real de conceptos

## Reglas de Dependencia

**Fundamental:** No depende de nada (o solo de otros fundamentales)
**Mecanismo:** Puede depender de fundamentales u otros mecanismos
**Ejemplo:** Puede depender de cualquiera
**Detalle:** Puede depender de cualquiera

**Jerarquía:** Fundamental > Mecanismo > Ejemplo > Detalle

## Conceptos Esperados (guía, no exhaustivo)

**Fundamentales (~10):**
- Soberanía popular
- Separación de poderes
- Jerarquía de legitimidad
- Estado de derecho
- [...]

**Mecanismos (~15):**
- Autodestrucción mutua
- Override popular
- Cláusulas pétreas
- Estados de excepción
- Bootstrap democrático
- [...]

**Ejemplos (~10):**
- Semipresidencialismo
- Elección corporativa jueces
- Cooldowns temporales
- [...]

**Detalles (~5):**
- Umbrales específicos (75%, 95%, etc.)
- Plazos concretos (2 años, 20 años, etc.)
- [...]

## Notas Importantes

- **Sé exhaustivo:** Es mejor incluir más conceptos y que sean simples, que pocos y complejos
- **IDs claros:** Usa kebab-case (separacion-poderes) para IDs de conceptos
- **No te preocupes por perfección:** El siguiente comando (conceptos.md) expandirá cada uno

---

Una vez termines, el usuario revisará el grafo antes de continuar con la Fase 3 (descripción de conceptos).
