---
title: "Don't repeat yourself"
date: 2024-01-08T20:44:30+02:00
draft: false
---

# Cómo mejoré la comunicación entre componentes con Event Bus

💡 **Contexto**:  
En mi trabajo reciente como desarrollador backend, me enfrenté al desafío de optimizar la comunicación entre componentes de un sistema complejo. La solución fue implementar un **Event Bus** para permitir una interacción desacoplada, escalable y fácil de mantener.

---

## 🛠️ ¿Qué es un Event Bus?  
Un Event Bus es un patrón de diseño que actúa como un mediador centralizado para eventos dentro de una aplicación.  
- **Publicadores**: Componentes que emiten eventos.  
- **Suscriptores**: Componentes que reaccionan a esos eventos.  
- **Eventos**: Estructuras que encapsulan información clave sobre una acción o cambio en el sistema.

---

## 🚀 Mi enfoque para implementarlo  
Para diseñar el Event Bus, me basé en principios como:  
- **Desacoplamiento**: Evitar que los publicadores y suscriptores dependan directamente entre sí.  
- **Extensibilidad**: Permitir la fácil adición de nuevos eventos y suscriptores.  
- **Trazabilidad**: Registrar los eventos emitidos para depuración y análisis.

El Event Bus tiene dos responsabilidades principales:  
1. **Registrar eventos**: Mantener un historial temporal de eventos.  
2. **Emitir eventos**: Procesar los eventos registrados, enviándolos a los suscriptores relevantes.

---

## 📢 Eventos y señales  
Cada evento encapsula información específica (por ejemplo, la creación de un contacto o la actualización de un inventario). Los eventos están asociados a señales, que son las encargadas de notificar a los suscriptores.

---

## 🔗 Suscriptores y manejadores  
Los suscriptores se conectan a señales específicas para ejecutar lógica personalizada. Por ejemplo:  
- Cuando se genera un evento de **creación de contacto**, el suscriptor puede encargarse de realizar acciones como almacenar la nueva información en bases de datos, notificar a otros sistemas o ejecutar cualquier otra acción relevante.  
- Cuando se genera un evento de **actualización de inventario**, el suscriptor puede actualizar los módulos interesados, como los sistemas de ventas o de logística, para asegurarse de que la información esté sincronizada en todas partes.

Cada suscriptor delega la ejecución de la lógica en un manejador especializado, lo que garantiza una estructura organizada y de fácil mantenimiento.

---

## 🌟 Impacto de la solución  
Con esta implementación:  
- Se redujo el acoplamiento entre componentes, facilitando la extensión del sistema.  
- Mejoró la escalabilidad al permitir procesar eventos de forma asíncrona.  
- El sistema se volvió más robusto al centralizar y controlar la gestión de eventos.
