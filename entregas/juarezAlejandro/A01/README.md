# A01 · Del dato a la inteligencia

## Estudiante

- Nombre: Alejandro Emmanuel Juárez Hernández
- Carpeta personal: [juarezAlejandro](/entregas/juarezAlejandro/)

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría | Justificación |
|---|---|---|
| A | Dato | Reproduce un único hecho tal como lo declara la organización, sin combinarlo ni interpretarlo (C03).
| B | Dato | Hecho aislado, tomado literalmente de la comunicación (C13).
| C | Información | Cruza dos hechos de la misma cronología (C05: la vía de entrada fue el procesamiento de datasets; C08: la cadena de suministro de software se declara no comprometida) para delimitar dónde está el problema y dónde no.
| D | Ninguna de las tres | Salta de "no se ha encontrado evidencia de manipulación" (C07) a la certeza "son seguros". Es una inferencia no sostenida — confunde ausencia de evidencia con evidencia de ausencia — no una valoración de inteligencia justificada.
| E | Inteligencia | Formula una valoración probabilística ("es probable") que combina información y la liga directamente a una decisión del comité (rotar credenciales → O3; mantener observación → O7).

### 1.2 Dato, información e inteligencia propios

| Capa | Formulación | Filas usadas | Qué limitación tiene |
|---|---|---|---|
| Dato | El acceso escaló a nivel de nodo, con recolección de credenciales de nube y de clúster, además de movimiento lateral por varios clústeres internos durante un fin de semana. | C06 | Es la versión de un único actor (la propia plataforma), sin verificación independiente (`corroboracion: una_parte`).
| Información | Las credenciales alcanzadas por el atacante incluyen las credenciales internas de servicio (S06), que la plataforma usa para autenticar sus propios servicios entre sí y contra su nube, no las credenciales de usuario u organización (S05), que no aparecen mencionadas como afectadas. | C04, C06, C11 (cronología) + S05, S06 (superficies) | Sigue dependiendo del relato de HF; no dice si otras credenciales (S05) fueron también revisadas o simplemente no mencionadas.
| Inteligencia | Dado que la cadena de suministro de software está verificada como no comprometida (C08) y no hay evidencia de manipulación en artefactos públicos (C07), pero sí hubo acceso a credenciales internas de servicio (C04, C06), el riesgo más probable para nosotros no está en los modelos ya descargados sino en credenciales propias que podamos tener expuestas frente a la plataforma — lo que apunta a priorizar O3 (rotar credenciales) y O5 (revisar credenciales propias publicadas) sobre O2 (congelar descargas). | C04, C06, C07, C08 | Asume que el relato de HF es completo; la propia HF deja abierto si afectó a datos de socios/clientes (C09), lo que podría cambiar el análisis.

---

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

| Componente | ¿Está? | Qué dice, o qué falta |
|---|---|---|
| Destinatario | Impreciso | El mensaje va dirigido a mi ("dime"), pero no dice quién usará el resultado: el contexto revela que hay un comité a las 13:00, pero eso no está en la petición formal. |
| Decisión | Falta | No dice qué se va a decidir. No menciona que hay opciones concretas (O1–O7) sobre la mesa ni qué tipo de acción está en juego. |
| Objeto | Impreciso | "Lo de la brecha de Hugging Face" no concreta qué aspecto interesa: ¿los modelos descargados?, ¿las credenciales propias?, ¿la relación contractual con HF? |
| Horizonte | Falta | No fija plazo ni corte temporal en la propia petición. El plazo de las 13:00 se conoce por el contexto de la situación, no por el mensaje del responsable. |
| Alcance | Impreciso | "Todo lo que haya" es lo opuesto a un alcance acotado: no dice si cubre solo a la empresa, también a clientes, a otras plataformas, etc. |
| Exclusiones | Falta | No excluye nada: ni otras plataformas, ni acciones sobre la infraestructura de HF, ni líneas de investigación fuera de lo permitido. |
| Producto | Impreciso | "Dime" sugiere algo breve, probablemente oral o muy corto, pero no especifica formato ni estructura. |

### 2.2 Componentes completados

- **Destinatario:** el responsable directo, que debe presentar una recomendación ante el comité de las 13:00 del 20 de julio de 2026.
- **Decisión:** qué opciones de las planteadas al comité (O1–O7) activar respecto a la exposición de la empresa frente al incidente.
- **Objeto:** si el incidente de seguridad de Hugging Face declarado el 16 de julio de 2026 (C03) afecta a los modelos/datasets que la empresa ha descargado de esa plataforma, o a las credenciales propias que la empresa usa contra ella.
- **Horizonte:** con la información pública disponible hasta las 09:00 del 20 de julio de 2026, con entrega antes de las 13:00 del mismo día.
- **Alcance:** limitado a la relación de la empresa con Hugging Face como plataforma: artefactos descargados de HF y credenciales/tokens propios usados para acceder a ella.
- **Exclusiones:** no cubre otras plataformas de IA, no incluye ninguna interacción con la infraestructura o cuentas de Hugging Face, y no cubre investigación de personas.
- **Producto:** una nota breve para el comité con lo que se puede afirmar, el nivel de confianza, la recomendación de opciones a activar y una limitación explícita.

### 2.3 Requerimiento en una frase

> Determinar, antes de las 13:00 del 20 de julio de 2026 y a partir de la información pública disponible sobre el incidente de Hugging Face, si este afecta a los artefactos descargados por la empresa o a sus credenciales propias frente a la plataforma, para que el responsable recomiende al comité qué opciones (O1–O7) activar, sin interactuar en ningún momento con la infraestructura de Hugging Face.

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta | Te ayuda a decidir |
|---:|---|---|
| 1 | ¿Hay evidencia de que los artefactos (modelos y datasets) ya descargados por la empresa pudieran haber sido manipulados como parte del incidente? | O1 (seguir descargando con normalidad) y O4 (verificar integridad de lo ya descargado) |
| 2 | ¿Qué tipo de credenciales alcanzó el atacante (internas de servicio de HF, o también de usuario/organización), y eso expone credenciales propias de la empresa usadas contra la plataforma? | O3 (rotar credenciales) y O5 (revisar credenciales propias publicadas)
| 3 | ¿Sigue siendo prudente mantener activas las descargas automatizadas mientras la evaluación de HF sobre datos de socios y clientes continúa abierta (C09)? | O2 (congelar descargas automatizadas) y O7 (mantener observación y fijar punto de revisión) |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase |
|---|---|---|---|---|
| Dirección y planificación | El requerimiento formulado en el paso 2. | Priorizar las preguntas de 2.4 y decidir qué fuentes consultar antes de las 13:00: la declaración oficial de HF (F01) y la cobertura y antecedentes fechados antes del 20 de julio (F05, F07, F08). | Un plan de obtención: qué documentos revisar y en qué orden para responder las tres preguntas priorizadas. | Obtención |
| Obtención | El plan de obtención de la fase anterior. | Recopilar el contenido de la declaración oficial (C03–C13) y contrastarlo con la cobertura de prensa (C14) y los antecedentes de 2024 (C01, C02), sin interactuar con ninguna infraestructura ni servicio. | El conjunto de hechos recopilados, con su nivel de corroboración (`una_parte` / `prensa`) ya identificado. | Procesamiento |
| Procesamiento | Los hechos recopilados en Obtención. | Cruzar cada hecho con la tabla de superficies para ubicarlo (p. ej. C04, C06, C11 → S06 credenciales internas de servicio; C05 → S03 procesamiento de datasets; C07, C08 → S01, S02, S08, S09 artefactos públicos y cadena de software) y descartar lo que la prensa repite sin aportar verificación propia (C14). | Un mapa hecho–superficie que separa lo verificado por HF de lo simplemente repetido, y lo que afecta a artefactos públicos de lo que afecta a infraestructura y credenciales internas. | Análisis y producción |
| Análisis y producción | El mapa hecho–superficie de Procesamiento. | Responder las preguntas priorizadas de 2.4, fijar el nivel de confianza según la corroboración disponible y formular la recomendación de opciones (O1–O7). | La nota para el comité (paso 4): qué se puede afirmar, confianza, recomendación y limitación. | Difusión |
| Difusión | La nota para el comité. | Presentar la nota al responsable antes de las 13:00, dejando constancia explícita de la limitación (la evaluación de HF sobre datos de socios y clientes sigue abierta, C09). | La decisión del comité sobre qué opciones activar (por ejemplo, aprobar O3 y O5, y mantener O7). | Retroalimentación |
| Retroalimentación | La decisión del comité y el hecho de que C09 deja abierta la evaluación sobre terceros. | Fijar el punto de revisión que exige O7: qué nueva información pública habría que vigilar para reevaluar el caso. | Un nuevo requerimiento, acotado a seguir la evolución del incidente hasta el próximo punto de revisión. | **Retorna a Dirección y planificación**, para replantear el requerimiento cuando aparezca información pública nueva. |

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

- El 16 de julio de 2026, Hugging Face declaró públicamente haber detectado y respondido a un acceso no autorizado a su infraestructura de producción (C03).
- Según su propia declaración, el acceso alcanzó un conjunto limitado de datasets internos y varias credenciales usadas por sus servicios (C04) — concretamente credenciales internas de servicio (S06), no credenciales de usuario u organización (S05) (C04, C06, C11).
- El vector de entrada fue el procesamiento de un conjunto de datos malicioso, que explotó dos vías de ejecución de código (C05; S03).
- La actividad escaló a nivel de nodo, con recolección de credenciales de nube/clúster y movimiento lateral por varios clústeres internos durante un fin de semana (C06; S10).
- Hugging Face no encontró evidencia de manipulación de modelos, datasets o espacios públicos (C07; S01, S02, S04), y declara verificada como no comprometida su cadena de suministro de software — imágenes de contenedor y paquetes — (C08; S08, S09).
- La evaluación sobre si se vieron afectados datos de socios o clientes sigue **abierta** en el momento de la publicación (C09).
- No se ha identificado al responsable ni se conoce el modelo que operó el ataque (C13).
- Todo lo anterior proviene de una única parte — la propia Hugging Face — sin verificación independiente (`corroboracion: una_parte` en C01–C13); la cobertura de prensa (C14) repite la declaración sin aportar verificación propia.

**Nivel de confianza y justificación**

**Media.** La declaración de Hugging Face es detallada, internamente coherente (fechas, vector de entrada, alcance técnico concreto) y proviene de la organización directamente afectada, que tiene incentivos regulatorios y reputacionales para ser precisa en lo que reconoce. Pero sigue siendo la versión de una sola parte (`una_parte` en toda la cronología, salvo C14 que solo repite sin corroborar), no hay verificación independiente todavía, y la propia Hugging Face deja explícitamente abierta la incógnita sobre terceros (C09). Eso impide una confianza alta; la ausencia de contradicciones o desmentidos impide bajarla de nivel.

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
|---|---|---|
| O1 · Seguir descargando con normalidad | Sí, con vigilancia | HF declara sin evidencia de manipulación en artefactos públicos y con la cadena de software verificada como no comprometida (C07, C08). Frenar del todo sería desproporcionado frente a esa evidencia; se combina con O4 y O7 en vez de aplicarse a ciegas. |
| O2 · Congelar las descargas automatizadas | No | El vector de entrada declarado está en el procesamiento interno de datasets de la propia plataforma (C05; S03), no en los artefactos públicos que la empresa descarga. Congelar todo sin evidencia de riesgo en lo que consumimos sería una medida desproporcionada al dato disponible. |
| O3 · Rotar las credenciales de la plataforma | Sí | Aunque HF solo confirma afectación de sus credenciales internas de servicio (S06), no de las nuestras (S05), es una medida barata, reversible y proporcionada dado el antecedente de 2024 de exposición de secretos (C01, C02). |
| O4 · Verificar la integridad de los artefactos ya descargados | Sí | Es una comprobación propia, de bajo coste, que no depende de confiar ciegamente en la declaración de HF (C07, C08); refuerza la confianza media en vez de sustituirla. |
| O5 · Revisar qué credenciales propias están publicadas fuera de la empresa | Sí | Buena práctica de higiene de credenciales que no depende de que se confirme afectación directa; reduce la superficie de exposición propia frente al patrón ya visto en 2024 (C01, C02). |
| O6 · Avisar a los clientes del servicio | No, por ahora | La evaluación de HF sobre afectación a socios/clientes sigue abierta (C09) y no hay ninguna indicación de que nuestros artefactos o servicio estén comprometidos. Avisar ahora sería desproporcionado y podría generar alarma sin base; se revisa en el punto de seguimiento (O7). |
| O7 · Mantener la observación y fijar un punto de revisión | Sí | Dado que C09 sigue abierta y no se identifica al responsable (C13), es la medida proporcionada mientras se espera más información pública, y conecta con la fase de Retroalimentación del paso 3. |

**Limitación**

No sabemos si la evaluación de Hugging Face sobre datos de socios y clientes (C09) nos incluye como usuarios de la plataforma, ni si nuestras propias credenciales de usuario/organización (S05) llegaron a estar expuestas — HF solo confirma afectación de sus credenciales internas de servicio (S06). Si esa pregunta se resolviera en sentido afirmativo, la recomendación de no activar O2 y O6 tendría que revisarse.

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
|---|---|---|
| El acceso no autorizado a la infraestructura de producción de Hugging Face fue detectado y comunicado el 16 de julio de 2026. | Hecho | Es lo que la propia organización declaró públicamente, con fecha e identificador verificable (C03). |
| El vector de entrada afectó a credenciales internas de servicio (S06) y no a credenciales de usuario u organización (S05). | Inferencia | Se deriva de que C04, C06 y C11 solo mencionan credenciales internas de servicio; ninguna fila de la cronología inicial menciona S05 como afectada, pero eso es un razonamiento por ausencia de mención, no una declaración explícita de que S05 esté a salvo. |
| Nuestras propias credenciales frente a la plataforma podrían estar expuestas, por lo que conviene rotarlas. | Supuesto | Asumimos que la empresa usa credenciales propias contra HF (razonable, dado que descarga modelos) y que el patrón de exposición de 2024 (C01, C02) podría repetirse, pero ninguna fila de la cronología inicial confirma que las credenciales de esta empresa en particular estén comprometidas. |

---

## 5. Revisa

### 5.1 Revisión de conclusiones

| Conclusión previa | ¿Cambia o se confirma? | Hecho que lo provoca | Nueva formulación |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

### 5.2 Efecto sobre la recomendación

<!-- ¿Cambiarías tu recomendación al comité? Sí o no, y por qué. -->

### 5.3 Conclusión sobre la retroalimentación

<!-- Una frase. -->

---

## Fuentes

| Identificador | Fuente | URL | Fecha de consulta |
|---|---|---|---|
| F01 | | | AAAA-MM-DD |

<!-- Solo las que hayas usado de verdad. Si añades fuentes propias, numéralas F13, F14… -->

## Decisiones y limitaciones

<!-- Cualquier decisión de método o límite que quieras dejar por escrito. -->

## Colaboración

<!-- Si trabajaste algún aspecto con otra persona, indica qué parte fue individual. -->

## Uso de inteligencia artificial

> **Apartado obligatorio.** Si no lo completas, tu entrega está incompleta y no se califica.

| | |
|---|---|
| **Herramienta utilizada** | <!-- Nombre, o «No se ha utilizado ninguna» --> |
| **Para qué la usaste** | <!-- Corrección de texto, búsqueda de ideas, generación de código, redacción… --> |
| **En qué fase intervino** | <!-- Paso 1, paso 3, revisión final… --> |

## Comprobación

- [ ] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
- [ ] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [ ] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [ ] No he interactuado con ninguna infraestructura ni servicio del caso.
- [ ] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [ ] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [ ] Solo he modificado `entregas/apellidoNombre/A01/`.
