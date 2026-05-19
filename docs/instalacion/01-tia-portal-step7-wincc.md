# 📘 Instalación de TIA Portal STEP 7 + Safety + WinCC V21

[⬅️ Volver al README principal](../../README.md)

---

## 📥 Descarga del instalador

**Archivo:** `TIA_Portal_STEP7_Safety_WinCC_V21.iso`
**Tamaño aproximado:** 8.1 GB

🔗 **[Descargar desde Google Drive](https://drive.google.com/file/d/1ui9wxSbE2sdGeSuwzYg-1B1X0qAk6vgO/view?usp=drive_link)**

---

## 📦 ¿Qué contiene este ISO?

Este paquete unificado de Siemens incluye **todos los componentes principales de ingeniería** para programación y configuración en el ecosistema TIA Portal V21:

### Componentes principales

| Componente | Función |
|---|---|
| **TIA Portal V21** | Entorno de desarrollo integrado |
| **STEP 7 Professional V21** | Programación de S7-1200, S7-1500 y ET 200SP |
| **STEP 7 Safety Advanced V21** | Programación de lógica de seguridad funcional (F-CPUs, SIL 3 / PLe) |
| **WinCC Basic V21** | Configuración de Basic Panels (ej. KTP400, KTP700) |
| **WinCC Comfort V21** | Configuración de Comfort Panels (ej. TP2200) |
| **WinCC Advanced V21** | SCADA clásico para PC (WinCC Runtime Advanced) |
| **WinCC Professional V21** | SCADA Professional para arquitecturas robustas |
| **WinCC Unified V21** | Configuración del SCADA Unified moderno (HTML5/Web) |
| **SIMATIC ProSave V21** | Herramienta de servicio para HMIs |
| **TIA Portal Openness** | API para automatización del propio TIA Portal |
| **Automation License Manager** | Gestión de licencias Siemens |

---

## 🖥️ Requisitos mínimos del sistema

| Componente | Requisito mínimo | Recomendado |
|---|---|---|
| Sistema operativo | Windows 10/11 Pro 64-bit | Windows 11 Pro 64-bit |
| Procesador | Intel Core i5 (3.0 GHz) | Intel Core i7/i9 o AMD Ryzen 7/9 |
| RAM | 16 GB | 32 GB |
| Disco duro | 50 GB libres en SSD | 100 GB libres en NVMe |
| Resolución | 1920 × 1080 | 2560 × 1440 |
| Tarjeta de red | Ethernet Gigabit | Ethernet Gigabit + Wi-Fi |

---

## 🚀 Pasos de instalación

### Paso 1 — Preparación del sistema

1. **Desactiva temporalmente el antivirus** (Windows Defender u otros)
2. **Cierra todos los programas en ejecución**
3. **Conecta el equipo a corriente** (no instalar con batería)
4. Verifica que tengas **permisos de administrador** en Windows

### Paso 2 — Montar el ISO

1. **Doble click** sobre `TIA_Portal_STEP7_Safety_WinCC_V21.iso`
2. Windows lo montará como una unidad virtual (ej. `D:\` o `E:\`)
3. Si no se monta automáticamente, click derecho → **Montar**

### Paso 3 — Ejecutar el instalador

1. Abre la unidad montada
2. **Click derecho** sobre `Start.exe` → **Ejecutar como administrador**
3. Acepta el aviso UAC de Windows

### Paso 4 — Configuración del idioma

Selecciona idioma de instalación:
- ☑ **Español** (recomendado para SENA)
- O English (si prefieres terminología original Siemens)

### Paso 5 — Selección de productos

⚠️ **Esta es la pantalla más importante.** Si pasas rápido, dejarás componentes sin instalar.

**Marcar OBLIGATORIAMENTE:**

| Componente | Estado |
|---|---|
| SIMATIC STEP 7 Professional + STEP 7 Safety | ✅ |
| SIMATIC WinCC Basic / Comfort / Advanced (todo el grupo) | ✅ |
| - WinCC Basic/Comfort/Advanced Devices | ✅ |
| - WinCC Panel Images | ✅ |
| - Simulation (SIMATIC Panels, WinCC Runtime Advanced) | ✅ |
| SIMATIC WinCC Unified | ✅ |
| - WinCC Unified Devices | ✅ |
| SIMATIC WinCC Professional | ✅ |
| - WinCC Professional Devices | ✅ |

**Tools:**

| Herramienta | Estado | Razón |
|---|---|---|
| SIMATIC ProSave | ✅ | Servicio de HMIs |
| TIA Portal Openness | ✅ | API útil a futuro |
| TIA Portal Help Viewer | ✅ | Documentación offline |
| OPC XML Gateway | ⬜ | No necesario |
| WinCC Audit Viewer | ⬜ | No necesario |
| TIA Portal Teamcenter Gateway | ⬜ | Solo si usas Teamcenter PLM |

**TIA Administrator:**

| Componente | Estado |
|---|---|
| Automation License Manager | ✅ (obligatorio) |

### Paso 6 — Configuración de seguridad

Aparecerá una ventana sobre **"User access control"**. Acepta los valores por defecto. Esto configura los firewalls necesarios.

### Paso 7 — Iniciar instalación

1. Click en **Install** o **Instalar**
2. La instalación toma entre **45 minutos y 2 horas** dependiendo del equipo
3. **NO interrumpas** el proceso ni cierres la ventana

### Paso 8 — Reinicio del sistema

Al terminar, el instalador solicitará **reiniciar el PC**.

⚠️ **Reinicia obligatoriamente.** Sin reiniciar, los servicios no se registran correctamente.

---

## ✅ Verificación de instalación

Después del reinicio:

1. **Win + S** → busca: `TIA Portal V21`
2. Debe aparecer el ícono de TIA Portal V21
3. Ejecútalo como administrador
4. Si abre correctamente la pantalla de bienvenida, la instalación fue exitosa

### Verificación de componentes instalados

Dentro de TIA Portal:

1. Crea un proyecto de prueba
2. Click en **"Add new device"**
3. Verifica que aparezcan estas categorías:

```
📁 Controllers (SIMATIC S7-1200, S7-1500, etc.)
📁 HMI
   ├─ SIMATIC Basic Panel
   ├─ SIMATIC Comfort Panel
   ├─ SIMATIC Unified Basic Panel  ← Confirma Unified instalado
   └─ SIMATIC Unified Comfort Panel ← Confirma Unified instalado
📁 PC systems
   └─ SIMATIC PC station
      └─ HMI Application
         ├─ WinCC RT Advanced
         ├─ WinCC RT Professional
         └─ WinCC Unified PC  ← Confirma Unified instalado
```

Si las categorías Unified aparecen, la instalación quedó completa.

---

## 🔑 Activación de licencias

Tras la instalación, los productos quedan en **modo Trial (21 días)**. Para uso continuo:

- **Opción educativa SENA:** Solicitar licencias SCE (Siemens Cooperates with Education) en https://www.siemens.com/sce
- **Opción para formación temporal:** Ver guía de [Gestión de licencias con Sim_EKB_Install](./04-sim-ekb-install.md)

---

## ❗ Problemas comunes

### El instalador no inicia
- Verifica que estés ejecutando como administrador
- Desactiva temporalmente el antivirus
- Revisa que el ISO no esté corrupto (compara hash SHA-256)

### Error de "archivo en uso"
- Reinicia el PC y vuelve a intentar
- Cierra completamente cualquier proceso de Siemens en el Administrador de tareas

### Instalación se queda colgada
- Espera hasta 30 minutos sin tocar nada
- Si pasa de 30 minutos, cancela y reinicia con el ISO montado nuevamente

---

## 📚 Siguiente paso

➡️ [Instalar WinCC Unified PC Runtime V21](./02-wincc-unified-runtime.md)

---

[⬅️ Volver al README principal](../../README.md)
