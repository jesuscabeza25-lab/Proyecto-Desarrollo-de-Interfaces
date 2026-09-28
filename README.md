# PayClear
> **Gestor ágil de gastos compartidos y liquidación de deudas en local**

[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](#)
[![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](#)
[![Swing](https://img.shields.io/badge/GUI-Swing%20%2F%20Matisse-blue?style=for-the-badge)](#)
[![Arquitectura](https://img.shields.io/badge/Arquitectura-MVC-green?style=for-the-badge)](#)
[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 1. ¿Qué es PayClear?

**PayClear** es una aplicación de escritorio y móvil desarrollada en Java/Flutter que simplifica la división de gastos, el calcular rapidamente las cuentas y el seguimiento de deudas cotidianas entre amigos, compañeros de piso, de trabajo o de lo que necesites.

>  **El problema que resolvemos:**  
> Nace como una alternativa directa y transparente a herramientas como *Splitwise* o *Tricount*, queremos eliminar las barreras de micropagos, las suscripciones recurrentes, la publicidad invasiva y los bloqueos por límites de uso diario.

* **Sin cuentas obligatorias:** No requiere registro de correos ni contraseñas.
* **100% Offline y Privada:** Los datos residen exclusivamente en local, garantizando privacidad total y funcionamiento sin conexión.
* **Flujo directo en dos clics:** `Registrar cuenta/ticket` ➔ `Calcular cuotas` ➔ `Minimizar transferencias pendientes`

---

## 2. Objetivos Principales

* Desarrollar una interfaz gráfica moderna, intuitiva y fluida utilizando **Java Swing** y el IDE **NetBeans**.
* Implementar una arquitectura **Modelo-Vista-Controlador (MVC)** que desacople completamente la lógica de balances de la capa de presentación.
* Diseñar **componentes visuales personalizados reutilizables (Custom JavaBeans)** con propiedades y eventos propios para representar las tarjetas de balance de los participantes.
* Disponer de una **Calculadora Rápida de Restaurante** para desglosar tickets en comidas o eventos y volcar el saldo deudor al panel principal en un solo clic.
* Aplicar un algoritmo simple (*greedy algorithm*) que simplifique y minimice el número total de pagos necesarios para saldar las cuentas del grupo.
* Trabajar bajo metodología **Scrum**, gestionando el avance técnico mediante Git, ramas temáticas y *Pull Requests*.

---

## 3.  Funcionalidades Clave

### 3.1 Menú de Deudas Rápidas
* **Control inmediato:** Visualiza en un solo vistazo quién te debe dinero y a quién debes tú.
* **Componente personalizado:** Tarjetas visuales dinámicas con código de colores según el balance:
  * 🟢 **Verde:** Saldo a favor (acreedor).
  * 🔴 **Rojo:** Deuda pendiente (deudor).

### 3.2  Calculadora Ágil de Restaurante y Eventos
* **División al instante:** Desglose rápido de tickets en cenas, viajes compartidos o taxis.
* **Reparto automático:** Calcula la cuota equitativa por comensal en segundos.
* **Integración en 1 clic:** Botón directo para volcar el resultado del ticket como deuda pendiente en el menú principal.

### 3.3  Balance y Liquidación Simplificada (*Settle Up*)
* **Minimización de pagos:** Algoritmo optimizado para saldar todas las deudas del grupo con el menor número posible de transferencias bancarias.


---

## 4. Benchmarking 

| Criterio / Característica | Splitwise | Tricount | Nuestra App (PayClear) |
| --- | --- | --- | --- |
| Plataforma principal | Móvil / Web | Móvil / Web | Movil / Web |
| Conexión requerida | Obligatoria (Nube) | Obligatoria para sincronizar | Funciona 100% offline (local) |
| Registro de usuario | Cuenta / Email obligatorio | Enlace de grupo / Opcional | Sin registro previo requerido |
| Modelo de negocio | Freemium (límites diarios en versión gratis) | Con publicidad en la app | Gratuita y sin anuncios |
| Minimización de pagos | Sí (algoritmo interno) | Sí | Sí (algoritmo propio en Java) |
| Dificultad de uso | Media (muchos menús y opciones) | Baja | Mínima (interfaz directa en una sola ventana) |


El resto de aplicaciones introducen demasiados micropagos y dificultades a la hora de dividir los gastos, nuestra aplicación ofrece una interfaz mucho mas sencilla rápida y sin coste alguno con usos ilimitados

Los datos introducidos se guardan localmente en tu dispositivo particular y no se va a ninguna base de datos de la empresa para garantizar máxima privacidad.

---

## 5. Ejemplo de Funcionamiento

Supongamos una salida de fin de semana con cuatro integrantes: **Guillermo**, **José Luis**, **Jesús** y **Pablo**. Durante la quedada se realizan los siguientes movimientos:

| Concepto | Importe | Pagado por | Participantes | Reparto |
| :--- | :--- | :--- | :--- | :--- |
| **Cena de Pizzas** | 40,00 € | Guillermo | Todos (4) | 10,00 € / persona |
| **Combustible coche** | 30,00 € | Jesús | Todos (4) | 7,50 € / persona |
| **Entradas de cine** | 18,00 € | José Luis | José Luis, Pablo | 9,00 € / persona |

### 5.1 Cálculo de Balances Individuales

| Persona | Pagó | Debe | Balance | Estado |
| :--- | :--- | :--- | :--- | :--- |
| **Guillermo** | 40,00 € | 17,50 € | **+22,50 €** | 🟢 Acreedor |
| **Jesús** | 30,00 € | 17,50 € | **+12,50 €** | 🟢 Acreedor |
| **José Luis** | 18,00 € | 26,50 € | **-8,50 €** | 🔴 Deudor |
| **Pablo** | 0,00 € | 26,50 € | **-26,50 €** | 🔴 Deudor |
| **Total** | **88,00 €** | **88,00 €** | **0,00 €** | — |

### 5.2 Resumen de Cuentas y Liquidación (*Settle Up*)

En lugar de realizar pagos cruzados múltiples, el sistema optimiza las transferencias a **3 transacciones directas**:

| Origen (Deudor) | Destino (Acreedor) | Importe | Método / Concepto |
| :--- | :--- | :--- | :--- |
| 🔴 **Pablo** | 🟢 **Guillermo** | 22,50 € | Transferencia directa |
| 🔴 **Pablo** | 🟢 **Jesús** | 4,00 € | Transferencia directa |
| 🔴 **José Luis** | 🟢 **Jesús** | 8,50 € | Transferencia directa |

> **Resultado:** Con solo 3 transferencias, todas las cuentas quedan saldadas a **0,00 €** sin transacciones intermedias innecesarias.
>
>


## 6. Estudio de Mercado y Validación con Usuarios

Para contrastar las hipótesis iniciales del proyecto y validar la necesidad real frente a las soluciones comerciales actuales, se desplegó un estudio de campo mediante un formulario estructurado de investigación. La muestra recoge hábitos de gasto compartido, herramientas empleadas, fricciones con los modelos de monetización vigentes y funcionalidades prioritarias.

---

### 6.1 Resultados Cuantitativos

#### 1. Frecuencia de gastos compartidos
> *¿Con qué frecuencia sueles compartir gastos en grupo (cenas, viajes, piso compartido, regalos comunes)?*

<p align="center">
  <img width="618" height="248" alt="Frecuencia de gastos compartidos" src="https://github.com/user-attachments/assets/84612323-377e-4459-8202-df6d45051bb5" />
</p>

* **Hallazgo:** El **85,7%** de los participantes comparte gastos de manera recurrente o en eventos puntuales, lo que ratifica la vigencia y regularidad del problema planteado.

---

#### 2. Herramientas utilizadas actualmente
> *¿Qué herramientas utilizas actualmente para gestionar esos gastos?*

<p align="center">
  <img width="750" height="251" alt="Herramientas utilizadas" src="https://github.com/user-attachments/assets/31727c0b-25f0-42eb-bb53-36e5f8ffac6b" />
</p>

* **Hallazgo:** El **85,7%** depende de métodos informales propensos al error (Bizum directo o memoria). Solo un 28,6% recurre a soluciones especializadas como Tricount y un 0% utiliza activamente Splitwise dentro de la muestra, evidenciando una barrera de adopción en el software existente.

---

#### 3. Nivel de fricción con las limitaciones comerciales
> *Del 1 al 5, ¿cuánto te molestan las limitaciones actuales de apps como Splitwise (límite de gastos al día, suscripciones de pago y anuncios)?*

<p align="center">
  <img width="631" height="228" alt="Molestia por limitaciones comerciales" src="https://github.com/user-attachments/assets/c70335b3-0037-419c-98ce-45834105b4e5" />
</p>

* **Hallazgo:** El **71,4%** de los encuestados sitúa su descontento en los niveles más altos (puntuaciones de 4 y 5) frente a los muros de pago, la publicidad invasiva y los límites diarios de registro.

---

#### 4. Factores clave para la adopción de una nueva alternativa
> *¿Qué motivos harían que probaras una nueva app de división de gastos?*

<p align="center">
  <img width="753" height="258" alt="Motivos de adopción" src="https://github.com/user-attachments/assets/41974071-6995-4dd0-95dc-3417f9a7f722" />
</p>

* **Hallazgo:** La gratuidad sin restricciones de uso diario (**85,7%**) y el acceso directo sin necesidad de registro ni cuentas obligatorias (**42,9%**) representan los dos catalizadores esenciales de conversión.

---

#### 5. Preferencia de plataforma
> *¿Qué plataforma te resultaría más útil para este tipo de aplicación?*

<p align="center">
  <img width="633" height="237" alt="Preferencia de plataforma" src="https://github.com/user-attachments/assets/c15ee398-f7e8-41f6-a910-01330bf6b985" />
</p>

* **Hallazgo:** El **57,1%** demanda una solución móvil con soporte para entornos de escritorio, respaldando la hoja de ruta técnica planteada: desarrollo del núcleo y prototipo de escritorio en Java Swing, con posterior cliente móvil en Flutter.

---

### 6.2 Demandas Cualitativas del Usuario

El análisis de texto abierto permitió categorizar las carencias funcionales más repetidas por los participantes:

| Categoría | Peticiones registradas | Impacto en PayClear |
| :--- | :--- | :--- |
| **Monetización y Fricción** | "No quiero anuncios ni micropagos abusivos." | Arquitectura 100% gratuita, sin capas de suscripción ni muros de pago. |
| **Privacidad y Control** | "Rapidez y más seguridad sin control estatal de mis gastos menores." | Modelo *Local-First*: los datos no viajan a servidores remotos ni requieren identificación personal. |
| **Flexibilidad Contable** | "Poder pagar a plazos tipo si debes 10€ poder pagar 5 y otro día otros 5."<br>"La división de gastos por persona." | Inclusión de liquidaciones parciales y desglose asimétrico de gastos en el modelo de datos. |
| **Operativa Diaria** | "Recordatorios constantes y programables." | Considerado para el módulo de notificaciones y exportación del Sprint 2. |

---

### 6.3 Conclusiones e Implicaciones de Diseño

El estudio confirma que el usuario medio no rechaza el concepto de repartir cuentas digitalmente, sino el modelo de negocio extractivo de los competidores actuales (límites artificiales y cobros recurrentes), lo que fuerza una regresión hacia métodos manuales e ineficientes como notas de móvil o transferencias desordenadas por Bizum.

Estos hallazgos consolidan las directrices de PayClear:
1. **Acceso Inmediato:** Cero pantallas de inicio de sesión o petición de datos personales.
2. **Soberanía del Dato:** Persistencia local estricta sin dependencia de servicios en la nube.
3. **Optimización Real de Pagos:** Implementación del algoritmo voraz para liquidar saldos cruzados con el menor número de operaciones bancarias posible.
