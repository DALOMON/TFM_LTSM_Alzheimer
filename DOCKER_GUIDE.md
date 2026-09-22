# Guía de Desarrollo: Entorno Docker

Esta guía explica cómo configurar y usar el entorno de trabajo para el proyecto **ProgresionAlzheimer**. Usaremos Docker para que todos tengamos las mismas librerías (Python 3.12, Pandas, Sklearn, etc.) sin instalar nada en nuestro sistema local.

---

## 1. Requisitos Previos

Antes de empezar, asegúrate de tener instalados estos tres componentes:

1. **Docker Engine / Desktop:** [Instalar Docker](https://docs.docker.com/get-docker/)
2. **Docker Compose V2:** [Instalar Compose V2](https://docs.docker.com/compose/install/linux/#install-the-plugin-next) (Normalmente ya viene incluido con Docker).
3. **Extensión de VS Code:** Busca e instala la extensión **[Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)**.

---

## 2. Puesta en Marcha (Flujo de Trabajo)

Sigue este orden exacto cada vez que quieras empezar a trabajar:

### Paso 1: Abrir la carpeta y la terminal
Abre tu terminal de Ubuntu (o la de tu sistema), navega hasta la carpeta del proyecto y lanza VS Code:

```bash
cd ~/Desktop/ProgresionAlzheimer
code .
```

<p align="center"> <img src="ReadmeImages/Terminal.png" alt="Terminal"> </p>

**IMPORTANTE: No cierres esta terminal.**

### Paso 2: Levantar el contenedor (Motor)
Al ejecutar el comando anterior se abre VSCode. Abre una terminal y ejecuta el siguiente comando:

```bash
docker-compose up -d --build
```

En esta sección verás muchas cosas, de la cúales no importa ninguna, a no ser que aparezca un error. La idea del Docker es descargar todas las dependencias que se vayan añadiendo a lo largo del proyecto, siempre dentro del contendor no de forma local.

<p align="center"> <img src="ReadmeImages/VSCodeTerminal.png" alt="VSCodeTerminal"> </p>

En esta imagen vemos exactamente eso, la instalación de las dependencias. Docker solo instala aquellas que no tiene instaladas ya, es decir, si detecta una dependencia ya instalada, no la vuelve a descargar. Por el contrario, si detecta que una dependencia no está instalada, la descarga dentro de este.

### Paso 3: Conectar VS Code al Docker
Para que VS Code use el Python del contenedor en vez del de tu PC:

1. Dentro de VS Code, pulsa la tecla `F1` (o `Ctrl + Shift + P`).

2. Escribe y selecciona: **Dev Containers: Reopen in Container**.
<p align="center"> <img src="ReadmeImages/Container.png" alt="OpenContainer"> </p>

3. Espera unos segundos. Sabrás que estás dentro cuando la barra inferior de VS Code cambie a color azul/verde y muestre:  
<p align="center"> <img src="ReadmeImages/ContainerOpened.png" alt="OpenContainer"> </p>

### Paso 4: Realizar código

### Paso 5: Cerrar la sesión de Docker
Para desconectarnos, tenemos que clicar sobre el botón azul (Esquima Inferior) y darle a esta opción:
<p align="center"> <img src="ReadmeImages/CloseDockerSession.png" alt="CloseDockerSession"> </p>

De esta manera, el docker se apaga, suele tardar 1 minuto aproximadamente.

### Paso 6: Subir nuestros cambios a Git desde la Terminal principal
De esta manera, nuestro repositorio queda actualizado con los últimos cambios realizados.
<p align="center"> <img src="ReadmeImages/GitPush.png" alt="CloseDockerSession"> </p>