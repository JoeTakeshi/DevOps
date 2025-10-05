Guía del Estudiante: Iniciación a GitHub para Ingenieros DevOps**

¡Bienvenido a tu guía de inicio en GitHub! En esta sesión, configuraremos tu entorno de desarrollo colaborativo de manera profesional y segura. Sigue estos pasos para construir tu identidad digital y preparar tus herramientas para el trabajo.

---

### **Parte 1: Fundamentos y Creación de tu Cuenta Profesional (20 minutos)**

#### **1.1 Entendiendo la Diferencia Clave**

Antes de empezar, asegúrate de entender esta distinción fundamental:

*   **Git:** Es el **software** que se instala en tu computadora. Es el motor que controla el historial de cambios de tu código localmente.
*   **GitHub:** Es el **servicio web** (la plataforma) donde alojamos nuestros repositorios Git para colaborar con otros. Es el "garaje en la nube" para nuestros proyectos, con herramientas sociales y de automatización.

#### **1.2 Creación de tu Cuenta de GitHub**

Vamos a crear tu perfil profesional. Esta será tu tarjeta de presentación en el mundo del desarrollo.

1.  **Navega a [github.com](https://github.com)** y haz clic en "Sign up".
2.  **Elige tu Nombre de Usuario:** ¡Este paso es importante!
    *   **✅ Bueno:** Usa una variación de tu nombre real. Es profesional y fácil de encontrar. Ejemplos: `juan-perez`, `jperez-dev`, `perez-juan-io`.
    *   **❌ A evitar:** Apodos, nombres de juegos o combinaciones poco profesionales. Ejemplos: `dark_coder92`, `luchito_crack`, `dev_master_pro`.
3.  **Completa el Registro:** Sigue los pasos proporcionando tu correo electrónico y creando una contraseña segura.

#### **1.3 Configurando tu Perfil Profesional**

Un perfil completo genera confianza y demuestra profesionalismo.

1.  Una vez creada tu cuenta, haz clic en tu ícono de perfil en la esquina superior derecha y selecciona **"Your profile"**.
2.  Haz clic en el botón **"Edit profile"**.
3.  **Añade una Foto de Perfil:** Usa una foto clara y profesional (tipo headshot).
4.  **Escribe tu Biografía (Bio):** Esta es tu "elevator pitch". Sé conciso y descriptivo.
    *   **Fórmula recomendada:** `[Tu Rol Actual/Aspiracional] en [Tecnologías Clave] | Apasionado por [Área de Interés]`
    *   **Ejemplo:** `DevOps Engineer enfocado en AWS & Kubernetes | Apasionado por la automatización de infraestructura y la cultura CI/CD.`

#### **1.4 ¡Obligatorio! Activa la Autenticación de Dos Factores (2FA)**

Esta es la medida de seguridad más importante para proteger tu cuenta.

1.  Ve a tu ícono de perfil → **Settings**.
2.  En el menú de la izquierda, haz clic en **"Password and authentication"**.
3.  En la sección "Two-factor authentication", haz clic en **"Enable two-factor authentication"**.
4.  Se te recomendará usar una **aplicación de autenticación**. Esta es la mejor opción.
    *   Descarga una app como **Google Authenticator**, **Microsoft Authenticator** o **Authy** en tu smartphone.
    *   Escanea el código QR que te muestra GitHub con la app.
    *   Ingresa el código numérico de 6 dígitos que genera tu app para confirmar.
5.  **¡CRÍTICO! Descarga y guarda tus códigos de recuperación.** Guárdalos en un lugar seguro (un gestor de contraseñas, por ejemplo). Te permitirán acceder a tu cuenta si pierdes tu teléfono.

---

### **Parte 2: Conexión Segura - Configuración de Claves SSH (15 minutos)**

Vamos a establecer un canal de comunicación seguro y sin contraseñas entre tu computadora y GitHub.

#### **2.1 Generar tu Par de Claves SSH**

1.  **Abre un terminal** en tu computadora.
    *   **Windows:** Abre Git Bash (viene con la instalación de Git) o Windows Terminal.
    *   **Mac/Linux:** Abre la aplicación Terminal.
2.  **Ejecuta el siguiente comando.** Reemplaza `"tu_email@ejemplo.com"` con el correo electrónico que usaste para tu cuenta de GitHub. `ed25519` es el algoritmo recomendado, moderno y seguro.

    ```bash
    ssh-keygen -t ed25519 -C "tu_email@ejemplo.com"
    ```

3.  **Sigue las instrucciones en la terminal:**
    *   Cuando te pregunte `Enter a file in which to save the key...`, simplemente **presiona Enter** para aceptar la ubicación por defecto.
    *   Cuando te pregunte `Enter passphrase (empty for no passphrase):`, **presiona Enter dos veces**. Para este curso, no usaremos una passphrase para simplificar, pero en entornos de alta seguridad, es una capa extra de protección.

    Verás un mensaje confirmando que tu clave ha sido generada.

#### **2.2 Añadir tu Clave SSH Pública a GitHub**

Ahora le diremos a GitHub cuál es tu "candado" (tu clave pública).

1.  **Copia tu clave pública al portapapeles.** Ejecuta uno de los siguientes comandos en tu terminal. El comando simplemente muestra el contenido del archivo de tu clave pública para que puedas copiarlo.

    *   **Mac:**
        ```bash
        pbcopy < ~/.ssh/id_ed25519.pub
        ```
    *   **Linux (requiere `xclip`):**
        ```bash
        xclip -selection clipboard < ~/.ssh/id_ed25519.pub
        ```
    *   **Windows (Git Bash):**
        ```bash
        cat ~/.ssh/id_ed25519.pub | clip
        ```
    *   **Si los comandos anteriores fallan,** simplemente muestra el contenido con `cat ~/.ssh/id_ed25519.pub` y cópialo manualmente. Asegúrate de copiar todo, desde `ssh-ed25519` hasta tu email.

2.  **Vuelve a GitHub en tu navegador.**
3.  Ve a tu ícono de perfil → **Settings**.
4.  En el menú de la izquierda, haz clic en **"SSH and GPG keys"**.
5.  Haz clic en el botón verde **"New SSH key"**.
6.  **Título (Title):** Dale un nombre descriptivo a tu clave para que sepas qué computadora es. Ejemplo: `Laptop de Trabajo Dell`, `MacBook Pro Personal`.
7.  **Clave (Key):** Pega el contenido de tu clave pública que copiaste en el paso 1.
8.  Haz clic en **"Add SSH key"**. Puede que te pida tu contraseña de GitHub para confirmar.

---

### **Parte 3: Taller de Exploración y Productividad (20 minutos)**

#### **3.1 Taller 1: La Anatomía de un Repositorio (Exploración Guiada)**

Navegaremos juntos por un repositorio popular como [**microsoft/vscode**](https://github.com/microsoft/vscode) para aprender a "leer" cualquier proyecto.

**Tu misión (sigue las indicaciones del profesor):**
1.  **Encontrar la Versión:** Localiza la sección "Releases" y anota el número de la última versión.
2.  **Investigar un Bug:** Ve a la pestaña "Issues", usa el filtro `Label` y encuentra un `bug` abierto.
3.  **Revisar Cambios Recientes:** Ve a la pestaña "Code" y haz clic en el historial de "commits". ¿Quién hizo el último cambio en la rama principal?
4.  **Ver la Automatización:** Explora la pestaña "Actions". Encuentra un workflow de CI y observa sus pasos.

#### **3.2 Taller 2: Integración de VS Code con GitHub**

Vamos a conectar tu editor de código para un flujo de trabajo súper eficiente.

1.  **Abre Visual Studio Code.**
2.  **Instala la Extensión Clave:**
    *   Ve a la vista de Extensiones en la barra lateral izquierda (el icono de los cuatro cuadrados).
    *   Busca **"GitHub Pull Requests and Issues"**.
    *   Haz clic en **"Install"**.
3.  **Inicia Sesión en tu Cuenta:**
    *   Una vez instalada, aparecerá un icono de una cuenta en la esquina inferior izquierda de VS Code (una silueta de persona).
    *   Haz clic en él y selecciona **"Sign in with GitHub..."**.
    *   Tu navegador se abrirá para que autorices a VS Code a acceder a tu cuenta de GitHub. Sigue los pasos para autorizarlo.
4.  **Prueba la Integración (El Momento Mágico):**
    *   Vuelve a la página de GitHub del repositorio [**microsoft/vscode**](https://github.com/microsoft/vscode).
    *   Haz clic en el botón verde **"< > Code"**. Asegúrate de que la pestaña **"SSH"** está seleccionada y copia la URL (debería empezar con `git@github.com:...`).
    *   Vuelve a VS Code. Abre la Paleta de Comandos con `Ctrl+Shift+P` (Windows/Linux) o `Cmd+Shift+P` (Mac).
    *   Escribe **`Git: Clone`** y presiona Enter.
    *   Pega la URL SSH que copiaste y presiona Enter.
    *   Elige una carpeta en tu computadora para guardar el proyecto.
    *   Observa cómo VS Code clona el repositorio sin pedirte contraseña.