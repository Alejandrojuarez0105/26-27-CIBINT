# Cómo preparar una entrega en GitHub

Las entregas publicables se trabajan en un *fork* personal y se proponen al repositorio de la asignatura mediante un *pull request*. No es necesario tener permisos de escritura sobre el repositorio original.

## 1. Crear el *fork*

1. Abrir `https://github.com/hector-ae21/26-27-CIBINT`.
2. Pulsar **Fork**.
3. Mantener el nombre `26-27-CIBINT` y crear el *fork* en la cuenta personal.
4. Clonar el *fork*, no el repositorio del profesor.

```bash
git clone https://github.com/TU-USUARIO/26-27-CIBINT.git
cd 26-27-CIBINT
git remote add upstream https://github.com/hector-ae21/26-27-CIBINT.git
```

Sustituye `TU-USUARIO` por tu nombre de usuario de GitHub.

## 2. Actualizar antes de trabajar

```bash
git switch main
git fetch upstream
git merge --ff-only upstream/main
git push origin main
```

Si el último comando falla porque has realizado cambios propios en `main`, no fuerces el envío. Consulta al profesor.

## 3. Crear una rama para la actividad

Cada actividad se prepara en una rama nueva:

```bash
git switch -c entrega/apellidoNombre/A01
```

Sustituye `apellidoNombre` y `A01` por tu carpeta y el código real indicado en el enunciado.

## 4. Crear la estructura

```text
entregas/
└── apellidoNombre/
    └── A01/
        ├── README.md
        └── otros archivos solicitados
```

- El nombre personal sigue el formato descrito en [entregas/README.md](entregas/README.md).
- El código de actividad debe coincidir exactamente con el enunciado.
- No modifiques archivos generales, plantillas, actividades ni carpetas de otras personas.
- El `README.md` de la entrega sirve como punto de entrada y debe enlazar cualquier archivo adicional.

## 5. Revisar y guardar los cambios

Antes de registrar una entrega:

```bash
git status
git diff
```

Comprueba que solo aparecen archivos dentro de tu carpeta. Después:

```bash
git add entregas/apellidoNombre/A01
git commit -m "Entrega A01 - Apellido Nombre"
git push -u origin entrega/apellidoNombre/A01
```

No utilices `git add .` si no has comprobado antes todos los cambios.

## 6. Abrir el *pull request*

Desde GitHub, abre un *pull request* desde la rama de tu *fork* hacia:

```text
hector-ae21/26-27-CIBINT:main
```

Título:

```text
[A01] Apellido Nombre
```

Completa la plantilla, revisa la pestaña **Files changed** y confirma que no aparecen cambios ajenos a tu entrega.

## Correcciones

Si el *pull request* sigue abierto, realiza las correcciones en la misma rama y vuelve a enviarla. GitHub actualizará la propuesta automáticamente.

```bash
git add entregas/apellidoNombre/A01
git commit -m "Corrige A01 según revisión"
git push
```

No abras otro *pull request* para la misma entrega salvo que el profesor lo indique.

## Entregas no publicables

No deben subirse al *fork* ni al *pull request*:

- datos personales no anonimizados;
- credenciales, secretos o tokens;
- evidencias de acceso restringido;
- informes marcados para entrega privada;
- cualquier contenido que el enunciado derive al Campus Virtual.

Si descubres que ya has publicado algo sensible, no lo redistribuyas ni intentes ocultarlo con un nuevo *commit*. Avisa inmediatamente al profesor por un canal privado para coordinar su retirada del historial.

## Problemas habituales

| Problema | Qué hacer |
|---|---|
| He modificado un archivo general | No abras el *pull request*; revierte ese cambio en tu rama |
| Mi *fork* está desactualizado | Actualiza `main` desde `upstream` y vuelve a crear la rama |
| El código de la actividad no coincide | Renombra la carpeta antes de entregar |
| Aparecen archivos de otra persona | Retíralos de la rama y revisa **Files changed** |
| El contenido no puede ser público | Detén la entrega y utiliza el canal indicado en el enunciado |
| Tengo un conflicto de integración | No fuerces la resolución; pregunta en Q&A o consulta al profesor |
