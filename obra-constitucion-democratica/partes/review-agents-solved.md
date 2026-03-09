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

---

## Correcciones mecánicas (batch)

Las siguientes correcciones son puramente mecánicas: ortografía, gramática, consistencia terminológica, anglicismos y paréntesis integrables. No cambian contenido ni diseño.

**Art 14/15 — "Corruptabilidad" → "Corruptibilidad":** Error ortográfico. La forma correcta en español es "corruptibilidad" (de "corruptible" + "-idad").

**Art 11 — "aplica" → "se aplica":** Corrección gramatical. El verbo requiere pronombre reflexivo.

**Art 22 — "Ratificar" → "Aprobar o rechazar":** Consistencia con Art 32, que es la fuente definitiva del mecanismo. "Ratificar" implica que no se puede rechazar, lo cual contradice el Art 32.

**Art 23 — "consenso N1" → "consenso de Nivel N1":** Formato inconsistente con el resto del texto constitucional.

**Art 40 — "ejecutar" → "activar", "invocó" → "activó" (3 cambios):** Consistencia verbal con Art 39 (que usa "activar") y con el propio primer párrafo del Art 40 (que usa "activación").

**Art 43 — "packs" → "grupos" (2 veces):** Anglicismo. Regla del proyecto: todo en español.

**Art 43 — Frase redundante eliminada:** "Su decisión es válida en cualquiera de los sentidos: tanto si confirma la inconstitucionalidad como si declara la norma constitucional." La frase anterior ya dice que puede "confirmar, revocar, matizar o reinterpretar".

**Art 35 — Paréntesis eliminado:** "(como los años de experiencia mínima requeridos)" era redundante. El texto ya dice "límites y condiciones específicas" y da el valor por defecto.

**Art 37 — Paréntesis integrado:** "votación popular vinculante (elección directa)" → "votación popular directa y vinculante".

**Art 62 — "En particular se aclara que:" → "En particular:":** "Se aclara" es débil para texto constitucional.

**Art 63 — "el procedimiento de reforma" → "los procedimientos de reforma":** Hay dos procedimientos (Art 67 para pétreas, Arts 68-69 para ordinarias). El singular era incorrecto.

**Art 61 — "A excepción de que el mecanismo..." → "El mecanismo...":** Construcción gramatical forzada eliminada. La excepción se entiende por el contexto (el Legislativo funciona con normalidad; la autodestrucción mutua es lo que se suspende).

---

## Art 5 (Nulidad Electoral)

**Hallazgo 3 - Loophole: sin mecanismo de nulidad electoral.** El artículo establecía consecuencias penales para los responsables de violar las garantías de votación, pero no decía nada sobre la validez de la votación afectada. Un atacante podía manipular una elección, sacrificar testaferros, y el resultado fraudulento quedaba en pie.

**Resolución:** Añadido mecanismo de nulidad electoral con tres elementos: (1) cualquier ciudadano con derecho a voto puede instar la nulidad ante el Poder Judicial; (2) si los votos afectados son suficientes para haber alterado el resultado, el juez declara la votación nula y debe repetirse; (3) las consecuencias penales aplican en todo caso, haya nulidad o no. El umbral de "suficiente para alterar el resultado" evita que un saboteador fuerce repeticiones anulando pocos votos deliberadamente.

---

**Hallazgo 4 - Cláusula pétrea incompleta:** La cláusula pétrea 3 del Art 66 solo protegía el secreto del voto, pero el Art 5 define cuatro propiedades (secreto, indelegabilidad, verificabilidad, auditabilidad). Un Legislativo con N4 podía eliminar la verificabilidad o auditabilidad sin tocar la cláusula pétrea.

**Resolución:** Cláusula pétrea 4 (antes "Secreto del Voto") ampliada a "Garantías del Voto": cubre explícitamente las cuatro propiedades del Art 5. Parte 2 actualizada con justificación expandida.

---

**Hallazgo 2 - Redacción del secreto demasiado absoluta:** "Ninguna persona o institución puede conocer el sentido del voto emitido por un ciudadano" era técnicamente falso (el propio votante lo conoce) e impedía implícitamente que instituciones procesaran votos (necesario si no se usa criptografía ZKP).

**Resolución:** Reformulado a "Ninguna persona, salvo el propio ciudadano que lo emitió, puede conocer el sentido del voto." Elimina "institución" (el sistema necesita procesar votos) y excluye al votante de la prohibición.

---

## Art 6 (Asimetría de la Anulación Popular)

**Hallazgo 2 - Asimetría base de cálculo:** La anulación popular usa el censo ciudadano como base, mientras que la aprobación legislativa usa los escaños. Esto hace que anular una ley N1 requiera movilizar al 51% de millones de ciudadanos, cuando aprobarla solo requirió el 51% de ~300 legisladores.

**Resolución:** Design choice intencional. La anulación popular es una válvula de emergencia para medidas profundamente impopulares, no un mecanismo cotidiano. La asimetría es inherente a la diferencia entre democracia representativa y directa. Justificación añadida en parte 2.
