# Hallazgos resueltos de la revisión por agentes

Hallazgos que ya fueron abordados y no requieren más acción.

---

## Art 66 (Cláusulas Pétreas)

**Hallazgo 1 - Inconsistencia Parte 2 vs Parte 1:** La Parte 2 decía "once cláusulas pétreas" pero la Parte 1 listaba 12 (la número 12 es "Lengua Oficial", artículo 9). La argumentación no incluía justificación para la cláusula pétrea 12.

**Resolución:** Parte 2 actualizada: "once" → "doce", lista reordenada por artículo referenciado, justificación de Lengua Oficial añadida.

---

**Hallazgo 4 - Loophole cláusula pétrea de reforma (11):** Protegía el "derecho de reforma" (arts 68-69), pero no protegía el propio art 67 (reforma de cláusulas pétreas). Un atacante con N4 legislativo podría reformar el art 67 vía reforma ordinaria, rebajando los umbrales del procedimiento pétreo. El contraargumento del art 68 párrafo 2 no era suficiente porque el art 67 no especificaba nivel de protección para sus parámetros.

**Resolución:** Commit d05cbb3. Art 66, cláusula 11 expandida de "artículos 68-69" a "artículos del 67 al 69 incluidos". Protege explícitamente el procedimiento de reforma de cláusulas pétreas contra supresión.

---

## Art 67 (Procedimiento de Reforma de Cláusulas Pétreas)

**Hallazgo 1 - Loophole falta nivel de protección de parámetros:** Los parámetros numéricos del art 67 (N5, 75%, N6, N1, 2 años, 21 años) no tenían cláusula de protección explícita como otros artículos.

**Resolución:** Commit d05cbb3. Añadida sección "Protección de parámetros" al Art 67: los parámetros solo pueden modificarse cumpliendo los procedimientos del propio Art 67. Patrón de doble capa (igual que Art 2): cláusula pétrea impide supresión + auto-protección especifica procedimiento para modificar parámetros.
