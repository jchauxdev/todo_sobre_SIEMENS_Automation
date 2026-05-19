# 🏭 Manual de Automatización Industrial con Siemens

> Repositorio sobre programación, configuración y puesta en marcha de soluciones de automatización industrial con tecnología Siemens (TIA Portal, WinCC Unified, S7-1500, ET 200SP, HMIs y SCALANCE).

---

## 📖 Introducción

Este repositorio funciona como **guía técnica y didáctica** para ingenieros y estudiantes que trabajan con el ecosistema Siemens en proyectos de automatización industrial. El material está construido a partir de experiencias prácticas reales con equipos físicos y entornos simulados, documentando paso a paso desde la instalación del software hasta la implementación de sistemas SCADA modernos basados en web.

El objetivo es proporcionar un recurso de consulta rápida, ordenado, en español, que cubra los escenarios típicos de:

- Programación de controladores S7-1200, S7-1500 y ET 200SP Open Controller
- Configuración de paneles HMI Basic y Comfort
- Desarrollo de aplicaciones SCADA con WinCC Unified
- Comunicación industrial PROFINET, OPC UA, MQTT
- Simulación virtual completa de plantas para entornos de aprendizaje
- Integración de redes inalámbricas industriales (SCALANCE)

---

## 🎯 Audiencia objetivo

| Perfil | Nivel sugerido |
|---|---|
| Ingenieros de automatización industrial | Todos los niveles |
| Ingenieros de mantenimiento industrial | Intermedio - Avanzado |
| Integradores de sistemas | Avanzado |

---

## 🧰 Equipos y software cubiertos

### Controladores
- CPU 1511 (S7-1500)
- CPU 1512C-1 PN (S7-1500 compacta)
- CPU 1516 (S7-1500)
- CPU 1200 (S7-1200)
- SIMATIC ET 200SP Open Controller

### Interfaces Hombre-Máquina (HMI)
- KTP600 Basic color PN (6AV6647-0AD11-3AX0)
- TP2200 Comfort (6AV2 124-0XC02-0AX1)

### Comunicaciones industriales
- 2× SCALANCE W788-1 RJ45 IWLAN Access Point (6GK5788-1FC00-0AA0)

### Software
- TIA Portal V21 (STEP 7 Professional + Safety + WinCC)
- WinCC Unified Engineering V21
- WinCC Unified PC Runtime V21
- S7-PLCSIM Advanced V7
- SIMATIC ProSave V21

---

## 📚 Contenido del repositorio

### TIA Portal V21

| # | Tema | Enlace |
|---|---|---|
| 1 | Instalación de TIA Portal STEP 7 + Safety + WinCC V21 | [📘 Ver guía](./docs/instalacion/01-tia-portal-step7-wincc.md) |
| 2 | Instalación de WinCC Unified PC Runtime V21 | [📘 Ver guía](./docs/instalacion/02-wincc-unified-runtime.md) |
| 3 | Instalación de S7-PLCSIM Advanced V7 | [📘 Ver guía](./docs/instalacion/03-plcsim-advanced.md) |
| 4 | Gestión de licencias con Sim_EKB_Install | [📘 Ver guía](./docs/instalacion/04-sim-ekb-install.md) |

### Solucionador de problemas

| # | Tema | Enlace |
|---|---|---|
| 🔧 | Error "Incompatible device" en PLCSIM Advanced | [🛠️ Ver solución](./docs/troubleshooting/plcsim-advanced-npcap.md) |

---

## ⚠️ Aviso legal

Este material es de carácter **educativo y de formación profesional**. Los enlaces de descarga apuntan a copias usadas en el contexto de aprendizaje del SENA. Para uso en proyectos comerciales o productivos, se requiere adquirir licencias oficiales a través de Siemens o sus distribuidores autorizados.

Las marcas SIMATIC, TIA Portal, WinCC, SCALANCE y todas las relacionadas son propiedad de Siemens AG.

---

## 🤝 Contribuciones

Este repositorio crece de forma incremental. Si encuentras errores, tienes sugerencias o quieres aportar nuevos temas, por favor abre un *Issue* o un *Pull Request*.

---

## 📞 Contacto

**Instructor responsable:** Julian Chaux
**Institución:** SENA Regional Huila
**Centro:** [Pendiente completar]

---

## 📅 Estado del proyecto

🟢 **Activo** — Documentación en construcción continua.

**Última actualización:** Mayo 2026
