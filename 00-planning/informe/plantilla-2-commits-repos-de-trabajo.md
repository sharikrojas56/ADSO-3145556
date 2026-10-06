# Informe 2 — Commits en los repositorios en los que trabajaste

**Periodo:** del 11 de agosto al 30 de septiembre de 2026 (hora Colombia, UTC-5)

**Repositorio principal de la ficha:** https://github.com/code-sena/ADSO-3145556

| Campo                             | Valor                                                           |
| --------------------------------- | --------------------------------------------------------------- |
| Aprendiz                          | Sharik Dayanna Rojas Ibarra                                     |
| Usuario de GitHub                 | sharikrojas56                                                   |
| Ficha                             | ADSO-3145556                                                    |
| Proyecto (equipo)                 | School Guardian                                                 |
| Correo(s) con el que haces commit | [sharikrojas.sena@gmail.com](mailto:sharikrojas.sena@gmail.com) |
| Fecha de elaboración              | 06/10/2026                                                      |

<details>

<summary><strong>Instrucciones — léelas y borra este bloque antes de entregar</strong></summary>

**Qué reporta este informe.** Todos los commits que hiciste en **los demás repositorios en los que trabajaste**: tu repositorio personal o de perfil, tu fork de `ADSO-3145556`, repositorios de otros equipos, `design-software` y cualquier otro. **No repitas aquí** los repositorios de tu equipo (`-docs`, `-api`, `-app`, `-db`, `-portal`, `-worker`): esos van en el Informe 1.

**Tipos de repositorio** (úsalos en la columna *Tipo*): `Personal` · `Fork de la ficha` · `Otro equipo` · `design-software` · `Otro`.

**Paso 1 — descubre en qué repositorios trabajaste.** Elige una de las dos formas (reemplaza `TU_USUARIO`):

* *Desde el navegador:* abre

  `https://github.com/search?q=author%3ATU_USUARIO+author-date%3A2026-08-01..2026-08-30&type=commits`

* *Desde la terminal* (requiere `gh`, la CLI de GitHub, con sesión iniciada):

```bash
gh search commits --author=TU_USUARIO --author-date=2026-08-01..2026-08-30 --limit 1000 \
  --json repository --jq '.[] | .repository.fullName' | sort | uniq -c
```

Te devuelve cada repositorio con el número de commits que encontró.

> **Advertencia:** la búsqueda de GitHub solo revisa la **rama por defecto** de cada repositorio. Si trabajaste en otra rama (`dev`, `docs`, `feature/…`), esos commits no aparecen. Por eso el Paso 2 es obligatorio, y además debes acordarte de los repositorios donde trabajaste solo en ramas secundarias.

> Los commits de los días 1 y 30 pueden cambiar de lado por la zona horaria: verifícalos con el Paso 2.

**Paso 2 — obtén los commits de cada repositorio.** Para cada repositorio, desde una terminal **Git Bash**, dentro de tu clon:

```bash
# Ajusta solo estas tres líneas
AUTOR="tu-correo@ejemplo.com"
DESDE="2026-08-01T00:00:00-05:00"
HASTA="2026-08-30T23:59:59-05:00"

URL=$(git remote get-url origin | sed -E 's#^git@github.com:#https://github.com/#; s#\.git$##')

git fetch --all --prune -q

git log --all --no-merges --author="$AUTOR" --since="$DESDE" --until="$HASTA" \
  --date=iso --reverse \
  --pretty=tformat:"| [%h]($URL/commit/%h) | %ad | %s |" | tee commits.md | wc -l
```

* Se imprime **el total de commits**. Las filas ya vienen en formato de tabla y quedan en `commits.md`.
* `--all` incluye **todas las ramas**.
* `--no-merges` deja por fuera los commits de fusión.
* Si el mensaje de un commit contiene el carácter `|`, reemplázalo por `/` para no romper la tabla.

**Repositorios privados.** Si un repositorio es privado, indica en *Visibilidad* si el usuario `ariel5253` tiene acceso.

**Qué cuenta como commit tuyo.** Solo los hechos con tu cuenta. Abre un commit en GitHub: si aparece tu foto de perfil, está vinculado.

**Copia el bloque de la sección 2 una vez por cada repositorio.** Si en el periodo trabajaste en un solo repositorio, deja un solo bloque.

</details>

## 1. Resumen de repositorios

| # | Repositorio                               | Enlace                                                     | Tipo | Visibilidad | Commits |
| - | ----------------------------------------- | ---------------------------------------------------------- | ---- | ----------- | ------: |
| 1 | `school-guardian-project/GuardianEscolar` | https://github.com/school-guardian-project/GuardianEscolar | Otro | Público     |  **12** |
|   | **Total**                                 |                                                            |      |             |  **12** |

## 2. Detalle por repositorio

### 2.1 `school-guardian-project/GuardianEscolar`

* **Enlace del repositorio:** https://github.com/school-guardian-project/GuardianEscolar
* **Tipo:** Otro
* **Visibilidad:** Público
* **Total de commits en el periodo:** **12**
* **Qué hice (2 a 3 líneas):** Trabajé en funcionalidades y correcciones del proyecto Guardian Escolar, incluyendo configuración de idioma y tema, validaciones del formulario de inicio de sesión y componentes relacionados con GPS. También desarrollé y ajusté la comunicación TCP, el procesamiento de paquetes GPS y el seguimiento de ubicación en tiempo real.

| Commit ID | Fecha y hora | Mensaje                                                                         |
| --------- | ------------ | ------------------------------------------------------------------------------- |
| `0f73b39` | 2026-08-11   | `feat: implementation of language and theme switching`                          |
| `62890a7` | 2026-09-03   | `feat: new class example`                                                       |
| `bc65a1f` | 2026-09-11   | `fix: correction of inputs`                                                     |
| `f85209d` | 2026-09-14   | `feat: implement GPS TCP communication and packet parsing`                      |
| `0269fd2` | 2026-09-14   | `feat: add form and login validation`                                           |
| `2af8996` | 2026-09-15   | `feat: change pom.xml`                                                          |
| `0442f31` | 2026-09-19   | `feat(gps-backend): add VT03F TCP server, packet parser and location endpoints` |
| `d8c524b` | 2026-09-22   | `fix(gps-backend): separate GPS timestamp from server reception time`           |
| `5399496` | 2026-09-23   | `fix(gps-backend): correction of the 0x31 ACKs`                                 |
| `450ca00` | 2026-09-23   | `refactor(gps-backend): reorganize TCP project structure`                       |
| `7e85f46` | 2026-09-24   | `feat: implement GPS live location tracking`                                    |
| `e6e4ca3` | 2026-09-30   | `test<gps>: add temporary screen to diagnose MapView on iPhone`                 |

## 3. Verificación del aprendiz

* [X ] Todos los commits listados los hice con mi cuenta (aparece mi foto de perfil en GitHub).
* [ X] Incluí los commits de **todas las ramas** de cada repositorio, no solo de la rama por defecto.
* [ X] Todos los commits caen entre el **11 de agosto y el 30 de septiembre de 2026** (hora Colombia).
* [X ] No repetí repositorios del Informe 1 (los de mi equipo).
* [X ] Cada enlace de repositorio y de commit abre en GitHub.
* [X ] El total de cada repositorio coincide con el número de filas de su tabla.
* [ X] En los repositorios privados indiqué si el instructor tiene acceso.

## 4. Observaciones

Los commits de fusión (*merge commits*) fueron excluidos del conteo, de acuerdo con el criterio establecido en las instrucciones. El informe contiene únicamente los **12 commits no merge** realizados en el periodo indicado.

---

*Declaro que la información de este informe es veraz y que los commits listados son de mi autoría.*

**Aprendiz:** sharik rojas_  **Fecha:** 06/10/2026