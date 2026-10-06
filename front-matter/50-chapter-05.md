# Capítulo V: Product Implementation, Validation & Deployment

## 5.1 Software Configuration Management

La gestión del proyecto incluye el código fuente, documentación, prototipos y configuraciones del entorno de desarrollo de la plataforma web de localización y reserva de estacionamientos. El proyecto contempla distintos productos digitales, incluyendo una Landing Page institucional, una aplicación web interactiva de tipo marketplace para conductores y propietarios de cocheras, y servicios backend orientados al procesamiento en tiempo real de ubicaciones, disponibilidad y gestión de reservas. El equipo adopta prácticas basadas en GitFlow, Conventional Commits y Semantic Versioning, asegurando un flujo de trabajo colaborativo y organizado.

### 5.1.1. Software Development Environment Configuration

| Categoría / Actividad | Nombre del Producto | Propósito de Uso en el Proyecto | Tipo / Plataforma | Ruta de Referencia / Descarga |
|---|---|---|---|---|
| Project Management | Trello | Gestión e itinerario de tareas del proyecto mediante tableros organizados por estados (To-Do, In Progress, Done), clave para el seguimiento de entregables como el reporte y la landing page. | SaaS | https://trello.com |
| Team Communication | Discord | Plataforma principal de comunicación remota para la realización de reuniones de equipo sincrónicas, planificación de Sprints y coordinación general. | SaaS / Desktop | https://discord.com/ |
| Requirements Management | Miro | Estructuración de ideas, diagramación de flujos de sistema, análisis del negocio y ejecución de la sesión de Event Storming para el ecosistema IoT. | SaaS | https://miro.com |
| Requirements Management | Structurizr | Modelado de la arquitectura de software del sistema DomotiCore bajo el modelo C4, representando los componentes clave (dashboard, gateway, nodos IoT y servicios de monitoreo). | SaaS / Desktop | https://structurizr.com |
| Product UX/UI Design | Figma | Diseño visual y prototipado interactivo de las interfaces del sistema, incluyendo el dashboard centralizado, paneles de control de dispositivos y visualización de consumo energético. | SaaS / Desktop | https://www.figma.com |
| Product UX/UI Design | Lucidchart | Elaboración de diagramas de flujo de trabajo, arquitectura técnica y diseño de procesos operativos del sistema. | SaaS | https://www.lucidchart.com |
| Software Development | HTML5 / CSS3 / JavaScript | Lenguajes y estándares base utilizados para el desarrollo del frontend web, las interfaces de usuario y la Landing Page del producto. | Lenguajes / Estándares | https://developer.mozilla.org/es/docs/Web |
| Software Development | WebStorm | Entorno de desarrollo integrado (IDE) principal utilizado para la programación, edición y depuración del código fuente del frontend. | Desktop | https://www.jetbrains.com/webstorm/download |
| Software Testing | Gherkin | Lenguaje de especificación para definir escenarios de prueba BDD (Behavior-Driven Development) basados en historias de usuario (control remoto, automatizaciones por horario y alertas de consumo). | Estándar / DSL | https://cucumber.io/docs/gherkin/reference |
| Software Documentation | GitHub | Repositorio central del proyecto para el control de versiones distribuido, registro de commits, trabajo colaborativo y alojamiento de la documentación del sistema. | SaaS | https://github.com |
| Software Deployment | GitHub Pages | Servicio de alojamiento y despliegue continuo para la Landing Page pública del producto, permitiendo exponer la propuesta de valor de DomotiCore. | SaaS | https://pages.github.com |


### 5.1.2. Source Code Management

La administración del código fuente del proyecto ParkShare se fundamenta en el uso de Git como sistema de control de versiones distribuido, alojado en la plataforma GitHub dentro de la organización oficial de la startup ACME Industries. Con el propósito de asegurar un flujo de trabajo ágil, colaborativo y trazable, el desarrollo del ecosistema digital se organiza mediante repositorios independientes para cada componente de la arquitectura (Landing Page, Frontend Web Application)

Estrategia de Branching (GitFlow)
Para gestionar de forma ordenada el ciclo de vida del software, el equipo adopta una adaptación del modelo GitFlow, estructurando el desarrollo a través de las siguientes ramas:

main: Constituye la rama de producción. Aloja únicamente código estable, auditado y listo para ser desplegado en los entornos finales. Cada versión liberada se asocia con etiquetas de versión semántica (ej. v1.0.0).

develop: Funciona como la rama principal de integración continua. En ella se consolidan todas las funcionalidades completadas y verificadas durante el sprint antes de su paso a producción.

feature/[nombre]: Ramas de trabajo temporal creadas a partir de develop para la construcción de User Stories específicas (ej. feature/US27-landing-drivers). Al culminar la tarea, el código se integra a develop mediante un Pull Request (PR) sujeto a revisión de pares.

Convención de Commits (Conventional Commits)

Para mantener un historial claro, consistente y facilitar la generación automática de changelogs, todos los commits deberán seguir el estándar de Conventional Commits:

Tipos permitidos

* **feat: Nueva funcionalidad**
(ej. feat(ordering): add automated order validation policy)

* **fix: Corrección de errores**
(ej. fix(auth): resolve token expiration on mobile devices)

* **docs: Cambios en documentación**
(ej. docs(interviews): update stakeholder interview records)



### 5.1.3. Source Code Style Guide and Conventions

Con el propósito de asegurar la legibilidad, mantenibilidad y coherencia arquitectónica en el código fuente del frontend de ParkShare, el equipo de ACME Industries establece un conjunto de directrices normativas de estilo. Estas convenciones garantizan un desarrollo modular, reducen la deuda técnica y facilitan el trabajo colaborativo entre los integrantes del equipo durante el desarrollo de la Landing Page y la Web Application.

Directrices para el Frontend (Angular / TypeScript)
El desarrollo del cliente web se fundamenta en las guías oficiales de estilo de Angular y las mejores prácticas del lenguaje TypeScript.

**Nomenclatura y Convenciones de Archivos:** 

- Componentes, Servicios y Módulos: Nombres de archivo en sintaxis kebab-case acompañados de su tipo explícito.

- Clases, Interfaces y Modelos: Redacción en PascalCase para la declaración de clases e interfaces de datos mock / modelos de interfaz.

- Variables y Métodos: Uso de camelCase para la declaración de propiedades, atributos y funciones.

- Constantes: Formato UPPER_SNAKE_CASE para valores inmutables o datos de prueba locales.

**Estructura y Arquitectura de la Aplicación Web:**

- Organización por Capas/Módulos: Distribución clara del código dividida en carpetas funcionales (components, services, models, guards, assets).

- Diseño Modular y Reutilización: Separación entre componentes de maquetación/UI (tarjetas de parqueos, filtros, encabezados) y servicios locales encargados de manejar el estado temporal de la interfaz.

**Estructura y Estilos Visuales (HTML / CSS):**

Uso de Flexbox y CSS Grid: Estructuración de pantallas adaptables (responsive) mediante grillas flexibles alineadas con las guías de diseño para dispositivos móviles y de escritorio.

**Calidad y Formateo de Código:**

Análisis Estático: Integración de ESLint con reglas de TypeScript (typescript-eslint) para asegurar el tipado explícito, evitar variables no utilizadas y mantener la limpieza en los componentes de Angular.


### 5.1.4. Software Deployment Configuration
En esta sección se detalla el procedimiento de configuración del entorno de despliegue para los productos digitales del proyecto ParkShare, describiendo los pasos técnicos requeridos para publicar el código fuente alojado en el repositorio oficial.

Para la presente entrega, la estrategia de distribución se apoya en la infraestructura de GitHub, utilizando el servicio GitHub Pages para la publicación y alojamiento del contenido web de la plataforma.

**Landing Page y Documentación del Proyecto**

La publicación pública de la Landing Page (desarrollada con el marco de trabajo Angular) y del informe técnico del proyecto se ejecuta a través de GitHub Pages, siguiendo el flujo operativo que se describe a continuación:

- Estructuración del Repositorio: Creación e inicialización del repositorio remoto bajo la organización oficial de la startup (ACME Industries).

- Compilación de Producción: Ejecución del comando de construcción en Angular para generar los artefactos finales optimizados de producción (archivos estáticos HTML, JavaScript y CSS) dentro del directorio objetivo (dist/learning-center/browser o equivalente del proyecto).

- Gestión de Ramas de Despliegue: Configuración del flujo de publicación asociando la rama principal (main) o la rama especializada de distribución (gh-pages).


- Aprovisionamiento del Servicio: Activación y validación de la fuente de publicación desde la sección de ajustes (Settings > Pages) del repositorio en GitHub.

- Emisión de Dominio Público: Generación automática de la URL pública cifrada mediante protocolo HTTPS para el acceso al sitio.



## 5.2. Landing Page, Services & Applications Implementation
En esta seccion se va a describir el proceso de implementacion del Proyecto ParkShare, donde se incluira el desarrollo, documentacion y despliegue del Landing Page.

Para este avance se implemento la primera version del Landing Page. El desarrollo se realizo utilizando GitHub como herramienta de control de versiones.

### 5.2.1. Sprint 1
En esta seccion se presentara el avance del Sprint 1 en terminos de desarrollo del producto y el trabajo colaborativo del equipo.

Durante este sprint se realizo la implementacion de la primera version del Landing Page, que se enfocara en presenta la propuesta de valor del sistema.

Asimismo se incluiran evidencias relacionadas con la planificacion del sprint, la organizacion del equipo, el desarrollo realizado, asi como los resultados obtenidos y la colaboracion.

#### 5.2.1.1. Sprint Planning 1
En esta seccion se describen los principales acuerdos y definiciones realizadas durante el Sprint Planning del Sprint 1, donde nos enfocaremos en la implementacion del Landing Page.

 Campo | Detalle |
|------|--------|
| **Sprint #** | Sprint 1 |
| **Sprint Planning Background** |  |
| Date | 2026-09-26 |
| Time | 16:30 |
| Location | Reunión virtual (Discord) |
| Prepared By | Daril Johan Palomino Vilcañaupa |
| Attendees (to planning meeting) | Palomino Vilcañaupa, Daril Johan -  Tello Palacios, Fabrizio Rafael - Checa Burga, Oscar Diego - Yanac Flores, Gabriel Stefano - Urviola Condori, Mateo Sebastian |
| **Sprint 1 – Review Summary** | En esta entrega se tomo encuenta el Product Backlog definido y los diseños web de la landing page. |
| **Sprint 1 – Retrospective Summary** | Para esta entrega no se aplico. No obstante, el equipo se enfoco en la distribucion de tareas y comunicacion constante. |
| **Sprint Goal & User Stories** |  |
| Sprint 1 Goal | Our goal is to build a fully functional and responsive landing page that clearly communicates ACME Industries' value proposition through its ParkShare solution. We believe this site will allow potential customers to accurately understand the product's benefits. We will confirm the success of this objective when users can view the platform, navigate smoothly between its main sections, and access it correctly from any device. |
| User Stories incluidas en el Sprint | US31: Visualizar Landing Page; US32: Navegar entre secciones del Landing Page; US33: Visualización responsive del Landing Page |
| **Sprint 1 speed of work** | 9 Story Points |
| **The sum of history points** | 9 Story Points |

-------

| Campo | Detalle |
| :--- | :--- |
| **Sprint Goal & User Stories** | |
| **Sprint 1 Goal** | Nuestro objetivo se enfoca en construir una Landing Page totalmente funcional y adaptativa que comunique con claridad la propuesta de valor de ParkShare para conductores y propietarios[cite: 173, 174]. Consideramos que esto permitirá a los visitantes comprender de forma precisa los beneficios del servicio[cite: 173, 174]. Confirmaremos el éxito de este objetivo cuando los usuarios puedan explorar el sitio público, interactuar sin fricciones entre sus secciones principales y acceder de manera óptima desde cualquier dispositivo[cite: 63, 64]. |
| **User Stories incluidas en el Sprint** | **US27**: Información para conductores en el Landing Page; **US28**: Información para propietarios en el Landing Page; **US29**: Información sobre funcionamiento y confianza; **US30**: Redirección desde el Landing Page a la Web Application. |
| **Sprint 1 Velocity** | 8 Story Points |
| **Sum of Story Points** | 8 Story Points |

#### 5.2.1.2. Aspect Leaders and Collaborators

#### 5.2.1.3. Sprint Backlog 1

#### 5.2.1.4. Development Evidence for Sprint Review

#### 5.2.1.5.  Execution Evidence for Sprint Review

En el Sprint 1 se logró implementar con éxito la Landing Page de ParkShare (desarrollada por ACME Industries), permitiendo comunicar de forma transparente y efectiva la propuesta de valor de la plataforma tanto para conductores que buscan estacionamiento como para propietarios de cocheras privadas en Lima.

A continuación, se presentan las evidencias visuales que respaldan las principales vistas y componentes implementados durante este Sprint:

Link de la Pagina Web: https://1asi0729-7793-parkshare.github.io/landing-page-ParkShare/ 

Screenshots del Landing Page

Vista General(Hero + Navbar)

![HERO + NAVBAR](../report/assets/landing1.png)

 Vista Demo de Cocheras(Demo)

![COCHERAS DISPONIBLES](../report/assets/landing2.png)

 Videos de Demo(Demo)

![Demo](../report/assets/landing3.png)

Planes del Producto

![Planes](../report/assets/landing4.png)

Pasos de Reserva

![Pasos](../report/assets/landing5.png)

Beneficios

![Beneficios](../report/assets/landing6.png)

About the Team

![Team](../report/assets/landing7.png)

Seccion Footer + Questions

![footer](../report/assets/landing8.png)




