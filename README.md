# KomprasTaller
# 🔧 Solicitud de Compra — Taller
 
> Formulario móvil para la gestión de solicitudes de material, integrado con Power Automate y Microsoft Lists.
 
---
 
## ¿Qué es esto?
 
Una aplicación web progresiva (**PWA-ready**) diseñada para funcionar directamente desde la pantalla de inicio del iPhone, sin instalación, sin tienda de apps, sin complicaciones.
 
Permite a cualquier operario del taller generar una solicitud de compra estructurada en segundos, enviarla por correo y dejar que **Power Automate** haga el resto: parsear los datos y almacenarlos automáticamente en **Microsoft Lists**.
 
---
 
## ✨ Características
 
- 📱 **Optimizado para iPhone** — interfaz táctil, tipografía legible, sin zoom accidental
- 👤 **Solicitante persistente** — el nombre se guarda en el dispositivo; cada operario solo lo escribe una vez
- 🗂️ **Áreas configuradas** — Taller, Oficina, Fábrica Inducción, Fábrica de Hornos, Generales, Almacén, Mantenimiento, Prevención, Matricería, Otros
- 🚨 **Niveles de urgencia** — Normal, Media, Urgente con indicador visual de color
- 📦 **Artículos ilimitados** — descripción, cantidad, unidad de medida y referencia por línea
- 🔢 **Número de tarea manual** — introducido por el operario según el sistema externo
- 👁️ **Vista previa del correo** antes de enviarlo
- 📧 **JSON embebido en el correo** — listo para ser parseado por Power Automate sin configuración adicional
- 🌐 **Sin dependencias de servidor** — un solo archivo `.html`, funciona offline
 
---
 
## 🚀 Instalación en iPhone
 
1. Abre la URL del proyecto en **Safari**
2. Pulsa el botón compartir **( □↑ )**
3. Selecciona **"Añadir a pantalla de inicio"**
4. Asigna el nombre deseado y pulsa **Añadir**
 
> ⚠️ Debe usarse Safari. Otros navegadores no soportan "Añadir a pantalla de inicio" en iOS.
 
---
 
## ⚙️ Integración con Power Automate
 
El correo generado incluye al final una línea con todos los datos en formato JSON:
 
```
DATOS_JSON::{"solicitante":"...","fecha":"...","numPedido":"...","area":"...","urgencia":"...","items":[...],"observaciones":"..."}
```
 
 
### Campos mapeados a Lists
 
| Campo JSON | Columna en Lists |
|---|---|
| `numPedido` | Número de tarea |
| `solicitante` | Solicitante |
| `fecha` | Fecha solicitud |
| `area` | Área |
| `urgencia` | Urgencia |
| `items` | Artículos (JSON o tabla) |
| `observaciones` | Observaciones |
 
---
 
## 📁 Estructura del proyecto
 
```
/
├── index.html       ← Formulario completo (todo en un archivo)
└── README.md        ← Este archivo
```
 
---
 
## 🛠️ Personalización
 
Abre `index.html` con cualquier editor de texto y localiza:
 
```javascript
const to = 'compras@tuempresa.com';
```
 
Sustitúyelo por la dirección de correo que dispara tu flujo de Power Automate.
 
Para añadir o modificar áreas, busca el `<select id="area">` en el HTML.
 
---
 
## 📋 Requisitos
 
- iPhone con Safari
- Cuenta de correo configurada en el dispositivo
- Flujo de Power Automate activo (opcional para uso básico)
 
---
 
## 📄 Licencia
 
Uso interno. Todos los derechos reservados.
 
