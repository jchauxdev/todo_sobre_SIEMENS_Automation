# 📘 Instalación de WinCC Unified PC Runtime V21

[⬅️ Volver al README principal](../../README.md)

---

## 📥 Descarga del instalador

**Archivo:** `SIMATIC_WinCC_Unified_RT_V21.iso`
**Tamaño aproximado:** 3 GB

🔗 **[Descargar desde Google Drive](https://drive.google.com/file/d/1CFY3YmVxdzMAvJWRaqMQC-naOvL0CW6L/view?usp=drive_link)**

---

## 📦 ¿Qué es WinCC Unified PC Runtime?

WinCC Unified PC Runtime es el **motor de ejecución del SCADA Unified** sobre PC con Windows. Es la plataforma SCADA moderna de Siemens, basada en tecnologías web (HTML5, SVG, JavaScript), que permite acceder a la visualización industrial desde cualquier navegador.

### Diferencias con WinCC Runtime Advanced

| Característica | Runtime Advanced (clásico) | Runtime Unified (moderno) |
|---|---|---|
| Tecnología base | Windows Forms | HTML5 / SVG / JavaScript |
| Acceso remoto | WebUX (limitado) | Cliente web nativo |
| Visualización | Aplicación de escritorio | Navegador web |
| Scripting | VBScript | JavaScript |
| Máximo PowerTags | 4.096 | Hasta 600.000 |
| Recomendado para | Mantenimiento de proyectos existentes | Proyectos nuevos |

---

## 🎯 ¿Cuándo instalar este Runtime?

Instala WinCC Unified PC Runtime cuando necesites:

✅ Ejecutar un proyecto SCADA Unified en un PC industrial
✅ Acceso al SCADA desde múltiples navegadores (laptops, tablets, celulares)
✅ Arquitecturas cliente-servidor en red local o industrial
✅ Probar localmente el deployment del SCADA durante desarrollo

❌ **NO lo necesitas si** solo vas a:
- Programar pantallas físicas (TP2200, KTP)
- Simular el desarrollo con el simulador integrado de Engineering

---

## ⚙️ Prerequisitos

Antes de instalar WinCC Unified Runtime:

1. ✅ Tener **TIA Portal V21** instalado con WinCC Unified Engineering
2. ✅ Sistema operativo **Windows 10/11 Pro 64-bit**
3. ✅ Mínimo **16 GB RAM** (recomendado 32 GB)
4. ✅ **30 GB de espacio libre** en disco
5. ✅ Permisos de **administrador** en Windows
6. ✅ Tarjeta de red Ethernet o Wi-Fi operativa

---

## 🚀 Pasos de instalación

### Paso 1 — Preparación

1. **Cierra TIA Portal V21** y cualquier programa Siemens en ejecución
2. **Desactiva temporalmente el antivirus**
3. Verifica conexión a internet (algunos componentes pueden requerir verificación)

### Paso 2 — Montar el ISO

1. **Doble click** sobre `SIMATIC_WinCC_Unified_RT_V21.iso`
2. Windows lo monta como unidad virtual

### Paso 3 — Ejecutar instalador

1. Abre la unidad montada
2. **Click derecho** sobre `Start.exe` → **Ejecutar como administrador**
3. Acepta el aviso UAC

### Paso 4 — Selección de componentes

En la pantalla de selección, marca:

| Componente | Estado | Función |
|---|---|---|
| **SIMATIC WinCC Unified PC RT** | ✅ | El runtime principal |
| **SIMATIC Runtime Manager** | ✅ | Herramienta para iniciar/detener proyectos Unified |
| **Unified Station Configurator** | ✅ | Configurador de la estación PC como host Unified |
| **WinCC Unified Configuration** | ✅ | Panel de gestión del servidor Unified |
| **Identity Service / UMC** | ✅ | Gestor de usuarios y autenticación |

### Paso 5 — Configuración inicial del servidor

Durante la instalación se solicitarán:

- **Nombre de la estación** (puede ser el nombre del PC)
- **Puerto HTTPS** (por defecto 443, dejar así)
- **Certificado autofirmado** (aceptar valores por defecto)

### Paso 6 — Iniciar instalación

1. Click en **Install**
2. Tiempo estimado: **30-45 minutos**
3. **No interrumpir** el proceso

### Paso 7 — Reiniciar el PC

🔴 **OBLIGATORIO.** Los servicios de Windows necesitan registrarse después del reinicio.

---

## ✅ Verificación de instalación

### Verificación 1 — Servicios Windows

1. **Win + R** → escribe `services.msc` → Enter
2. Busca servicios que empiecen con:
   - `SIMATIC`
   - `Siemens`
   - `WinCC Unified`
3. Verifica que estén en estado **"Running"** (En ejecución)

### Verificación 2 — Acceso al portal web

1. Abre Edge o Chrome
2. Navega a: `https://localhost`
3. Aceptar el certificado autofirmado (Advanced → Continue)
4. Debe aparecer la pantalla de bienvenida con cuatro opciones:
   - WinCC Unified RT
   - My WinCC Unified
   - User management
   - WinCC Unified Help

Si aparece esta pantalla, el Runtime está correctamente instalado y operativo.

### Verificación 3 — SIMATIC Runtime Manager

1. Menú Inicio → busca **"SIMATIC Runtime Manager"**
2. Ábrelo
3. Debe mostrar el estado de tu estación local
4. Permite iniciar, detener y monitorear proyectos Unified cargados

---

## 🔧 Configuración post-instalación

### Configuración del firewall

Verifica que el firewall de Windows permita los siguientes puertos:

| Puerto | Protocolo | Uso |
|---|---|---|
| 443 | HTTPS | Acceso web al SCADA |
| 4848 | HTTPS | Configuración Unified |
| 102 | TCP | Comunicación S7 con PLCs |
| 4840 | TCP | OPC UA |

### Configuración del IIS

Algunos componentes de Unified requieren **Internet Information Services (IIS)** habilitado en Windows:

1. **Panel de control** → Programas → Características de Windows
2. Marca: ☑ **Internet Information Services**
3. Reinicia el PC

---

## 🚀 Flujo de trabajo típico con Unified

```
┌───────────────────────────────────────────────────────────┐
│ 1. Diseño                                                 │
│    TIA Portal V21 + WinCC Unified Engineering             │
│    └── Crear proyecto, pantallas, tags                    │
└───────────────────────────┬───────────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────────┐
│ 2. Compilación                                            │
│    Click derecho PC-System → Compile                      │
└───────────────────────────┬───────────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────────┐
│ 3. Despliegue                                             │
│    Download to device → Software (all)                    │
│    Destino: WinCC Unified PC Runtime local                │
└───────────────────────────┬───────────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────────┐
│ 4. Operación                                              │
│    https://localhost desde navegador                      │
│    Login con credenciales configuradas                    │
└───────────────────────────────────────────────────────────┘
```

---

## ❗ Problemas comunes

### `https://localhost` no responde

**Solución:**
1. Verifica que los servicios Unified estén corriendo en `services.msc`
2. Reinicia el PC
3. Espera 2-3 minutos para que arranquen todos los servicios

### "Waiting for IPSimatic-Logon" se queda colgado

**Solución:**
1. Refresca con F5
2. Si persiste, reinicia servicios Unified
3. Limpia caché del navegador (Ctrl + Shift + Suprimir)
4. Prueba en modo incógnito

### Error al descargar el proyecto

**Solución:**
1. Verifica que la IP del PC-System en TIA Portal coincida con la IP real del PC
2. Configura las contraseñas correctamente en Runtime Settings → User administration
3. Asegúrate de tener una **pantalla de inicio asignada**

---

## 📚 Siguiente paso

➡️ [Instalar S7-PLCSIM Advanced V7](./03-plcsim-advanced.md)

---

[⬅️ Volver al README principal](../../README.md)
