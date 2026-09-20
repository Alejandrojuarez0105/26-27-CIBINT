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
| Destinatario | | |
| Decisión | | |
| Objeto | | |
| Horizonte | | |
| Alcance | | |
| Exclusiones | | |
| Producto | | |

### 2.2 Componentes completados

<!-- Contenido de los componentes que faltaban o que estaban sin concretar. -->

### 2.3 Requerimiento en una frase

>

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta | Te ayuda a decidir |
|---:|---|---|
| 1 | | |
| 2 | | |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase |
|---|---|---|---|---|
| Dirección y planificación | | | | |
| Obtención | | | | |
| Procesamiento | | | | |
| Análisis y producción | | | | |
| Difusión | | | | |
| Retroalimentación | | | | |

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

<!-- Con sus identificadores. -->

**Nivel de confianza y justificación**

<!-- Baja, media o alta, y qué la sostiene en ese nivel y no en otro. -->

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
|---|---|---|
| | | |

**Limitación**

<!-- Qué te falta saber y cómo condiciona lo anterior. -->

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
|---|---|---|
| | | |
| | | |
| | | |

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
