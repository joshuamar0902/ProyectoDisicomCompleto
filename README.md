#  Sistema de Monitoreo de Motores en Tiempo Real

Este proyecto es una aplicación web desarrollada en Django para la visualización en tiempo real de datos operativos provenientes de un PLC (Controlador Lógico Programable) conectado a motores de embarcaciones. La aplicación proporciona un dashboard dinámico e intuitivo para monitorear métricas clave como velocidad, temperatura, presión y otros indicadores vitales.
![WhatsApp Image 2025-10-06 at 13 11 58_be63f845](https://github.com/user-attachments/assets/eef56649-56e7-4437-96a3-b27aac158d5e)



---

## ✨ Características Principales

* **Dashboard Interactivo:** Visualización de datos mediante velocímetros (gauges) y gráficas que se actualizan en tiempo real.
* **Comunicación en Tiempo Real:** Uso de Django Channels y WebSockets para una conexión persistente y de baja latencia entre el servidor y el cliente.
* **Integración Industrial:** Conexión directa con un PLC utilizando la librería `snap7` para leer bloques de datos (DBs) específicos.
* **Backend Robusto:** Construido sobre el framework Django, garantizando escalabilidad y seguridad.
* **Persistencia de Datos:** Almacenamiento de lecturas históricas para futuro análisis y generación de reportes.

---

## 🔧 Tecnologías Utilizadas

* **Backend:**
    * ![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)
    * ![Django](https://img.shields.io/badge/Django-4.2%2B-darkgreen?logo=django&logoColor=white)
    * ![Django Channels](https://img.shields.io/badge/Channels-WebSocket-blue)
* **Frontend:**
    * ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
    * ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
    * ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
* **Comunicación PLC:**
    * `python-snap7`
* **Base de Datos:**
    * `SQLite3` (desarrollo)
    * `PostgreSQL` (producción)

---

## ⚙️ Puesta en Marcha Local

Sigue estos pasos para ejecutar el proyecto en tu máquina local.

### **Prerrequisitos**

* Python 3.10 o superior
* Git
* Un simulador de PLC (como PLCSIM) o un PLC físico accesible en la red.

### **Instalación**

1.  **Clona el repositorio:**
    ```bash
    git clone [https://github.com/joshuamar0902/ProyectoDisicomCompleto.git](https://github.com/joshuamar0902/ProyectoDisicomCompleto.git)
    cd ProyectoDisicomCompleto
    ```

2.  **Crea y activa un entorno virtual:**
    ```bash
    # En Windows
    python -m venv venv
    .\venv\Scripts\activate

    # En macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Instala las dependencias:**
    *(Primero, asegúrate de tener un archivo `requirements.txt`. Si no lo tienes, créalo con `pip freeze > requirements.txt`)*
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configura las variables de entorno:**
    * Crea un archivo `.env` en la raíz del proyecto y añade la configuración necesaria, como la `SECRET_KEY` de Django y los datos de conexión al PLC.
    ```
    SECRET_KEY='[Tu_Secret_Key_Aqui]'
    PLC_IP_ADDRESS='192.168.0.1'
    PLC_RACK=0
    PLC_SLOT=1
    ```

5.  **Aplica las migraciones de la base de datos:**
    ```bash
    python manage.py migrate
    ```

6.  **Inicia el servidor de Django:**
    ```bash
    python manage.py runserver
    ```

7.  **Inicia el script de comunicación con el PLC:**
    * En una **terminal separada**, ejecuta el script que lee los datos del PLC y los envía a través de Channels.
    ```bash
    python [nombre_de_tu_script_plc.py]
    ```

8.  ¡Listo! Abre tu navegador y ve a `http://127.0.0.1:8000` para ver el dashboard en acción.

---

## 👤 Autor

* **Joshua Marín**
* **GitHub:** [@joshuamar0902](https://github.com/joshuamar0902)
