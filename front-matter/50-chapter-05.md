# Capítulo V: Product Implementation, Validation & Deployment

## 5.1 Software Configuration Management

La gestión del proyecto incluye el código fuente, documentación, prototipos y configuraciones del entorno de desarrollo de la plataforma web de localización y reserva de estacionamientos. El proyecto contempla distintos productos digitales, incluyendo una Landing Page institucional, una aplicación web interactiva de tipo marketplace para conductores y propietarios de cocheras, y servicios backend orientados al procesamiento en tiempo real de ubicaciones, disponibilidad y gestión de reservas. El equipo adopta prácticas basadas en GitFlow, Conventional Commits y Semantic Versioning, asegurando un flujo de trabajo colaborativo y organizado.

### 5.1.1. Software Development Environment Configuration

| Categoría / Actividad   | Nombre del Producto       | Propósito de Uso en el Proyecto                                                                                                                                                                     | Tipo / Plataforma      | Ruta de Referencia / Descarga               |
| ----------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | ------------------------------------------- |
| Project Management      | Trello                    | Gestión e itinerario de tareas del proyecto mediante tableros organizados por estados (To-Do, In Progress, Done), clave para el seguimiento de entregables como el reporte y la landing page.       | SaaS                   | https://trello.com                          |
| Team Communication      | Discord                   | Plataforma principal de comunicación remota para la realización de reuniones de equipo sincrónicas, planificación de Sprints y coordinación general.                                                | SaaS / Desktop         | https://discord.com/                        |
| Requirements Management | Miro                      | Estructuración de ideas, diagramación de flujos de sistema, análisis del negocio y ejecución de la sesión de Event Storming para el ecosistema IoT.                                                 | SaaS                   | https://miro.com                            |
| Requirements Management | Structurizr               | Modelado de la arquitectura de software del sistema ParkShare bajo el modelo C4, representando los componentes clave (dashboard, gateway, nodos IoT y servicios de monitoreo).                      | SaaS / Desktop         | https://structurizr.com                     |
| Product UX/UI Design    | Figma                     | Diseño visual y prototipado interactivo de las interfaces del sistema, incluyendo el dashboard centralizado, paneles de control de dispositivos y visualización de consumo energético.              | SaaS / Desktop         | https://www.figma.com                       |
| Product UX/UI Design    | Lucidchart                | Elaboración de diagramas de flujo de trabajo, arquitectura técnica y diseño de procesos operativos del sistema.                                                                                     | SaaS                   | https://www.lucidchart.com                  |
| Software Development    | HTML5 / CSS3 / JavaScript | Lenguajes y estándares base utilizados para el desarrollo del frontend web, las interfaces de usuario y la Landing Page del producto.                                                               | Lenguajes / Estándares | https://developer.mozilla.org/es/docs/Web   |
| Software Development    | WebStorm                  | Entorno de desarrollo integrado (IDE) principal utilizado para la programación, edición y depuración del código fuente del frontend.                                                                | Desktop                | https://www.jetbrains.com/webstorm/download |
| Software Testing        | Gherkin                   | Lenguaje de especificación para definir escenarios de prueba BDD (Behavior-Driven Development) basados en historias de usuario (control remoto, automatizaciones por horario y alertas de consumo). | Estándar / DSL         | https://cucumber.io/docs/gherkin/reference  |
| Software Documentation  | GitHub                    | Repositorio central del proyecto para el control de versiones distribuido, registro de commits, trabajo colaborativo y alojamiento de la documentación del sistema.                                 | SaaS                   | https://github.com                          |
| Software Deployment     | GitHub Pages              | Servicio de alojamiento y despliegue continuo para la Landing Page pública del producto, permitiendo exponer la propuesta de valor de ParkShare.                                                    | SaaS                   | https://pages.github.com                    |

### 5.1.2. Source Code Management

Para la gestión del código fuente y de los artefactos asociados al proyecto ParkShare, el equipo utiliza Git como sistema de control de versiones distribuido y GitHub como plataforma central para el almacenamiento de repositorios, seguimiento de cambios y coordinación del trabajo colaborativo.

El proyecto se encuentra organizado dentro de la organización de GitHub **1ASI0729-7793-ParkShare**, donde se mantienen repositorios independientes para la documentación del proyecto, la Landing Page y la aplicación web.

Los principales repositorios utilizados son los siguientes:

| Repositorio            | Propósito                                                                                                             | Enlace                                                            |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Proyect-Park-Share     | Almacena el informe académico, documentación, assets, diagramas, wireframes, mockups y demás artefactos del proyecto. | https://github.com/1ASI0729-7793-ParkShare/Proyect-Park-Share     |
| landing-page-ParkShare | Contiene el código fuente correspondiente a la Landing Page de ParkShare.                                             | https://github.com/1ASI0729-7793-ParkShare/landing-page-ParkShare |
| ParkShare-frotend      | Contiene el código fuente de la aplicación web principal desarrollada con Angular.                                    | https://github.com/1ASI0729-7793-ParkShare/ParkShare-frotend      |

El equipo utiliza una estrategia de branching basada en una adaptación de **GitFlow**, con una rama principal estable, una rama de integración y ramas temporales para el desarrollo de funcionalidades específicas.

La estructura general seguida es la siguiente:

```text
main
  │
  └── develop
       ├── feature/*
       ├── docs/*
       └── otras ramas de trabajo
```

La rama `main` contiene las versiones consolidadas y listas para ser consideradas como entregables estables del proyecto. Por otro lado, la rama `develop` se utiliza como punto de integración de los cambios desarrollados por los integrantes del equipo antes de incorporarlos a `main`.

Para implementar nuevas funcionalidades, cada integrante crea una rama independiente a partir de `develop`, utilizando un nombre descriptivo relacionado con la funcionalidad o bounded context asignado.

En el repositorio del frontend, por ejemplo, se han utilizado ramas como:

```text
feature/identity-and-access
feature/parking-space-management
feature/reputation&notifications
```

Cada una de estas ramas representa un conjunto funcional independiente de la aplicación. De esta manera, el desarrollo de un bounded context puede realizarse sin interferir directamente con el trabajo de otros integrantes.

El flujo de trabajo seguido para una nueva funcionalidad es el siguiente:

```text
develop
   │
   ├── feature/identity-and-access
   │
   ├── feature/parking-space-management
   │
   └── feature/reputation&notifications
          │
          ▼
       desarrollo
          │
          ▼
   integración en develop
          │
          ▼
         main
```

Antes de comenzar el desarrollo de una funcionalidad, el integrante actualiza la rama `develop` y crea su rama de trabajo:

```bash
git checkout develop
git pull origin develop
git checkout -b feature/nombre-de-la-feature
```

Una vez completados y verificados los cambios, estos se registran mediante commits y se envían al repositorio remoto:

```bash
git add .
git commit -m "feat(scope): description"
git push origin feature/nombre-de-la-feature
```

Posteriormente, la funcionalidad es integrada nuevamente a `develop`, donde puede ser validada junto con los demás componentes del sistema.

Durante el desarrollo de la aplicación web, por ejemplo, el bounded context **Parking Space Management** fue trabajado inicialmente en la rama:

```text
feature/parking-space-management
```

y posteriormente integrado a `develop`, permitiendo consolidar funcionalidades relacionadas con la publicación, edición, disponibilidad y tarifas de espacios de estacionamiento.

Para la nomenclatura de commits se emplea la convención **Conventional Commits**, con el objetivo de mantener un historial de cambios claro y fácilmente interpretable. Algunos prefijos utilizados son:

| Prefijo    | Uso                                                                       |
| ---------- | ------------------------------------------------------------------------- |
| `feat`     | Incorporación de una nueva funcionalidad.                                 |
| `fix`      | Corrección de errores o problemas de funcionamiento.                      |
| `style`    | Cambios visuales o de formato que no modifican la lógica principal.       |
| `docs`     | Modificaciones relacionadas con documentación.                            |
| `refactor` | Reorganización o mejora del código sin alterar su comportamiento externo. |
| `test`     | Incorporación o modificación de pruebas.                                  |
| `chore`    | Cambios de mantenimiento, configuración o tareas auxiliares.              |

Algunos ejemplos de commits realizados durante el desarrollo son:

```text
feat(parking-space): implement parking space management flow
style(parking-space): align typography with design guidelines
feat(parking-space): align management dashboard with mockup 7
fix: align parking-space routes to owner area
feat: add parking space title and features
```

Además del uso de ramas `feature`, el repositorio de documentación emplea ramas específicas para actividades relacionadas con el informe. Entre ellas se encuentran:

```text
docs/interview-design
feature/competitive-analysis
feature/needfinding
```

Esta organización permite separar el trabajo de documentación del desarrollo de software, manteniendo un historial independiente y facilitando la integración progresiva de los avances.

En conjunto, esta estrategia de gestión de código permite al equipo reducir conflictos entre integrantes, mantener trazabilidad sobre los cambios realizados, aislar el desarrollo de funcionalidades y consolidar de forma progresiva versiones estables del producto.

### 5.1.3. Source Code Style Guide & Conventions

Para mantener consistencia, legibilidad y facilidad de mantenimiento en el código fuente de ParkShare, el equipo adopta convenciones de estilo aplicadas principalmente al desarrollo de la aplicación web en Angular y TypeScript. Estas convenciones se apoyan tanto en la estructura del proyecto como en archivos de configuración presentes en el repositorio, entre ellos `.editorconfig`, `.prettierrc` y `tsconfig.json`.

El objetivo de estas reglas es asegurar que los distintos integrantes puedan trabajar sobre bounded contexts separados manteniendo una base de código homogénea y fácil de integrar.

#### Convenciones generales de formato

El repositorio utiliza `.editorconfig` para establecer reglas básicas de formato entre distintos editores e IDE. Las principales configuraciones utilizadas son:

| Regla                                | Convención             |
| ------------------------------------ | ---------------------- |
| Codificación                         | UTF-8                  |
| Indentación                          | Espacios               |
| Tamaño de indentación                | 2 espacios             |
| Nueva línea al final del archivo     | Obligatoria            |
| Espacios en blanco al final de línea | Eliminados             |
| Comillas en TypeScript               | Comillas simples       |
| Longitud máxima en Markdown          | Sin límite configurado |

Adicionalmente, el proyecto incluye una configuración de **Prettier** mediante `.prettierrc`. Las principales reglas definidas son:

```json
{
  "printWidth": 100,
  "singleQuote": true,
  "overrides": [
    {
      "files": "*.html",
      "options": {
        "parser": "angular"
      }
    }
  ]
}
```

Por lo tanto, el código TypeScript utiliza preferentemente comillas simples y una longitud de línea objetivo de 100 caracteres. Los archivos HTML se formatean utilizando el parser específico de Angular.

#### Convenciones de nombres

El proyecto utiliza nombres en inglés para los elementos internos del código fuente con el fin de mantener coherencia con las convenciones del framework y con el lenguaje ubicuo utilizado en la arquitectura.

Las principales convenciones son:

| Elemento                  | Convención                    | Ejemplo                       |
| ------------------------- | ----------------------------- | ----------------------------- |
| Clases                    | PascalCase                    | `ParkingSpaceManagementStore` |
| Entidades                 | PascalCase                    | `ParkingSpace`                |
| Interfaces y tipos        | PascalCase                    | `ParkingSpaceFeature`         |
| Métodos                   | camelCase                     | `loadParkingSpaces()`         |
| Variables                 | camelCase                     | `parkingSpaces`               |
| Constantes globales       | UPPER_SNAKE_CASE              | `PARKING_SPACE_FEATURES`      |
| Archivos                  | kebab-case                    | `parking-space.entity.ts`     |
| Carpetas                  | kebab-case                    | `parking-space-management`    |
| Selectores de componentes | kebab-case con prefijo `app-` | `app-parking-space-card`      |
| Rutas                     | kebab-case                    | `/parking-spaces`             |

Los nombres deben ser descriptivos y representar claramente su responsabilidad dentro del bounded context.

#### Organización por bounded contexts

El frontend se organiza siguiendo una separación por contextos funcionales. Cada bounded context mantiene sus propias responsabilidades y evita depender directamente de detalles internos pertenecientes a otros contextos.

Ejemplo:

```text
src/app/
├── parking-space-management/
├── profile/
└── shared/
```

Dentro de bounded contexts como **Parking Space Management**, el código se separa en capas:

```text
parking-space-management/
├── domain/
├── application/
├── infrastructure/
└── presentation/
```

Esta estructura permite distinguir entre reglas de dominio, coordinación de casos de uso, acceso a datos e interfaz de usuario.

Las responsabilidades generales de las capas son:

| Capa             | Responsabilidad                                                 |
| ---------------- | --------------------------------------------------------------- |
| `domain`         | Entidades, tipos y reglas propias del dominio.                  |
| `application`    | Stores, contratos y coordinación de casos de uso.               |
| `infrastructure` | Persistencia, acceso a API, repositorios y adaptación de datos. |
| `presentation`   | Componentes, páginas, formularios, validadores y rutas.         |

Los elementos reutilizables que no pertenecen exclusivamente a un bounded context se ubican en `shared`.

#### Convenciones para Angular

La aplicación utiliza Angular con componentes standalone. Cada componente mantiene separados sus archivos de TypeScript, HTML, CSS y pruebas.

Ejemplo:

```text
parking-space-card/
├── parking-space-card.ts
├── parking-space-card.html
├── parking-space-card.css
└── parking-space-card.spec.ts
```

La declaración de un componente sigue la estructura estándar del proyecto:

```ts
@Component({
  selector: "app-parking-space-card",
  imports: [],
  templateUrl: "./parking-space-card.html",
  styleUrl: "./parking-space-card.css",
})
export class ParkingSpaceCard {}
```

Se evita concentrar lógica de negocio dentro de los componentes visuales. La capa de presentación debe delegar operaciones de estado y casos de uso hacia la capa `application`.

#### Manejo de estado

Para el manejo de estado local de los bounded contexts se emplean las capacidades reactivas de Angular, principalmente **Signals**.

Un store puede exponer estados de solo lectura como:

```ts
readonly parkingSpaces = this.parkingSpacesSignal.asReadonly();
readonly loading = this.loadingSignal.asReadonly();
readonly error = this.errorSignal.asReadonly();
```

Este enfoque permite mantener el estado centralizado dentro de la capa `application` y evita que los componentes modifiquen directamente la información almacenada.

Cuando un valor depende de otro estado reactivo, se puede utilizar `computed()`.

#### Formularios y validación

Para los formularios de la aplicación se utiliza **Reactive Forms**, lo que permite mantener las reglas de validación de forma explícita y tipada.

Ejemplo:

```ts
protected readonly form = this.formBuilder.nonNullable.group({
  name: ['', [Validators.required, Validators.maxLength(100)]],
  address: ['', [Validators.required, Validators.maxLength(180)]],
  hourlyRate: [0, [Validators.required, Validators.min(0.01)]],
});
```

Cuando una validación involucra más de un campo, se utilizan validadores personalizados. Un ejemplo dentro del bounded context Parking Space Management es la validación de períodos de disponibilidad, donde la hora de inicio debe ser anterior a la hora de finalización.

#### Separación del acceso a datos

Los componentes de presentación no deben comunicarse directamente con `HttpClient` ni con mecanismos concretos de persistencia.

La comunicación debe mantener una separación similar a:

```text
Presentation
     ↓
Application
     ↓
Infrastructure
     ↓
API / Data Source
```

Esto permite sustituir una implementación temporal en memoria por una integración HTTP sin modificar la lógica de la interfaz.

Durante el desarrollo pueden utilizarse implementaciones de repositorio en memoria o servicios simulados, siempre que respeten los contratos definidos en la capa `application`.

#### Internacionalización

La aplicación utiliza `ngx-translate` para manejar textos en distintos idiomas. Los textos visibles para el usuario deben almacenarse en archivos de traducción en lugar de duplicarse directamente dentro de los templates.

Los archivos utilizados se encuentran en:

```text
public/i18n/
├── en.json
└── es.json
```

Ejemplo de uso en un template:

```html
<h1>{{ 'parkingSpace.create.title' | translate }}</h1>
```

También se utilizan claves jerárquicas para agrupar textos de acuerdo con el bounded context y la funcionalidad:

```json
{
  "parkingSpace": {
    "form": {
      "name": "Título",
      "address": "Dirección",
      "hourlyRate": "Tarifa por hora"
    }
  }
}
```

#### Estilos visuales

Los estilos específicos de un componente se mantienen en su archivo `.css` asociado, evitando mezclar estilos locales con configuraciones globales.

Para valores visuales compartidos se utilizan variables CSS definidas a nivel global cuando corresponde.

Ejemplo:

```css
color: var(--color-primary-dark);
background: var(--color-light-bg);
```

La aplicación utiliza Angular Material para distintos controles de interfaz, incluyendo formularios, botones, chips, iconos y otros elementos visuales.

Los componentes deben mantener coherencia con los lineamientos visuales establecidos en el capítulo de Style Guidelines y con los mockups definidos para ParkShare.

#### TypeScript y compilación estricta

El archivo `tsconfig.json` habilita diferentes verificaciones que favorecen un código más seguro y predecible.

Entre las opciones configuradas se encuentran:

```json
{
  "noImplicitOverride": true,
  "noPropertyAccessFromIndexSignature": true,
  "noImplicitReturns": true,
  "noFallthroughCasesInSwitch": true,
  "isolatedModules": true
}
```

Angular también mantiene configuraciones estrictas para inyección de dependencias e inputs:

```json
{
  "strictInjectionParameters": true,
  "strictInputAccessModifiers": true
}
```

Por ello, se procura utilizar tipos explícitos cuando ayudan a clarificar contratos y evitar el uso innecesario de `any`.

#### Pruebas

Los componentes y servicios pueden acompañarse de archivos `.spec.ts`. El proyecto incluye Vitest dentro de sus dependencias de desarrollo y dispone del comando:

```bash
npm test
```

Para validar que la aplicación puede compilar correctamente se utiliza:

```bash
npm run build
```

o su equivalente:

```bash
ng build
```

Antes de integrar una feature a `develop`, se recomienda comprobar al menos que el proyecto compile sin errores y que las pruebas asociadas a la funcionalidad modificada continúen funcionando.

#### Convenciones de commits

Como complemento de las convenciones de código, los commits siguen el enfoque de **Conventional Commits** descrito en la sección anterior.

Formato general:

```text
type(scope): description
```

Ejemplos:

```text
feat(parking-space): implement parking space management flow
fix(parking-space): align parking-space routes to owner area
style(parking-space): align typography with design guidelines
```

Los mensajes deben describir de forma breve la intención del cambio y mantener una relación clara con la funcionalidad modificada.

En conjunto, estas convenciones permiten mantener una base de código uniforme, reducir diferencias de estilo entre desarrolladores y facilitar la integración de cambios realizados en distintos bounded contexts del proyecto.

### 5.1.4. Software Deployment Configuration

En esta sección se detalla el procedimiento de configuración del entorno de despliegue para los productos digitales del proyecto ParkShare, describiendo los pasos técnicos requeridos para publicar el código fuente alojado en el repositorio oficial.

Para la presente entrega, la estrategia de distribución se apoya en la infraestructura de GitHub, utilizando el servicio GitHub Pages para la publicación y alojamiento del contenido web de la plataforma.

**Landing Page y Documentación del Proyecto**

La publicación pública de la Landing Page (desarrollada con el marco de trabajo Angular) y del informe técnico del proyecto se ejecuta a través de GitHub Pages, siguiendo el flujo operativo que se describe a continuación:

- Estructuración del Repositorio: Creación e inicialización del repositorio remoto bajo la organización oficial de la startup (ACME Industries).

- Compilación de Producción: Ejecución del comando de construcción en Angular para generar los artefactos finales optimizados de producción (archivos estáticos HTML, JavaScript y CSS) dentro del directorio objetivo (dist/ParkShare/browser o equivalente del proyecto).

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

| Campo                                | Detalle                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint #**                         | Sprint 1                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Sprint Planning Background**       |                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Date                                 | 2026-09-26                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Time                                 | 16:30                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Location                             | Reunión virtual (Discord)                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Prepared By                          | Daril Johan Palomino Vilcañaupa                                                                                                                                                                                                                                                                                                                                                                                                             |
| Attendees (to planning meeting)      | Palomino Vilcañaupa, Daril Johan - Tello Palacios, Fabrizio Rafael - Checa Burga, Oscar Diego - Yanac Flores, Gabriel Stefano - Urviola Condori, Mateo Sebastian                                                                                                                                                                                                                                                                            |
| **Sprint 1 – Review Summary**        | En esta entrega se tomo encuenta el Product Backlog definido y los diseños web de la landing page.                                                                                                                                                                                                                                                                                                                                          |
| **Sprint 1 – Retrospective Summary** | Para esta entrega no se aplico. No obstante, el equipo se enfoco en la distribucion de tareas y comunicacion constante.                                                                                                                                                                                                                                                                                                                     |
| **Sprint Goal & User Stories**       |                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Sprint 1 Goal                        | Our goal is to build a fully functional and responsive landing page that clearly communicates ACME Industries' value proposition through its ParkShare solution. We believe this site will allow potential customers to accurately understand the product's benefits. We will confirm the success of this objective when users can view the platform, navigate smoothly between its main sections, and access it correctly from any device. |
| User Stories incluidas en el Sprint  | US31: Visualizar Landing Page; US32: Navegar entre secciones del Landing Page; US33: Visualización responsive del Landing Page                                                                                                                                                                                                                                                                                                              |
| **Sprint 1 speed of work**           | 9 Story Points                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **The sum of history points**        | 9 Story Points                                                                                                                                                                                                                                                                                                                                                                                                                              |

---

| Campo                                   | Detalle                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| :-------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint Goal & User Stories**          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Sprint 1 Goal**                       | Nuestro objetivo se enfoca en construir una Landing Page totalmente funcional y adaptativa que comunique con claridad la propuesta de valor de ParkShare para conductores y propietarios[cite: 173, 174]. Consideramos que esto permitirá a los visitantes comprender de forma precisa los beneficios del servicio[cite: 173, 174]. Confirmaremos el éxito de este objetivo cuando los usuarios puedan explorar el sitio público, interactuar sin fricciones entre sus secciones principales y acceder de manera óptima desde cualquier dispositivo. |
| **User Stories incluidas en el Sprint** | **US27**: Información para conductores en el Landing Page; **US28**: Información para propietarios en el Landing Page; **US29**: Información sobre funcionamiento y confianza; **US30**: Redirección desde el Landing Page a la Web Application.                                                                                                                                                                                                                                                                                                     |
| **Sprint 1 Velocity**                   | 8 Story Points                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Sum of Story Points**                 | 8 Story Points                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

#### 5.2.1.2. Aspect Leaders and Collaborators

Para este primer sprint, los frentes de trabajo se enfocaron en la construcción integral de la Landing Page de ParkShare, abarcando la maquetación visual, el flujo de navegación entre módulos y la adaptabilidad para múltiples pantallas (responsive design).

A continuación, se presenta la distribución de roles según las responsabilidades asignadas en el sprint (L: Líder, C: Colaborador, A: Apoyo, X: Sin participación directa)

| Team Member (Last Name, First Name)  | GitHub Username | Estructura del Landing Page | Navegación entre secciones | Diseño Responsive |
| :----------------------------------- | :-------------- | :-------------------------: | :------------------------: | :---------------: |
| **Palomino Vilcañaupa, Daril Johan** | `Daroh19`       |              C              |             C              |         C         |
| **Urviola Condori, Mateo Sebastian** | `BeyaminUv`     |              C              |             C              |         C         |
| **Checa Burga, Oscar Diego**         | `OscarCheca`    |              C              |             L              |         L         |
| **Tello Palacios, Fabrizio Rafael**  | `F4bris`        |              C              |             C              |         C         |
| **Yanac Flores, Gabriel Stefano**    | `u20241d945`    |              L              |             C              |         L         |

#### 5.2.1.3. Sprint Backlog 1

Durante el Sprint 1, la prioridad principal fue el desarrollo y despliegue de la Landing Page de ParkShare, diseñada para exponer de forma transparente, intuitiva y accesible la propuesta de valor del sistema, respondiendo a las necesidades de los conductores urbanos y de los propietarios de cocheras en Lima.

El seguimiento del Sprint Backlog se administró de manera ágil mediante la plataforma Trello. A través de un flujo estructurado en columnas (To-Do, In Progress y Done), las User Stories del portal web se dividieron en tareas técnicas específicas de maquetación, diseño y maquetado de componentes interactivos.

#### 5.2.1.4. Development Evidence for Sprint Review

En este Sprint se logró la implementación de la Landing Page de ParkShare, estructurando su arquitectura web mediante HTML5, CSS3 y JavaScript, así como la navegación fluida entre sus secciones principales y el desarrollo del diseño adaptativo para dispositivos móviles y de escritorio.

| Repository                        | Commit ID | Commit Message                                                                            | Commit Message Body                                                                                               | Commit Date |
| :-------------------------------- | :-------- | :---------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------- | :---------- |
| **Daroh19/Proyect-Park-Share**    | `6ad44ab` | `feat: add final sections for Proyect-Park-Share.`                                        | Se implemento las seccciones de Footer y questions en la pagina web.                                              | 18/09/2026  |
| **BeyaminUv/Proyect-Park-Share**  | `7b1d344` | `feat(css2): add styles for toast notifications and responsive adjustments in styles.css` | Implementacion de secciones de css de la landing page.                                                            | 18/09/2026  |
| **OscarCheca/Proyect-Park-Share** | `becd907` | `docs: add images and initial documentation and docs: add javascript for landing page`    | Implementacion de de seccion de documentacion dentro de la landing page.                                          | 19/09/2026  |
| **F4bris/Proyect-Park-Share**     | `c047492` | `feat(css): implement CSS variables for color palette, typography, and layout styles`     | Implementacion de variables de colores , topografia y javascript.                                                 | 19/09/2026  |
| **u20241d945/Proyect-Park-Share** | `becd907` | `feat: Add initial index.html for Proyect-Park-Share`                                     | Se implementan las secciones principales del index(hero +nabvar, Map & Parking cards and Video showcase section). | 19/09/2026  |

#### 5.2.1.5. Execution Evidence for Sprint Review

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

### 5.2.2. Sprint 2

En esta sección se presenta el avance del Sprint 2 en términos de desarrollo del producto y trabajo colaborativo del equipo.

Durante este sprint se implementó la primera versión de la Web Application de ParkShare, desarrollada en Angular con Angular Material, internacionalización (inglés y español) y una arquitectura basada en Domain-Driven Design. El avance se centró en la estructura general de la aplicación (barra lateral de navegación y selector de rol Conductor / Propietario) y en el módulo de perfil del conductor, que incluye el registro de su vehículo y la carga de documentos de verificación.

Asimismo, se incluyen evidencias de la planificación del sprint, la organización del equipo, el desarrollo realizado y los resultados obtenidos.

#### 5.2.2.1. Sprint Planning 2

En esta sección se describen los principales acuerdos y definiciones realizados durante el Sprint Planning del Sprint 2, donde el equipo se enfocó en la implementación de la Web Application para el rol de Conductor.

| Campo                                   | Detalle                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| :-------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint #**                            | Sprint 2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Sprint Planning Background**          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Date                                    | [COMPLETAR: AAAA-MM-DD]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Time                                    | [COMPLETAR: HH:MM]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Location                                | Reunión virtual (Discord)                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Prepared By                             | [COMPLETAR: nombre del integrante]                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Attendees (to planning meeting)         | Palomino Vilcañaupa, Daril Johan - Tello Palacios, Fabrizio Rafael - Checa Burga, Oscar Diego - Yanac Flores, Gabriel Stefano - Urviola Condori, Mateo Sebastian                                                                                                                                                                                                                                                                                                                                       |
| **Sprint 2 – Review Summary**           | En esta entrega se tomó en cuenta el Sprint 1 (Landing Page), el Product Backlog definido y los prototipos de la Web Application diseñados en el capítulo IV.                                                                                                                                                                                                                                                                                                                                          |
| **Sprint 2 – Retrospective Summary**    | [COMPLETAR: qué funcionó, qué no y qué se mejorará en el siguiente sprint]                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Sprint Goal & User Stories**          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Sprint 2 Goal**                       | Nuestro objetivo es construir la primera versión de la Web Application de ParkShare, con una navegación clara por rol y un perfil de conductor funcional. Consideramos que esto permitirá a los conductores mantener actualizados los datos de su vehículo y gestionar sus documentos de verificación. Confirmaremos el éxito de este objetivo cuando el conductor pueda consultar, editar y guardar la información de su vehículo, y cargar sus documentos, con los datos persistidos en la Fake Api. |
| **User Stories incluidas en el Sprint** | **US04**: Registro de vehículo; **US03**: Verificación de identidad (carga de documentos y estados de revisión).                                                                                                                                                                                                                                                                                                                                                                                       |
| **Sprint 2 Velocity**                   | [COMPLETAR según Trello]                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Sum of Story Points**                 | 11 Story Points (US04: 3, US03: 8)                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

#### 5.2.2.2. Aspect Leaders and Collaborators

Para este sprint, los frentes de trabajo se enfocaron en la estructura de la Web Application, el módulo de perfil del conductor y la API simulada que respalda sus datos.

A continuación, se presenta la distribución de roles según las responsabilidades asignadas en el sprint (L: Líder, C: Colaborador, A: Apoyo, X: Sin participación directa)

| Team Member                          | GitHub Username | Layout y navegación | Perfil y vehículo (US04) | Verificación de documentos (US03) | API simulada (json-server) |
| :----------------------------------- | :-------------- | :-----------------: | :----------------------: | :-------------------------------: | :------------------------: |
| **Palomino Vilcañaupa, Daril Johan** | `Daroh19`       |          …          |            …             |                 …                 |             …              |
| **Urviola Condori, Mateo Sebastian** | `BeyaminUv`     |          …          |            …             |                 …                 |             …              |
| **Checa Burga, Oscar Diego**         | `OscarCheca`    |          …          |            …             |                 …                 |             …              |
| **Tello Palacios, Fabrizio Rafael**  | `F4bris`        |          C          |            L             |                 C                 |             C              |
| **Yanac Flores, Gabriel Stefano**    | `u20241d945`    |          …          |            …             |                 …                 |             …              |

#### 5.2.2.3. Sprint Backlog 2

Durante el Sprint 2, la prioridad principal fue el desarrollo de la primera versión de la Web Application de ParkShare para el rol de Conductor, respondiendo a la necesidad de mantener un perfil vigente y confiable dentro de la plataforma.

El seguimiento del Sprint Backlog se administró mediante Trello, con las columnas To-Do, In Progress y Done. Las User Stories se dividieron en las siguientes tareas técnicas:

| User Story  | Tarea técnica                                                                                                      |   Estado    |
| :---------- | :----------------------------------------------------------------------------------------------------------------- | :---------: |
| Transversal | Configuración del proyecto Angular, Angular Material, tema y estructura por bounded contexts (`shared`, `profile`) | [COMPLETAR] |
| Transversal | Layout con barra lateral, selector de rol Conductor / Propietario y rutas por vista                                | [COMPLETAR] |
| Transversal | Internacionalización con ngx-translate (EN / ES) y selector de idioma                                              | [COMPLETAR] |
| US04        | Entidad `Profile`, assembler, endpoint y servicio de infraestructura                                               | [COMPLETAR] |
| US04        | Vista de detalle del perfil con datos del vehículo registrado                                                      | [COMPLETAR] |
| US04        | Formulario de edición del vehículo con validaciones (placa, modelo, tipo)                                          | [COMPLETAR] |
| US03        | Entidad `VerificationDocument`, assembler, endpoint y servicio                                                     | [COMPLETAR] |
| US03        | Lista de documentos con estado (Verificado, En revisión, Rechazado) y carga de archivo                             | [COMPLETAR] |
| Transversal | API simulada con json-server (`db.json`)                                                                           | [COMPLETAR] |

#### 5.2.2.4. Development Evidence for Sprint Review

En este Sprint se logró la implementación de la estructura base de la Web Application de ParkShare y del módulo de perfil del conductor, aplicando una arquitectura por capas (domain, application, infrastructure y presentation) separada en bounded contexts, con estado manejado mediante signals y sin valores fijos en el código (URLs en archivos de entorno y textos en archivos de idioma).

| Repository  | Commit ID     | Commit Message | Commit Message Body | Commit Date |
| :---------- | :------------ | :------------- | :------------------ | :---------- |
| [COMPLETAR] | `[COMPLETAR]` | `[COMPLETAR]`  | [COMPLETAR]         | [COMPLETAR] |

#### 5.2.2.5. Execution Evidence for Sprint Review

En el Sprint 2 se logró implementar la primera versión funcional de la Web Application de ParkShare para el rol de Conductor. A continuación, se presentan las evidencias visuales de las principales vistas implementadas:

Perfil del conductor: datos del vehículo registrado y documentos de verificación

![Perfil del conductor](../report/assets/sprint2-perfil-detalle.png)

Edición del vehículo

![Edición del vehículo](../report/assets/sprint2-perfil-edicion.png)

Vista en inglés (internacionalización)

![Vista en inglés](../report/assets/sprint2-perfil-en.png)

#### 5.2.2.6. Services Documentation Evidence for Sprint Review

Durante este sprint, los datos del perfil se consumen desde una API REST simulada con json-server. La URL base y las rutas de cada recurso se definen en los archivos de entorno de la aplicación.

| Recurso    | Método | Ruta                          | Descripción                                                            |
| :--------- | :----- | :---------------------------- | :--------------------------------------------------------------------- |
| Perfil     | GET    | `/profiles`                   | Obtiene los perfiles registrados                                       |
| Perfil     | PUT    | `/profiles/{id}`              | Actualiza los datos del vehículo del perfil                            |
| Documentos | GET    | `/verificationDocuments`      | Obtiene los documentos de verificación                                 |
| Documentos | PUT    | `/verificationDocuments/{id}` | Registra el archivo cargado y pasa el documento a estado "En revisión" |

#### 5.2.2.7. Software Deployment Evidence for Sprint Review

[COMPLETAR: describir como se desplego la Web Application (se despliega en github pages porsiaca) con los pasos realizados: compilación de producción con Angular (`dist/parkshare/browser`), configuración de la rama de publicación y activación del servicio.]

Link de la Web Application: [COMPLETAR]

#### 5.2.2.8. Team Collaboration Insights during Sprint

[COMPLETAR: captura del grafico de contribuciones de GitHub del sprint y breve descripción de la participacion de cada uno.]

![Contribuciones Sprint 2](../report/assets/sprint2-contribuciones.png)
