
- Establecer una norma: Ningún artículo con numero inferior (inferior en este caso es de mayor magnitud) puede sobreescribir un artículo con numero superior. Inversamente, un artículo con numero superior puede sobreescribir un artículo con numero inferior.
    - Ejemplo arbitrario: El Artículo 10 no puede sobreescribir el Artículo 5, pero el Artículo 5 puede sobreescribir el Artículo 10.

- Artículo 5 (antes 4), condiciones de poder votar... Quiza es mejor decir derecho a voto? Y a veré.

- Artículo 6 (antes 5): Lo del poder distrital ya vere como lo explico de manera más clara y si puede ser que sea coherente apareciendo solo 1 vez. Quiźa hará falta un articulo nuevo de alto número.

- Artículo 10 (antes 9): Pensar en como generalizarlo a cualquier pais, no hardcodear los 95.000 y 120.000 habitantes.

- ~~Revisar claramente que ciertas condiciones solo aplican a CIUDADANOS, otras a RESIDENTES, otras a ambos, y otras a CIUDADANO CON DERECHO A VOTO. Y que no haya contradicciones entre artículos.~~ HECHO: Art 4 (Sujetos Constitucionales) define persona/ciudadano/votante. Estandarizado en toda la constitución.

- Acordarse de hacer ilegal la propaganda electoral durante X dias de las elecciones, si se detecta, aunque sea de manera indirecta o apologia a ella, multa/castigo.

- ~~Artículo 19 (antes 18), quien comanda mientras se hace todo eso si es que hay que esperar 14 dias?~~ HECHO

- Artículo 22 (antes 20, funciones del ejecutivo): Declaración de estados de excepción (con aprobación legislativa) // no siempre... con que sean muy claros ya vale. HAY QUE decir que declararlo sin que sea verdad es un delito. Dirección de los ministerios: puede delegar sus funciones excepto aquellas prohibidas en esta constitución (mecanismos para entrar en guerra etc).

- Artículo 30 (antes 28), revisar: sin perjuicio de la anulación popular establecida en los artículos 49 a 52 (antes 47 a 50).

- ~~Asegurar consistencia de limites de nivel consenso del proceso de arranque y de funcionamiento normal.~~ HECHO: Auditoría completa de niveles de protección realizada. Establecido sistema de 3 capas (pétrea / parámetros / Art 50 default). Nueva regla anti-bypass en Art 50.

- ~~Analizar consistencia de nombramiento de niveles y mini menciones a los respectivos % a lo largo de la constitucion.~~ HECHO: Eliminados todos los paréntesis redundantes con porcentajes (3a). Art 3 es fuente única.

- Añadir limite de leyes aprobadas semanales por legislativo. 14. La idea es que los jueces tengan un tiempecito diario para revisar constitucionalidad de 2 leyes en caso de que se aprueben y alguien apele casacion. No se si es demasiado o no y deberia ser 7 leyes semanales, pero hoy en dia y con IA creo que 14 es realista. Esto hay que tenerlo en cuenta para la parte de las explicaciones en el libro.

- ~~Artículo 46 (antes 44), ciudadanos capaces de contradecir procesos judiciales tambien??? Claro, porque no, pero requisitos mas altos. Como el 30% como grupo y las firmas del 51%.~~ HECHO: Añadido ámbito ordinario al Art 44 con 30% grupo iniciador y firmas del nivel de consenso máximo de las leyes involucradas. Arts 42 y 43 actualizados con responsabilidad/sanciones ordinarias de menor gravedad. Título IV renombrado a "Control de Legitimidad Judicial".

- ~~Artículo 57 (antes 55), revisar que cosas si pueden reformarse y cuales no segun este articulo. Quiza haya que simplemente decirlo en cada articulo si puede reformarse o no y ya. El artículo 6 (antes 5) gran parte de él se dedica a eso, hay que ver si es consistente con el resto de arts.~~ HECHO: Sistema de protección formalizado. Art 50 es el default. Cada artículo con parámetros especifica su nivel. Regla anti-bypass cierra loophole.

- Discrepancia en traición: El juicio sobre si se aplica esta pena corresponde al Tribunal Supremo, previa acusación por al menos el 40% del Legislativo. (REVISAR: en Part 1 Art 67 (antes 65) dice "Legislativo puede aprobar mediante consenso de Nivel N1 (51%)" — discrepancia 40% vs 51%, y Tribunal Supremo vs Legislativo)

- ~~REVISAR EN QUE CASOS CONTAMOS EL CENSO Y CUALES DERECHO A VOTO Y VER SI SOMOS CONSISTENTES CON LA ARGUMENTACIÓN.~~ HECHO: Censo = censo electoral definido en Art 4. Ámbitos (nacional/distrital) explícitos en cada artículo.

- Revisar que esto se cumple siempre: Judicial < Legislativo < Popular. Dejamos al legislativo al final anular al judicial con un consenso alto? N5 o algo?

---

# ANÁLISIS ARQUITECTÓNICO (estilo software)

## ~~1. TERMINOLOGÍA INCONSISTENTE~~ HECHO

Art 4 (Sujetos Constitucionales) define persona/ciudadano/ciudadano con derecho a voto/pueblo/censo. Estandarizado en toda la constitución.

## ~~2. "CENSO" vs "CIUDADANOS CON DERECHO A VOTO"~~ HECHO

Censo = censo electoral definido en Art 4. Ámbitos (nacional/distrital) explícitos en cada artículo.

## ~~3. VIOLACIONES DRY~~ HECHO

- 3a: Eliminados todos los paréntesis redundantes con porcentajes.
- 3b: Eliminadas referencias redundantes al procedimiento de cláusulas pétreas de Arts 1, 5, 6, 18, 53. Art 46 es fuente única con 11 cláusulas pétreas.
- 3c: Decidido NO generalizar Arranque como default — cada artículo mantiene su regla propia porque los patrones varían.

## ~~4. ARTÍCULOS QUE DEBERÍAN DIVIDIRSE~~ HECHO

- ~~Art 42: proceso de constitucionalidad + responsabilidad penal legisladores + responsabilidad penal jueces + sanciones = 4-5 responsabilidades en 1 artículo (viola SRP).~~ HECHO: Dividido en Arts 41 (Proceso), 42 (Responsabilidad Penal), 43 (Sanciones).
- ~~Art 56: 3 tipos de excepción + configurabilidad + arranque + niveles modificación = monolítico.~~ HECHO: Dividido en Arts 53 (Tipos) y 54 (Configurabilidad).
- ~~Art 24: sucesión + incapacidad + causas + apelación + recuperación + sucesión secundaria = largo tras adiciones.~~ HECHO: Dividido en Arts 24 (Sucesión) y 25 (Incapacidad).

## ~~5. ARTÍCULOS QUE PODRÍAN UNIRSE~~ HECHO

- ~~Art 27 (1 frase) → párrafo del Art 25.~~ HECHO: Integrado en Art 26 (Autodestrucción Mutua - Mecanismo).
- ~~Arts 39-40 (Arranque) → Art 40 dice "cuando termina 39, termina".~~ HECHO: Unificado en Art 39.
- ~~Arts 43-45 (Anulación Popular) → 3 cortos = 1 proceso.~~ HECHO: Unificado en Art 44.
- ~~Arts 47-49 (Reforma Cláusulas Pétreas) → 3 cortos = 1 proceso.~~ HECHO: Unificado en Art 46.

## 6. CONTRADICCIONES / LOOPHOLES

- ~~Arts 5 y 17 usan "procedimiento de cláusulas pétreas" pero NO están en la lista de Art 46.~~ HECHO: Ahora 11 cláusulas pétreas. Referencias redundantes eliminadas.
- ~~Art 24: "muerte" como causa de incapacidad es absurdo — la muerte activa sucesión directamente, no requiere declaración judicial.~~ DESCARTADO: Especificar muerte como causa es explícito y correcto — no deja ambigüedad sobre qué activa la sucesión.
- ~~Art 44: 51% de TODOS los ciudadanos con derecho a voto deben FIRMAR — umbral prácticamente imposible, hace inoperativa la anulación popular.~~ DESCARTADO: Es un último recurso deliberadamente alto (N1 del censo). Los incentivos penales a jueces ya hacen el trabajo pesado; esto es la válvula de seguridad final. Con firma digital será más viable. N1 equilibra entre accesibilidad y evitar caos.
- ~~Art 15 vs Arts 43-45: dos mecanismos de anulación distintos (legislativa vs judicial) sin relación clara entre sí.~~ DESCARTADO: Art 15 garantiza el DERECHO a que existan mecanismos de anulación popular (pétrea, no se puede prohibir). Art 44 DEFINE uno específico (anulación de decisiones judiciales sobre constitucionalidad). No hay contradicción: uno protege la existencia, otro implementa un caso concreto.

## ~~7. ABSTRACCIÓN FALTANTE: "sistema público auditable"~~ DESCARTADO

~~Usado en 7+ artículos pero nunca definido. Merece definición propia (¿Título I?).~~ DESCARTADO: "Sistema público auditable" es suficientemente claro — un sistema donde cualquier ciudadano puede revisar que los procesos se han ejecutado conforme a lo establecido. No requiere definición formal adicional.


---

notas 2:

- ~~la recomendacion de menor de edad no votar en art5, mmm... quiza no haga ni falta, se sobre entiende que ese numbero es importatne al requrerir consenso N6.~~ HECHO: eliminado "pero no recomendables" de Part 1.

- ~~PENDIENTE: Inconsistencia N6 vs procedimiento de cláusulas pétreas. Art 3 define N6 = 95%. Pero el procedimiento de cláusulas pétreas (Arts 47-49) es mucho más: referéndum con N5 + 75% participación + doble votación + 2 años reflexión + 21 años cooldown. Los Arts 1, 5, 6 y 18 dicen "procedimiento de cláusulas pétreas: consenso N6" lo cual es engañoso — N6 es solo una de dos vías para CONVOCAR el referéndum.~~ PARCIALMENTE HECHO: Las frases engañosas de Arts 1, 5, 6, 18 han sido eliminadas. Art 46 es fuente única. Queda pendiente: aclarar en Art 3 o Part 2 que N6 ≠ procedimiento pétreo completo.
