# Revisión de artículos constitucionales

## Procedimiento

Revisar de 5 en 5 artículos usando un flujo híbrido:

1. **Primera pasada (agentes)**: Lanzar 1 agente por artículo en paralelo. Cada agente lee las 4 partes completas de la obra y revisa su artículo asignado según los criterios. Prompt del agente:
   - Leer los 4 archivos de partes/ (parte-0 a parte-3)
   - Revisar el artículo asignado según los 5 criterios
   - Responder en español, directo, solo hallazgos sustanciales
   - Formato: **Art X**: hallazgo breve → propuesta concreta

2. **Filtrado (Claude)**: Consolidar resultados de los agentes, eliminar ruido, descartar hallazgos que ya se discutieron o son intencionales, validar contra el contexto acumulado de la sesión.

3. **Presentación**: Presentar hallazgos filtrados al usuario. No tocar nada hasta confirmación.

## Criterios de revisión

### 1. Redaccion
- Eliminar parentesis que se puedan integrar en el texto
- Simplificar frases sin perder precision juridica
- Eliminar ambiguedades terminologicas

### 2. Referencias cruzadas
- Anadir referencias explicitas a articulos donde falten (formato: "articulo X" o "conforme al articulo X")
- Corregir referencias incorrectas
- No referenciar lo obvio (articulos consecutivos, niveles N->Art 2)

### 3. Consistencia
- Verificar que usa los mismos terminos que el resto de la constitucion para el mismo concepto
- Verificar que los numeros, umbrales y niveles N son coherentes con lo establecido en otros articulos
- Verificar que las reglas de calculo (votos emitidos vs censo vs total escanos) son correctas segun Art 2 y Art 22
- Verificar formato consistente de niveles ("consenso de Nivel NX")

### 4. Loopholes
- Pensar como atacante con recursos ilimitados: como se rompe este articulo?
- Crea algun conflicto con otro articulo que pueda explotarse?
- Hay escenarios no cubiertos que dejen un vacio?

### 5. Alineamiento
- Encaja con la filosofia: mentalidad defensiva, coste de corrupcion prohibitivo, mecanismos sobre moral?
- Es DRY (no repite lo que otro articulo ya establece)?
- Es KISS (no anade complejidad innecesaria)?

## Formato de presentacion

Por cada articulo con hallazgos, presentar:
- **Art X**: hallazgo breve -> propuesta concreta

Articulos sin hallazgos: listar como "Art X: OK".

## Estado de progreso

- Arts 1-18: revisados
- Arts 19-23: revisados
- Arts 24-28: revisados (pendiente de aplicar cambios)
- Arts 29-71: pendientes
