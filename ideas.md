
- Establecer una norma: Ningún artículo con numero inferior (inferior en este caso es de mayor magnitud) puede sobreescribir un artículo con numero superior. Inversamente, un artículo con numero superior puede sobreescribir un artículo con numero inferior.
    - Ejemplo arbitrario: El Artículo 10 no puede sobreescribir el Artículo 5, pero el Artículo 5 puede sobreescribir el Artículo 10.

- Artículo 5 (antes 4), condiciones de poder votar... Quiza es mejor decir derecho a voto? Y a veré.

- Artículo 6 (antes 5): Lo del poder distrital ya vere como lo explico de manera más clara y si puede ser que sea coherente apareciendo solo 1 vez. Quiźa hará falta un articulo nuevo de alto número.

- Artículo 10 (antes 9): Pensar en como generalizarlo a cualquier pais, no hardcodear los 95.000 y 120.000 habitantes.

- Revisar claramente que ciertas condiciones solo aplican a CIUDADANOS, otras a RESIDENTES, otras a ambos, y otras a CIUDADANO CON DERECHO A VOTO. Y que no haya contradicciones entre artículos.

- Acordarse de hacer ilegal la propaganda electoral durante X dias de las elecciones, si se detecta, aunque sea de manera indirecta o apologia a ella, multa/castigo.

- Artículo 19 (antes 18), quien comanda mientras se hace todo eso si es que hay que esperar 14 dias?

- Artículo 22 (antes 20, funciones del ejecutivo): Declaración de estados de excepción (con aprobación legislativa) // no siempre... con que sean muy claros ya vale. HAY QUE decir que declararlo sin que sea verdad es un delito. Dirección de los ministerios: puede delegar sus funciones excepto aquellas prohibidas en esta constitución (mecanismos para entrar en guerra etc).

- Artículo 30 (antes 28), revisar: sin perjuicio de la anulación popular establecida en los artículos 49 a 52 (antes 47 a 50).

- Asegurar consistencia de limites de nivel consenso del proceso de arranque y de funcionamiento normal.

- Analizar consistencia de nombramiento de niveles y mini menciones a los respectivos % a lo largo de la constitucion.

- Añadir limite de leyes aprobadas semanales por legislativo. 14. La idea es que los jueces tengan un tiempecito diario para revisar constitucionalidad de 2 leyes en caso de que se aprueben y alguien apele casacion. No se si es demasiado o no y deberia ser 7 leyes semanales, pero hoy en dia y con IA creo que 14 es realista. Esto hay que tenerlo en cuenta para la parte de las explicaciones en el libro.

- Artículo 46 (antes 44), ciudadanos capaces de contradecir procesos judiciales tambien??? Claro, porque no, pero requisitos mas altos. Como el 30% como grupo y las firmas del 51%.

- Artículo 57 (antes 55), revisar que cosas si pueden reformarse y cuales no segun este articulo. Quiza haya que simplemente decirlo en cada articulo si puede reformarse o no y ya. El artículo 6 (antes 5) gran parte de él se dedica a eso, hay que ver si es consistente con el resto de arts.

- Discrepancia en traición: El juicio sobre si se aplica esta pena corresponde al Tribunal Supremo, previa acusación por al menos el 40% del Legislativo. (REVISAR: en Part 1 Art 67 (antes 65) dice "Legislativo puede aprobar mediante consenso de Nivel N1 (51%)" — discrepancia 40% vs 51%, y Tribunal Supremo vs Legislativo)

- REVISAR EN QUE CASOS CONTAMOS EL CENSO Y CUALES DERECHO A VOTO Y VER SI SOMOS CONSISTENTES CON LA ARGUMENTACIÓN.

- Revisar que esto se cumple siempre: Judicial < Legislativo < Popular. Dejamos al legislativo al final anular al judicial con un consenso alto? N5 o algo?

---

# ANÁLISIS ARQUITECTÓNICO (estilo software)

## 1. TERMINOLOGÍA INCONSISTENTE — el problema más grande

4 formas distintas de referirse al mismo concepto:
- "ciudadanos con derecho a voto" (Art 14, 23, 41, 42, 43, 46)
- "ciudadanos que cumplan con las condiciones de poder votar" (Art 5)
- "persona física con derecho a voto" (Art 12)
- "ciudadano" a secas (Art 8, 12, 20, 52, 62, 70, 71)

Problema: Art 8 dice "cualquier ciudadano" sin especificar "con derecho a voto" — un menor de 15 años podría iniciar revocación. Art 52 define derechos para "todo ciudadano" pero un turista debería tener derecho a expresión e integridad personal; Art 60 sí usa "persona". Propuesta: definir sujetos constitucionales (persona, ciudadano, ciudadano con derecho a voto) en artículo temprano y usar siempre el término correcto.

## 2. "CENSO" vs "CIUDADANOS CON DERECHO A VOTO"

"Censo" aparece en Art 8, 9, 21, 46, 49, 50. "Ciudadanos con derecho a voto" en Art 14, 42, 43, 46. Art 3 distingue las bases pero nunca se define si "censo" = censo electoral (solo votantes) o censo general (todos los habitantes). Bug semántico.

## 3. VIOLACIONES DRY

3a. Redundancia N1-N6 con paréntesis: desde que existe Art 3, escribir "(mayoría simple, 51%)" es redundante. Estandarizar a forma corta.
3b. Frase "procedimiento de reforma de cláusulas pétreas establecido en los artículos 46-48" repetida en Art 1, 4, 5, 17. Simplificar a "conforme al artículo 45".
3c. Patrón "N6 normal, N1 en Arranque" repetido en Art 8, 27, 34, 53, 55. Podría ser regla general en Art 38.

## 4. ARTÍCULOS QUE DEBERÍAN DIVIDIRSE

- Art 41: proceso de constitucionalidad + responsabilidad penal legisladores + responsabilidad penal jueces + sanciones = 4-5 responsabilidades en 1 artículo (viola SRP).
- Art 55: 3 tipos de excepción + configurabilidad + arranque + niveles modificación = monolítico.
- Art 23: sucesión + incapacidad + causas + apelación + recuperación + sucesión secundaria = largo tras adiciones.

## 5. ARTÍCULOS QUE PODRÍAN UNIRSE

- Art 26 (1 frase) → párrafo del Art 24 o 25.
- Arts 38-39 (Arranque) → Art 39 dice "cuando termina 38, termina".
- Arts 42-44 (Anulación Popular) → 3 cortos = 1 proceso.
- Arts 46-48 (Reforma Cláusulas Pétreas) → 3 cortos = 1 proceso.

## 6. CONTRADICCIONES / LOOPHOLES

- Arts 5 y 17 usan "procedimiento de cláusulas pétreas" pero NO están en la lista de Art 45.
- Art 23: "muerte" como causa de incapacidad es absurdo — la muerte activa sucesión directamente, no requiere declaración judicial.
- Art 43: 51% de TODOS los ciudadanos con derecho a voto deben FIRMAR — umbral prácticamente imposible, hace inoperativa la anulación popular.
- Art 14 vs Arts 42-44: dos mecanismos de anulación distintos (legislativa vs judicial) sin relación clara entre sí.

## 7. ABSTRACCIÓN FALTANTE: "sistema público auditable"

Usado en 7+ artículos pero nunca definido. Merece definición propia (¿Título I?).


---

notas 2:

- la recomendacion de menor de edad no votar en art5, mmm... quiza no haga ni falta, se sobre entiende que ese numbero es importatne al requrerir consenso N6. (HECHO: eliminado "pero no recomendables" de Part 1)

- PENDIENTE: Inconsistencia N6 vs procedimiento de cláusulas pétreas. Art 3 define N6 = 95%. Pero el procedimiento de cláusulas pétreas (Arts 47-49) es mucho más: referéndum con N5 + 75% participación + doble votación + 2 años reflexión + 21 años cooldown. Los Arts 1, 5, 6 y 18 dicen "procedimiento de cláusulas pétreas: consenso N6" lo cual es engañoso — N6 es solo una de dos vías para CONVOCAR el referéndum. Hay que decidir cómo aclarar esto.
