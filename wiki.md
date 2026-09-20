# 📚 Wiki — La Legión del Mal

> Centro de conocimiento oficial de la Legión. Si llegaste aquí sin ser reclutado, corre.

---

## 🗺️ Índice

1. [Manual del recluta](#-manual-del-recluta)
2. [Estructura del repositorio](#-estructura-del-repositorio)
3. [Flujo de trabajo con Git](#-flujo-de-trabajo-con-git)
4. [Convenciones](#-convenciones)
5. [Manejo de secretos](#-manejo-de-secretos)
6. [Gestión de misiones](#-gestión-de-misiones)
7. [Catálogo de miembros](#-catálogo-de-miembros)
8. [Glosario](#-glosario)
9. [FAQ](#-faq)

---

## 🐣 Manual del recluta

Bienvenido a la Legión. Antes de tocar nada, lee esto:

1. Lee el `README.md` completo. Sí, completo. Incluidos los emojis.
2. Configura tu identidad villana en Git:
   ```bash
   git config user.name "Tu Alias Malvado"
   git config user.email "tu_alias@legion-del-mal.local"
   ```
3. **Jamás trabajes directo sobre `main`.** Tu rama debe seguir el formato:
   ```
   feature/<tu-alias>-<descripcion-corta>
   ```
4. Antes de pedir merge, asegúrate de que tu rama no rompe nada.
5. Si dudas, pregunta. Un mal commit cuesta más que una buena pregunta.

---

## 📁 Estructura del repositorio

Detalle de cada carpeta y qué va (y qué **NO**) en ella.

### `planes/`
Operaciones estratégicas aprobadas por el Consejo. Cada plan debe incluir:
- 🎯 Objetivo
- 🛠️ Recursos necesarios
- 🦸 Héroes involucrados (y cómo esquivarlos)
- 🏃 Plan de escape (regla #1: **obligatorio**)

### `miembros/`
Fichas individuales. Formato: `miembros/<alias>.md`. Una ficha por villano.

### `guaridas/`
Estado de las bases. Coordenadas clasificadas. Aquí solo va información pública:
capacidad, estado actual, responsable asignado.

### `inteligencia/`
Expedientes sobre héroes enemigos. Cada expediente debe contener:
fortalezas, debilidades, ubicación conocida y patrones de comportamiento.

### `misiones.yaml`
Registro global de operaciones activas y pasadas. Fuente única de verdad.

### `codigos-lanzamiento.env`
⚠️ **NUNCA subir al repositorio.** Ver [Manejo de secretos](#-manejo-de-secretos).

### `log/` y `logs/`
Registros de operaciones. Diferencia intencional: revisa cuál usar con tu líder.

---

## 🧬 Flujo de trabajo con Git

### Ramas

| Tipo de rama        | Prefijo        | Ejemplo                              |
|---------------------|----------------|--------------------------------------|
| Nueva funcionalidad | `feature/`     | `feature/luthor-clonar-krypton`      |
| Corrección          | `fix/`         | `fix/doom-arreglar-armadura`         |
| Documentación       | `docs/`        | `docs/wiki-estructura`               |
| Experimento         | `experiment/`  | `experiment/magneto-imanes-v2`       |

### Commits

Formato: `<tipo>: <descripción breve en minúsculas>`

Tipos válidos:
- `feat` — nueva funcionalidad
- `fix` — corrección de bug
- `docs` — solo documentación
- `refactor` — cambio que no añade ni arregla funcionalidad
- `chore` — tareas menores (limpiar, mover archivos)

### Pull Requests

- Título claro y **sin monólogos** (regla #5: Joker ya fue amonestado dos veces).
- Descripción con: qué cambia, por qué, cómo probarlo.
- Al menos **una revisión del Consejo** antes de merge a `main`.

### Conflictos

Cuando ocurran (y ocurrirán):
1. No entres en pánico.
2. Coordina con el autor de la otra rama.
3. Resuelve y documenta en el commit qué decidiste y por qué.

---

## 📝 Convenciones

- **Nombres de archivo:** `kebab-case.md` para documentación.
- **Idiomas:** docs en español, comentarios de código en inglés.
- **Emojis:** permitidos y alentados en docs internas. Con moderación.
- **Tamaños:** idealmente menos de 300 líneas por archivo de doc.
- **Encoding:** UTF-8. Siempre.

---

## 🔒 Manejo de secretos

### La regla de oro

**Los códigos de lanzamiento, llaves de acceso y credenciales JAMÁS van al repo.**

El que los suba será entregado a Batman. ☠️

### Cómo gestionarlos

1. Crea tu archivo local basado en la plantilla:
   ```bash
   cp .env.template codigos-lanzamiento.env
   ```
2. Verifica que `.gitignore` ignora tu archivo:
   ```
   codigos-lanzamiento.env
   *.env
   .env
   ```
3. Si por error subes un secreto:
   - 🚫 No comentes nada en público.
   - 📡 Avisa al Director de Tecnología (Brainiac) por canal seguro.
   - 🔄 Se rota la clave **inmediatamente**.

### Antes de cada commit

```bash
git status
git diff --staged
```

Si ves algo raro en `codigos-lanzamiento.env` u otro `.env`, **aborta**.

---

## 🎯 Gestión de misiones

Estados posibles (ver `misiones.yaml`):

- 🟢 **Operativa** — en ejecución
- 🟡 **En desarrollo** — planificándose
- 🔴 **En planificación** — idea inicial
- ⚫ **Abortada** — retirada
- ✅ **Completada** — objetivo cumplido

Cada misión debe tener:

- 🆔 ID único (`MISION-001`, `MISION-002`, ...)
- 🦹 Líder responsable
- 🛠️ Recursos asignados
- 📅 Fecha objetivo

---

## 🦹 Catálogo de miembros

Ver carpeta `miembros/` para fichas individuales.

| Alias           | Especialidad                       | Rango           |
|-----------------|------------------------------------|-----------------|
| Lex Luthor      | Estrategia y financiamiento        | 🥇 Líder supremo |
| Magneto         | Militar / magnetismo               | 🥈 Segundo      |
| Mystique        | Infiltración                       | 🥉 Jefa         |
| Brainiac        | Tecnología                         | ⚙️ Director     |
| Joker           | Caos y distracción                 | Operativo       |
| Doctor Doom     | Armamento / magia                   | Operativo       |
| Loki            | Engaño / diplomacia hostil          | Operativo       |
| Catwoman        | Robo de alta precisión              | Operativo       |
| Venom           | Fuerza bruta                        | Operativo       |
| Green Goblin    | Tecnología / tácticas de terror     | Operativo       |

---

## 📖 Glosario

- **PR** — Pull Request. Como pedirle permiso al Consejo.
- **Merge** — Unir tu rama con `main`. Solo después de aprobado.
- **Rebase** — Reescribir historia. Úsalo con cuidado y sin force-push sin permiso.
- **Conflict** — Dos villanos querían cambiar lo mismo. Decide uno y documenta.
- **Force push** — Solo permitido con autorización explícita de Brainiac.
- **Cherry-pick** — Tomar un commit específico de otra rama y traerlo a la tuya.
- **Stash** — Guardar cambios temporalmente sin commit. Útil para cambiar de rama rápido.

---

## ❓ FAQ

**¿Puedo hacer commit directo a `main`?**
No. Jamás. Ni siquiera para una sola línea. Ni siquiera para arreglar un typo.

**¿Por qué mi PR fue rechazado?**
Lee los comentarios. Si no entiendes, pregunta. Si sigues sin entender, pregunta más fuerte.

**Olvidé agregar un archivo al último commit. ¿Qué hago?**
```bash
git add archivo-olvidado.md
git commit --amend --no-edit
```
Solo si aún no hiciste push. Si ya hiciste push, abre un PR nuevo.

**¿Cómo cambio el nombre de mi rama después de subirla?**
```bash
git branch -m nuevo-nombre
git push origin :nombre-viejo
git push origin nuevo-nombre
```

**¿Cómo actualizo mi rama con los últimos cambios de `main`?**
```bash
git checkout main
git pull
git checkout mi-rama
git merge main
```
o, alternativamente, `git rebase main` (más limpio, pero reescribe historia).

**¿Por qué mis commits aparecen como otro autor?**
Tu `git config user.email` no coincide con tu identidad registrada. Arréglalo antes del próximo commit.

---

_Mantenedor: Lex Luthor · Última actualización: 2026-09-19_
