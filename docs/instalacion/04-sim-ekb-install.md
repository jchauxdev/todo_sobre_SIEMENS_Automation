# 📘 Gestión de licencias con Sim_EKB_Install

[⬅️ Volver al README principal](../../README.md)

---

## 📥 Descarga

**Archivo:** `Sim_EKB_Install_2025_12_04`

🔗 **[Descargar desde Google Drive](https://drive.google.com/file/d/1O8QYsBTRU-iRjZny165OCUiNi1nBrHk6/view?usp=drive_link)**

---

## ⚠️ Aviso importante

Este utilitario se utiliza en contextos de **formación profesional y aprendizaje** dentro del entorno SENA. Para uso en proyectos productivos comerciales, debe adquirirse la licencia oficial correspondiente a través de Siemens o sus distribuidores autorizados.

Como instructor SENA, recuerda gestionar también las **licencias legítimas** disponibles para instituciones educativas:

- 🔗 [Siemens SCE (Siemens Cooperates with Education)](https://www.siemens.com/sce)
- 🔗 [SITRAIN Access](https://www.sitrain-learning.siemens.com)

---

## 📦 ¿Qué es Sim_EKB_Install?

Herramienta utilitaria para gestión de claves de licencia (EKB = Electronic Keys) en entornos formativos. Permite habilitar las funcionalidades completas del software Siemens durante el periodo de aprendizaje.

---

## 🚀 Procedimiento de uso

### Paso 1 — Prerequisitos

Antes de ejecutar la herramienta:

1. ✅ TIA Portal V21 debe estar **completamente instalado**
2. ✅ Reinicia el PC al menos una vez después de instalar TIA Portal
3. ✅ **Cierra TIA Portal** y cualquier programa Siemens
4. ✅ Verifica que el **Automation License Manager** esté instalado

### Paso 2 — Ejecución

1. Extrae el archivo descargado
2. **Click derecho** sobre el ejecutable → **Ejecutar como administrador**
3. Si Windows Defender alerta, agrégalo a las excepciones temporalmente

### Paso 3 — Selección de productos

En la interfaz de la herramienta:

1. Localiza la sección correspondiente a **TIA Portal V21**
2. Selecciona los productos a habilitar:
   - STEP 7 Professional V21
   - STEP 7 Safety Advanced V21
   - WinCC Comfort/Advanced V21
   - WinCC Professional V21
   - WinCC Unified Engineering V21
   - WinCC Unified PC Runtime V21 (según tamaño de PowerTags requerido)
   - S7-PLCSIM Advanced V7
   - TIA Portal Openness

3. Click en **Long** o **Install**

### Paso 4 — Verificación

1. Abre **Automation License Manager**
2. Verifica que las licencias aparezcan en la pestaña correspondiente
3. Cierra ALM
4. Abre TIA Portal V21
5. Las funcionalidades deben estar disponibles sin restricción de tiempo

---

## ✅ Verificación final

Para confirmar que las licencias quedaron correctamente registradas:

1. Abre TIA Portal V21
2. Menú **Help** → **Installed software**
3. Cada componente debe aparecer con estado **"Licensed"** o sin marca de Trial

---

## 🔧 Problemas comunes

### El Automation License Manager no muestra las licencias

**Solución:**
1. Detén el servicio "Automation License Manager" en `services.msc`
2. Ejecuta nuevamente la herramienta como administrador
3. Reinicia el servicio

### Después de actualizar TIA Portal, las licencias desaparecen

**Solución:** Vuelve a ejecutar Sim_EKB_Install con los productos actualizados.

### Error "License key not found"

**Solución:**
1. Verifica que el archivo no esté corrupto
2. Descarga nuevamente desde el enlace oficial
3. Ejecuta como administrador

---

## 💡 Recomendaciones para instructores SENA

Como instructor responsable, te sugiero:

1. **Solicita licencias SCE oficiales** lo antes posible — son gratuitas para instituciones educativas
2. **Documenta el proceso de licenciamiento** para tus aprendices, explicando la diferencia entre versiones Trial, Educativas y Comerciales
3. **Enseña la importancia de las licencias legítimas** en entornos de producción industrial

---

[⬅️ Volver al README principal](../../README.md)
