# OpenSpeedTest -- Contenedor Docker

Este repositorio contiene la configuración mínima necesaria para
desplegar **OpenSpeedTest** mediante **Docker Compose**.\
OpenSpeedTest es una herramienta de medición de velocidad que permite
evaluar el rendimiento de tu red local (LAN) o a través de Internet
desde cualquier navegador.

## 🚀 Características

-   Basado en la imagen oficial: `openspeedtest/latest`
-   Despliegue extremadamente sencillo
-   No requiere configuración adicional
-   Interfaz web accesible desde cualquier dispositivo
-   Reinicio automático (`unless-stopped`)

## 📁 docker-compose.yml

``` yaml
services:
  ost:
    image: openspeedtest/latest
    container_name: openspeedtest
    ports:
      - '8400:3000'
      - '8300:3001'
    restart: unless-stopped
```

## 🌐 Puertos utilizados

  Puerto Host   Puerto Contenedor   Uso
  ------------- ------------------- -----------------------------------------
  **8400**      3000                Interfaz web principal de OpenSpeedTest
  **8300**      3001                Endpoint auxiliar interno

## ▶️ Puesta en marcha

### 1️⃣ Clona el repositorio

``` bash
git clone https://github.com/tuusuario/openspeedtest-docker.git
cd openspeedtest-docker
```

### 2️⃣ Arranca el contenedor

``` bash
docker compose up -d
```

### 3️⃣ Abre OpenSpeedTest en tu navegador

    http://TU-IP:8400

## 🛑 Detener el contenedor

``` bash
docker compose down
```

## 🔄 Actualizar a la última versión

``` bash
docker compose pull
docker compose up -d
```

