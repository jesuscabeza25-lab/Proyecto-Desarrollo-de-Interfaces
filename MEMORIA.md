# Memoria Técnica de Desarrollo: PayClear

* Asignatura: Desarrollo de Interfaces
* Curso: 2º Desarrollo de Aplicaciones Multiplataforma (DAM)
* Convocatoria: Sprint 1 - Ideación, Arquitectura y Prototipado Base

---

## 1. Descripción del Proyecto y Justificación del Problema

### 1.1 Planteamiento y Necesidad Real
PayClear es una plataforma de software orientada a la gestión contable y la compensación multilateral de saldos en entornos compartidos. En ámbitos grupales, los adelantos económicos asimétricos suelen desembocar en transferencias cruzadas redundantes, disputas interpersonales y falta de transparencia contable.

A diferencia de las opciones comerciales existentes en el mercado, PayClear garantiza soberanía de datos (Local-First), ausencia total de muros de pago o límites diarios de operación, y un flujo de entrada optimizado en dos pasos: registrar movimiento y liquidar deudas.

### 1.2 Identificación del Público Objetivo
* **Compañeros de Piso:** Reparto mensual de suministros comunes (electricidad, gas, agua, conexión a internet) y cesta de limpieza sin necesidad de registros manuales.
* **Viajeros y Grupos de Ocio:** Liquidación al término de desplazamientos donde existen gastos heterogéneos (alojamientos, combustibles, entradas, peajes).
* **Colectivos y Asociaciones:** Entidades juveniles, deportivas o estudiantiles donde varios coordinadores adelantan compras y necesitan cerrar cuentas sin descuadres.

### 1.3 Objetivos Principales de la Interfaz Gráfica
* Diseñar un espacio de trabajo limpio donde la tabla de registros y el balance individual coexistan en una sola ventana de escritorio.
* Implementar retroalimentación visual instantánea mediante un componente propio que transmita el estado del participante mediante cambios de color (verde para saldo acreedor, rojo para saldo deudor y gris para saldo neutral).
* Aislar la capa de renderizado de la capa matemática y de negocio siguiendo el patrón arquitectónico Modelo-Vista-Controlador (MVC).

---

## 2. Benchmarking (Análisis Comparativo)

| Parámetro de Evaluación | Splitwise | Tricount | <u>PayClear<u>  |
| :--- | :--- | :--- | :--- |
| Plataforma Objetivo | Web y Móvil | Web y Móvil | Prototipo de escritorio navegable (Figma) con hoja de ruta a Swing y Flutter |
| Dependencia de Conexión | Conectividad continua obligatoria | Obligatoria para sincronización | Funcionamiento 100% en local |
| Gestión de Identidad | Cuenta y autenticación obligatoria | Enlace de grupo o cuenta | Sin registro ni almacenamiento de datos personales |
| Modelo de Explotación | Freemium con restricciones diarias | Inserción de publicidad comercial | Software libre sin limitaciones ni costes |
| Algoritmo de Liquidación | Cerrado en servidor | Algoritmo básico en la nube | Algoritmo voraz local |
| Sobrecarga de Interfaz | Compleja con múltiples submenús | Moderada | Mínima y orientada a la tarea directa |

---

## 3. Planificación Ágil y Metodología Scrum (Sprint 1)

El desarrollo del proyecto se estructura bajo el marco de Scrum 2020 utilizando GitHub Projects como herramienta de control y seguimiento.

### 3.1 Pila del Producto (Product Backlog) Priorizada

| Código | Descripción de la Funcionalidad | Prioridad | Estimación | Estado |
| :---: | :--- | :---: | :---: | :--- |
| PB-01 | Prototipo interactivo en Figma de la vista principal y calculadora | Muy Alta | 8 pts | Terminado |
| PB-02 | Sistema de componentes visuales reutilizables en Figma (TarjetaSaldo) | Muy Alta | 8 pts | Terminado |
| PB-03 | Especificación técnica de arquitectura MVC y modelo de clases | Alta | 5 pts | Terminado |
| PB-04 | Pruebas de usabilidad y verificación del prototipo interactivo | Alta | 5 pts | Terminado |
| PB-05 | Implementación del maquetado Swing con NetBeans Matisse | Alta | 8 pts | Sprint 2 |
| PB-06 | Programación del Custom JavaBean en Java Swing | Muy Alta | 8 pts | Sprint 2 |
| PB-07 | Persistencia local de balances en formato plano / JSON | Media | 5 pts | Sprint 2 |
| PB-08 | División avanzada asimétrica y soporte de pagos parciales | Media | 8 pts | Sprint 2 |
| PB-09 | Exportación de balances a ficheros CSV y PDF | Baja | 3 pts | Sprint 3 |
| PB-10 | Migración multiplataforma con cliente nativo en Flutter | Baja | 13 pts | Sprint 3 |

### 3.2 Pila del Sprint (Sprint Backlog 1)

* Objetivo del Sprint (Sprint Goal): Diseñar y entregar un prototipo interactivo de alta fidelidad en Figma que simule de forma completa el comportamiento de una interfaz operativa de escritorio, definiendo el sistema de componentes visuales reutilizables y la especificación técnica formal de la arquitectura MVC para su posterior implementación.
* Definición de Terminado (Definition of Done - DoD):
  1. Flujo completo navegable en Figma sin enlaces rotos ni botones sin acción en el caso de uso base.
  2. Componente visual reutilizable modelado con variantes de estado (acreedor, deudor y neutral).
  3. Memoria técnica completa en Markdown cubriendo los criterios del RA1.
  4. Tablero de GitHub Projects actualizado con las tareas del Sprint 1 finalizadas y vinculadas al incremento entregado.

| Issue | Tarea Técnica | Criterio RA1 | Responsable | Estimación |
| :---: | :--- | :---: | :--- | :---: |
| #15 | Redacción de la Memoria Técnica en Markdown | RA1.a | Guillermo / Jesús | 3 pts |
| #17 | [Diseño/UI] Sistema de Componentes Reutilizables en Figma (TarjetaSaldoParticipante) | RA1.d, RA1.g | Guillermo | 5 pts |
| #18 | [Diseño/UI] Maquetación de la Ventana Principal en Figma (VistaPrincipal) | RA1.b, RA1.c | José Luis | 6 pts |
| #19 | [Diseño/UI] Diseño del Diálogo Modal de la Calculadora Rápida en Figma | RA1.b, RA1.c | José Luis | 3 pts |
| #20 | [Prototipado] Conexión Interactiva y Flujo de Navegación en Figma | RA1.f, RA1.g | Guillermo | 5 pts |
| #21 | [Validación/QA] Pruebas de Usabilidad y Verificación del Prototipo Interactivo | RA1.h | Equipo Scrum | 2 pts |
| #22 | [Sprint] Preparación y Ensayo de la Sprint Review (10 min) | Evaluación | Equipo Scrum | 2 pts |
| #23 | [Arquitectura] Especificación del Modelo de Datos y Flujo de Navegación | RA1.h | Jesús | 4 pts |

---

## 4. Alcance Técnico y Arquitectura del Sistema

### 4.1 Patrón de Arquitectura Gráfica: MVC
Se define una arquitectura desacoplada para garantizar que las clases visuales no contengan responsabilidades de negocio durante el desarrollo:

```text
       Eventos de Usuario
  [Vista] ────────────────> [Controlador]
     ^                           │
     │ Actualiza                 │ Modifica estado
     │ componentes               ▼ y ejecuta cálculos
     └─────────────────────── [Modelo]
```

* Modelo (com.payclear.modelo): Clases Participante y Gasto. Mantendrán el estado contable y la lógica del algoritmo voraz sin dependencias de paquetes gráficos.
* Vista (com.payclear.vista): Formularios prototipados inicialmente en Figma y proyectados para maquetación en NetBeans Matisse (VistaPrincipal y DialogoDivisionRapida). Su función se restringe a renderizar información y capturar interacciones.
* Controlador (com.payclear.controlador): Clase ControladorPrincipal. Gestionará los eventos de usuario mediante interfaces de escucha, mediando entre el modelo de balances y los componentes de la vista.

### 4.2 Análisis Comparativo de Tecnologías de Interfaz (Criterio RA1.a)

| Tecnología Evaluada | Naturaleza de Componentes | Ventajas Destacadas | Inconvenientes Identificados | Selección en el Proyecto |
| :--- | :--- | :--- | :--- | :--- |
| Java AWT | Pesados, renderizados por el SO | Rendimiento nativo en sistemas legados | Apariencia anticuada, inconsistencia visual entre plataformas | Descartado |
| Java Swing | Ligeros, dibujados por la JVM | Totalmente personalizable, soporte nativo de la especificación JavaBeans y compatibilidad con editores visuales | Mayor carga de memoria si no se gestiona correctamente el repintado | Seleccionado como tecnología de escritorio para la fase de código |
| JavaFX | Avanzados basados en Scene Graph | Soporte nativo para CSS, aceleración gráfica por GPU y separación declarativa con FXML | Desacoplado del JDK a partir de Java 11; requiere módulos externos | Evaluado para iteraciones posteriores |
| Flutter / Dart | Motor de renderizado propio (Impeller/Skia) | Código base único para móvil, web y escritorio, alto rendimiento nativo | Requiere introducir un lenguaje ajeno a Java (Dart) | Seleccionado en la hoja de ruta móvil del Proyecto Integrador |

### 4.3 Especificación del Componente Reutilizable (Criterios RA1.d, RA1.g)
Para la representación gráfica de saldos individuales se ha creado el componente maestro reutilizable TarjetaSaldoParticipante en Figma, modelando sus especificaciones técnicas de cara a su futura conversión a JavaBean en Java Swing:

* Requisitos del Componente:
  * Diseñado como componente maestro con propiedades editables de texto: Nombre del participante e Importe de saldo.
  * Variantes de estado visual creadas mediante componentes conmutables:
    * Estado Acreedor: Fondo o acento verde suave, texto destacado en verde (#2E7D32) para saldos positivos a favor.
    * Estado Deudor: Fondo o acento rojo suave, texto destacado en rojo (#C62828) para saldos negativos pendientes.
    * Estado Neutral: Tipografía en gris medio (#757575) para balances en 0,00 €.
* Campo de Aplicación: Componente modular diseñado para insertarse de manera dinámica en listas verticales dentro del panel lateral de la ventana principal, permitiendo escalar el número de integrantes sin desajustar el diseño base.

### 4.4 Simulación de Eventos y Transiciones en el Prototipo (Criterios RA1.e, RA1.f, RA1.g)
El prototipo de Figma satisface los criterios de asociación de eventos y respuesta a acciones mediante la configuración de su motor de interacción:

1. Asociación de Acciones a Disparadores: Se han vinculado eventos On Click en los botones de acción principales.
2. Diálogo Modal Desacoplado: El botón de la calculadora de división rápida dispara la apertura de la ventana secundaria utilizando la propiedad Open Overlay centrada con fondo oscurecido (Backdrop), garantizando el comportamiento modal requerido.
3. Transición de Estado y Carga de Datos: La acción de confirmar gasto conduce a la pantalla donde las tarjetas de balance cambian automáticamente de estado neutro a variantes acreedoras y deudoras.
4. Simulación de Liquidación: Un botón de acción principal conduce a la vista de conciliación, desplegando el número mínimo de pagos directos resultantes del caso de uso.

### 4.5 Catálogo Conceptual de Clases y Métodos

```text
com.payclear
|-- modelo
|   |-- Participante
|   |   |-- Atributos: identificador (String), nombre (String), saldo (double)
|   |   `-- Métodos: getIdentificador(), getNombre(), getSaldo(), modificarSaldo(double)
|   `-- Gasto
|       |-- Atributos: identificador (String), concepto (String), importeTotal (double), pagador (Participante), participantes (List<Participante>)
|       `-- Métodos: getImporteTotal(), getPagador(), obtenerCuotaPorPersona()
|-- componente
|   `-- TarjetaSaldoParticipante (Componente visual reutilizable)
|       |-- Propiedades: nombreParticipante, saldoActual, estadoCromatico
|       `-- Variantes de visualización: Acreedor (verde), Deudor (rojo), Neutral (gris)
|-- vista
|   |-- VistaPrincipal (Frame principal)
|   |   `-- Elementos: panelTarjetas, tablaGastos, barraAcciones
|   `-- DialogoDivisionRapida (Modal Overlay)
|       `-- Elementos: campoImporte, selectorPersonas, cuotaCalculada
`-- controlador
    `-- ControladorPrincipal (Gestión de eventos)
        `-- Acciones: registrarGasto, registrarParticipante, calcularDivision, liquidarBalances
```

---

## 5. Validación Funcional del Algoritmo y Prototipo

Para validar el flujo interactivo de la interfaz y la precisión contable del modelo de datos, se define un caso de uso real con cuatro integrantes (Guillermo, Jesús, José Luis y Pablo). 

En este escenario, los gastos no se dividen a partes iguales de forma ciega: una persona adelanta el importe total de la factura, pero el sistema asigna a cada participante su cuota individual en función de su consumo real.

---

### 5.1 Registro de Movimientos con Consumo Individualizado

| Concepto Registrado | Importe Total | Pagado por | Desglose de Consumo Individual por Integrante |
| :--- | :---: | :--- | :--- |
| **Cena en restaurante** | 50,00 € | Guillermo | José Luis: 20,00 € (plato especial)<br>Guillermo: 12,00 € (consumo propio)<br>Pablo: 10,00 € (menú estándar)<br>Jesús: 8,00 € (plato básico) |
| **Compra compartida de piso** | 40,00 € | José Luis | Jesús: 15,00 € (artículos personales)<br>José Luis: 15,00 € (consumo propio)<br>Guillermo: 10,00 € (productos comunes)<br>Pablo: 0,00 € (no participa) |
| **Transporte / Taxi puntual** | 20,00 € | Jesús | Pablo: 15,00 € (traslado personal)<br>Jesús: 5,00 € (trayecto propio)<br>Guillermo: 0,00 € (no participa)<br>José Luis: 0,00 € (no participa) |

---

### 5.2 Determinación de Balances Netos

El balance se calcula restando el gasto real imputado al total adelantado por cada persona (`Balance = Total Pagado - Total Consumido`):

| Integrante | Total Adelantado | Total Imputado (Consumo) | Balance Final | Estado Visual de la Tarjeta en Figma |
| :--- | :---: | :---: | :---: | :--- |
| **Guillermo** | 50,00 € | 22,00 € (12 + 10) | **+28,00 €** | 🟢 [Acreedor] |
| **José Luis** | 40,00 € | 35,00 € (20 + 15) | **+5,00 €** | 🟢 [Acreedor] |
| **Jesús** | 20,00 € | 28,00 € (8 + 15 + 5) | **-8,00 €** | 🔴 [Deudor] |
| **Pablo** | 0,00 € | 25,00 € (10 + 15) | **-25,00 €** | 🔴 [Deudor] |
| **Total Grupo** | **110,00 €** | **110,00 €** | **0,00 €** | Equilibrio contable verificado |

---

### 5.3 Compensación Multilateral Simplificada (Settle Up)

Si los integrantes pagaran sus deudas de forma manual y cruzada por cada ticket, se requerirían múltiples transferencias redundantes. 

El algoritmo voraz toma los saldos consolidados y calcula la ruta óptima de liquidación en solo 3 pagos directos:

```text
[Deudor] Pablo  ──────── 25,00 € ────────> [Acreedor] Guillermo
[Deudor] Jesús  ────────  3,00 € ────────> [Acreedor] Guillermo
[Deudor] Jesús  ────────  5,00 € ────────> [Acreedor] José Luis
```

* Pablo salda su deuda total (-25,00 €) transfiriendo 25,00 € a Guillermo.
* Jesús salda su deuda total (-8,00 €) pagando 3,00 € a Guillermo (completando los +28,00 € que le correspondían cobrar) y 5,00 € a José Luis (completando los +5,00 € que le correspondían cobrar).

**Resultado:** Con únicamente 3 transferencias bancarias, todas las posiciones deudoras y acreedoras quedan extinguidas a 0,00 € con exactitud matemática, respetando el consumo real de cada miembro.
