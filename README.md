# PayClear
> **Gestor ágil de gastos compartidos y liquidación de deudas en local**

[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](#)
[![Java](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](#)
[![Swing](https://img.shields.io/badge/GUI-Swing%20%2F%20Matisse-blue?style=for-the-badge)](#)
[![Arquitectura](https://img.shields.io/badge/Architecture-MVC-green?style=for-the-badge)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
---

##  ¿Qué es PayClear?

**PayClear** es una aplicación de escritorio y móvil desarrollada en Java/Flutter que simplifica la división de gastos, el calcular rapidamente las cuentas y el seguimiento de deudas cotidianas entre amigos, compañeros de piso, de trabajo o de lo que necesites.

>  **El problema que resolvemos:**  
> Nace como una alternativa directa y transparente a herramientas como *Splitwise* o *Tricount*, queremos eliminar las barreras de micropagos, las suscripciones recurrentes, la publicidad invasiva y los bloqueos por límites de uso diario.

##  Funcionalidades Clave

### 1. Menú de Deudas Rápidas
* **Control inmediato:** Visualiza en un solo vistazo quién te debe dinero y a quién debes tú.
* **Componente personalizado:** Tarjetas visuales dinámicas con código de colores según el balance:
  * 🟢 **Verde:** Saldo a favor (acreedor).
  * 🔴 **Rojo:** Deuda pendiente (deudor).

### 2.  Calculadora Ágil de Restaurante y Eventos
* **División al instante:** Desglose rápido de tickets en cenas, viajes compartidos o taxis.
* **Reparto automático:** Calcula la cuota equitativa por comensal en segundos.
* **Integración en 1 clic:** Botón directo para volcar el resultado del ticket como deuda pendiente en el menú principal.

### 3.  Balance y Liquidación Simplificada (*Settle Up*)
* **Minimización de pagos:** Algoritmo optimizado para saldar todas las deudas del grupo con el menor número posible de transferencias bancarias.


---

| Criterio / Característica | Splitwise | Tricount | Nuestra App (PayClear) |
| --- | --- | --- | --- |
| Plataforma principal | Móvil / Web | Móvil / Web | Movil / Web |
| Conexión requerida | Obligatoria (Nube) | Obligatoria para sincronizar | Funciona 100% offline (local) |
| Registro de usuario | Cuenta / Email obligatorio | Enlace de grupo / Opcional | Registro (opcional) |
| Modelo de negocio | Freemium (límites diarios en versión gratis) | Con publicidad en la app | Gratuita y sin anuncios |
| Minimización de pagos | Sí (algoritmo interno) | Sí | Sí (algoritmo propio en Java) |
| Dificultad de uso | Media (muchos menús y opciones) | Baja | Mínima (interfaz directa en una sola ventana) |

El resto de aplicaciones introducen demasiados micropagos y dificultades a la hora de dividir los gastos, nuestra aplicación ofrece una interfaz mucho mas sencilla rápida y sin coste alguno con usos ilimitados

Los datos introducidos se guardan localmente en tu dispositivo particular y no se va a ninguna base de datos de la empresa para garantizar máxima privacidad.
