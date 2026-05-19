# 📘 Instalación de S7-PLCSIM Advanced V7

[⬅️ Volver al README principal](../../README.md)

---

## 📥 Descarga del instalador

**Archivo:** `S7-PLCSIM_Advanced_V7.iso`
**Tamaño aproximado:** 2 GB

🔗 **[Descargar desde Google Drive](https://drive.google.com/file/d/1HvrziPWIQmeu_lf_4Zl65raoZruFowif/view?usp=drive_link)**

---

## 📦 ¿Qué es S7-PLCSIM Advanced?

S7-PLCSIM Advanced es el **simulador avanzado de PLCs Siemens S7-1500**. A diferencia del PLCSIM clásico que viene con TIA Portal, esta versión avanzada permite:

- ✅ Simular CPUs S7-1500 con **interfaz PROFINET real**
- ✅ Crear **adaptadores virtuales de red con IP real**
- ✅ Ejecutar hasta **16 instancias** de CPU simultáneamente
- ✅ Soportar **OPC UA Server**
- ✅ Soportar **Web Server** del PLC
- ✅ Comunicarse con HMIs externos, SCADA y aplicaciones de terceros
- ✅ Probar arquitecturas multi-PLC realistas

### Comparación: PLCSIM clásico vs PLCSIM Advanced

| Característica | PLCSIM clásico | PLCSIM Advanced V7 |
|---|---|---|
| Comunicación | Softbus interno | TCP/IP real |
| OPC UA Server | ❌ | ✅ |
| Web Server | ❌ | ✅ |
| Multi-instancia | ❌ | ✅ (hasta 16) |
| Acceso desde HMI externo | ❌ | ✅ |
| Compatible con SCADA | Limitado | Total |
| Recomendado para | Pruebas simples | Simulación profesional |

---

## 🖥️ Requisitos del sistema

| Componente | Mínimo | Recomendado |
|---|---|---|
| Sistema operativo | Windows 10/11 Pro 64-bit | Windows 11 Pro 64-bit |
| Procesador | Intel Core i5 + virtualización (VT-x/AMD-V) | Intel Core i7/i9 |
| RAM | 16 GB | 32 GB |
| Disco duro | 10 GB libres | 20 GB libres |
| TIA Portal | V14 o superior | V19 (compatibilidad óptima) |
| Driver de red | Npcap OEM (incluido) | Npcap OEM (incluido) |

### ⚠️ Compatibilidad con TIA Portal

Según el manual oficial de Siemens (V7.0, noviembre 2024):

> Las instancias simuladas de PLC en S7-PLCSIM Advanced V7 corresponden a CPU S7-15xx V3.1, **compatible con TIA Portal V14 a V19**.

**Notas importantes:**
- Con TIA Portal V20 y V21 puede haber **comportamientos inconsistentes**
- La compatibilidad total esperada es con **PLCSIM Advanced V8** (cuando Siemens lo libere)
- Para TIA Portal V21, considera **bajar la versión del firmware del CPU** en el proyecto a V2.9 o inferior

---

## 🚀 Pasos de instalación

### Paso 1 — Preparación del sistema

1. **Cierra TIA Portal** y cualquier programa Siemens
2. **Desactiva temporalmente el antivirus**
3. **Cierra Wireshark** si lo tienes abierto (puede conflictuar con Npcap)
4. Verifica que **NO tengas WinPcap** instalado (Npcap lo reemplaza)

### Paso 2 — Montar el ISO

1. **Doble click** sobre `S7-PLCSIM_Advanced_V7.iso`
2. Windows lo monta como unidad virtual

### Paso 3 — Ejecutar instalador

1. Abre la unidad montada
2. **Click derecho** sobre `Start.exe` → **Ejecutar como administrador**

### Paso 4 — Componentes a instalar

| Componente | Estado | Función |
|---|---|---|
| **S7-PLCSIM Advanced V7** | ✅ | El simulador principal |
| **Npcap OEM** | ✅ (se instala automático) | Driver de red para adaptador virtual |
| **PLCSIM V5.4 SP8** | ✅ (incluido) | Para compatibilidad con simulación de S7-300/400 |
| **Runtime Manager** | ✅ | Gestor de instancias |
| **API Documentation** | ⬜ (opcional) | Documentación de API para automatización |

### Paso 5 — Configuración de Npcap durante la instalación

⚠️ **CRÍTICO:** Cuando el instalador ejecute el sub-instalador de Npcap, **debes marcar correctamente las opciones**:

| Opción | Estado correcto |
|---|---|
| Restrict Npcap driver's access to Administrators only | ⬜ Desmarcado |
| Support raw 802.11 traffic (and monitor mode) for wireless adapters | ⬜ Desmarcado |
| **Install Npcap in WinPcap API-compatible Mode** | ✅ **MARCADO** |

> Si saltaste esta pantalla sin configurar correctamente, verás errores de "Incompatible device" al intentar descargar. Ver la [guía de solución de problemas](../troubleshooting/plcsim-advanced-npcap.md).

### Paso 6 — Finalizar instalación

1. Click **Install** o **Instalar**
2. Tiempo estimado: **15-30 minutos**
3. Al terminar, **REINICIA EL PC** (obligatorio)

---

## ✅ Verificación de instalación

### Verificación 1 — Driver Npcap activo

1. **Win + S** → busca: `cmd`
2. Click derecho → **Ejecutar como administrador**
3. Escribe:
   ```
   sc query npcap
   ```
4. Debe mostrar: **STATE: 4 RUNNING**

### Verificación 2 — Adaptador virtual presente

En el mismo CMD:
```
ipconfig /all
```

Busca una sección que diga:
```
Adaptador Ethernet ...
Descripción . . . . . : Siemens PLCSIM Virtual Ethernet Adapter
Dirección IPv4. . . . : 192.168.X.X
```

Si aparece, el adaptador virtual está operativo.

### Verificación 3 — PLCSIM Advanced abre correctamente

1. Menú Inicio → busca: **"S7-PLCSIM Advanced V7"**
2. **Click derecho** → **Ejecutar como administrador**
3. Debe abrir el **Control Panel** con las opciones:
   - Online Access (PLCSIM / TCP/IP Single Adapter / TCP/IP Multiple Adapter)
   - Virtual Time Scaling
   - Start Simulated PLC Instance

---

## 🎮 Uso básico

### Crear primera instancia virtual

1. Abre **S7-PLCSIM Advanced V7** como administrador
2. **Online Access**: selecciona **TCP/IP Single Adapter**
3. **TCP/IP communication with**: `<Local>` o `Ethernet`
4. En **Start Simulated PLC Instance**:
   - Instance name: `CPU_Sim_1`
   - IP address: `192.168.1.10` (debe coincidir con la IP del PLC en TIA Portal)
   - Subnet mask: `255.255.255.0`
   - PLC family: `S7-1500`
5. Click **Start**

### Configurar IP del adaptador virtual

Para que TIA Portal pueda encontrar la instancia:

1. **Panel de control** → Centro de redes y recursos compartidos
2. Click en **"Cambiar configuración del adaptador"**
3. Localiza **"Siemens PLCSIM Virtual Ethernet Adapter"**
4. Click derecho → Propiedades → **Protocolo de Internet versión 4 (TCP/IPv4)**
5. Configura:
   - IP: `192.168.1.50` (debe ser distinta a la del PLC virtual)
   - Máscara: `255.255.255.0`
   - Sin gateway

### Descargar proyecto desde TIA Portal

1. En TIA Portal V21, click derecho sobre el PLC del proyecto
2. **Download to device → Hardware and software (all)**
3. Configurar:
   - Type of PG/PC interface: **PN/IE**
   - PG/PC interface: **Siemens PLCSIM Virtual Ethernet Adapter**
   - Connection: **PN/IE_1**
4. **Start search** → debe aparecer el CPU virtual
5. Click **Load** → confirma el proceso

---

## ❗ Problemas comunes

### "Incompatible device detected"

**Causa típica:** Npcap mal configurado.

➡️ [Ver solución completa](../troubleshooting/plcsim-advanced-npcap.md)

### El adaptador virtual no aparece en `ipconfig`

**Posibles causas:**
- Falta reiniciar el PC después de instalar
- Npcap no quedó instalado
- Hyper-V o VMware están secuestrando los adaptadores

**Solución:**
1. Reinicia el PC
2. Verifica `sc query npcap` (debe estar RUNNING)
3. Desactiva temporalmente Hyper-V si está activo:
   ```
   bcdedit /set hypervisorlaunchtype off
   ```
4. Reinicia y vuelve a probar

### Instancia no pasa de STOP a RUN

**Causa:** Una instancia recién creada con CPU "Unspecified" arranca en STOP esperando que TIA Portal descargue el proyecto. Esto es normal.

**Solución:** Descarga el proyecto desde TIA Portal — al terminar el download, automáticamente pasa a RUN.

---

## 🔗 Integraciones avanzadas

Con PLCSIM Advanced funcionando correctamente, puedes:

- **Conectar OPC UA clients** (Prosys, KEPServerEX) al puerto 4840 del PLC virtual
- **Usar Factory I/O** para simulación 3D de plantas
- **Probar comunicación MQTT** con brokers externos
- **Desarrollar arquitecturas SCADA distribuidas** con WinCC Unified

---

## 📚 Siguiente paso

➡️ [Gestión de licencias con Sim_EKB_Install](./04-sim-ekb-install.md)

---

[⬅️ Volver al README principal](../../README.md)
