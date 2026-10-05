### 4.1. Style Guidelines.

### 4.1.1. General Style Guidelines.

El diseño visual de Proyect-Park-Share se basa en los principios de claridad, confiabilidad y agilidad operacional. Está pensado para conductores que buscan un estacionamiento sin perder tiempo y propietarios que desean rentabilizar sus cocheras de manera segura y sin complicaciones.

Se prioriza una interfaz limpia e intuitiva, fácil de usar tanto para jóvenes acostumbrados a aplicaciones móviles como para propietarios de mayor edad que prefieren evitar procesos complejos.

#### Principios de diseño:

- Simplicidad: Interfaces despejadas y con baja carga cognitiva para que la reserva o publicación de una cochera se realice en pocos pasos.

- Consistencia: Uso uniforme de patrones visuales, botones y componentes en toda la plataforma para facilitar el aprendizaje.

- Jerarquía visual: Organización de la información según su urgencia, destacando datos críticos como el estado de la reserva, la ubicación en el mapa y el costo por hora.

- Accesibilidad: Diseñado con contrastes adecuados, tipografía legible y botones amplios para asegurar un uso cómodo en cualquier condición.

#### Paleta de colores:

La combinación de colores transmite seguridad, transparencia y dinamismo urbano:

![PaletadeColores](/report/assets/paletadecolores.png)

### Tipografía:

Se selecciona la familia tipográfica Inter por su excelente legibilidad en pantallas digitales de diversos tamaños y su apariencia clara y moderna.

#### Jerarquía tipográfica:

- Heading 1: Títulos principales, Inter, Bold, 28px – 34px.

- Heading 2: Subtítulos y secciones, Inter, Semi-Bold, 20px – 24px.

- Heading 3: Encabezados de tarjetas o modales, Inter, Medium, 16px – 18px.

- Body Text: Texto principal y formularios, Inter, Regular, 14px – 16px.

#### Espaciado:

Se adopta un sistema basado en múltiplos de 8px para asegurar una alineación precisa:

8px: Separación mínima entre elementos estrechos.

16px: Separación estándar entre campos de formulario y botones.

24px: Distancia entre tarjetas o bloques de información.

32px: Margen entre secciones principales del documento o pantalla.

#### Tono de comunicación:

Práctico y accesible: Pensado para agilizar la interacción.

Formal pero cercano: Brinda seguridad en los pagos sin ser rígido.

Claro y sereno: Enfocado en resolver la necesidad de parqueo sin distracciones ni lenguaje confuso.

### 4.1.2. Web Style Guidelines.

1. #### Diseño y Distribución de la Pantalla (Layout)

- La plataforma web de Proyect-Park-Share está diseñada para que la búsqueda y el alquiler de cocheras se realicen de forma rápida e intuitiva.

- Menú Lateral: Una barra fija a la izquierda permite gestionar las cocheras registradas, revisar el historial de reservas y configurar la cuenta.

- Área Principal: Pantalla dividida que muestra el mapa dinámico a un lado y la lista de opciones de parqueo al otro, permitiendo comparar alternativas fácilmente.

- Tarjetas de Información: Recuadros limpios donde se agrupa la información de cada cochera (fotos, precio por hora, dirección y calificación).

2. #### Organización en Rejilla (Grid System)

Para asegurar una presentación limpia y adaptada a distintas pantallas:

- Sistema de grilla flexible basado en 12 columnas para mantener los elementos alineados.

- Espaciado uniforme guiado por múltiplos de 8px (8px, 16px, 24px) que evita la saturación visual.

3. #### Componentes Visuales de la Interfaz

- Tablas de Historial: Utilizadas para detallar las reservas pasadas y los ingresos del propietario, incluyendo filtros por fecha y barra de búsqueda.

- Acciones Principales: En tonos azul o verde para acciones clave como "Reservar ahora" o "Publicar cochera".

- Acciones Secundarias: Botones neutros para acciones como "Ver detalles" o "Volver".

- Estados: Variaciones visuales para indicar cuando el botón está activo, en hover o deshabilitado.

- Etiquetas de Estado: Indicadores visuales en color para identificar rápidamente la situación del parqueo (Disponible, Solicitud Pendiente, Ocupado).

- Formularios: Campos sencillos con etiquetas claras superiores y validación en tiempo real (por ejemplo: "Ingrese una placa válida").

- Avisos y Notificaciones: Alertas flotantes (Toasts) que confirman la reserva o notifican cuando el tiempo de estacionamiento está por concluir.

4. #### Comportamiento Visual e Interacción

- Respuesta Inmediata: Confirmación visual instantánea tras cada acción (guardar datos, solicitar parqueo o cancelar).

- Reglas del Flujo: El sistema bloquea acciones no permitidas, como solicitar una cochera si el vehículo excede las dimensiones permitidas.

- Líneas de Tiempo: Una barra de progreso muestra la etapa actual del servicio (Solicitado > Confirmado > En uso > Finalizado).

5. Adaptación a Pantallas

- Versión Desktop: Vista completa a pantalla dividida con el mapa interactivo y la lista de resultados en paralelo.

6. Navegación e Iconos

- Barra Superior: Acceso rápido al inicio, selector para alternar entre el perfil de Conductor o Propietario y acceso a la cuenta.

- Iconos: Símbolos simples y de rápida asociación (lupa para buscar, pin para ubicación, auto para parqueo y candado para seguridad).

### 4.2. Information Architecture.

La arquitectura de información de Proyect-Park-Share está pensada para que tanto los conductores que buscan un estacionamiento como los propietarios que alquilan su espacio puedan usar la plataforma de forma rápida, clara y sin perderse.

Se prioriza una estructura sencilla orientada a tareas directas: encontrar una cochera, reservarla o ponerla en alquiler en pocos pasos.

### 4.2.1. Organization Systems.

Los sistemas de organización estructuran los datos de la plataforma para que cualquier usuario pueda realizar sus gestiones sin complicaciones ni rodeos. Para lograrlo, combinamos formas visuales de ordenar la pantalla con listas lógicas adaptadas al uso diario.

#### Organización visual del contenido:

- Organización jerárquica: Se aplica en la pantalla principal y en los detalles del parqueo. Muestra primero la información indispensable (ubicación en el mapa, precio por hora y disponibilidad) y deja en segundo plano los datos secundarios.

- Organización secuencial (Paso a paso): Se utiliza en los procesos principales como el registro de usuarios, la verificación de identidad (DNI y placa) y el flujo de reserva. Guía al usuario paso a paso para evitar equivocaciones.

- Organización matricial: Se aplica en las tablas del panel de control (dashboard). Permite a los propietarios ver de un vistazo varios datos a la vez, como fechas, montos cobrados y estado de sus alquileres.

#### Categorización del contenido:

- Tipo de usuario: La plataforma adapta lo que muestra según el rol activo. Los conductores ven opciones de búsqueda y reservas, mientras que los propietarios acceden a la publicación y cobros.

\*Por Secciones: El contenido se agrupa por áreas de interés: Búsqueda, Mis Reservas, Mis Cocheras y Pagos.

- Cronológica: Organiza los historiales de alquileres y los cobros realizados de más reciente a más antiguo.

#### Módulos principales del sistema:

- Inicio / Buscador: Vista principal con el mapa interactivo para ubicar cocheras cercanas.

- Mis Reservas: Sección donde el conductor revisa sus alquileres activos y pasados.

- Mis Cocheras: Panel del propietario para administrar sus espacios, precios y horarios.

- Pagos e Ingresos: Espacio para gestionar tarjetas de crédito/débito y revisar las ganancias obtenidas.

- Perfil y Verificación: Lugar para subir documentos personales (DNI, licencia de conducir y tarjeta de propiedad).

### 4.2.2. Labeling Systems.

El sistema de etiquetado de Proyect-Park-Share está pensado para nombrar cada parte de la plataforma de forma sencilla, breve y coherente. Su meta principal es eliminar dudas al navegar, logrando que tanto un conductor apurado por estacionar como un propietario que alquila su garaje entiendan la pantalla al instante sin encontrarse con términos raros o confusos.

Se prioriza el uso de palabras cotidianas y directas, teniendo en cuenta que los usuarios tienen diferentes niveles de experiencia usando aplicaciones.

#### Principios de etiquetado:

- Simplicidad: Usamos la menor cantidad de palabras posible en cada botón o título. Se evitan modismos técnicos o nombres complicados para que cualquiera identifique rápido para qué sirve cada opción.

- Claridad: La etiqueta indica exactamente lo que va a pasar al hacer clic o qué información contiene la sección, sin dejar espacio a malinterpretaciones.

- Consistencia: Mantenemos las mismas palabras en toda la web y la aplicación. Por ejemplo, usamos siempre el término "Cochera" en lugar de cambiar a cada rato entre "Garaje", "Estacionamiento" o "Parqueo".

- Lenguaje simple: Empleamos un vocabulario habitual y conocido por todos los conductores y dueños de casa, como "Placa", "Reserva", "Ingresos" o "Licencia".

#### Etiquetas de navegación principal (Módulos):

Representan las pantallas clave de la plataforma y permiten moverse de forma directa entre secciones:

- Inicio / Buscar: Pantalla principal con el mapa interactivo para ubicar espacios cercanos.

- Mis Reservas: Sección donde el conductor revisa sus alquileres activos, programados y pasados.

- Mis Cocheras: Panel donde el propietario administra sus espacios registrados, precios y horarios de disponibilidad.

- Mis Ingresos: Espacio para consultar las ganancias acumuladas y el historial de pagos recibidos.

- Verificación: Zona del perfil para subir documentos (DNI, licencia de conducir y tarjeta de propiedad).

- Mi Perfil: Configuración de la cuenta de usuario, teléfono y datos personales.

#### Etiquetas de acciones principales:

- Utilizan verbos claros y directos en infinitivo para indicar qué hará el sistema al presionar el botón:

- Reservar ahora: Inicia el proceso de solicitud de un espacio de parqueo.

- Publicar cochera: Abre el formulario para registrar un nuevo garaje en el sistema.

- Cancelar reserva: Anula un alquiler solicitado o confirmado.

- Confirmar llegada: Notifica al propietario que el vehículo ya ingresó al espacio.

- Finalizar parqueo: Registra la salida del vehículo y cierra el conteo de tiempo.

- Subir documento: Carga las fotos del DNI o licencia para la revisión de identidad.

- Retirar dinero: Solicita la transferencia de los ingresos hacia la cuenta bancaria del propietario.

#### Etiquetas de estado y respuesta:

Permiten al usuario entender de un vistazo la situación de su reserva o su cochera:

- Disponible: Indica que la cochera se encuentra libre para ser reservada de inmediato.

- Ocupada: Señala que el espacio ya cuenta con un vehículo en uso.

- Pendiente: Muestra que la solicitud de reserva está a la espera de confirmación.

- Verificado: Confirma que los documentos presentados han sido validados con éxito.

- En revisión: Avisa que la identidad o la propiedad del garaje aún está siendo comprobada.

#### Etiquetas de asociación:

Sirven para mostrar de forma limpia cómo se conectan los datos dentro de la plataforma sin amontonar la pantalla:

- Cochera asignada: Muestra cuál es el garaje específico vinculado a la reserva activa.

- Vehículo registrado: Indica qué auto y placa están autorizados para ingresar al espacio.

- Propietario responsable: Identifica al dueño de la cochera con quien se coordinará el acceso.

- Pago vinculado: Conecta la boleta o comprobante con el alquiler correspondiente.

### 4.2.3. SEO Tags and Meta Tags

Las etiquetas SEO y las etiquetas Meta de **Proyect-Park-Share** permiten que la plataforma se posicione adecuadamente en los motores de búsqueda como Google. Su función principal es describir de forma directa el propósito de cada vista dentro de la web para ayudar a que los conductores que necesitan estacionamiento y los dueños de estacionamientos nos encuentren fácilmente.

Se configuran directamente en el encabezado HTML de cada vista principal del sitio web y la aplicación mediante los atributos _Title_, _Meta Description_, _Keywords_ y _Author_.

#### Página Principal / Bienvenida (Landing Page)

- Title: Proyect-Park-Share | Tu Red de Cocheras Privadas en Lima
- Meta Description:Olvídate del tráfico y busca un estacionamiento seguro por horas o pon en alquiler tu cochera libre para generar dinero extra.
- Keywords: parqueo en lima, estacionamiento por hora, alquilar mi cochera, estacionamiento privado, parqueo seguro
- Author: Equipo Proyect-Park-Share

#### Buscador e Integración de Mapa

- Title: Ubicar Estacionamientos Cercanos | Proyect-Park-Share
- Meta Description: Consulta las cocheras disponibles cerca de tu posición en tiempo real, compara costos por hora y realiza tu reserva al instante.
- Keywords: mapa de parqueos, cocheras libres, reservar estacionamiento, costo por hora parqueo
- Author: Equipo Proyect-Park-Share

#### Módulo de Registro de Espacios (Para Propietarios)

- Title: Publica tu Garage y Genera Ingresos | Proyect-Park-Share
- Meta Description: Registra tu espacio de parqueo desocupado, establece las horas en que está libre y recibe pagos seguros por cada alquiler.
- Keywords: ganar dinero con mi cochera, rentar garage desocupado, alquiler de estacionamiento lima
- Author: Equipo Proyect-Park-Share

#### Acceso y Registro de Usuarios

- Title: Entrar a la Plataforma | Proyect-Park-Share
- Meta Description: Inicia sesión con tu cuenta para administrar tus solicitudes de parqueo activas o revisar los alquileres de tu cochera.
- Keywords: ingreso proyect park share, entrar a mi cuenta, login estacionamiento
- Author: Equipo Proyect-Park-Share

#### Panel Principal de Gestión -Dashboard:

- Title: Resumen de Mi Cuenta | Proyect-Park-Share
- Meta Description: Administra el estado de tus reservas, verifica el conteo de tiempo de parqueo y revisa las ganancias del mes.
- Keywords: resumen de reservas, historial de pagos, panel de control cochera
- Author: Equipo Proyect-Park-Share

### 4.2.4. Searching Systems.

El sistema de búsqueda está pensado para que los conductores encuentren un parqueo disponible rápidamente y sin rodeos, evitando que pierdan tiempo dando vueltas o buscando entre opciones que no se ajustan a su viaje.

Se da prioridad a una búsqueda sencilla, directa y fácil de usar en el día a día, permitiendo ubicar el espacio ideal en pocos clics.

#### Tipos y Formas de Búsqueda

La plataforma incluye una barra de búsqueda clara en la pantalla principal y en el mapa interactivo. El usuario puede buscar un espacio utilizando distintos datos cotidianos:

- Dirección o avenida principal (por ejemplo: "Av. Javier Prado").
- Distrito o zona específica (por ejemplo: _"Surco"_ o "Miraflores").
- Puntos de referencia conocidos (por ejemplo: "Cerca al centro comercial" o "Frente a la universidad").
- Nombre del propietario o código de la cochera.

#### Filtros para Ajustar la Búsqueda

Para ayudar al conductor a encontrar justo lo que necesita, el sistema permite filtrar las opciones según criterios prácticos:

##### En la búsqueda de parqueos:

- Rango de precio por hora.
- Horario y fecha necesaria.
- Tamaño del vehículo (auto compacto, camioneta, moto).
- Características (cochera techada, portón automático, vigilancia).

##### En la lista de reservas del usuario:

- Estado de la reserva (activa, pendiente, finalizada, cancelada).
- Fecha de alquiler.

##### En el panel del propietario:

- Cocheras libres u ocupadas.
- Histórico de cobros por fecha.

#### Presentación de los Resultados

Las opciones encontradas se organizan en pantalla de dos maneras fáciles de entender:

- Pines en el Mapa: Puntos de ubicación que muestran directamente el costo por hora sobre la zona seleccionada. Al presionar un punto, se abre una vista previa con la foto del garaje.
- Tarjetas en Lista: Cuadros ordenados por cercanía o menor precio que resumen la foto de la cochera, la distancia, la tarifa y la calificación del dueño.
- Resultados Ordenados: Posibilidad de ordenar la lista por el precio más bajo, la distancia más corta o las mejores opiniones.

#### Avisos y Respuestas del Sistema

La aplicación te orienta en todo momento mientras buscas:

- Sin resultados: Si no hay lugares libres en la zona elegida, la pantalla te avisa claramente y te sugiere ampliar el radio de búsqueda a calles cercanas.
- Carga rápida: Si la señal está lenta, un pequeño ícono visual indica que los datos se están actualizando.
- Cambio al instante: Cada vez que activas un filtro (como "Cochera techada"), la lista y el mapa se actualizan inmediatamente sin necesidad de recargar la página.

### 4.2.5. Navigation Systems

Se busca que el usuario nunca esté a más de tres interacciones de realizar una acción clave, como buscar una plaza disponible, realizar una reserva, calcular tarifas o validar credenciales.

### Navegación Global (Menú superior persistente)

Se implementa mediante una barra de navegación horizontal fija en la parte superior que otorga acceso directo a los módulos principales del sistema:

- **Search:** Búsqueda rápida de estacionamientos disponibles por ubicación o zona.
- **How it works:** Guía explicativa sobre el funcionamiento del sistema de alquiler y uso de plazas.
- **Media & Demos:** Demostraciones visuales y material interactivo de la plataforma.
- **Pricing:** Estructura de tarifas, planes y costos del servicio.
- **Calculator:** Herramienta interactiva para proyectar o estimar costos de estacionamiento.
- **Verification:** Módulo para la validación de identidad, vehículos o permisos.
- **Selector de Idioma (EN / ES):** Cambio inmediato de interfaz entre inglés y español.
- **Acceso de Usuario (Log In / Register Now):** Botones directos para la autenticación e inicio de sesión.

Esta estructura asegura una navegación clara y accesible desde cualquier sección del sitio.

---

### Navegación de Contexto (Breadcrumbs / Rutas)

Permite al usuario ubicarse dentro del flujo de la plataforma mediante rutas jerárquicas como:

- `Search` > `Lima Centro` > `Estacionamiento A` > `Reservar`
- `Calculator` > `Tarifa Nocturna` > `Estimación de Costo`
- `Verification` > `Documentación` > `Validación de Vehículo`

Esto facilita la orientación del usuario respecto a su posición actual en la aplicación.

---

### Navegación Local

Dentro de cada módulo se organizan las funcionalidades específicas mediante pestañas o secciones internas:

- **En la ficha de un estacionamiento:** Detalles de la plaza, Disponibilidad en tiempo real, Tarifas por hora/día, Reseñas.
- **En el perfil de usuario:** Historial de reservas, Métodos de pago, Vehículos registrados, Alertas.

Esto evita la saturación visual al categorizar la información relevante.

---

### Acciones Rápidas

Se integran botones de llamada a la acción (CTA) destacados para optimizar los flujos más frecuentes:

- **Register Now:** Botón principal para el registro inmediato de nuevos usuarios.
- **Log In:** Acceso directo a la cuenta personal.
- **Buscar / Reservar:** Botones directos dentro de los resultados para completar la reserva en pocos pasos.

---

### Navegación Adaptativa (Responsive)

La barra de navegación ajusta su distribución según la pantalla (desktop, tablet, móvil). En dispositivos móviles, los enlaces centrales se colapsan en un menú desplegable (hamburguesa), manteniendo los botones clave de acceso rápido para priorizar la usabilidad en pantallas pequeñas.

### 4.3. Landing Page UI Design.

### 4.3.1. Landing Page Wireframe.

**4.3.1 Landing Page Wireframe**

La _landing page_ de Proyect-Park-Share presenta una estructura clara y orientada a la conversión, iniciando con una sección principal (_Hero Section_) que introduce la solución para la reserva de estacionamientos seguros y el alquiler de cocheras privadas en Lima, resaltando beneficios como el ahorro de tiempo, la transparencia en tarifas y la conexión con propietarios verificados[cite: 5].

### Estructura y Secciones del Wireframe

- **Header / Navigation Bar:**
  - **Branding:** Identificador visual y nombre del proyecto (_Proyect-Park-Share_).
  - **Menú Principal:** Enlaces de acceso rápido a los módulos principales (_Search_, _How it works_, _Media & Demos_, _Pricing_, _Calculator_, _Verification_).
  - **Herramientas y Accesos:** Selector de idioma (_EN / ES_) y botones directos para inicio de sesión (_Log In_) y registro (_Register Now_).

- **Hero Section (Búsqueda Inicial y Propuesta de Valor):**
  - Mensaje principal enfocado en encontrar parqueo seguro o monetizar cocheras privadas.
  - Selector de rol para la interfaz (_I'm a Driver_ / _I'm a Parking Owner_).
  - Botones de llamada a la acción (_Book Now_, _Learn More_).
  - **Quick Garage Finder:** Formulario flotante para filtrar búsqueda por distrito/avenida, tipo de vehículo y tarifa máxima por hora.

- **Available Parking Spaces Nearby (Búsqueda en Tiempo Real):**
  - Listado de tarjetas de cocheras con precio por hora, dirección, atributos (_24/7 Surveillance_, _Automatic Gate_, _Compact Auto_) y calificación de usuarios.
  - Mapa dinámico e interactivo adjunto que muestra los marcadores de geolocalización y precios en tiempo real.

- **Platform Video Demonstrations & Case Studies (Media & Demos):**
  - Reproductores de video integrados con casos de estudio y demostraciones técnicas: _About the Team_ (proceso de desarrollo y visión urbana) y _ParkShare Platform_ (presentación oficial y validación de necesidades).

- **Transparent Pricing & Flexible Plans (Pricing):**
  - Comparativa de planes según el tipo de usuario:
    - **Pay As You Go (S/. 5.00/hr avg):** Para conductores ocasionales.
    - **Driver Pass (S/. 29.90/month):** Opción destacada con descuentos en tarifa horaria y cola de reserva prioritaria.
    - **Garage Owner (0% monthly fee):** Publicación gratuita y pagos automáticos para propietarios.

- **Simple Step-by-Step Flow (How It Works):**
  - Explicación del ciclo de servicio en cuatro etapas correlativas:
    1. **Requested:** Selección de cochera en el mapa y envío de solicitud.
    2. **Confirmed:** Notificación del propietario y reserva del espacio.
    3. **In Use:** Estacionamiento seguro y temporizador activo durante la estancia.
    4. **Finished:** Confirmación de salida, liberación automática de pago y evaluación mutua.

- **Calculate Your Monthly Earnings as an Owner (Calculator):**
  - Widget interactivo que permite a los propietarios estimar sus ingresos mensuales (ej. S/. 1,008.00) ajustando variables como horas disponibles al día y tarifa por hora.

- **Trust & Document Verification (Verification):**
  - Módulo enfocado en la seguridad y validación de la comunidad con opción para subir documentación (_Upload Document_):
    - **National ID / DNI:** Verificación de identidad de conductores y propietarios.
    - **Driver's License & Plate:** Confirmación de licencia autorizada y placa vehicular.
    - **Property Title or Utility Bill:** Validación de legitimidad de la propiedad o cochera.

- **Frequently Asked Questions (FAQ):**
  - Acordeón interactivo con preguntas frecuentes sobre el cálculo de tarifas, límites de tamaño vehicular y métodos de pago a propietarios.

- **Footer:**
  - Pie de página con el logo, declaración del servicio, enlaces de navegación, módulos del usuario, políticas legales/privacidad y derechos de autor.

  <div style="text-align:center;"><img src="../assets/landing-page/Landing-page-wireframe1.png" alt="texto"></div>
  <div style="text-align:center;"><img src="../assets/landing-page/Landing-page-wireframe2.png" alt="texto"></div>
  <div style="text-align:center;"><img src="../assets/landing-page/Landing-page-wireframe3.png" alt="texto"></div>
  <div style="text-align:center;"><img src="../assets/landing-page/Landing-page-wireframe4.png" alt="texto"></div>

### 4.3.2. Landing Page Mock-up.

El wireframe de la landing page en su versión de escritorio ha permitido organizar de forma clara y jerárquica los elementos principales de Proyect-Park-Share, facilitando la presentación de la propuesta de valor centrada en la búsqueda de estacionamientos seguros y la monetización de cocheras privadas en Lima. A partir de esta estructura inicial, se desarrolló el mockup de la interfaz, manteniendo coherencia con las funcionalidades definidas, como la localización en tiempo real con mapa interactivo, la simulación de ganancias, la verificación de documentos y el flujo estructurado de reserva.

En la implementación final se puede apreciar el uso consistente de una paleta de colores basada en tonos azul marino y blanco con acentos verdes para botones clave, así como una tipografía moderna seleccionada, lo que contribuye a una estética limpia y tecnológica. Además, la distribución de secciones como el explorador de parqueos cercanos (_Quick Garage Finder_), los planes flexibles, las demostraciones en video y la guía paso a paso refuerzan la claridad y usabilidad de la plataforma. En conjunto, el diseño refleja una identidad visual alineada con los valores de seguridad, claridad y eficiencia operacional, transmitiendo confianza tanto para conductores como para propietarios de cocheras

<div style="text-align:center;"><img src="../assets/landing-page/Landing-page-mockup1.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/landing-page/Landing-page-mockup2.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/landing-page/Landing-page-mockup3.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/landing-page/Landing-page-mockup4.png" alt="texto"></div>

### 4.4. Web Applications UX/UI Design.

### 4.4.1. Web Applications Wireframes.

La aplicación web de Proyect-Park-Share constituye el núcleo operativo de la plataforma, permitiendo la interacción coordinada entre los actores clave del ecosistema de movilidad urbana: conductores que buscan estacionamiento seguro, propietarios de cocheras privadas que desean monetizar sus espacios y administradores de la red. El diseño de experiencia de usuario (UX) e interfaz de usuario (UI) se estructura para garantizar la visualización rigurosa de cocheras disponibles en tiempo real, la gestión centralizada de reservas y cobros, y la trazabilidad técnica y validación de seguridad de los vehículos y propiedades.

### 4.4.1. Web Applications Wireframes

Los wireframes de la aplicación web definen la disposición esquemática, la jerarquía de información y los flujos funcionales para entornos de escritorio (Desktop Web Browser).

<div style="text-align:center;"><img src="../assets/app-web/app-wireframe1.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe2.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe3.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe4.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe5.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe6.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe7.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-wireframe8.png" alt="texto"></div>

### 4.4.2. Web Applications Wireflow Diagrams.

  <div align="center"><img src="../assets/app-web/wireflow_reserva.png" alt="wireflow reserva">
  
</div>

**User Goal:** El conductor busca una cochera disponible, revisa su detalle, confirma la reserva y recibe la confirmación.

Pantallas:

1. **Buscar cochera:** pantalla de búsqueda con filtros por ubicación, fecha y hora, más una lista de cocheras cercanas con precio y distancia.

2. **Parqueos disponibles:** lista de resultados con detalles resumidos (nombre, dirección, precio por hora, disponibilidad).

3. **Reservar:** pantalla de detalle de la cochera con formulario para seleccionar fecha, hora de inicio y duración, junto con el botón de confirmación.

4. **Reserva concretada:** pantalla de éxito que confirma que la reserva se realizó correctamente.

5. **Reserva no puedo realizarse:** pantalla alternativa que muestra un error cuando la reserva no puede completarse.

<br>
<br>

**User Goal:** El conductor actualiza la información de su vehículo y verifica su identidad para mantener su perfil vigente en SafeStep.



<div align="center"><img src="../assets/app-web/perfil.png" alt="wireflow reserva">
  
</div>

Pantallas:

1. **Buscar cochera:** punto de entrada desde la navegación principal (bottom nav → Perfil).

2. **Mi perfil:** pantalla con la información del vehículo (placa, marca, modelo, color) y la sección de verificación de identidad (DNI, licencia de conducir).

3. **Confirmación de cambio:** pantalla que muestra el mensaje "Se guardaron los cambios" tras actualizar la información.

4. **Mi perfil (actualizado):** pantalla de regreso al perfil con los datos ya actualizados.

### 4.4.2. Web Applications Mock-ups.

<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup1.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup2.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup3.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup4.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup5.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup6.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup7.png" alt="texto"></div>
<div style="text-align:center;"><img src="../assets/app-web/app-web-mockup8.png" alt="texto"></div>

### 4.4.3. Web Applications User Flow Diagrams.

En esta sección se presentan los User Flow Diagrams de SafeStep, elaborados a partir de los User Personas y sus objetivos principales. Cada diagrama representa el camino que sigue un usuario para completar una tarea específica dentro de la aplicación, mostrando los pasos, las decisiones y las rutas alternativas que puede tomar.

<br>

 ### User flow 1: Conductor reserva o busca cochera 

<div style="text-align:center;"><img src="../assets/app-web/userflow1.png" alt="wireflow reservas"></div>

<br>

Este flujo describe el camino que sigue el conductor desde que ingresa a SafeStep hasta que completa una reserva. Comienza con el login, continúa con la búsqueda de cocheras mediante filtros de ubicación, fecha y hora, y avanza hacia la selección de una cochera y la confirmación del pago. Incluye rutas alternativas para el caso en que no haya resultados disponibles o el pago falle, lo que permite al usuario corregir su búsqueda o reintentar la operación sin perder el contexto.

<br>
<br>

### User flow 2: Consultar historial de reservas

<div style="text-align:center;"><img src="../assets/app-web/userflow2.png" alt="wireflow reservas"></div>

<br>

El conductor accede al historial de sus reservas anteriores. Desde el dashboard, el usuario selecciona la opción "Mis reservas" y visualiza la lista completa. Puede seleccionar una reserva para ver su detalle, cancelarla si aún está activa, o descargar el comprobante correspondiente. Si no tiene reservas registradas, el sistema muestra una pantalla de estado vacío con un mensaje orientador.

<br>
<br>

### User flow 3: Conductor gestiona perfil y vehiculos

<div style="text-align:center;"><img src="../assets/app-web/userflow3.png" alt="wireflow reservas"></div>

<br>

 El conductor administra su información personal y los datos de su vehículo. Desde el dashboard, accede a "Mi perfil" y puede editar sus datos personales, actualizar los datos del vehículo o completar la verificación de identidad subiendo su DNI y licencia de conducir. Si los datos no son válidos, el sistema muestra un mensaje de error y permite corregirlos antes de guardar. Al final, el usuario recibe una confirmación de que los cambios se guardaron correctamente.

 <br>
 <br>

 ### User flow 4: Propietario publica cochera

 <div style="text-align:center;"><img src="../assets/app-web/userflow4.png" alt="wireflow reservas"></div>

 <br>

 En este flujo se describe cómo el propietario registra una nueva cochera en la plataforma. Desde el dashboard, accede a "Mis cocheras" y selecciona la opción de publicar una nueva. Completa el formulario con la dirección, el precio, el horario y las fotos de la cochera. Si los datos están incompletos, el sistema muestra un error y solicita completar los campos faltantes. Al confirmar la publicación, la cochera aparece en el listado y queda disponible para los conductores.

 <br>
 <br>

 ### User flow 5: Propietario consulta ingresos

 <div style="text-align:center;"><img src="../assets/app-web/userflow5.png" alt="wireflow reservas"></div>

<br>

Este flujo describe cómo el propietario revisa los ingresos generados por sus cocheras. Desde el dashboard, accede a "Mis ingresos" y visualiza un resumen con los montos acumulados y las reservas que los generaron. Puede aplicar filtros por fecha o por cochera para analizar períodos específicos, y exportar el reporte en formato PDF o Excel para conservarlo como respaldo.

<br>
<br>

### 4.5. Web Applications Prototyping.

En esta sección se presentan los prototipos de UI desarrollados en Figma para la aplicación web de SafeStep, tanto en su versión Desktop como Mobile. Los prototipos incluyen simulación de interacción y navegación, alineados con los User Flow Diagrams definidos previamente. El objetivo es demostrar cómo los usuarios pueden completar sus tareas principales a través de los flujos diseñados.

<div align="center"><img src="../assets/app-web/video_prototipo.png" alt="prototipo web">
  <p>
    <i><b>Fuente</b>: Elaboración propia.</i>
  </p>
</div>

<br>

<div align="center">
  <a href="https://upcedupe-my.sharepoint.com/:v:/g/personal/u202113310_upc_edu_pe/IQBcEJ_ITJTYQaugUbTGYrrtAQnXLhbBgqHUf9B7Hzy5onI?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=k9wWZl">Ver video de prototipo web</a>
</div>

<br>

<div align="center"><img src="../assets/app-web/prototipo.png" alt="prototipo figma"></div>

Para el usuario **Conductor**, el dashboard (pantalla inicial) se muestra luego del inicio de sesión exitoso.
<div align="center"><img src="../assets/app-web/mobile_proto.png" alt="prototipo web">
  <p>
    <i><b>Fuente</b>: Elaboración propia.</i>
  </p>
</div>
<br>

<div align="center">
  <a href="https://upcedupe-my.sharepoint.com/:v:/g/personal/u202113310_upc_edu_pe/IQBcEJ_ITJTYQaugUbTGYrrtAQnXLhbBgqHUf9B7Hzy5onI?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=k9wWZl">Ver video de prototipo mobile</a>
</div>

<br>

<br>

Los criterios de interacción que guiaron el diseño fueron:

- **Consistencia:** todos los flujos mantienen el mismo estilo visual, patrones de navegación y componentes reutilizables.
- **Minimización de pasos:** cada tarea se completa en el menor número de clics posible.
- **Feedback inmediato:** cada acción del usuario genera una respuesta visual clara (confirmaciones, cambios de estado, mensajes de error).
- **Navegación predecible:** el menú lateral y la barra superior mantienen siempre la misma estructura y ubicación.
- **Accesibilidad:** contraste adecuado, tipografía legible, botones con estados de foco y navegación por teclado.

Los prototipos respetan las decisiones de arquitectura de información definidas previamente:

- **Sistema de navegación:** el menú lateral contiene las secciones principales (Dashboard, Mis reservas, Mis cocheras, Ingresos, Perfil) y se mantiene fijo en todas las pantallas.
- **Jerarquía visual:** los indicadores clave (KPIs) se ubican en la parte superior de cada pantalla, seguidos de las acciones principales y los detalles secundarios.
- **Etiquetado:** los textos de la interfaz son cortos, claros y consistentes con el lenguaje ubicuo del dominio.
- **Búsqueda y filtrado:** las pantallas de búsqueda permiten filtrar por fecha, ubicación y tipo de cochera.

<br>

A continuación presentaremos los flujos de interacción cubiertos por los prototipos.

**Flujo de Conductores**

Este flujo corresponde al usuario que busca y reserva una cochera.

1. **Login:** el conductor ingresa con sus credenciales.
Dashboard Driver: visualiza el resumen de sus reservas y accesos rápidos.

2. **Búsqueda:** filtra cocheras por ubicación, fecha y hora.

3. **Resultados:** revisa las cocheras disponibles con su información resumida.

4. **Detalle de cochera:** consulta la información completa y el precio.

5. **Confirmación de reserva:** selecciona la duración y confirma el pago.

6. **Reserva exitosa:** recibe la confirmación y los detalles de la reserva.

7. **Mis reservas:** consulta el historial de reservas anteriores.

<br>

**Flujo de propietarios**

Este flujo corresponde al usuario que publica y gestiona cocheras.

1. **Login:** el propietario ingresa con sus credenciales.

2. **Dashboard propietario:** visualiza los indicadores de su negocio (ingresos, reservas activas, ocupación).

3. **Solicitudes de reserva:** revisa y aprueba o rechaza solicitudes.

4. **Mis cocheras:** administra las cocheras publicadas.

5. **Publicar cochera:** completa el formulario con los datos de la nueva cochera.

6. **Mis ingresos:** consulta los ingresos generados y los reportes.

### 4.6. Domain-Driven Software Architecture.

### 4.6.1. Design-Level Event Storming

Para desarrollar el Design-Level Event Storming de ParkShare se tomó como punto de partida el Big Picture Event Storming realizado previamente. A partir de dicho modelo se llevó a cabo un proceso de refinamiento orientado a identificar con mayor detalle las responsabilidades, límites y elementos principales que conforman el dominio de la solución.

Para este proceso se tomó como referencia la metodología de Design-Level Event Storming propuesta en la guía proporcionada para el curso, considerando las siguientes etapas:

- Unstructured Exploration
- Timelines
- Pain Points
- Pivotal Points
- Commands
- Policies
- Read Models
- External Systems
- Aggregates
- Bounded Contexts

Estas etapas permitieron analizar los principales procesos de ParkShare e identificar actores, comandos, agregados, eventos de dominio y consultas relacionadas con el funcionamiento del servicio. A partir de este análisis se establecieron los principales Bounded Contexts de la solución.

#### Design-Level Event Storming de ParkShare

El siguiente diagrama fue elaborado en Miro y representa el resultado del proceso de Design-Level Event Storming. En él se muestran los principales Bounded Contexts de ParkShare junto con los Commands, Aggregates, Domain Events, Actors y Queries / Read Models involucrados en los procesos del dominio.

![Design-Level Event Storming de ParkShare](../assets/level-eventstorming.png)

#### Bounded Contexts identificados

Como resultado del proceso se identificaron seis Bounded Contexts. Estos fueron clasificados como **Core** o **Supporting** de acuerdo con el nivel de importancia que poseen dentro de la propuesta de valor y funcionamiento de ParkShare.

| Bounded Context            | Tipo       | Responsabilidad                                                                                                                                        | User Stories     |
| -------------------------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------- |
| Identity & Access          | Supporting | Gestiona el registro de usuarios, selección de roles, perfiles, verificación de identidad y vehículos asociados a los conductores.                     | US01–US05        |
| Parking Space Management   | Core       | Gestiona la creación, publicación, actualización, disponibilidad y tarifas de los espacios de estacionamiento ofrecidos por los propietarios.          | US06–US10        |
| Booking                    | Core       | Gestiona la búsqueda de espacios, consulta de disponibilidad, solicitudes de reserva, confirmaciones, rechazos y cancelaciones.                        | US11–US18        |
| Parking Operations         | Core       | Gestiona el pase de estacionamiento, validación de acceso e inicio y finalización de la sesión de uso del espacio reservado.                           | US19–US21        |
| Payments & Payouts         | Supporting | Gestiona los pagos asociados a las reservas, cálculo de cargos, registro de ingresos y transferencias correspondientes a los propietarios.             | US22, US23, US26 |
| Reputation & Notifications | Supporting | Gestiona las calificaciones, reputación de los usuarios y notificaciones relacionadas con reservas, pagos y otras operaciones relevantes del servicio. | US24–US26        |

#### Landing Page

Las User Stories **US27–US30** corresponden al Landing Page de ParkShare y no fueron consideradas como parte de un Bounded Context.

El Landing Page tiene como objetivo presentar la propuesta de valor del producto, explicar su funcionamiento para conductores y propietarios y dirigir a los visitantes hacia la Web Application. Por ello, funciona como un medio de presentación y captación de usuarios, pero no representa un área independiente del dominio de negocio.

### 4.6.2. Software Architecture Context Diagram.

![ParkShare Context Diagram](../assets/chapter-04/SystemContext-dark.png)

### 4.6.3. Software Architecture Container Diagrams.

![ParkShare Container Diagram](../assets/chapter-04/Containers-dark.png)

### 4.6.4. Software Architecture Components Diagrams.
#### Identity & Access
![Identity Component Diagram](../assets/chapter-04/IdentityComponents-dark.png)
#### Parking Management 
![Parking Component Diagram](../assets/chapter-04/ParkingComponents-dark.png)
#### Payment & Billing
![Payment Component Diagram](../assets/chapter-04/PaymentComponents-dark.png)
#### Reservation & Parking Session
![Reservation Component Diagram](../assets/chapter-04/ReservationComponents-dark.png)

### 4.7. Software Object-Oriented Design.

### 4.7.1. Class Diagrams.
En esta sección se presenta el diseño orientado a la solución, desarrollado a partir de los requerimientos funcionales, User Stories, User Task Matrix, eventos identificados durante el proceso de análisis del dominio. El objetivo de este diseño es representar la estructura lógica del sistema mediante diagramas que describen las principales entidades, relaciones y comportamientos involucrados en ParkShare, la plataforma de búsqueda, reserva y gestión de espacios de estacionamiento.

La solución fue modelada considerando un enfoque basado en bounded contexts, permitiendo organizar las responsabilidades del sistema en módulos funcionales relacionados con la gestión de usuarios, la administración de espacios de estacionamiento, la búsqueda y visualización en mapa interactivo, las reservas y disponibilidad, los pagos y facturación, y las notificaciones. Cada diagrama incluye clases, atributos, métodos, relaciones, multiplicidades y niveles de acceso. Para la elaboración de los diagramas se utilizará PlantUML.

<div style="text-align:center;"><img src="../assets/class_diagram.png" alt="texto"></div>

### 4.8. Database Design.

### 4.8.1. Database Diagrams.
En esta sección se presenta el diseño de base de datos, desarrollado a partir de los requerimientos funcionales, entidades identificadas y funcionalidades relacionadas con la búsqueda, reserva y administración de espacios de estacionamiento.

El objetivo es garantizar la integridad y organización de la información utilizada por la plataforma, permitiendo almacenar datos relacionados con usuarios, vehículos, espacios de estacionamiento, disponibilidad, reservas, pagos y notificaciones. Se contemplan relaciones entre entidades, restricciones y mecanismos que soporten operaciones de búsqueda en tiempo real y gestión confiable de reservas.

Para la elaboración de los diagramas de base de datos se utilizará PlantUML, empleando diagramas entidad-relación para representar tablas, columnas, claves primarias, claves foráneas y relaciones entre entidades.

<div style="text-align:center;"><img src="../assets/parkShare-database-diagram.png" alt="texto"></div>


