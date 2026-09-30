# Memoria del Proyecto Intermodular: PayClear

* Asignatura: Proyecto Intermodular
* Curso: 2º Desarrollo de Aplicaciones Multiplataforma (DAM)
* Convocatoria: Sprint 1 - Ideación, Arquitectura y Prototipado Base
* Fecha: Octubre 2026

---

# 1. INTRODUCCIÓN

## 1.1. Contexto del proyecto
El proyecto **PayClear** se desarrolla en el marco académico del módulo profesional de **Proyecto Intermodular**, correspondiente al segundo curso del Ciclo Formativo de Grado Superior en **Desarrollo de Aplicaciones Multiplataforma (DAM)**.

La iniciativa surge durante el **Sprint 1** (fase orientada a ideación, arquitectura y prototipado base) como respuesta a la necesidad de diseñar una herramienta de software centrada en la gestión contable y la compensación multilateral de deudas en entornos compartidos. El proyecto se articula en una hoja de ruta progresiva: parte de un prototipo interactivo de alta fidelidad en Figma, continúa con una implementación de escritorio en Java Swing mediante NetBeans Matisse, y culmina en su posterior adaptación multiplataforma con Flutter.

## 1.2. Problema o necesidad detectada
En dinámicas de convivencia y actividades colectivas (pisos compartidos, viajes grupales, asociaciones o colectivos juveniles), la asimetría de los gastos adelantados por distintos miembros produce habitualmente:
* Transferencias cruzadas repetitivas e ineficientes.
* Errores en el cálculo manual y falta de transparencia sobre las cantidades pendientes.
* Conflictos y desacuerdos interpersonales.

Frente a esta situación, las alternativas comerciales más extendidas del mercado (como Splitwise o Tricount) presentan una serie de deficiencias estructurales:

| Problema en el Mercado | Impacto en el Usuario | Enfoque Crítico |
| :--- | :--- | :--- |
| **Dependencia de la nube** | Obliga a disponer de conexión continua a internet para consultar o ingresar datos. | Inoperatividad en situaciones sin cobertura (viajes, desplazamientos). |
| **Recopilación de datos** | Exige registro formal, correos electrónicos y almacenamiento de datos personales en servidores ajenos. | Pérdida de privacidad y fricción al dar de alta a participantes casuales. |
| **Monetización invasiva** | Restricciones de operaciones diarias bajo muro de pago (*freemium*) o inserción agresiva de publicidad. | Experiencia de usuario degradada para una necesidad aritmética básica. |
| **Interfaces sobrecargadas** | Múltiples menús, pasos innecesarios y algoritmos de liquidación en caja negra remota. | Pérdida de agilidad en el uso cotidiano. |

## 1.3. Propuesta de solución
PayClear se define como una plataforma de software orientada a la tarea directa bajo el paradigma **Local-First**, fundamentada en:

* **Soberanía y privacidad absoluta de datos:** Funcionamiento 100% en local, sin cuentas obligatorias, contraseñas ni almacenamiento en servidores externos.
* **Modelo abierto y sin barreras:** Ausencia total de publicidad, suscripciones o limitaciones diarias en el registro de movimientos.
* **Algoritmo voraz local:** Optimización matemática integrada en el cliente que reduce el saldo consolidado al menor número posible de pagos directos entre personas.
* **Flujo directo en dos pasos:** Interfaz optimizada exclusivamente para dos tareas esenciales: registrar movimiento y liquidar deudas.
* **Diseño visual modular y desacoplado:** Presentación unificada en una sola ventana (tabla de gastos y balances individuales) con retroalimentación cromática del estado financiero y arquitectura desacoplada Modelo-Vista-Controlador (MVC).

## 1.4. Objetivos del proyecto

### 1.4.1. Objetivo general
Diseñar, prototipar y validar técnicamente una interfaz de usuario limpia, intuitiva y desacoplada para la gestión contable y la compensación multilateral de gastos compartidos en local, maximizando la privacidad y minimizando las transferencias bancarias necesarias.

### 1.4.2. Objetivos específicos

| Área de Trabajo | Objetivos Específicos |
| :--- | :--- |
| **Diseño y Usabilidad (UI/UX)** | • Diseñar un espacio de trabajo único que integre en una sola ventana la tabla de registros y el balance por integrante.<br>• Crear el componente reutilizable `TarjetaSaldoParticipante` con señalización cromática según el estado contable.<br>• Diseñar un diálogo modal desacoplado (`DialogoDivisionRapida`) para agilizar el reparto sin interferir en la vista principal. |
| **Arquitectura Técnica** | • Implementar el patrón Modelo-Vista-Controlador (MVC) para independizar el renderizado visual de la lógica matemática.<br>• Planificar la migración del prototipo hacia Java Swing con NetBeans Matisse y la especificación de Custom JavaBeans.<br>• Modelar el catálogo formal de clases y eventos de interacción del sistema. |
| **Lógica Contable** | • Diseñar e integrar un algoritmo voraz local para calcular la ruta óptima de liquidación en el mínimo número de transacciones.<br>• Permitir el cálculo de balances contemplando tanto el reparto proporcional como el consumo individualizado por participante. |

## 1.5. Alcance del proyecto
El alcance del proyecto se estructura en tres fases e hitos técnicos:

| Fase / Sprint | Estado | Entregables y Líneas de Trabajo |
| :---: | :---: | :--- |
| **Sprint 1** | **Completado** | • Prototipo interactivo navegable de alta fidelidad en Figma (vista principal y calculadora modal).<br>• Sistema de componentes visuales reutilizables con variantes de estado (`TarjetaSaldoParticipante`).<br>• Especificación técnica de la arquitectura MVC, modelo de clases y validación funcional del algoritmo de liquidación. |
| **Sprint 2** | *Planificado* | • Maquetación de la interfaz gráfica de escritorio en Java Swing con NetBeans Matisse.<br>• Implementación del componente reutilizable como Custom JavaBean.<br>• Persistencia de datos en ficheros locales estructurados (JSON/fichero plano) y lógica avanzada de reparto asimétrico. |
| **Sprint 3** | *Proyectado* | • Módulo de exportación de resúmenes y balances a documentos CSV y PDF.<br>• Migración e implementación de un cliente nativo multiplataforma utilizando Flutter y Dart. |

## 1.6. Limitaciones y exclusiones
Para mantener el foco en la calidad de la interfaz y la privacidad de la arquitectura, se establecen las siguientes restricciones:

* **Alcance de la fase actual:** El entregable del Sprint 1 se limita al prototipo interactivo de alta fidelidad en Figma, sus especificaciones de diseño y la memoria técnica; la implementación en código ejecutable (Swing/Flutter) forma parte de los sprints posteriores.
* **Exclusión de conectividad y nube:** No se contempla la inclusión de pasarelas de pago telemático, sincronización multiusuario en tiempo real ni almacenamiento en bases de datos en la nube.
* **Exclusión de cuentas y perfiles:** Se descartan módulos de inicio de sesión, roles de usuario, sistemas de autenticación y gestión de credenciales.
* **Tecnologías descartadas:** Se excluye de forma justificada el uso de bibliotecas gráficas obsoletas como Java AWT, debido a su dependencia del sistema operativo, estética desfasada e inconsistencias visuales multiplataforma.

## 1.7. Estructura de la memoria
El resto del presente documento técnico se desarrollará a lo largo del curso en los siguientes bloques temáticos:

| Sección | Contenido Proyectado |
| :--- | :--- |
| **1. Análisis del Contexto y Viabilidad** | Estudio de mercado exhaustivo, encuestas de usuarios, viabilidad técnica, económica y legal (RGPD). |
| **2. Planificación y Gestión del Proyecto** | Metodología Scrum, roles, presupuesto detallado y gestión del repositorio. |
| **3. Análisis de Requisitos** | Requisitos funcionales, no funcionales, reglas de negocio y matriz de trazabilidad. |
| **4. Diseño de la Solución** | Arquitectura del software, diseño de datos, mapas de navegación y diseño visual. |
| **5. Desarrollo e Implementación** | Construcción de componentes, frameworks, persistencia y código significativo. |
| **6. Pruebas y Aseguramiento de Calidad** | Casos de prueba, cobertura, pruebas de usabilidad y corrección de incidencias. |
| **7. Despliegue y Puesta en Producción** | Empaquetado de la solución, requisitos de instalación y mantenimiento. |
| **8. Manuales de Uso** | Manual técnico, guía de usuario y resolución de dudas comunes. |
| **9. Resultados y Evaluación Final** | Cumplimiento de objetivos, valor aportado y competencias adquiridas. |
| **10. Conclusiones y Líneas Futuras** | Retos superados, escalabilidad y balance global del proyecto. |


* Pablo salda su deuda total (-25,00 €) transfiriendo 25,00 € a Guillermo.
* Jesús salda su deuda total (-8,00 €) pagando 3,00 € a Guillermo (completando los +28,00 € que le correspondían cobrar) y 5,00 € a José Luis (completando los +5,00 € que le correspondían cobrar).

**Resultado:** Con únicamente 3 transferencias bancarias, todas las posiciones deudoras y acreedoras quedan extinguidas a 0,00 € con exactitud matemática, respetando el consumo real de cada miembro.
