# AI Windows Security Monitor v1.0

Herramienta de monitoreo de seguridad para Windows desarrollada en Python.

El proyecto está orientado a detectar actividad potencialmente sospechosa relacionada con PowerShell, procesos del sistema y técnicas comunes utilizadas en ejecución de malware o abuso administrativo.

Fue desarrollado como proyecto personal para practicar monitoreo de procesos, análisis básico de comportamiento y logging en tiempo real.

---

## Características

- Monitoreo de procesos en tiempo real
- Detección heurística basada en keywords y comportamiento
- Detección de PowerShell sospechoso
- Monitoreo de LOLBins comunes de Windows
- Detección de relaciones sospechosas parent/child
- Sistema de severidad (LOW / MEDIUM / HIGH)
- Logging persistente en archivo `.log`
- Interfaz de terminal utilizando Rich
- Agrupación y deduplicación básica de alertas

---

## Demo

<img width="583" height="444" alt="image" src="https://github.com/user-attachments/assets/2b3d42c1-06b1-4869-b739-60f402d8f5c1" />

---

## Ejemplos de detección

El monitor detecta patrones asociados a:

- `ExecutionPolicy Bypass`
- `WindowStyle Hidden`
- `encodedcommand`
- `Invoke-Expression`
- `Invoke-WebRequest`
- `Net.WebClient`
- LOLBins como:
  - `certutil.exe`
  - `mshta.exe`
  - `rundll32.exe`
  - `regsvr32.exe`
  - `wscript.exe`

---

## Capturas

### Interfaz principal

<img width="1299" height="706" alt="terminal-ui-on" src="https://github.com/user-attachments/assets/10254119-6ed3-4836-8a61-95ffb0596bcd" />

<img width="1308" height="712" alt="terminal-ui-off" src="https://github.com/user-attachments/assets/21a2956c-e7ae-44fc-bf59-c5e1523fb3a9" />


---

### Lógica de monitoreo de procesos

<img width="1914" height="1028" alt="process-monitor-code" src="https://github.com/user-attachments/assets/016f373e-15ff-4536-8052-8eb76fd140dd" />

---

### Configuración de reglas y severidad

<img width="1913" height="1030" alt="config-code" src="https://github.com/user-attachments/assets/a9afe9a4-d997-4e99-b18b-5f7fb1082c68" />

---

### Codigo principal

<img width="1648" height="1030" alt="main-code" src="https://github.com/user-attachments/assets/876de88c-08d5-4da3-ac21-7e53b02c2d7d" />

---

### Deteccion activa

<img width="1916" height="1028" alt="alerts-deteccion-on" src="https://github.com/user-attachments/assets/003d8ec0-3863-44f0-986f-6ff0bd208f4a" />

<img width="1917" height="1027" alt="alerts-deteccion-off" src="https://github.com/user-attachments/assets/90022714-8eae-44e1-bbdc-980e9218421f" />

---

### Alerts log .txt

<img width="279" height="169" alt="alerts-log-1" src="https://github.com/user-attachments/assets/44f9f2c9-8b48-4128-a767-109999937547" />

<img width="1879" height="1029" alt="alerts-log-2" src="https://github.com/user-attachments/assets/0e033f1f-f01f-4085-9810-97aa76f95920" />

<img width="1910" height="1024" alt="alerts-log-3" src="https://github.com/user-attachments/assets/7143cf5c-529e-480c-9fd5-6a3588f04f74" />

---

## Tecnologías utilizadas

- Python
- psutil
- Rich
- PyInstaller
- Windows Event Logs

---

## Estructura del proyecto

```text
AI-Windows-Security-Monitor/
│
├── screenshots/
├── logs/
├── main.py
├── process_monitor.py
├── event_log_monitor.py
├── alert_logger.py
├── config.py
├── requirements.txt
└── README.md
```

---

## Instalación

### Requisitos

- Windows 10 / 11
- Python 3.11+

### Instalar dependencias

```bash
pip install -r requirements.txt
```

### Ejecutar

```bash
python main.py
```

---

## Compilar ejecutable

```bash
pyinstaller --onefile main.py
```

---

## Objetivo del proyecto

El objetivo principal fue aprender sobre:

- Monitoreo de procesos.
- Heurísticas básicas de detección.
- Logging.
- Manejo de eventos de Windows.
- Arquitectura modular en Python.

No pretende reemplazar soluciones EDR o antivirus profesionales.

---

## Estado actual

Proyecto funcional en desarrollo y aprendizaje.

Posibles mejoras futuras:

- más reglas heurísticas.
- dashboard visual.
- exportación avanzada de logs.
- mejor correlación de eventos.
- configuración personalizada.

---

## Autor

Toolcee
