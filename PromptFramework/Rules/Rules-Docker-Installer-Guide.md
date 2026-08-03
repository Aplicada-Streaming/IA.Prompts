---
doc_id: RC-INSTALL-GUIDE
doc_type: normativa-documental
title: "Reglas constructivas de los documentos *-Docker-Installer-Guide.md"
status: vigente
origin: agent
confidence: alta
owner: fernando
last_review: 2026-08-02
audience: [humans, agents]
traces:
  - RGH-INSTALL   # Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-Docker-Installer-Guide.md
---

# Reglas constructivas — guías de instalación de contenedores

## Resumen ejecutivo

Este documento extrae, del único `*-Docker-Installer-Guide.md` redactado hasta hoy
—[`Runner-GitHub-Docker-Installer-Guide.md`](../../../../../../../../Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-Docker-Installer-Guide.md),
742 líneas—, las **reglas constructivas** que debe respetar un agente IA al redactar las guías
equivalentes de los demás contenedores del host `i7infra` (`Docker.Web.Portal`, `Docker.Utils`,
`Docker.NVR.Server`, y los que se agreguen).

Las reglas se agrupan en cuatro planos: **identidad** (nomenclatura y metadatos), **estructura**
(qué secciones existen y en qué orden), **relato** (cómo se jerarquizan y encadenan las ideas) y
**tipografía** (cómo se marca cada tipo de dato). Todas son **descriptivas del original**: cada
una cita la evidencia que la sostiene en la sección [Evidencias](#evidencias). No se incorporó
ninguna regla que el documento fuente no practique.

> **Este documento no es una plantilla para rellenar.** Es el conjunto de restricciones que el
> resultado debe cumplir. La [plantilla mínima](#plantilla-mínima) del final es una consecuencia
> de las reglas, no su reemplazo: una guía puede omitir secciones que no apliquen (regla
> [RC-11](#rc-11--omitir-antes-que-vaciar)) pero no puede reordenarlas ni renombrarlas.

---

## Contenido

- [Resumen ejecutivo](#resumen-ejecutivo)
- [Alcance y fuente](#alcance-y-fuente)
- [1 · Identidad del documento](#1--identidad-del-documento)
  - [RC-01 — Nombre de archivo y ubicación](#rc-01--nombre-de-archivo-y-ubicación)
  - [RC-02 — Frontmatter obligatorio](#rc-02--frontmatter-obligatorio)
  - [RC-03 — Identificadores internos](#rc-03--identificadores-internos)
- [2 · Estructura canónica](#2--estructura-canónica)
  - [RC-04 — Orden de las secciones](#rc-04--orden-de-las-secciones)
  - [RC-05 — Resumen ejecutivo](#rc-05--resumen-ejecutivo)
  - [RC-06 — Tabla de contenido](#rc-06--tabla-de-contenido)
  - [RC-07 — Advertencia previa](#rc-07--advertencia-previa)
  - [RC-08 — Marco de referencia](#rc-08--marco-de-referencia)
  - [RC-09 — Arquitectura y diagramas](#rc-09--arquitectura-y-diagramas)
  - [RC-10 — Configuración de referencia](#rc-10--configuración-de-referencia)
  - [RC-11 — Omitir antes que vaciar](#rc-11--omitir-antes-que-vaciar)
- [3 · Procedimientos y operación](#3--procedimientos-y-operación)
  - [RC-12 — Anatomía de un paso](#rc-12--anatomía-de-un-paso)
  - [RC-13 — Prerrequisitos verificables](#rc-13--prerrequisitos-verificables)
  - [RC-14 — Operación por tarea, no por comando](#rc-14--operación-por-tarea-no-por-comando)
  - [RC-15 — Diagnóstico como tabla de traducción](#rc-15--diagnóstico-como-tabla-de-traducción)
- [4 · Reglas del relato](#4--reglas-del-relato)
  - [RC-16 — El porqué antes del cómo](#rc-16--el-porqué-antes-del-cómo)
  - [RC-17 — Desactivar el falso síntoma](#rc-17--desactivar-el-falso-síntoma)
  - [RC-18 — Referenciar en vez de duplicar](#rc-18--referenciar-en-vez-de-duplicar)
  - [RC-19 — Declarar lo que no se hizo](#rc-19--declarar-lo-que-no-se-hizo)
  - [RC-20 — Preguntas guía](#rc-20--preguntas-guía)
- [5 · Evidencia y honestidad epistémica](#5--evidencia-y-honestidad-epistémica)
  - [RC-21 — Hecho, interpretación y acción](#rc-21--hecho-interpretación-y-acción)
  - [RC-22 — Tabla de evidencias](#rc-22--tabla-de-evidencias)
  - [RC-23 — Datos no verificados](#rc-23--datos-no-verificados)
  - [RC-24 — Origen del dato numérico](#rc-24--origen-del-dato-numérico)
- [6 · Convenciones tipográficas y de redacción](#6--convenciones-tipográficas-y-de-redacción)
  - [RC-25 — Registro y persona](#rc-25--registro-y-persona)
  - [RC-26 — Marcado semántico](#rc-26--marcado-semántico)
  - [RC-27 — Blockquotes de peso](#rc-27--blockquotes-de-peso)
  - [RC-28 — Tablas](#rc-28--tablas)
  - [RC-29 — Bloques de código](#rc-29--bloques-de-código)
  - [RC-30 — Enlaces y anclas](#rc-30--enlaces-y-anclas)
  - [RC-31 — Formato físico](#rc-31--formato-físico)
- [Antipatrones](#antipatrones)
- [Checklist de validación](#checklist-de-validación)
- [Plantilla mínima](#plantilla-mínima)
- [Evidencias](#evidencias)
  - [Datos no verificados](#datos-no-verificados)
- [Referencias](#referencias)

---

## Alcance y fuente

**Fuente única.** Las reglas se derivaron de un solo documento. De los cuatro archivos
`*-Docker-Installer-Guide.md` presentes en el workspace, **tres están vacíos** (0 bytes):

| Archivo | Tamaño | Uso |
|---------|--------|-----|
| `Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-Docker-Installer-Guide.md` | 742 líneas | **Fuente de estas reglas** |
| `Repos-Docker/Docker.NVR.Server/Guides/Runner-GitHub-Docker-Installer-Guide.md` | 0 | vacío — **nombre heredado del copiado, incumple [RC-01](#rc-01--nombre-de-archivo-y-ubicación)** |
| `Repos-Docker/Docker.Web.Portal/Guides/Web-Portal-Docker-Installer-Guide.md` | 0 | vacío |
| `Repos-Docker/Docker.Utils/Guides/Utils-Services-Docker-Installer-Guide.md` | 0 | vacío |

**Consecuencia sobre la confianza.** Con una sola muestra no es posible distinguir lo que es
**convención del corpus** de lo que es **rasgo particular** de la guía del runner. Por eso cada
regla lleva una marca de confianza:

| Marca | Significado |
|-------|-------------|
| **Estructural** | Se sostiene sola: el documento la practica de forma sistemática y hay una razón explícita en el propio texto o en las `Rules` del PromptFramework |
| **Inferida** | Se observa en el original pero podría ser un rasgo del dominio «runner» y no una convención general. Aplicarla salvo que el contenedor la contradiga |

Las reglas son **compatibles** con `Rule-Markdown.md` y `Rule-Evidences.md` del PromptFramework:
donde estas fijan un principio general («tablas para comparar», «diferenciar hechos de
interpretaciones»), las de aquí fijan la forma concreta que ese principio toma en una guía de
instalación.

---

## 1 · Identidad del documento

### RC-01 — Nombre de archivo y ubicación

**Estructural.**

- El archivo vive en `Guides/` del repositorio del contenedor, nunca en la raíz.
- El nombre sigue el patrón `<Ámbito>-Docker-Installer-Guide.md`, donde `<Ámbito>` identifica al
  servicio en *Capitalized-Kebab-Case*: `Runner-GitHub-`, `Web-Portal-`, `Utils-Services-`.
- El sufijo `-Docker-Installer-Guide` es fijo y distingue a este documento de sus hermanos del
  mismo directorio: `-Configuration-Guide` (ajustes del proveedor externo) y
  `-WorkFlow-User-Guide` (uso del servicio). **Cada uno tiene un lector distinto y no se
  fusionan.**

### RC-02 — Frontmatter obligatorio

**Estructural.** El documento abre con un bloque YAML con estas claves, en este orden:

| Clave | Valor | Regla |
|-------|-------|-------|
| `doc_id` | `RGH-INSTALL` | Sigla del ámbito + `-INSTALL`, en mayúsculas |
| `doc_type` | `guia-operacion` | Fijo para este tipo de documento |
| `title` | texto entre comillas | Frase nominal descriptiva, **no** el nombre del archivo |
| `status` | `vigente` | Estado del documento |
| `origin` | `agent` | Quién lo redactó |
| `confidence` | `alta` | Confianza global |
| `owner` | `fernando` | Responsable |
| `last_review` | `2026-08-02` | Fecha ISO de la última verificación **real** contra el sistema |
| `audience` | `[humans, agents]` | Lectores previstos |
| `traces` | lista de `doc_id` | Documentos relacionados, **cada uno con la ruta en comentario** |

> **`last_review` no es la fecha de edición.** Es la fecha en la que se corrieron los comandos de
> la sección [Evidencias](#evidencias) contra el sistema. Editar la redacción sin re-verificar no
> la mueve.

### RC-03 — Identificadores internos

**Estructural.** El documento numera lo que después referencia. Tres familias, sin mezclarse:

| Familia | Patrón | Ejemplo | Dónde se define |
|---------|--------|---------|-----------------|
| Escenarios | `E-<n>` | `E-3 · Rotación del token` | Tabla de [escenarios](#rc-08--marco-de-referencia) |
| Observaciones propias | `O-<SIGLA>-<NN>` | `O-RGH-01` | Sección Observaciones |
| Observaciones del host | `O-<NN>` | `O-02`, `O-14` | Auditoría del host — **se citan, no se redefinen** |

Cada identificador se define **una vez** y a partir de ahí se lo invoca por su código
(«Escenario **E-3**», «la observación **O-08** del host»). Un identificador que no se referencia
después sobra.

---

## 2 · Estructura canónica

### RC-04 — Orden de las secciones

**Estructural.** Los `##` aparecen en este orden. El orden **no es negociable**: responde a la
secuencia en que el lector necesita la información —qué es, qué riesgo corro, qué palabras uso,
cómo está armado, qué necesito, cómo lo hago, cómo lo mantengo, qué hago si falla, qué sé y qué
no.

| # | Sección | Obligatoria | Función |
|---|---------|-------------|---------|
| 1 | `# <Título>` (H1) | Sí | Único H1 del documento |
| 2 | `## Resumen ejecutivo` | Sí | Qué es, para quién, qué lo compone, dónde está el fundamento |
| 3 | `## Contenido` | Sí | TOC con anclas |
| 4 | `## Advertencia … — leer antes de continuar` | Condicional | Solo si hay un riesgo que invalida el resto |
| 5 | `## Marco de referencia` | Sí | Vocabulario: escenarios, contextos, actores |
| 6 | `## Arquitectura del despliegue` | Sí | Diagrama + qué comparte y qué no |
| 7 | `## Configuración de referencia` | Sí | Todos los valores concretos, en tabla |
| 8 | `## Prerrequisitos` | Sí | Qué debe existir antes, y cómo comprobarlo |
| 9 | `## Procedimiento` | Sí | Pasos numerados hasta el servicio validado |
| 10 | `## Operación` | Sí | Tareas del día a día y del ciclo de vida |
| 11 | `## Diagnóstico` | Sí | Síntoma → causa → solución |
| 12 | `## Preguntas guía` | Inferida | Autoevaluación del lector |
| 13 | `## Observaciones` | Sí | Hallazgos con hecho / interpretación / acción |
| 14 | `## Evidencias` | Sí | Cómo se verificó cada afirmación + datos no verificados |
| 15 | `## Referencias` | Sí | Documentos hermanos, archivos del repo, fuentes externas |

Entre secciones `##` va un separador `---`. **No se usa `---` entre subsecciones `###`.**

### RC-05 — Resumen ejecutivo

**Estructural.** Tres a cinco párrafos, en este orden funcional:

1. **Qué explica el documento y a quién está dirigido**, incluyendo *a quién no*: «quien escribe
   workflows no necesita leerlo, le alcanza con la guía de uso».
2. **De qué se compone el despliegue**: instancias, imagen base, componentes, y el porqué de esa
   composición.
3. **Dónde está el fundamento de las decisiones**, enlazado. El resumen no argumenta: delega en
   el análisis.
4. Cierra con un **blockquote que corrige el malentendido más probable** sobre el servicio.

### RC-06 — Tabla de contenido

**Estructural.** Lista anidada de dos niveles (`##` y `###`) con anclas GitHub. Va inmediatamente
después del resumen ejecutivo, bajo el título `## Contenido`. Los `###` del procedimiento se
listan **con su número** (`- [1. Verificar el espacio en disco](#1-verificar-el-espacio-en-disco)`).

### RC-07 — Advertencia previa

**Inferida.** Se incluye **solo si existe un riesgo que cambia la decisión de desplegar**. Cuando
existe, se ubica antes del contenido técnico y se construye así:

1. Cita textual de la fuente autorizada, entre comillas angulares « », con enlace a la fuente.
2. Consecuencia en negrita, aplicada a este despliegue.
3. Un caso real documentado que demuestre que el riesgo no es teórico.
4. Tabla de **mitigaciones aplicadas por diseño** (`Mitigación | Cómo`).
5. Párrafo explícito con las mitigaciones que **no** se aplican hoy y qué las bloquea, con enlace
   a la observación correspondiente.

> **El punto 5 es el que distingue una advertencia útil de una decorativa.** Enumerar solo lo que
> sí se hizo convierte la sección en publicidad del despliegue.

### RC-08 — Marco de referencia

**Estructural.** Fija el vocabulario **antes** de usarlo. Tres subsecciones, siempre tablas:

| Subsección | Columnas | Qué normaliza |
|------------|----------|---------------|
| `### Escenarios` | `Escenario \| Cuándo ocurre \| Sección que lo resuelve` | Las situaciones que traen al lector al documento |
| `### Contextos` | `Contexto \| Qué cambia` | Las variantes que alteran los valores del procedimiento |
| `### Actores` | `Actor \| Responsabilidad \| Qué decide` | Quién hace qué |

La tercera columna de **Escenarios** es un enlace interno: el marco funciona como índice por
situación, no solo como glosario.

Tras la tabla de actores va un párrafo que reconoce cuándo los roles los ejerce la misma persona
y **por qué conviene distinguirlos igual** (típicamente: el paso que más bloquea pertenece a un
rol distinto del que ejecuta).

### RC-09 — Arquitectura y diagramas

**Estructural.** Dos diagramas Mermaid, con funciones distintas:

| Diagrama | Tipo | Muestra |
|----------|------|---------|
| Arquitectura | `flowchart LR` con `subgraph` por frontera (proveedor externo / host) | Qué habla con qué, en qué dirección y por qué puerto |
| Ciclo de vida | `sequenceDiagram` | La secuencia temporal que explica los comportamientos raros |

Reglas del `flowchart`: cada nodo lleva **nombre, dirección de red y etiquetas** en líneas
separadas con `<br/>`; los volúmenes se dibujan con la forma cilindro `[( )]`; las aristas se
**etiquetan con el protocolo y el sentido** (`"long polling 443 saliente"`).

Después del diagrama, un párrafo que responde **qué comparten y qué no** las instancias o
servicios dibujados. El diagrama muestra la topología; el párrafo, sus consecuencias.

El `sequenceDiagram` cierra con una `Note over` que explica el estado final, y **el párrafo
posterior nombra los comportamientos que ese ciclo produce y que parecen fallas**
(ver [RC-17](#rc-17--desactivar-el-falso-síntoma)).

### RC-10 — Configuración de referencia

**Estructural.** Todos los valores concretos viven acá y **en ningún otro lado**; el procedimiento
los referencia. Dos tablas:

1. **Lo que difiere entre instancias**: una columna por instancia, una fila por parámetro
   (directorio en el repo, directorio de despliegue, nombre de contenedor, imagen, IP, volumen…).
   Con una sola instancia, la tabla es `Parámetro | Valor`.
2. **Lo común a todas**: base, versiones, red, límites de memoria y CPU.

Cierra con un **blockquote de colisiones**: qué valores no pueden coincidir entre instancias y
**qué rompe cada uno**, distinguiendo los que impiden levantar el servicio de los que solo
degradan la operación.

### RC-11 — Omitir antes que vaciar

**Estructural.** Una sección que no aplica **se omite**; no se deja con «N/A» ni con un párrafo de
relleno. Lo que sí es obligatorio es explicitar la omisión cuando el lector podría esperarla:

> **Los runners no exponen ningún servicio.** Se conectan **salientes** a `github.com:443` […]
> no hay UI ni puertos publicados.

Ese blockquote reemplaza a una sección «Acceso al servicio» que en este contenedor no tiene
sentido. Un contenedor con UI **sí** debe documentarla, dentro de `Operación`.

---

## 3 · Procedimientos y operación

### RC-12 — Anatomía de un paso

**Estructural.** El `## Procedimiento` abre con un párrafo que declara **para qué escenarios sirve
la misma secuencia** y **qué cambia entre ellos** (típicamente: solo los valores de la tabla de
configuración). Luego, un `###` por paso, numerado, con título en **infinitivo**:
`### 3. Preparar el directorio de despliegue`.

Cada paso contiene, en este orden y omitiendo lo que no aplique:

| Elemento | Regla |
|----------|-------|
| **Justificación** | Una o dos frases sobre por qué existe el paso o por qué se eligió este camino y no el obvio |
| **Estructura de archivos** | Bloque ` ``` ` con árbol y **anotación al margen** de qué clave del compose apunta a cada ruta |
| **Comandos** | Bloque `bash`, con variables al inicio para no repetir literales |
| **Resultado esperado** | En negrita, `**Resultado esperado.**`, describiendo qué se debe ver — no «si funciona, funciona» |
| **Comando de verificación** | Un segundo bloque que comprueba objetivamente el resultado |
| **Blockquote de advertencia** | Solo si hay un modo de falla no evidente o una decisión pendiente |

El último paso del procedimiento **siempre es una validación funcional** («Validar con un workflow
de humo»), no la puesta en marcha. Levantar el contenedor no es terminar.

### RC-13 — Prerrequisitos verificables

**Estructural.** Tabla `Requisito | Detalle | Cómo verificar`. La tercera columna es **un comando
ejecutable o un enlace a la sección que lo resuelve** — nunca «verificar manualmente».

El requisito que más frecuentemente bloquea el despliegue se marca en negrita en la tabla **y
además es el paso 1 del procedimiento**. La guía del runner lo dice explícitamente: «Es el
prerrequisito que más frecuentemente bloquea el despliegue».

Los requisitos de recursos se expresan con **rango medido y desglose** (ver
[RC-24](#rc-24--origen-del-dato-numérico)), acompañados de un blockquote **«Si no hay
suficiente…»** con las opciones de reducción y cuánto ahorra cada una.

### RC-14 — Operación por tarea, no por comando

**Estructural.** `## Operación` se organiza en `###` por **tarea del ciclo de vida**, no por
comando. El orden observado es: comandos habituales → comportamiento esperado → rotación de
credenciales → ajuste de recursos → contención con otros servicios del host → actualización →
baja → sincronización con el repositorio.

Reglas particulares:

- **Comandos habituales** es una tabla `Acción | Comando`, precedida por la aclaración de **desde
  qué directorio** se ejecutan y por qué.
- Cada tarea que corresponde a un escenario del marco lo **nombra por su código**: «Escenario
  **E-3**».
- Cuando un comando intuitivo **no** sirve, se dice y se explica: «`docker compose restart` **no
  alcanza**: reinicia el proceso sin releer `env_file`».
- La sincronización con el repositorio incluye los `diff` concretos y cierra con la dirección
  prohibida en negrita: «**Nunca al revés.**».

### RC-15 — Diagnóstico como tabla de traducción

**Estructural.** `## Diagnóstico` es una tabla `Síntoma | Causa probable | Solución`, ordenada de
lo más frecuente a lo más específico, donde:

- El **síntoma** es el texto literal del error tal como aparece en los logs, en `code`.
- La **causa probable** va en negrita cuando es la explicación dominante, y agrega el dato de
  frecuencia si se conoce («Es el fallo más común en operación»).
- La **solución** enlaza a la sección que la desarrolla; no la repite.
- **Los comportamientos normales están en la tabla**, con causa «**Comportamiento normal**» y
  solución «Ninguna». Quien busca por síntoma no sabe todavía que no es una falla.

Tras la tabla, uno o dos `###` que desarrollan los diagnósticos que se confunden entre sí
(«Distinguir 401 de 403 y de 404») y el `###` de inspección del entorno instalado, con la variante
que funciona **cuando el contenedor está caído** —`docker run --rm --entrypoint sh`—, porque
`exec` no sirve ahí.

---

## 4 · Reglas del relato

### RC-16 — El porqué antes del cómo

**Estructural.** Ninguna instrucción aparece sin su motivo cuando el motivo no es evidente. El
patrón textual es «Se usa X y no Y porque Z»:

> Se usa un PAT y no el *registration token* de la UI porque este último **expira en 1 hora**.

Aplica a los tres niveles: elección de sección, elección de herramienta y elección de valor.

### RC-17 — Desactivar el falso síntoma

**Estructural.** Cuando el diseño produce un comportamiento que parece una falla, el documento
lo **anticipa, lo nombra y da el criterio para distinguirlo de la falla real**:

> **El contenedor se reinicia después de cada job. Eso es correcto, no es una falla.**
> […] La diferencia con un fallo real está en los logs: un ciclo sano muestra `Listening for
> Jobs` antes de terminar; un fallo de registro no llega nunca a esa línea.

Tres componentes obligatorios: **afirmación en negrita** del comportamiento, **explicación** por
el mecanismo, **criterio discriminante** contra el fallo real.

### RC-18 — Referenciar en vez de duplicar

**Estructural.** Cuando el detalle vive en un documento hermano, la guía deja un **resumen
operativo mínimo** (típicamente una tabla de tres filas) y enlaza a la sección exacta del otro
documento con su ancla: `[guía de uso, §2](…-User-Guide.md#2-alta-del-runner…)`.

La frase que introduce el enlace declara **qué se encontrará allá**, para que el lector decida si
necesita ir: «dónde se genera, qué scope marcar según el alcance, cómo autorizarlo si la
organización usa SAML SSO».

### RC-19 — Declarar lo que no se hizo

**Estructural.** Las decisiones pendientes o descartadas se documentan **en el lugar donde el
lector se las preguntaría**, no solo en Observaciones, y se marcan en negrita:

> Si la reconstrucción se vuelve lenta, agregar un `.dockerignore` […] **No aplicado**, no fue
> necesario hasta ahora.

### RC-20 — Preguntas guía

**Inferida.** Antes de Observaciones, una lista numerada de 5 a 8 preguntas que el responsable
debería poder responder **sin releer el documento**. Cada pregunta apunta a una decisión no
obvia ya explicada en el texto —no a un dato memorizable— y **al menos una plantea un caso
concreto con números**: «Un contenedor acumula 43 reinicios en una hora. ¿Cómo se decide si es la
efimeridad trabajando o un fallo de registro?».

Las preguntas guía **no llevan respuestas**: si una no se puede responder desde el documento, lo
que falta es contenido, no una respuesta.

---

## 5 · Evidencia y honestidad epistémica

### RC-21 — Hecho, interpretación y acción

**Estructural.** `## Observaciones` abre declarando **la fecha y el sistema sobre el que se
verificó** y que se distinguen hechos de interpretaciones. La tabla tiene exactamente cuatro
columnas:

| Columna | Contenido |
|---------|-----------|
| `#` | `O-<SIGLA>-<NN>` en negrita |
| `Hecho verificado` | Solo lo observable, con los valores concretos medidos |
| `Interpretación` | Qué significa ese hecho — separado del hecho, nunca fundido con él |
| `Acción propuesta` | El comando o el cambio, o «Ninguna» |

Una interpretación puede afirmar que un hallazgo es **deliberado y no un descuido**; esa
distinción pertenece a la columna de interpretación, jamás a la de hecho.

Tras la tabla, un párrafo de **cierre de ciclo**: qué hallazgos de revisiones anteriores están
resueltos y qué queda pendiente, para que el lector no arrastre problemas ya cerrados.

### RC-22 — Tabla de evidencias

**Estructural.** `## Evidencias` es una tabla `Afirmación | Cómo se verificó | Resultado` donde la
columna del medio contiene el **comando exacto o el endpoint exacto**, reproducible por otra
persona, y la de la derecha el **resultado obtenido**, con los valores literales.

Las fuentes documentales se citan **con fecha de consulta**: «(consultado 2026-08-02)».

### RC-23 — Datos no verificados

**Estructural.** `### Datos no verificados`, como subsección de Evidencias. Lista de viñetas donde
cada ítem declara, en negrita, **qué** no se verificó, seguido de **por qué** no se pudo y **qué
riesgo** implica:

> **Reserva DHCP de `192.168.1.120` y `.121`**: no se inspeccionó la configuración del router. Si
> esas IPs están dentro del rango dinámico, hay riesgo de conflicto (**O-10** del host). Tampoco
> se pudo comprobar por `ping` desde el host: macvlan aísla al host de sus propios contenedores.

Esta sección **es obligatoria**. Un documento sin datos no verificados declara implícitamente que
todo se verificó, lo cual casi nunca es cierto.

### RC-24 — Origen del dato numérico

**Estructural.** Todo número lleva unidad y, cuando se lo pueda confundir con una estimación,
**origen**. La guía dedica una columna entera a esto (`Componente | Tamaño | Origen del dato`,
con valores «medido», «`docker images`», «suma») y marca explícitamente lo que **no** es medición:

> Los valores de `memory: 8G` y `cpus: "4.0"` son un punto de partida fundamentado, **no una
> medición**.

Los valores aproximados usan `≈` o `~`; los rangos, guion (`25–30 GB`). Los decimales van con
coma (`2,36 GB`), coherentes con el español del documento.

---

## 6 · Convenciones tipográficas y de redacción

### RC-25 — Registro y persona

**Estructural.**

- Español técnico, **impersonal con «se»** («se construyen», «se levantan», «se registra»). No se
  usa «usted» ni la primera persona.
- Las recomendaciones se expresan con **«conviene»**, **«corresponde»**, **«se recomienda»**; las
  obligaciones con **«debe»** o con negrita imperativa («**deben usarse únicamente con
  repositorios privados**»).
- Presente indicativo para describir el sistema; infinitivo para las instrucciones («Verificar
  el espacio», «Agregarla al `.env`»).
- Párrafos de 3 a 6 líneas. Ninguna sección consiste solo en una lista o una tabla sin prosa que
  la introduzca.

### RC-26 — Marcado semántico

**Estructural.** Cada marca tiene un significado fijo y **no se usa decorativamente**:

| Marca | Uso | Ejemplo |
|-------|-----|---------|
| `` `code` `` | Todo identificador literal: rutas, archivos, variables, comandos, nombres de contenedor e imagen, etiquetas, códigos de error | `` `EPHEMERAL=true` ``, `` `192.168.1.120` `` |
| **Negrita** | El dato accionable o el veredicto de la frase; nunca frases enteras | «**un solo job**», «**No aplicado**» |
| *Cursiva* | Elementos de la interfaz de un producto externo y términos citados en otro idioma | *Settings → Actions → Runners*, *runner group* |
| « » | Cita textual de una fuente | «Self-hosted runners should **almost never**…» |
| `→` | Navegación por menús y transiciones de estado | `Settings → Actions`, `registrarse → ejecutar → desregistrarse` |
| `·` | Separador dentro de un identificador o de una lista corta en línea | `E-1 · Alta inicial` |

Las versiones se escriben completas y en negrita cuando son decisivas: **2.335.1**, **.NET 10**,
**API 36**.

### RC-27 — Blockquotes de peso

**Estructural.** El `>` se reserva para lo que el lector **no debe pasar por alto**, y siempre
abre con una **frase en negrita que es la conclusión**, seguida del desarrollo:

> **Si falta la variable de destino, el contenedor no aborta: entra en bucle.** El entrypoint
> imprime `ORG_NAME required for org runners` […]

Cuatro usos válidos, todos observados en el original: modo de falla no evidente, restricción
absoluta («**Nunca usar `ulimit -v`**»), corrección de un malentendido probable, y decisión
pendiente. **No** se usa para resaltar información que ya está en una tabla.

### RC-28 — Tablas

**Estructural.**

- Encabezado en negrita **no**; los encabezados van en texto plano.
- La primera columna es la clave de búsqueda del lector (síntoma, parámetro, requisito, actor).
- Sin celdas de párrafo largo: si una celda necesita más de dos oraciones, el contenido pertenece
  a un blockquote o a una subsección.
- Las celdas pueden contener enlaces internos, `code` y negrita, respetando [RC-26](#rc-26--marcado-semántico).
- Toda tabla va precedida por al menos una oración que dice **qué compara** y **para qué sirve**.

### RC-29 — Bloques de código

**Estructural.**

- Siempre con lenguaje declarado: `bash`, `mermaid`, o sin lenguaje para árboles de directorios y
  salidas literales.
- Los bloques `bash` definen **variables al principio** (`INSTANCIA=…`, `REPO=…`) y las reutilizan,
  para que el lector cambie un solo valor al aplicar el procedimiento a otra instancia.
- Las salidas esperadas van en un bloque **sin lenguaje**, conteniendo solo las líneas que
  importan —no el log completo.
- Ningún bloque de código aparece sin una frase previa que diga qué hace ni una posterior que
  diga qué se debe observar.

### RC-30 — Enlaces y anclas

**Estructural.**

- Enlaces internos por ancla `#seccion` para todo cruce dentro del documento; el marco de
  referencia y el diagnóstico dependen de ellos.
- Enlaces a documentos hermanos con **ruta relativa**, y a su **sección exacta** cuando el destino
  es un punto concreto.
- Enlaces externos con el **título real de la página**, no la URL desnuda; el `## Referencias`
  final los agrupa con una línea de qué aporta cada uno.
- `## Referencias` se ordena: documentos hermanos → análisis de diseño → archivos del repositorio
  → documentación oficial del proveedor → proyectos de terceros.

### RC-31 — Formato físico

**Estructural.**

- Ancho de línea de la prosa: **wrap manual a ~100 columnas**. Solo exceden las URLs largas, las
  filas de tabla y los comandos que no se pueden cortar.
- Un solo `#` en todo el documento; jerarquía sin saltos de nivel.
- `---` entre secciones `##`; nunca entre `###`.
- Sin líneas en blanco múltiples ni espacios al final de línea.
- El documento termina con la última referencia, sin firma ni pie.

---

## Antipatrones

Prácticas que el documento fuente evita de forma sistemática y que, por lo tanto, quedan
proscritas:

| # | Antipatrón | Por qué |
|---|-----------|---------|
| **A-01** | Repetir un valor de configuración fuera de la tabla de referencia | Dos fuentes de verdad divergen; el procedimiento debe referenciar, no copiar |
| **A-02** | Comando sin resultado esperado | El lector no puede saber si el paso salió bien |
| **A-03** | Presentar una estimación como medición | Viola `Rule-Evidences`; ver [RC-24](#rc-24--origen-del-dato-numérico) |
| **A-04** | Fundir hecho e interpretación en la misma celda | Impide revisar la interpretación sin re-verificar el hecho |
| **A-05** | Omitir la sección de datos no verificados | Declara implícitamente una verificación total que no ocurrió |
| **A-06** | Duplicar el contenido de un documento hermano | Las copias se desincronizan; ver [RC-18](#rc-18--referenciar-en-vez-de-duplicar) |
| **A-07** | Sección vacía o con «N/A» | Ver [RC-11](#rc-11--omitir-antes-que-vaciar) |
| **A-08** | Negrita decorativa o en frases completas | Destruye la señal de «esto es lo accionable» |
| **A-09** | Listar solo las mitigaciones aplicadas | Convierte la advertencia de seguridad en propaganda |
| **A-10** | Terminar el procedimiento al levantar el contenedor | El último paso es una validación funcional |
| **A-11** | Documentar el despliegue sin el mecanismo de sincronización con el repositorio | Es cómo se acumulan las divergencias |
| **A-12** | Dejar fuera del diagnóstico los comportamientos normales | Quien busca por síntoma todavía no sabe que no es una falla |

---

## Checklist de validación

Antes de dar por terminada una guía `*-Docker-Installer-Guide.md`:

- [ ] Frontmatter completo, con `last_review` correspondiente a una verificación real ([RC-02](#rc-02--frontmatter-obligatorio)).
- [ ] Las 15 secciones en el orden canónico; las omitidas, justificadas ([RC-04](#rc-04--orden-de-las-secciones), [RC-11](#rc-11--omitir-antes-que-vaciar)).
- [ ] TOC completo y con todas las anclas resueltas ([RC-06](#rc-06--tabla-de-contenido)).
- [ ] Cada escenario de la tabla tiene una sección que lo resuelve, y viceversa ([RC-08](#rc-08--marco-de-referencia)).
- [ ] Mermaid sintácticamente correcto y con las aristas etiquetadas ([RC-09](#rc-09--arquitectura-y-diagramas)).
- [ ] Ningún valor de configuración aparece fuera de la tabla de referencia (**A-01**).
- [ ] Cada paso del procedimiento tiene resultado esperado y verificación ([RC-12](#rc-12--anatomía-de-un-paso), **A-02**).
- [ ] El último paso es una validación funcional (**A-10**).
- [ ] El diagnóstico incluye los comportamientos normales (**A-12**).
- [ ] Cada número decisivo declara su origen ([RC-24](#rc-24--origen-del-dato-numérico)).
- [ ] Observaciones separa hecho, interpretación y acción ([RC-21](#rc-21--hecho-interpretación-y-acción)).
- [ ] La tabla de evidencias permite reproducir cada verificación ([RC-22](#rc-22--tabla-de-evidencias)).
- [ ] Existe `### Datos no verificados` y no está vacía ([RC-23](#rc-23--datos-no-verificados)).
- [ ] Todos los enlaces relativos resuelven a archivos existentes ([RC-30](#rc-30--enlaces-y-anclas)).
- [ ] Prosa envuelta a ~100 columnas ([RC-31](#rc-31--formato-físico)).

---

## Plantilla mínima

Esqueleto que resulta de aplicar las reglas. Los comentarios `<!-- -->` indican la regla que rige
cada sección y **no se conservan** en el documento final.

```markdown
---
doc_id: <SIGLA>-INSTALL
doc_type: guia-operacion
title: "<Frase nominal descriptiva>"
status: vigente
origin: agent
confidence: alta
owner: <responsable>
last_review: <YYYY-MM-DD>
audience: [humans, agents]
traces:
  - <DOC-ID>   # <ruta relativa>
---

# Guía de alta — <servicio> en Docker

## Resumen ejecutivo
<!-- RC-05: qué/para quién/de qué se compone/dónde está el fundamento + blockquote correctivo -->

## Contenido
<!-- RC-06 -->

---

## Advertencia … — leer antes de continuar
<!-- RC-07: condicional -->

---

## Marco de referencia
### Escenarios
### Contextos
### Actores
<!-- RC-08 -->

---

## Arquitectura del despliegue
### Ciclo de vida de <la unidad de trabajo>
<!-- RC-09: flowchart LR + sequenceDiagram -->

---

## Configuración de referencia
<!-- RC-10: tabla por instancia + tabla de comunes + blockquote de colisiones -->

---

## Prerrequisitos
<!-- RC-13: Requisito | Detalle | Cómo verificar -->

---

## Procedimiento
### 1. <Infinitivo>
### N. Validar con <prueba funcional>
<!-- RC-12 -->

---

## Operación
### Comandos habituales
### Comportamiento esperado
### <Rotación / actualización / baja / sincronización>
<!-- RC-14 -->

---

## Diagnóstico
<!-- RC-15: Síntoma | Causa probable | Solución -->

---

## Preguntas guía
<!-- RC-20 -->

---

## Observaciones
<!-- RC-21: # | Hecho verificado | Interpretación | Acción propuesta -->

---

## Evidencias
### Datos no verificados
<!-- RC-22, RC-23 -->

---

## Referencias
<!-- RC-30 -->
```

---

## Evidencias

Todas las verificaciones se hicieron el **2026-08-02** sobre el workspace
`~/workspaces/workspace-dev`. La columna del medio permite reproducirlas.

| Afirmación | Cómo se verificó | Resultado |
|-----------|------------------|-----------|
| El documento fuente existe y tiene 742 líneas | `wc -l Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-Docker-Installer-Guide.md` | `742` |
| Los otros tres `*-Docker-Installer-Guide.md` están vacíos | `wc -l` sobre los cuatro archivos hallados con `find . -iname "*Installer-Guide*"` | `0` en `Docker.NVR.Server`, `Docker.Web.Portal` y `Docker.Utils` |
| El insumo declarado por el tool-prompt está vacío | `ls -la .../01-Caracterizar-Docker-Installer-Guide/OUTPUTs/` | `Docker-Installer-Guide.md` de **0 bytes** |
| Frontmatter y sus claves ([RC-02](#rc-02--frontmatter-obligatorio)) | Lectura de las líneas 1–14 del documento fuente | 10 claves en el orden documentado; `traces` con comentario de ruta |
| Orden de las 15 secciones ([RC-04](#rc-04--orden-de-las-secciones)) | Lectura del TOC (líneas 42–79) y de los `##` del cuerpo | El TOC coincide con el orden de aparición |
| Separador `---` entre `##` y no entre `###` | Inspección de las líneas 40, 81, 112, 151, 203, 243, 258, 462, 607, 653, 670, 693, 730 | Un `---` antes de cada `##`; ningún `---` entre subsecciones |
| Familias de identificadores ([RC-03](#rc-03--identificadores-internos)) | Búsqueda de `E-<n>`, `O-RGH-<NN>` y `O-<NN>` en el texto | `E-1`…`E-6` (líneas 123–128); `O-RGH-01`…`O-RGH-07` (679–685); `O-02`, `O-08`, `O-10`, `O-14` citadas como del host |
| Dos diagramas Mermaid con tipos distintos ([RC-09](#rc-09--arquitectura-y-diagramas)) | Líneas 155–176 y 184–197 | `flowchart LR` con dos `subgraph` y nodos cilindro; `sequenceDiagram` con `Note over` |
| Patrón «Resultado esperado» ([RC-12](#rc-12--anatomía-de-un-paso)) | Ocurrencias en los pasos del procedimiento | Líneas 276, 340, 416 — uno por paso que ejecuta comandos |
| El último paso es una validación funcional ([RC-12](#rc-12--anatomía-de-un-paso), **A-10**) | Línea 456 | `### 8. Validar con un workflow de humo` |
| Comportamientos normales dentro del diagnóstico (**A-12**) | Línea 620 | «El runner aparece y desaparece constantemente → **Comportamiento normal** → Ninguna» |
| Falso síntoma desactivado ([RC-17](#rc-17--desactivar-el-falso-síntoma)) | Líneas 483 y 490–491 | Afirmación en negrita + mecanismo + criterio discriminante por logs |
| Origen del dato numérico ([RC-24](#rc-24--origen-del-dato-numérico)) | Tabla de las líneas 279–288 y frase de la línea 517 | Columna `Origen del dato` con «medido» / `docker images`; «**no una medición**» para los límites |
| Hecho / interpretación / acción separados ([RC-21](#rc-21--hecho-interpretación-y-acción)) | Cabecera de la tabla de la línea 677 | `# \| Hecho verificado \| Interpretación \| Acción propuesta` |
| Tabla de evidencias reproducible ([RC-22](#rc-22--tabla-de-evidencias)) | Líneas 697–713 | `Afirmación \| Cómo se verificó \| Resultado`, con comandos y endpoints literales |
| Sección de datos no verificados ([RC-23](#rc-23--datos-no-verificados)) | Líneas 715–728 | Cinco ítems, cada uno con qué, por qué y riesgo |
| Preguntas guía sin respuestas ([RC-20](#rc-20--preguntas-guía)) | Líneas 655–668 | Siete preguntas; la #3 plantea un caso con números |
| Wrap de prosa a ~100 columnas ([RC-31](#rc-31--formato-físico)) | `awk 'length>100 && $0 !~ /^\|/ && $0 !~ /^ *[-*] / && $0 !~ /http/'` | Solo 4 líneas exceden: dos enlaces largos, una flecha de estados y un comando `docker run` |
| Reglas del PromptFramework aplicadas | Lectura de `RuleSet-Default.md` y de `Rule-All`, `Rule-Workflow`, `Rule-Evidences`, `Rule-Markdown` | Compatibles: `Rule-Markdown` exige tablas, Mermaid, enlaces relativos y estructura jerárquica; `Rule-Evidences` exige distinguir hechos de interpretaciones y marcar lo no verificado |

### Datos no verificados

- **Generalidad de las reglas.** Se derivaron de **un solo documento**. Las marcadas como
  *Inferidas* ([RC-07](#rc-07--advertencia-previa), [RC-20](#rc-20--preguntas-guía)) podrían ser
  rasgos del dominio «runner» y no convenciones del corpus. Se confirmarán o corregirán al
  redactar la segunda guía.
- **Intención del autor.** Las reglas describen **lo que el documento hace**, no lo que su autor
  se propuso. No se consultó ninguna especificación previa de estilo — no consta que exista.
- **Secciones ausentes por no aplicar.** El contenedor del runner no expone servicio ni UI, así
  que **no hay evidencia** de cómo el corpus documenta puertos publicados, credenciales de acceso
  o certificados. [RC-11](#rc-11--omitir-antes-que-vaciar) indica que van dentro de `Operación`,
  pero eso es una **propuesta**, no una convención observada.
- **Validez de los enlaces del documento fuente.** No se comprobó que
  `Runner-GitHub-Configuration-Guide.md` ni las anclas hacia la guía de uso resuelvan; solo se
  verificó que los archivos hermanos existen en `Guides/`.
- **Convención de `doc_type`.** `guia-operacion` se observó una sola vez; no se relevó el
  vocabulario completo de `doc_type` usado en el workspace.

---

## Referencias

- [Documento fuente — `Runner-GitHub-Docker-Installer-Guide.md`](../../../../../../../../Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-Docker-Installer-Guide.md)
  — la guía de la que se extrajeron estas reglas.
- Documentos hermanos que fijan la distinción de roles del [RC-01](#rc-01--nombre-de-archivo-y-ubicación):
  [`Runner-GitHub-WorkFlow-User-Guide.md`](../../../../../../../../Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-WorkFlow-User-Guide.md) ·
  [`Runner-GitHub-Configuration-Guide.md`](../../../../../../../../Repos-Docker/Docker.RunnerGitHub/Guides/Runner-GitHub-Configuration-Guide.md)
- PromptFramework — reglas generales que estas reglas concretan:
  [`RuleSet-Default.md`](../../../../../../../../IA/IA.Prompts/PromptFramework/RuleSets/RuleSet-Default.md) ·
  [`Rule-Markdown.md`](../../../../../../../../IA/IA.Prompts/PromptFramework/Rules/Rule-Markdown.md) ·
  [`Rule-Evidences.md`](../../../../../../../../IA/IA.Prompts/PromptFramework/Rules/Rule-Evidences.md)
- Guías pendientes de redactar a las que aplican estas reglas:
  `Docker.Web.Portal/Guides/Web-Portal-Docker-Installer-Guide.md` ·
  `Docker.Utils/Guides/Utils-Services-Docker-Installer-Guide.md` ·
  `Docker.NVR.Server/Guides/NVR-Server-Docker-Installer-Guide.md`

  > **El archivo que hoy existe en `Docker.NVR.Server/Guides/` se llama
  > `Runner-GitHub-Docker-Installer-Guide.md`** (0 bytes) y es un residuo del copiado del proyecto del
  > runner: incumple [RC-01](#rc-01--nombre-de-archivo-y-ubicación), que exige `<Ámbito>-Docker-Installer-Guide.md`.
  > El destino correcto es `NVR-Server-Docker-Installer-Guide.md`; el residuo se elimina al redactar la guía.
