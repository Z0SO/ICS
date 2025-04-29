
## Briefing Document: Revisión de Conceptos Clave en Ingeniería de Software y Metodologías Ágiles

  

**Fecha:** 16 de mayo de 2024

  

**Preparado para:** zoso

**Propósito:** Este documento proporciona un resumen detallado de los temas, ideas y hechos más importantes extraídos de los cuatro documentos fuente proporcionados. Se incluyen citas directas para ilustrar los puntos clave.

  

### 1. Patrones del Proceso (Apunte IyCSW)
  

Los patrones del proceso son soluciones reutilizables a problemas comunes encontrados durante el trabajo de ingeniería de software.

* **Definición:** Un patrón del proceso describe un problema relacionado con el proceso, identifica el ambiente en el que surge y sugiere soluciones.

* **Niveles de Abstracción:** Pueden definirse a varios niveles, desde modelos completos hasta actividades específicas.

* **Tipos de Patrones:**

* **Patrones de fase:** Definen secuencias de actividades estructurales (ejemplo: Modelo Espiral).

* **Patrones de etapa:** Abordan problemas de actividades estructurales completas (ejemplo: Establecer Comunicación).

* **Patrones de tarea:** Resuelven problemas asociados con acciones específicas (ejemplo: Recabar Requerimientos).

* **Formato Estructurado:** Los patrones siguen un formato que incluye nombre, fuerzas, tipo, contexto inicial, problema, solución, contexto resultante, patrones relacionados y ejemplos de uso.

* **Beneficios:**

* Proporcionan mecanismos efectivos para enfrentar problemas recurrentes.

* Permiten desarrollar descripciones jerárquicas del proceso.

* Facilitan la reutilización para definir variantes del proceso.

* **Aplicación:** Actúan como bloques constitutivos para definir modelos de proceso específicos adaptados a las necesidades de los equipos.

  

### 2. Gestión de la Configuración del Software (GCS)

  

La GCS es crucial para manejar la evolución de los artefactos del software a lo largo de su ciclo de vida.

  

* **Elementos de Configuración:** Los ICS (Ítems de Configuración del Software) son los diversos artefactos del software que se gestionan.

* **Versiones, Revisiones y Variantes:**

* **Versión:** "Una instancia de un artefacto del software. De cualquier elemento de software, son varios".

* **Revisión:** "Versión de un artefacto, para reemplazar versiones anteriores de un artefacto". Una revisión reemplaza versiones previas.

* **Variante:** "Se añaden cosas, pero ya una versión existente. No se reemplaza". Se agregan funcionalidades sin reemplazar la base existente.

* **Entrega (Release):** "Versión entregada al cliente". No necesariamente implica su puesta en producción (puede ser una versión alpha). La documentación también puede ser una release.

* **Repositorio:** "En la actualidad, los ICS se mantienen en una base de datos del proyecto, o repositorio". Sirve para almacenamiento y provee servicios, especialmente en relación con el versionado. "El repositorio debe guardar todas estas versiones para permitir la administración efectiva de los productos liberados y, a los desarrolladores, regresar a versiones anteriores".

* **Contabilidad del Estado:** Implica conocer el estado del entorno de desarrollo. El "reporte del estado de la configuración (en ocasiones llamado contabilidad de estado) es una tarea ACS que responde las siguientes preguntas: 1) ¿Qué ocurrió? 2) ¿Quién lo hizo? 3) ¿Cuándo ocurrió? 4) ¿Qué más se afectará?".

* **Control de Versiones:** Facilita el almacenamiento y referencia a versiones a lo largo del tiempo y "helps us bridge the gap between single-developer and multideveloper processes". Es crítico para escalar equipos y organizaciones.

* **La Regla de "Una Versión":** Para cada dependencia en el repositorio, debe haber solo una versión para evitar ambigüedad ("For every dependency in our repository, there must be only one version of that dependency to choose from?").

* **Sistemas de Control de Versiones:** Actualmente existen muchos en el mercado (Git, GitLab, etc.). "GIT local, y github te venden el servicio".

* **Checkout:** "Sacar LC del repo a tu entorno de trabajo". Es la acción de obtener una copia de los archivos del repositorio para trabajar en ellos.

  

### 3. DevOps, Integración Continua (IC), Entrega Continua y Despliegue Continuo (INTEGRADOR - ISW.pdf)

  

Estos conceptos buscan optimizar el ciclo de vida del software mediante la automatización y la colaboración.

  

* **DevOps:** Engloba el Control de la Configuración, Control de Cambios y Control de Versiones.

* **Control de Cambios:** Se gestiona a través del repositorio de código y los elementos que contiene.

* **Integración Continua (IC):** Proceso donde el código se integra frecuentemente, se construye y se prueba automáticamente. "¿QUÉ ES LA BUILD?": Es el resultado del proceso de compilación. Elementos clave de la IC son el Equipo, el Control de Versiones, el Servidor de IC y el Feedback.

* Ejemplo de pipeline CI: Descarga el código al subir al master, compila, ejecuta pruebas unitarias y/o despliega a un entorno de integración para pruebas de sistema.

* **Despliegue Continuo:** Automatiza el despliegue de nuevas versiones a producción.

* **Entrega Continua:** Asegura que el software esté siempre listo para ser desplegado a producción, aunque la decisión final sea manual. "Continous Delivery vs Continous Deployment": La entrega continua permite decidir cuándo desplegar, mientras que el despliegue continuo lo automatiza.

* **DevOps Culture:** Fomenta la colaboración, la automatización y la mejora continua.

* **Estrategias de Deployment en Entornos Masivos:**

* **Blue/Green Deployment:** Mantiene dos entornos idénticos (uno activo - blue, uno inactivo - green). La nueva versión se despliega al entorno inactivo y se prueba antes de cambiar el tráfico. Permite un rollback fácil.

* **Canary Release:** Despliega la nueva versión a un pequeño subconjunto de usuarios para probarla en un entorno real antes de lanzarla a todos. "Podemos hacer smoke tests (probar un uso normal de un usuario) para ver si todo está funcionando".

* **Facebook Multiple Canary Releases:** Utiliza múltiples despliegues canarios con diferentes grupos de usuarios.

  

### 4. Metodologías Ágiles y Historias de Usuario (Todos los documentos)

  

Las metodologías ágiles se centran en la entrega de valor temprana y continua, la colaboración y la adaptación al cambio. Las Historias de Usuario son una forma de expresar los requisitos desde la perspectiva del usuario.

  

* **Manifiesto Ágil:** Prioriza individuos e interacciones sobre procesos y herramientas, software funcionando sobre documentación extensiva, colaboración con el cliente sobre negociación contractual y respuesta al cambio sobre seguir un plan.

* **Historias de Usuario (US o HUS):**

* **Formato:** "[Título] Cómo [ROL en esa funcionalidad], quiero hacer [FUNCIONALIDAD] con el objetivo de [BENEFICIO]".

* **Componentes (Las 3 C de Ron Jeffries):** Tarjeta (Card - representación física), Conversación (Conversation - discusión y planificación), Confirmación (Confirmation - pruebas y validación).

* **Epics → US → Tasks:** Las epics son funcionalidades grandes que se dividen en historias de usuario, las cuales a su vez se descomponen en tareas.

* **Criterios de Aceptación:** "Es todo aquello que me indica el usuario para definir el testing y me sirve para saber si es lo que el usuario esperaba, para validar si lo que estamos haciendo es lo que el cliente quiere". Se verifican a través de tests y en la review.

* **¿Cuándo se obtienen las HUS?:** "Al principio y durante el proyecto, porque estamos hablando de agilidad". El Product Backlog está en constante movimiento.

* **Comprobar Calidad (MÉTODO INVEST):** Independent, Negotiable, Valuable, Estimateable, Small, Testable. "el método invest sirve para comprobar la calidad de una historia de usuario".

* **Tips para escribir buenas HUS:** Historia objetivo, Slice the cake (dividir por funcionalidades completas), Write Closed Stories (con un logro significativo).

* **User Stories’ Bad Smells:** Historias demasiado grandes, dependencias fuertes, goldplating (añadir funcionalidades innecesarias).

* **Mapas de Historias de Usuario:** Ayudan a visualizar el product backlog, organizar las historias y definir el flujo del usuario. "THINK - WRITE - EXPLAIN - PLACE".

* **Priorización:** Es clave para entregar valor. El Product Owner (PO) es quien prioriza, considerando el valor para el cliente, el costo y el riesgo. Métodos de priorización: Filtro de priorización, Pirámide de priorización, KANO (Necesidades, Esperados, No esperados, Indiferentes), MÉTODO MOSCOW (Must have, Should have, Could have, Won't have).

* **Producto Mínimo Viable (MVP):** "El MVP es el producto mínimo viable. Es el producto mínimo por el qué el cliente me va a pagar". Ayuda a validar hipótesis y obtener feedback temprano. "definir la primer release → como minimo tendra todas las US con prioridad “M” (must be done)".

* **Estimación:** Determinar el tiempo y costo. Se realiza en Puntos de Historia (medida relativa de la complejidad, esfuerzo y riesgo). "Un punto de historia es la cantidad de esfuerzo qué supone desarrollar una historia de usuario, la complejidad de su desarrollo y el riesgo inherente. Es el esfuerzo ideal". Técnicas: Planning Poker, Analogía. "No existe una forma para calcular los puntos de historia, importan los valores relativos de una historia frente a otra".

* **Velocidad del Equipo:** "La velocidad es la cantidad de puntos de historia que el equipo puede terminar en un sprint". Clave para la estimación ágil y la planificación. Se basa en el histórico de sprints anteriores ("Yesterday’s weather").

* **SCRUM:** Marco de trabajo ágil. Pilares: Transparencia, Inspección, Adaptación. Valores: Coraje, Enfoque, Compromiso, Respeto, Apertura. Roles: Scrum Master, Product Owner, Equipo.

* **Product Owner (PO):** Responsable del Product Backlog, prioriza las necesidades del cliente, escribe las US, define el MVP y el Definition of Done (DOD). "Es el encargado de escribir las US -debe definir buenas US-".

* **Equipo:** Auto-organizado y multifuncional, define cómo realizar el trabajo.

* **Scrum Master:** Facilita el proceso Scrum, elimina impedimentos.

* **Eventos (Meetings):** Sprint Planning, Dailys (reuniones diarias), Sprint Review (revisión del sprint con stakeholders), Sprint Retrospective (retrospectiva para la mejora continua).

* **Sprint:** Iteración de tiempo fijo para completar un conjunto de trabajo. Al final se obtiene un incremento potencialmente entregable.

  

### 5. Calidad del Software y Testing (INTEGRADOR - ISW.pdf, Resumen Ing de SW.pdf)

  

La calidad se aborda en múltiples dimensiones y el testing es fundamental para asegurarla.

  

* **Calidad del SW:** Abarca calidad del proceso, del producto y de las personas.

* **Deuda Técnica:** Consecuencia de decisiones de diseño o implementación que son convenientes a corto plazo pero pueden generar problemas a largo plazo.

* **Factores de Calidad de McCall:** Características Operativas, Adaptabilidad a Nuevos Entornos, Capacidad de soportar cambio (Revisión).

* **Verificación y Validación:** "Si el SW construido cumple los requerimientos, caja negra" (validación).

* **Modelos de Calidad:** CMMI, SPICE - ISO 33000, ISO 29110, CISQ, ISO 25000.

* **Testing:** Proceso para encontrar defectos en el software.

* **Técnicas de Testing:** Diseño de Casos de Prueba.

* **Pruebas de Caja Blanca (o caja de cristal):** Se basan en la estructura interna del código. "Me preocupo y diseño la prueba basándome en la estructura de código dentro del artefacto". Técnicas: Prueba del Camino Básico, Complejidad Ciclomática, Pruebas de Estructura de Control, Prueba de Bucles.

* **Pruebas de Caja Negra (o prueba de comportamiento):** Se basan en los requisitos funcionales y no consideran la estructura interna. "evaluó variables de entrada y sus posibles salidas". Técnicas: Partición Equivalente, Análisis de Valores Límite, Prueba de Comparación, Prueba de la Tabla Ortogonal, Métodos de Pruebas Basadas en Grafos.

* **Estrategias de Testing:** Unit Tests (pruebas unitarias), Integration Tests (pruebas de integración), Pruebas de Regresión, Smoke Tests (pruebas de humo - verificar la funcionalidad básica), Validation Tests (pruebas de validación - ¿se hizo el producto correcto?), System Tests (pruebas del sistema - el software en su entorno).

* **Automatización de Pruebas:** Automatizar la ejecución de pruebas para aumentar la eficiencia y la cobertura.

* **Release y Pruebas:** Las releases deben ser testeadas. Las estrategias de deployment (Blue/Green, Canary) incorporan pruebas en el proceso de liberación.

  

### 6. Gestión de Versiones y Ramificación (GIT) (INTEGRADOR - ISW.pdf, Resumen Ing de SW.pdf)

  

El control de versiones, especialmente con Git, es esencial para la gestión de cambios.

  

* **Repositorio (Repo):** Almacén centralizado del código y su historial. "Repo de código → repo GIT - con host en GITHUB o BITBUCKET".

* **Commit:** Unidad de cambio en Git. "Cada modificación entre un commit y otro implica una serie de modificaciones → delta de cambios". Se recomienda hacer commits frecuentes y con cambios coherentes.

* **Branch (Rama):** Línea de desarrollo paralela. Estrategias de branching definen cómo se gestionan las diferentes versiones y funcionalidades. "Estrategia branch → ¿desarrollaremos en distintas ramas? ¿tendremos una rama de integración que vigilará el servidor de integración continua? ¿Mantendremos una única rama?".

* **Pull:** Obtener los últimos cambios del repositorio remoto al local. "Al inicio del día arrancó con un pull para tener la última versión → hago pull todas las veces que quiera".

* **Push:** Subir los cambios del repositorio local al remoto.

  

### 7. Evolución de la Ingeniería de Software (Resumen Ing de SW.pdf)

  

La disciplina de la ingeniería de software ha evolucionado significativamente.

  

* **Década del 50:** Se trata la IS igual que la de HW ("measure twice cut once").

* **Década del 60:** Enfoque "code and fix", "cowboy programmers", código spaghetti. Surgen las ideas de reutilización y arquitectura software.

* **Década del 70:** Formalidad y procesos en cascada, modularidad, cohesión y acoplamiento, information hiding.

* **Década del 00:** La adaptabilidad gana a la repetibilidad. Consideración de stakeholders. YAGNI (You Ain't Gonna Need It).

* **Década del 10:** Mantener el alcance dentro de lo posible.

  

### 8. Definición del Ámbito (INTEGRADOR - ISW.pdf, Resumen Ing de SW.pdf)

  

Definir claramente el alcance del proyecto es fundamental para evitar ambigüedades y gestionar expectativas.

  

* **Elementos para determinar el ámbito:** Contexto, Información (entrada/salida), Conjunto de Funcionalidad, Rendimiento.

* **Características de una buena definición del ámbito:** No debe ser ambiguo, definir bien los límites y restricciones, acotar el enunciado en problemas grandes, considerar los riesgos de no incluir ciertas partes.

  

### 9. Hitos (Resumen Ing de SW.pdf, [Extra] Apunte - Primer Parcial.pdf)

  

Un hito es un punto de referencia, "un ítem a cumplir para una entrega parcial".

  

### 10. Open Source (INTEGRADOR - ISW.pdf, Resumen Ing de SW.pdf)

  

El desarrollo de código abierto creció con Stallman, el Kernel Linux de Torvalds y la ampliación de estándares web por Tim Berners-Lee.

  

### 11. Clientes Exigentes (INTEGRADOR - ISW.pdf, Resumen Ing de SW.pdf)

  

La creciente familiaridad con las computadoras llevó a los consumidores a exigir más características en el software.

  

### 12. UML (INTEGRADOR - ISW.pdf, Resumen Ing de SW.pdf)

  

El Lenguaje Unificado de Modelado (UML) potenció el uso de patrones y la Programación Orientada a Objetos (POO).

  

### 13. Release vs Prototipo ([Extra] Apunte - Primer Parcial.pdf)

  

* **Release:** Implica la implementación del producto, está en producción y es usado por el usuario.

* **Prototipo:** No está implementado, su propósito es que el Product Owner valide la funcionalidad desarrollada. "La diferencia radica en que una release implica la implementación del producto, es decir, está en producción, es usado por el usuario. Por otro lado, el prototipo no está implementado, tiene como propósito que el product owner valide la funcionalidad desarrollada."

  

Este resumen destaca los conceptos centrales abordados en los documentos proporcionados, ofreciendo una visión detallada y organizada de la ingeniería de software, las metodologías ágiles y las prácticas de gestión de la configuración y pruebas.