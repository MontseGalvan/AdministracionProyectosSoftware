# Tarea 1. Introducción a la administración de proyectos y entorno de trabajo

| Campo | Dato |
|---|---|
| **UEA y clave** | Administración de Proyectos de Software (1151055) |
| **Trimestre** | 26-O |
| **Licenciatura** | Ingeniería en Computación |
| **Nombre** | Montserrath Galván Velázquez |
| **Matrícula** | 2212002252 |
| **Profesor** | Gabriel Hurtado Avilés |
| **Fecha de entrega** | 16 de octubre del 2026 |

---

## Ejercicio 2. Investigación

### 1. ¿Qué es un proyecto de software?

Un proyecto es un esfuerzo temporal para la creación un producto, servicio o resultado único, tiene un inicio y un final definidos, y termina cuando se alcanzan sus
objetivos (Project Management Institute [PMI], 2021). En cambio, una operación continua es un trabajo repetitivo y permanente que sostiene el negocio día
con día (como mantener en línea un servidor o atender soporte) (Lewis, 2007).

Asimismo podemos separar tres conceptos que suelen confundirse:

- **Proyecto**: el esfuerzo temporal y organizado para construir algo.
- **Producto**: el resultado que queda cuando el proyecto termina.
- **Proceso**: la forma de trabajar, el conjunto de actividades y métodos que se siguen para llegar al producto (Pressman, 2009).

Para la gestión de todo proyecto de software deben definirse los siguientes criterios: el alcance (qué se va a construir y qué no), el tiempo (cuándo debe estar listo),
el costo (cuántos recursos consume) y la calidad (qué tan bien cumple lo que debe hacer). Cada una de ellas afecta a las demás por lo que administrar un proyecto requiere 
mantener el equilibrio entre estas cuatro variables (Lewis, 2007; PMI, 2021).

> **Fuentes:** Lewis (2007); Project Management Institute (2021); Pressman (2009).

### 2. ¿Cómo se administra?

Existen marcos de referencia que ordenan cómo llevar un proyecto. Dos de los más conocidos son la Guía del PMBOK y Scrum.

La Guía del PMBOK (Project Management Body of Knowledge), publicada por el PMI, reúne las buenas prácticas, principios y dominios de desempeño reconocidos en la administración de
proyectos. Como su nombre lo dice es un marco de referencia, y no una estricta metodología a seguir (PMI, 2021).

Scrum es un marco de trabajo ágil y ligero para resolver problemas complejos de forma adaptativa. Organiza el trabajo en ciclos cortos llamados sprints, con roles definidos
(Scrum Master, Product Owner y el equipo de desarrollo) y eventos como la planeación del sprint y la retrospectiva, de modo que el producto se entregue en incrementos pequeños y
frecuentes (Schwaber & Sutherland, 2020).

Estos marcos se apoyan en distintos modelos de ciclo de vida:

- **Predictivo (en cascada):** se planea todo al inicio y se avanza por fases secuenciales (requisitos -> diseño -> construcción -> pruebas), lo que funciona cuando los requisitos son estables
   pero no es flexible ante cambios (Sommerville, 2004).
- **Iterativo:** el producto se construye en versiones sucesivas que se refinan poco a poco, cada iteración mejora la anterior (Pressman, 2009).
- **Ágil:** entregas cortas y frecuentes, con retroalimentación constante del cliente y apertura al cambio. Scrum es el marco más utilizado y difundido (Schwaber & Sutherland, 2020).

**¿Cuál elegiría para un proyecto como el del curso?** Para un proyecto pequeño, de corta duración y donde los requisitos y herramientas necesarias se pueden ir entendiendo sobre la 
marcha debido a la poca experiencia de los integrantes del equipo de desarrollo, elegiría un enfoque ágil como Scrum, esto nos permitiría entregar algo funcional pronto, 
recibir correcciones del profesor y ajustar lo necesario, cosa que un modelo predictivo no facilita cuando aún no se tiene claro el alcance definitivo.

> **Fuentes:** Project Management Institute (2021); Schwaber & Sutherland (2020); Sommerville
> (2004); Pressman (2009).

### 3. ¿Con qué herramientas?

En el desarrollo de software se usan varias familias de herramientas:

- **Control de versiones**: registra cada cambio del código y su autor, permite volver a estados anteriores y que varias personas trabajen sobre el mismo proyecto sin problemas
  (Chacon & Straub, 2014).
- **Tableros de trabajo**: hacen visible el trabajo pendiente, en curso y terminado, y ayudan al equipo a coordinarse (Schwaber & Sutherland,2020).
- **Contenedores**: empaquetan una aplicación con todo lo que necesita para correr, de modo que funcione igual en cualquier máquina (Docker Inc., s.f.).
- **Integración continua (CI):** automatiza la compilación y las pruebas cada vez que se sube un cambio para detectar errores pronto (Sommerville, 2004).

**Herramientas del curso:**

- **Docker vs máquina virtual:** una Virtual Machien virtualiza un sistema operativo completo sobre un hipervisor, por lo que es pesada y lenta de arrancar. Un contenedor
  comparte el núcleo del sistema anfitrión y solo aísla la aplicación y sus dependencias, por lo que es mucho más ligero y rápido (Docker Inc., s.f.).
- **Dockerfile vs `compose.yaml`:** el Dockerfile son las instrucciones para construir una imagen por primera vez (qué sistema base usar, qué instalar, qué copiar). El `compose.yaml`
  describe cómo levantar y orquestar uno o varios servicios ya definidos (como qué imagen usar, puertos, volúmenes, variables), y permite arrancarlos juntos con un solo comando (Docker
  Inc., s.f.).
- **El volumen:** es el mecanismo con el que Docker conserva los datos fuera del contenedor, de manera que si el contenedor es borrado, los datos permanecen (Docker Inc., s.f.).
- **Comandos de Docker Compose usados en la tarea:**

  | Comando | Qué hace |
  |---|---|
  | `docker compose up -d` | Levanta los servicios en segundo plano y devuelve el cursor (*detached*). |
  | `docker compose exec` | Ejecuta un comando dentro de un contenedor que ya está corriendo. |
  | `docker compose stop` | Detiene los servicios sin borrarlos. |
  | `docker compose down` | Detiene y elimina los contenedores (y su red). |
  | `docker compose ps` | Muestra el estado de los servicios. |
  | `docker compose logs` | Muestra los registros (salida) de los servicios. |

> **Fuentes:** Docker Inc. (s.f.); Chacon & Straub (2014); Sommerville (2004); Schwaber &
> Sutherland (2020).

### 4. ¿Bajo qué licencia se distribuye el software?

Toda pieza de software se distribuye con una licencia que define qué puede hacer quien la recibe (usarla, modificarla, redistribuirla, venderla) y bajo qué obligaciones (Open Source
Initiative [OSI], s.f.).

#### a) Los dos grandes tipos

- **Permisivas** (MIT, BSD, Apache 2.0): imponen pocas condiciones, suelen pedir únicamente que se conserve el aviso de copyright y la propia licencia y permiten usar el código, incluso en
  software privativo (OSI, s.f.).
- **Copyleft** (GPL, LGPL, AGPL): permiten usar y modificar, pero obligan a que las obras derivadas se distribuyan bajo la misma licencia, manteniendo el código abierto "hacia
  adelante" (GNU Project, s.f.).

| Licencia | Tipo | Permite | Exige |
|---|---|---|---|
| **MIT** | Permisiva | Usar, copiar, modificar, redistribuir y vender, incluso en proyectos privativos | Conservar el aviso de copyright y el texto de la licencia |
| **Apache 2.0** | Permisiva | Lo mismo que MIT, con concesión expresa de patentes | Conservar avisos y dejar constancia de los cambios |
| **GPL** | Copyleft (fuerte) | Usar, modificar y redistribuir | Que todo derivado se publique también bajo GPL, con el código fuente disponible |
| **LGPL** | Copyleft (débil) | Enlazar la biblioteca desde software privativo | Liberar bajo LGPL solo las modificaciones a la propia biblioteca |
| **AGPL** | Copyleft (fuerte, para red) | Usar, modificar y redistribuir | Como GPL, y además liberar el código cuando el software se ofrece como servicio en red |

#### b) Mi elección: MIT

El repositorio usa la licencia MIT porque es permisiva, breve y personalmente fácil de entender, lo que la hizo ideal para este trabajo académico: permite que cualquiera lea, 
reutilice o aprenda del código con la mínima fricción, exigiendo solo que se conserve el aviso de autoría (OSI, s.f.). 
Si en cambio se hubiera elegido GPL, cualquier proyecto que reutilizara este código estaría obligado a publicarse también bajo GPL y a mantener su código abierto; 
eso protege la libertad del software "hacia adelante", pero limita que el código pueda integrarse en proyectos privativos (GNU Project, s.f.).

#### c) Caso real: MySQL → Oracle y el nacimiento de MariaDB

MySQL fue creado por la empresa MySQL AB y distribuido bajo licencia GPL. En 2008 MySQL AB fue adquirida por Sun Microsystems y en 2010 Oracle compró Sun y con ella el control de
MySQL, ante el temor de que Oracle restringiera el desarrollo abierto del proyecto, Michael "Monty" Widenius (uno de los creadores originales) lo bifurcó (fork) y fundó MariaDB,
que mantiene compatibilidad con MySQL y sigue siendo libre (MariaDB Foundation, s.f.).

Ya que MySQL estaba bajo GPL, cualquiera tenía el derecho de tomar su código, modificarlo y redistribuirlo sin el permiso de Oracle, y fue justamente el copyleft de la GPL 
lo que permitió que la alternativa MariaDB pudiera crearse legalmente, hoy muchas distribuciones de Linux la incluyen en lugar de MySQL (GNU Project, s.f.; MariaDB Foundation, s.f.).

> **Fuentes:** Open Source Initiative (s.f.); GNU Project (s.f.); MariaDB Foundation (s.f.).

---

## Ejercicio 3. De PostgreSQL 17 a 18
 
### 1. Tabla de diferencias entre los dos contenedores

| Qué comparar | PostgreSQL 17 | PostgreSQL 18 | Por qué cambió |
|---|---|---|---|
| **Nombre del archivo** | `docker-compose.yml` | `compose.yaml` | compose.yaml es el nombre que recomienda la Compose Specification, docker-compose.yml es el nombre antiguo, de cuando Compose era un programa aparte. |
| **Primera línea** | `version: '3.8'` | No hay | Compose V2 ignora la clave `version:` y avisa que es obsoleta (ya no hace falta). |
| **Imagen** | `postgres:17` | `FROM postgres:18.6` | Se actualiza a PostgreSQL 18 y se fija la versión completa (18.6). |
| **Datos** | `./data:/var/lib/postgresql/data` | `datos_db:/var/lib/postgresql` | PostgreSQL 18 cambió el punto de montaje de los datos, además se pasa de un *bind mount* a un volumen con nombre, más portable y administrado por Docker. |
| **Contraseña** | escrita: `postgres` | `${POSTGRES_PASSWORD:-...}` | Se saca la contraseña del archivo que se versiona y se maneja con un `.env` y un valor por defecto. |
| **Puerto** | `"5432:5432"` | `"127.0.0.1:5434:5432"` | Ahora solo se publica en localhost (es más seguro) y en el 5434, para no chocar con un PostgreSQL ya instalado en el 5432. |
| **¿Sabe si está lista?** | No | `healthcheck` | Docker comprueba con `pg_isready` que la base responde, no solo que el contenedor existe. |
| **Interfaz web** | No | Adminer | Se agrega Adminer para ver y consultar la base desde el navegador. |
| **La carpeta del proyecto, dentro** | No, sólo `data/` | `./:/trabajo` | Monta el proyecto dentro del contenedor para poder trabajar en él y correr los scripts de `extras/`. | 

### 2. ¿Se usaba el Dockerfile viejo?
 
No, en el `docker-compose.yml` de PostgreSQL 17 el servicio se define con `image: postgres:17` y no aparece la clave `build:`, lo que significa que Compose descargaba directamente la imagen oficial `postgres:17` desde el registro y nunca construía nada a partir del Dockerfile. El Dockerfile de la carpeta `1-postgres17/` quedaba ignorado, en cambio, el nuevo `compose.yaml` sí incluye `build: .`, por lo que ahora la imagen sí se construye a partir del Dockerfile (Docker Inc., s.f.).
 
### 3. Versionado semántico y por qué pasar de la 17 a la 18 es un cambio mayor
 
El versionado semántico (*SemVer*) es una convención para numerar versiones con el formato MAYOR.MENOR.PARCHE, donde cada número se incrementa según el tipo de cambio (Preston-Werner, s.f.):
 
- **MAYOR:** cambios incompatibles con versiones anteriores.
- **MENOR:** se añade funcionalidad de forma compatible hacia atrás.
- **PARCHE:** correcciones de errores compatibles hacia atrás.
Pasar de PostgreSQL 17 a 18 es un cambio mayor porque sube el primer número de la versión e introduce cambios que rompen la compatibilidad, el mayor ejemplo en esta tarea es que PostgreSQL 18 cambió el punto de montaje de los datos (de `/var/lib/postgresql/data` a `/var/lib/postgresql`), de modo que un contenedor configurado para la 17 ya no arranca tal cual en la 18. Por eso el `!` del mensaje de confirmación (`build!: actualiza el contenedor a PostgreSQL 18`) señala un cambio que rompe la compatibilidad (Preston-Werner, s.f.; Docker Inc., s.f.).
 
> **Fuentes:** Docker Inc. (s.f.); Preston-Werner (s.f.).

---

## Referencias

Chacon, S., & Straub, B. (2014). *Pro Git* (2.ª ed.). Apress. https://git-scm.com/book/es/v2

Docker Inc. (s.f.). *Docker documentation*. Recuperado el 15 de octubre de 2026, de https://docs.docker.com

GNU Project. (s.f.). *Licencias — Proyecto GNU*. Recuperado el 15 de octubre de 2026, de https://www.gnu.org/licenses/

Lewis, J. P. (2007). *Fundamentals of project management* (3.ª ed.). AMACOM.

MariaDB Foundation. (s.f.). *About MariaDB Foundation*. Recuperado el 15 de octubre de 2026, de https://mariadb.org/about/

Open Source Initiative. (s.f.). *Licenses & standards*. Recuperado el 15 de octubre de 2026, de https://opensource.org/licenses

Pressman, R. S. (2009). *Software engineering: A practitioner's approach* (7.ª ed.). McGraw-Hill.

Project Management Institute. (2021). *A guide to the project management body of knowledge (PMBOK guide)* (7.ª ed.). PMI.

Schwaber, K., & Sutherland, J. (2020). *La guía de Scrum*. https://scrumguides.org

Sommerville, I. (2004). *Ingeniería de software* (7.ª ed.). Addison Wesley.
 
---

## Auditoría de Inteligencia Artificial

Para esta tarea se utilizó el asistente de inteligencia artificial Claude (Anthropic) como apoyo en el formato de las citas, redacción de ideas de la investigación.



