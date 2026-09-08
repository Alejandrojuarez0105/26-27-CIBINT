# Entregas

Esta carpeta recibe las actividades publicables mediante *pull request*. Cada estudiante trabaja en un *fork* personal y modifica únicamente su propia carpeta.

## Nombre de la carpeta personal

Formato:

```text
apellidoNombre
```

Ejemplos:

| Nombre | Carpeta |
|---|---|
| María García | `garciaMaria` |
| Daniel Pérez Gómez | `perezDaniel` |
| María García, si ya existe `garciaMaria` | `garciaLopezMaria` |

Reglas:

- primer apellido seguido del nombre;
- sin espacios, tildes, guiones ni caracteres especiales;
- apellido en minúscula y nombre iniciado en mayúscula;
- se añade el segundo apellido solo para resolver coincidencias;
- la misma carpeta se utiliza durante todo el curso.

## Una carpeta por actividad

```text
entregas/
└── garciaMaria/
    ├── A01/
    │   └── README.md
    ├── A02/
    │   ├── README.md
    │   └── diagrama.puml
    └── CODIGO-INDICADO/
        └── archivos solicitados
```

El nombre de la actividad debe coincidir exactamente con el código de su enunciado. No se agrupan varias actividades en una misma carpeta.

## Qué puede modificarse

| Ruta | Permiso del estudiante |
|---|---|
| `entregas/apellidoNombre/**` | Sí, dentro de su propia carpeta |
| `entregas/otraPersona/**` | No |
| Cualquier otra ruta del repositorio | No |

Un *pull request* que contenga cambios fuera de la carpeta personal deberá corregirse antes de su revisión.

## Contenido mínimo

Cada entrega tendrá un `README.md` con:

- identificación de la actividad;
- respuesta o enlace a los archivos solicitados;
- fuentes y fecha de consulta cuando corresponda;
- decisiones o limitaciones relevantes;
- declaración de colaboración y uso de inteligencia artificial exigida por el enunciado.

La [plantilla de entrega](../plantillas/README-entrega.md) sirve como punto de partida. El enunciado de la actividad siempre prevalece sobre la plantilla general.

## Información publicable

El repositorio es público. Solo se admite información ficticia, reservada para documentación, abiertamente publicable o correctamente anonimizada.

No se suben:

- datos personales innecesarios;
- credenciales, secretos, tokens o claves;
- volcados, filtraciones o evidencias de acceso restringido;
- capturas que expongan identificadores o sesiones;
- informes que el enunciado derive al Campus Virtual.

## Flujo de entrega

1. Actualizar el *fork* desde el repositorio original.
2. Crear una rama para una única actividad.
3. Añadir o modificar solo `entregas/apellidoNombre/CODIGO/`.
4. Comprobar todos los archivos y datos antes de publicar.
5. Abrir el *pull request* con el título solicitado.
6. Mantener la misma rama si se piden correcciones.
