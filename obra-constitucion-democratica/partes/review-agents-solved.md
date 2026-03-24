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

---

## Art 35 (Nombramiento de Jueces) y Art 37 (Experiencia Tribunal Supremo)

**Loophole 1 - Quién nombra a los jueces ordinarios:** El artículo definía requisitos (titulación, experiencia, examen) pero no quién nombra. El procedimiento quedaba delegado a ley ordinaria (N1), permitiendo captura de la base judicial.

**Loophole 2 - Quién diseña el examen:** Sin definir, un Ejecutivo podía controlar el contenido del examen para filtrar jueces afines.

**Redacción 2 - Experiencia 1,5 años:** Valor paradójico (no puedes tener experiencia judicial sin ser juez) y curiosamente bajo.

**Referencia cruzada Art 37:** No quedaba claro si los requisitos del Art 35 aplican a magistrados del Supremo, ni si estos necesitan experiencia judicial previa.

**Resolución:** Art 35 reescrito: eliminado requisito de experiencia (paradójico), examen y acreditación exclusivamente diseñados y administrados por el Poder Judicial, titulaciones válidas determinadas por 2/3 del Tribunal Supremo con ciclo de 8 años y periodo de transición de 1 año, corregida gramática ("la independencia judicial"). Añadido régimen de acreditación de facultades (mismo sistema que titulaciones, Arranque con defaults del régimen anterior, primera ronda N1, después 2/3). Art 37: añadido requisito de experiencia mínima como juez de 5 años (rango 5-10, Arranque N1, post-Arranque N4), referencia explícita al Art 35 para facultades acreditadas. Desambiguada cláusula N5 ("del Poder Legislativo"). Parte 2 actualizada con argumentación.

---

## Art 30 (Manipulación del Índice de Inflación)

**Hallazgo 1 - Loophole: no se define quién calcula ni certifica la inflación.** Un atacante que controle el organismo estadístico podría inflar el presupuesto indefinidamente sin votación legislativa.

**Resolución:** Riesgo aceptado por diseño. La inflación es perceptible en el día a día por cualquier ciudadano; una manipulación grosera sería evidente sin carga cognitiva significativa. Una manipulación sutil (1-2% extra) produce un beneficio marginal que no justifica el riesgo político. Además, el Legislativo puede aprobar un presupuesto nuevo en cualquier momento, así que la prórroga con inflación es un fallback temporal.

---

## Art 7 (Umbral de Votación para Independencia Territorial)

**Hallazgo 2 - Sin umbral mínimo constitucional de participación ni consenso para la votación de independencia.** Un Legislativo hostil podría poner umbrales ridículamente bajos (fragmentar el Estado) o imposibles (bloquear la secesión de facto).

**Resolución:** Design choice. El artículo delega los umbrales a ley ordinaria deliberadamente: dependen del contexto (tamaño del territorio, demografía). El rango de 21-42 años ya es un filtro serio contra separaciones impulsivas. Si un Legislativo pone umbrales abusivos, el Judicial puede declararlos inconstitucionales por violar el espíritu del artículo ("bajo ninguna circunstancia puede prohibirse ni suprimirse").

---

## Art 42-43 (Nulidad de Pleno Derecho vs. Inaplicabilidad)

**Hallazgo - Contradicción entre nulidad automática y declaración judicial:** Art 42 dice "nula de pleno derecho" (automático) pero Art 43 requiere declaración judicial de inaplicabilidad (procesal). Un atacante podría argumentar que una ley inconstitucional sigue vigente hasta sentencia firme.

**Resolución:** Non-issue. Es una distinción jurídica clásica presente en prácticamente todas las constituciones: la nulidad de pleno derecho es el principio, la declaración judicial es el mecanismo procesal para constatarla. Sin procedimiento, cualquiera podría incumplir cualquier ley alegando inconstitucionalidad sin confirmación judicial. El Art 44 ya castiga penalmente a los legisladores que aprobaron leyes declaradas inconstitucionales, lo que disuade el abuso.

---

## Art 56 (Atacantes de la Nación) y Art 57 (Inconsistencia N4/N5)

**Hallazgo Art 56.2 - Loophole: "atacantes de la nación" sin definir.** El término no estaba definido en ningún artículo. Un gobierno hostil podría etiquetar opositores políticos como "atacantes" para despojarlos de todos los derechos fundamentales.

**Hallazgo Art 57.2 - Inconsistencia N4/N5 para supuestos tecnológicos.** La línea "La lista de supuestos de desastre tecnológico puede ampliarse con N4" contradecía la regla general de N5 para modificación de causas en la misma frase.

**Resolución:** Commit 80ab674. (1) Los supuestos concretos de cada causa (incluyendo la definición de "atacante de la nación") se desarrollan por ley con N3 (Art 57). (2) Se añade excepción en Art 6: esta legislación puede ser anulada por el pueblo con N1 (51% del censo), independientemente del N3 legislativo, compensando la asimetría de poder durante estados de excepción. (3) Se elimina la línea de N4 para desastres tecnológicos — con el nuevo N3 para supuestos concretos, la distinción era redundante y confusa. (4) Corrección menor: "a autoridad militar" → "a la autoridad militar" (x2 en Art 56). Argumentación añadida en Parte 2 en dos secciones.

---

## Art 56 (Corrección gramatical)

**Hallazgo: "a autoridad militar"** faltaba el artículo determinado en dos ocurrencias.

**Resolución:** Corregido a "a la autoridad militar" en ambas instancias (commit 80ab674).

---

## Non-issues descartados (lote Arts 1-16)

Los siguientes hallazgos fueron evaluados y descartados como non-issues:

- **Art 1 (l.12)** — "Art 6 es garantía, no mecanismo activo". Sutileza semántica; Art 1 referencia correctamente al artículo que habilita la herramienta.
- **Art 6, hallazgo 3 (l.53)** — DRY: enumera porcentajes ya en Art 2. Legibilidad > DRY estricto en texto constitucional. Art 2 es cláusula pétrea, los porcentajes no cambiarán sin Art 67.
- **Art 6, hallazgo 5 (l.61)** — Falta plazo y procedimiento de anulación. Intencional: Art 6 garantiza el derecho, no impone mecanismo.
- **Art 7, referencia cruzada (l.75)** — Art 7 aislado sin consecuencias institucionales. Deliberadamente delegado a ley ordinaria; proceso de 21-42 años da tiempo para legislar.
- **Art 9, hallazgo 2 (l.93)** — Cooficialidad por N1 como sabotaje. Escenario teórico extremo; la carga administrativa recae sobre el Estado que lo aprueba.
- **Art 10, hallazgo 1 (l.99)** — Formato de configurabilidad no estandarizado. Cosmético; la información está en el artículo, solo en prosa.
- **Art 10, hallazgo 5 (l.113)** — Falta cláusula de Arranque. El rango 0-2 con N4 es razonable desde el día uno.
- **Art 13, hallazgos 1-2 empates (l.143-145)** — Empates en primera y segunda vuelta. Estadísticamente casi imposible con distritos de 100.000+ hab. La ley electoral puede cubrirlo.
- **Art 13, hallazgo 7 (l.161)** — "Más votos" vs "mayor porcentaje". Equivalentes en la práctica con un solo censo.
- **Art 15, hallazgo 3 (l.178)** — Discrepancia argumentación vs texto sobre Arranque. Verificar y corregir parte 2 si necesario, no es cambio al texto constitucional.
- **Art 16, hallazgo 1 (l.188)** — "Si esta situación se repite" sin decir "2" explícitamente. Legible como está.

---

## Non-issues descartados (lote Arts 55-65)

- **Art 55, hallazgo 1** — Artículo largo en un solo párrafo. Denso pero legible; hay artículos más largos.
- **Art 55, hallazgo 4** — No define quién juzga falsedad de declaración. Ya cubierto por Art 52 (responsabilidad penal presidencial) y Art 8 (no inmunidad).
- **Art 56, hallazgo 1** — "Activación automática" sin definir quién constata. Diseño deliberado: la activación es hecho jurídico, no acto discrecional. Controles en la salida (ratificación, Art 62, Art 55). Explicación añadida en parte 2.
- **Art 58, hallazgo 1** — Renovación sin quórum definido. Ya cubierto por Art 23: escaños vacantes cuentan como votos en contra, creando quórum implícito. Explicado en parte 2 (l.394).

---

## Non-issues descartados (lote Arts 16-30)

- **Art 16, hallazgo 5** — "Dinero sobrante" ambiguo. Redacción mejorable pero contexto lo aclara; no es loophole explotable.
- **Art 17, hallazgo 1 DRY** — Lista 1-2-3 duplica Art 5. Legibilidad > DRY en texto constitucional; artículo funciona autocontenido.
- **Art 17, hallazgo 3 coerción** — Voto remoto no garantiza secreto físico. Limitación inherente, no resoluble constitucionalmente. Materia de ley ordinaria.
- **Art 18, hallazgo 3** — Fase intermedia Legislativo sin Presidente. El texto ya dice "sometido a los principios y normas de esta Constitución"; el Legislativo ejerce funciones desde que se constituye.
- **Art 19, hallazgo 2** — Art 19 no dice que Judicial se constituye en Arranque. Cada artículo dice lo suyo (Arts 36-38). No necesita ser autocontenido.
- **Art 20, hallazgo 2** — "Independencia de nombramiento" abstracta. Cada subtítulo lo concreta; no necesita referencias cruzadas aquí.
- **Art 23, hallazgo 3** — "Por semana" no definido. Regulable por reglamento. KISS.
- **Art 24, hallazgo 4** — Empate en segunda vuelta presidencial. Con millones de votos, estadísticamente imposible.
- **Art 25, redacción-2** — "En ningún aspecto" debería explicitar preparación y propuesta. Ya es suficientemente claro.
- **Art 25, loophole-1** — Funciones de alto riesgo delegables como propuesta. Correcto por diseño; propuesta requiere aprobación presidencial.
- **Art 26, hallazgo muerte** — "Muerte" redundante con Art 25. Válido técnicamente pero moverlo solo simplifica, no cierra loophole. Menor.
- **Art 26, hallazgo formato** — "Consenso N2" vs "consenso de Nivel N2". Inconsistencia global conocida, no específica de este artículo.
- **Art 26, referencia Art 43** — Referencia imprecisa pero funcional como marco general de responsabilidad judicial.
- **Art 28, hallazgo 1** — Falta nivel de modificabilidad explícito fuera del Arranque. Art 68 aplica por defecto. Patrón roto pero no explotable.
- **Art 29, hallazgo 1** — Oración larga, falta coma. Cosmético.

---

## Non-issues descartados (lote Arts 30-44)

- **Art 30, hallazgo 5** — "Del periodo" ligeramente ambiguo. Detalle técnico menor; la interpretación razonable es obvia (inflación anual).
- **Art 31, DRY con Art 47** — Solapamiento en "sistema público auditable". Complementarios, no redundantes.
- **Art 31, referencia cruzada faltante** — Art 31 debería referenciar Art 47. Menor; ambos autocontenidos.
- **Art 31, consistencia Art 53** — Tensión con partidas clasificadas. Ya cubierto por Art 47 que reconoce excepción del Art 53.
- **Art 33, inconsistencia "Segunda Instancia"** — Confusión terminológica entre Art 33 y Art 43. Problema más del Art 43, menor.
- **Art 36, redacción 2 "pulgar del pie"** — Estilístico. Chirriante pero funcional.
- **Art 38, falta modificabilidad** — Consecuencia de la redundancia DRY. Se resuelve eliminando/reduciendo Art 38.
- **Art 39, hallazgo 1 asimetría candidatura** — Design choice. La asimetría de coste es intencional por la concentración de poder del Presidente.
- **Art 40, cooldown/estado de excepción** — Ambigüedad menor. Durante estado de excepción la autodestrucción ya está bloqueada (Art 39), el cooldown es irrelevante.
- **Art 41, hallazgo 5 "resoluciones" vs "sentencias"** — Menor. Párrafo introductorio general para abarcar causa 2 (legislación ordinaria).
- **Art 43, consistencia "Segunda Instancia (Casación)"** — Etiqueta confusa pero sustancia clara. Menor.

---

## Non-issues descartados (lote Arts 43-61)

- **Art 43, redacción-2 párrafo denso** — Denso pero funcional. Comparable al Art 55 (mismo criterio).
- **Art 44, hallazgo 5 título engañoso** — Cosmético. Contenido claro pese al título impreciso.
- **Art 44, hallazgo 6 legisladores fuera del cargo** — Principio general del derecho penal: responsabilidad no se extingue por cese. No necesita explicitación.
- **Art 45, redacción párrafo monolítico** — Denso pero funcional. Mismo criterio que Art 55/43.
- **Art 46, redacción 2.b** — Mejorable pero comprensible. No es loophole.
- **Art 47, solapamiento Art 31** — Complementarios, no redundantes (ya marcado desde Art 31).
- **Art 48, ambigüedad "sistemas establecidos"** — Intencional. Legislación ordinaria puede ampliar.
- **Art 52, redacción doble condicional** — Estilístico. Funcional como está.
- **Art 53, redacción "procedimiento ordinario"** — Referencia implícita razonable. Arts 30-31 cubren presupuesto.
- **Art 61, referencia cruzada incompleta** — Paráfrasis + referencia redundante pero no peligroso.

---

## Non-issues descartados (lote Arts 62-72)

- **Art 63, paréntesis integrables** — Estilístico. Ejemplos entre paréntesis menores.
- **Art 65, redundancia DRY** — Resumen útil para legibilidad. No es loophole.
- **Art 66, clausula 4 paréntesis** — "Este procedimiento" se entiende por contexto. Menor.
- **Art 68, hallazgo 1 vías alternativas** — Se entiende del contexto. Menor.
- **Art 68, hallazgo 3 plazo entrada en vigor** — "Desde la aprobación" suficientemente claro. Menor.
- **Art 71, hallazgo 1 DRY Art 70** — Redundancia intencional como refuerzo en texto constitucional.
- **Art 72, hallazgo 2 lista orientativa** — Paréntesis con lista orientativa. Menor.

---

## Art 2 (N3 = "66%" vs dos tercios)

**Hallazgo:** N3 se definía como "mayoría de dos tercios: 66%". Dos tercios es 66,67%, no 66%. Ambigüedad entre la etiqueta y el porcentaje.

**Resolución:** El porcentaje redondo (66%) manda. Eliminadas todas las etiquetas descriptivas del Art 2 (mayoría simple, mayoría reforzada, etc.), dejando solo "Nivel NX: Y%". Los nombres clásicos se documentan en la parte 2 como referencia. Corregidas dos menciones a "dos tercios" en la parte 2 que referían a N3.

---

## Art 3 (Derechos de ciudadano en el extranjero)

**Hallazgo:** La cláusula "conservan todos los derechos establecidos para personas" podría interpretarse como que los derechos de ciudadano sí dependen de ubicación.

**Resolución:** Non-issue. La ciudadanía se define por nacionalidad, no por ubicación. La cláusula existe para resolver que "persona" depende de presencia física; los derechos de ciudadano no necesitan cláusula equivalente porque la ciudadanía no depende de ubicación. El argumento contrario requiere una lectura *a silentio* que ignora la definición explícita de ciudadano.

---

## Art 4 hallazgo 1 (Contradicción "18 años")

**Hallazgo:** "Todo ciudadano mayor de 18 años" se contradice con la edad vigente si el Legislativo la sube a 23 con N5.

**Resolución:** Reformulado: "Todo ciudadano que alcance la edad de voto tiene derecho al sufragio." Segundo párrafo: "La edad de voto es de 18 años por defecto." El derecho es genérico; el valor concreto es un default modificable.

---

## Art 4 hallazgo 2 (N5 sin especificar quién)

**Hallazgo:** "mediante consenso de Nivel N5" no especificaba si era legislativo, referéndum, o ambos.

**Resolución:** Añadido "del Poder Legislativo" explícitamente.

---

## Art 5 (Ambigüedad auditabilidad)

**Hallazgo:** "como mínimo, por ciudadanos con derecho a voto" era ambiguo — podía leerse como "al menos un ciudadano" en vez de "cualquier ciudadano".

**Resolución:** Cambiado a "auditable por cualquier ciudadano con derecho a voto". Alineado con la formulación del Art 17.

---

## Art 6 hallazgo 1 (Censo vs votos emitidos)

**Hallazgo:** "apoyo del 51% de los ciudadanos con derecho a voto" no usaba la palabra "censo", inconsistente con Art 46 y la regla del Art 2.

**Resolución:** Cambiado a "del censo nacional" (x2, incluyendo la excepción de estados de excepción). Alineado con la terminología del Art 46 y la regla del Art 2/3.

---

## Art 6 hallazgo 4 (Aprobar con nivel alto para hacer inanulable)

**Hallazgo:** Un atacante legislativo podría aprobar leyes con N4 cuando solo necesitaba N1, haciendo la anulación popular prácticamente imposible (requeriría 75% del censo).

**Resolución:** Cambiado "nivel de consenso de dicha decisión" → "nivel de consenso mínimo requerido para dicha decisión". La anulación siempre corresponde al nivel mínimo constitucional, no al nivel con el que se votó efectivamente.

---

## Non-issues descartados (lote continuación revisión 1-a-1)

- **Art 7, loophole 1 "territorio" sin definir** — Non-issue por diseño. El proceso dura 21-42 años, la ley puede exigir requisitos (ejército, autosuficiencia, viabilidad económica) que un barrio no cumple. La delegación a ley ordinaria ya está en el artículo.
- **Art 7, loophole 3 cooldown y procesos simultáneos** — Non-issue. El proceso de 21 años mínimo ya es el cooldown. Lanzar docenas de procesos simultáneos requiere territorios reales que cumplan requisitos legales durante décadas.
- **Art 8, weaponización procesal** — Non-issue. Materia de ley procesal (filtros, costas, denuncia falsa). Art 8 ya prevé tramitación preferente. Aclaración añadida en parte 2.
- **Art 8, suspensión durante proceso** — Non-issue. Presunción de inocencia: ejerce hasta condena firme. Art 29 lo confirma para ministros. Ley ordinaria desarrolla. Aclaración añadida en parte 2.
- **Art 11, frase final redundante** — Non-issue. La cláusula pétrea protege contra reforma constitucional; la frase del Art 11 contra ley ordinaria. Capas distintas.
- **Art 11, título ambiguo** — Non-issue. La primera frase dice "del Poder Legislativo".
- **Art 12, asimetría 2 años censado** — Design choice documentado en parte 2. La revocación es más vulnerable a migración masiva coordinada que la elección. Los 2 años son mitigación activa.
- **Art 12, migración censal en elecciones** — Mitigado por los 2 años en revocación, candidatos locales, AOCD y coste de mover miles de personas. Documentado en parte 2.
- **Art 12, cooldown tras revocación fallida** — Non-issue. Un cooldown sería explotable: el representante en el poder podría iniciar una recogida, fallar aposta y activar el cooldown como escudo. El filtro natural es que recoger firmas del 10% repetidamente sin causa real genera rechazo social.
- **Art 12, conflicto entre plazos** — Non-issue. Las 2 semanas (proceso de revocación) y los 7 días (nueva elección) son eventos consecutivos, no solapados.

---

## Art 1/11 ("cargos electos" → "representantes legislativos")

**Hallazgo:** Art 1 decía "la revocación de cargos electos" pero Art 11 solo cubre legisladores. El Presidente es cargo electo y no es revocable por el pueblo.

**Resolución:** Cambiado en Art 1 a "la revocación de representantes legislativos".

---

## Art 12 (Ambigüedad "convocatoria")

**Hallazgo:** "Desde convocatoria hasta resultado" era ambiguo — ¿desde inicio de recogida de firmas o desde que se alcanzan?

**Resolución:** Cambiado a "desde la convocatoria formal de la votación hasta el resultado". Corregidos artículos gramaticales faltantes.

---

## Art 13 (Plazo entre vueltas, participación, repetición)

**Hallazgo 1 - Boicot indefinido:** Non-issue. En distritos pequeños, un boicot sostenido es expresión democrática. El escaño cuenta como voto en contra (Art 23), lo cual es autocorrector.

**Hallazgo 2 - Sin plazo entre primera y segunda vuelta:** Vacío explotable.

**Hallazgo 3 - Ambigüedad sobre qué se repite:** No quedaba claro si se repetía todo o solo la vuelta fallida.

**Hallazgo 4 - Falta Arranque:** Non-issue / design choice. N6 para parámetros electorales es coherente con su importancia.

**Hallazgo 5 - Redacción:** Non-issue menor.

**Resolución hallazgos 2 y 3:** Añadido plazo máximo de 7 días entre primera y segunda vuelta. Aclarado que si falla la participación en cualquier vuelta, se repite la elección completa desde la primera vuelta. Añadido el nuevo parámetro (7 días entre vueltas) a la cláusula de configurabilidad.

---

## Art 14 (Granularidad de datos y "cuando sea posible")

**Hallazgo 1 - Granularidad de datos manipulable:** Non-issue. Demasiado complejo para nivel constitucional; regulado por legislación ordinaria.

**Hallazgo 2 - "Cuando sea posible" como válvula de escape.**

**Resolución hallazgo 2:** Invertida la carga de la prueba. Antes: "la delimitación debe respetar fronteras... cuando sea posible." Ahora: "la delimitación respeta fronteras... Solo puede cruzar estas fronteras cuando sea estrictamente necesario para cumplir las restricciones de población establecidas en este artículo."

---

## Art 15 (Referéndum sin umbral, comisión, rechazo)

**Hallazgo 1 - Referéndum sin umbral.** No especificaba nivel de consenso ni participación mínima.

**Resolución:** Cambiado de referéndum popular a ratificación por el Poder Legislativo con N1. El AOCD con especificaciones públicas y auditables ya es el control principal; el Legislativo ratifica la ejecución correcta. El conflicto de interés se mitiga porque el algoritmo constitucionalizado deja poco margen de manipulación.

**Hallazgo 2 - Comisión técnica sin definir.** Non-issue. La comisión es un órgano operativo delegado a ley ordinaria. El control real está en el algoritmo público + la ratificación legislativa.

**Hallazgo 3 - Rechazo sin fallback.**

**Resolución:** Añadido mecanismo de dos intentos: si el Legislativo rechaza, la comisión puede ejecutar una nueva propuesta con datos corregidos o actualizados. Si la segunda propuesta también es rechazada, se mantiene la distribución vigente hasta la siguiente actualización programada.

---

## Art 16 (Financiación electoral — todos non-issues)

- **Hallazgo 2 - Financiación ilegal por candidato:** Non-issue. El anti-DoS ya existe: segunda convocatoria procede independientemente. El DoS máximo es 7 días y el atacante pierde todo el dinero (expropiado). La concentración por candidato es dinero tirado si la elección se anula.
- **Hallazgo 3 - Donación secreta inauditable:** Non-issue / delegado a diseño de sistema. La Constitución establece la garantía ("1 donación, verificable, secreto en destino"), la implementación técnica queda delegada. Con criptografía ZK se puede verificar sin revelar destinatario — mencionable en parte 2 pero no prescribible constitucionalmente.
- **Hallazgo 4 - Falta Arranque:** Design choice. N6 para financiación electoral incluso durante Arranque es más defensivo. Intencional.
- **Hallazgo 6 - Sanción solo si se identifica:** Non-issue. La anulación de la elección ya es el castigo principal. La sanción económica es disuasorio adicional, no la defensa principal.
- **Art 17 - Obligación de habilitar voto remoto:** Non-issue. "Puede" es deliberado — derecho, no obligación inmediata. Art 5 ya delega detalles tecnológicos al Arranque. Implementación por ley ordinaria.
- **Art 18, hallazgo 1 - Quién declara excepción Natural durante Transición:** Non-issue / design choice. Sin instituciones democráticas, solo operan activaciones automáticas. Darle función declarativa al régimen anterior sería darle más poder.
- **Art 18, hallazgo 2 - Estado de excepción como bloqueo de Transición:** Riesgo aceptado. Sin instituciones democráticas no hay controles institucionales. Art 55 sanciona declaración falsa con 10 años. La garantía real es la vigilancia ciudadana.
- **Art 19 - Extensión indefinida del Arranque:** Non-issue. Durante el Arranque ya hay Legislativo y Presidente en funciones. La ciudadanía recién movilizada por la Constitución nueva es el momento de mayor vigilancia social. Un abuso de estados de excepción sucesivos generaría reacción social inmediata.

---

## Non-issues descartados (limpieza final pre-Art 20)

- **Art 25, redacción decisiones militares** — Menor, la argumentación en parte 2 lo justifica.
- **Art 26, ambigüedad gramatical "mediante N2"** — Lectura forzada. "A o B mediante X" aplica X a B.
- **Art 30, hallazgo 2 consistencia N1 presupuesto** — Art 23 define N1 como default. No necesita explicitación.
- **Art 30, hallazgo 3 primer año fiscal** — Cubierto por Transición/Arranque.
- **Art 39, estado excepción como escudo** — Legislativo revoca con N1 y activa autodestrucción en misma sesión. Secuencia fluida.
- **Art 40, Art 41 durante cooldown** — Riesgo bajo. Tribunal Supremo filtra abusos.
- **Art 42, actos administrativos sin procedimiento** — Se impugnan por vía judicial ordinaria. Art 43 es específico para leyes.
- **Art 46, hallazgo 4b verificación firmas** — Materia de ley ordinaria.
- **Art 46, hallazgo 4c paréntesis confuso** — Redacción menor, no loophole.
- **Art 47, solapamiento Art 31** — Complementarios, no redundantes.
- **Art 50, hallazgos 3-4 menores** — El propio agente los califica de menores.
- **Art 52, prescripción acusación** — No-prescripción de operaciones militares secretas es estándar en derecho internacional.
- **Art 61, DRY Art 39** — Redundancia intencional por legibilidad (agrupa los 6 límites).
- **Art 62, ambigüedad "derechos aplicables"** — Intención clara: recurrir por violación de derechos vigentes o restricción excesiva.
- **Art 20, referencia Art 53** — Non-issue. El presupuesto militar es parte de la financiación del Ejecutivo. La referencia es correcta e intencional. El Legislativo no necesita protección financiera especial porque él mismo aprueba el presupuesto general.
- **Art 21, mandato 4 años sin protección** — Non-issue. N4 ya es el default por Art 68. No necesita cláusula explícita.
- **Art 23, hallazgo 1 "7 leyes" sin modificabilidad** — Non-issue. Misma razón: N4 por defecto vía Art 68.
- **Art 23, hallazgo 2 leyes ómnibus** — Non-issue. Definir "ley" en la Constitución viola KISS. Control de constitucionalidad y anulación popular son salvaguardas suficientes.
- **Art 25, parálisis ejecutiva temporal** — Non-issue. Feature, no bug. Unos días sin decisiones no es crisis. Delegación temporal abriría vector de ataque del Vicepresidente.

---

## Art 25 (Referencia Art 29)

**Hallazgo:** "conforme al artículo 29" sugería que el Art 29 regulaba la delegación, cuando regula el nombramiento.

**Resolución:** Cambiado a "en los ministros nombrados conforme al artículo 29".

---

## Art 43 (Anglicismo "pack")

**Hallazgo:** "pack" usado 2 veces como anglicismo.

**Resolución:** Cambiado a "paquete" (x2).

---

## Arts 26-27 (Sucesión e Incapacidad Presidencial)

**Art 26.1 - Vicepresidente sin umbral:** Non-issue. El juez es el filtro, la declaración es recurrible por cualquier ciudadano, y el juez paga si se revoca. Contrapesos suficientes.

**Art 26.2 - Recuperación antes de elecciones:** Vacío real.
**Resolución:** Añadido al Art 27: "Si el Presidente recupera su capacidad antes de que se celebren nuevas elecciones presidenciales, retoma el cargo de forma automática."

**Art 26.3 - Efecto suspensivo:** Non-issue. Efecto inmediato es correcto — un Presidente en coma no puede esperar semanas de apelación. Documentado en parte 2.

**Art 27.1 - Referencia Art 44 incorrecta:** El Art 44 no cubría incapacidad revocada.
**Resolución:** Añadido cuarto bloque al Art 44: "Responsabilidad penal de jueces por declaración de incapacidad presidencial revocada". La referencia del Art 27 al Art 44 ahora es correcta.

**Art 27.2 - Muerte como causa de incapacidad:** Absurdo exigir declaración judicial para muerte evidente.
**Resolución:** "Muerte" movida del Art 27 al Art 26 como activador directo de sucesión ("Si el Presidente fallece, dimite o es declarado incapaz"). Art 27 reservado para coma y deterioro cognitivo.

**Art 27.3 - Declaración revocada vs recuperación:** Non-issue. Tras elecciones, el nuevo Presidente es legítimo. La elección democrática es definitiva.

**Art 27.4 - N1 para restitución:** Non-issue (eliminado). El mecanismo de restitución N1 se eliminó. Tras elecciones, no hay restitución. El remedio contra declaración errónea es la sanción al juez, no anular una elección.

---

## Arts 28-30

- **Art 28, organismos equivalentes:** Non-issue. El Presidente controla la estructura; el Legislativo controla el presupuesto. La proliferación de entidades menores es materia de ley ordinaria.
- **Art 29, "condena" sin "firme":** Corregido a "sentencia penal firme". Sin "firme", un juez corrupto podría cesar automáticamente a un ministro con condena en primera instancia que será revocada en apelación. Explicación añadida en parte 2.
- **Art 29, inhabilitación en artículo de ministerios:** Pendiente. Debe moverse al Título I y protegerse a N5. Requiere renumeración.
- **Art 30, prórrogas indefinidas:** Non-issue. La prórroga con inflación es el fallback seguro. La parálisis legislativa se desbloquea con autodestrucción mutua (Art 39).
- **Art 24, hallazgos 2-3 redacción segunda vuelta** — Menores descartados.
- **Art 24, hallazgo 5 bucle infinito participación** — Non-issue. Mismo diseño que Art 13; presidente saliente sigue en funciones.

---

## Art 24 (Configurabilidad de parámetros)

**Hallazgo:** Parámetros electorales presidenciales (51%, 30%, 14 días, 5 años, 2 mandatos, 1 cooldown) sin cláusula de protección. El Art 13 (equivalente distrital) los protege a N6.

**Resolución:** Añadida cláusula de configurabilidad a N6, coherente con el Art 13. Lista completa de parámetros incluida.

---

## Art 69 (Corrección mecánica)

**Hallazgo:** "Un tercio (33%)" inconsistente con el principio de usar porcentajes redondos (Art 2). Un tercio es 33,33%, no 33%.

**Resolución:** Cambiado a "El 33% de los miembros del Poder Legislativo". Consistente con la eliminación de etiquetas descriptivas del Art 2.
- **Art 10, hallazgo 2 mecanismo distrital** — Non-issue. El Art 10 ya dice "según procedimientos establecidos por ley ordinaria". El *qué* (el distrito puede hacer override) es explícito; el *cómo* está delegado.

---

## Art 10 hallazgo 3 (Suplentes agotados)

**Hallazgo:** No se definía qué pasa cuando un distrito queda sin representante ni suplentes. Escaños vacantes cuentan como votos en contra (Art 23), creando incentivo perverso.

**Resolución:** Añadida frase al Art 10: "Cuando un distrito queda sin representante ni suplentes disponibles, se convoca nueva elección conforme al artículo 13."

---

## Art 10 DRY (Enumeración ejemplificativa)

**Hallazgo:** El último párrafo enumeraba ejemplos de prevalencia distrital ("como la configuración de suplentes... o la revocación...") que ya constaban en sus propios artículos. Frágil ante cambios futuros.

**Resolución:** Eliminada la enumeración. Queda: "únicamente en los casos establecidos explícitamente en esta Constitución." Los Arts 10, 11 y 12 ya son explícitos sobre la prevalencia distrital en cada caso.
