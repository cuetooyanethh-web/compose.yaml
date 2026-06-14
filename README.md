# Instalación de OpenVAS en Docker Corregido por Cueto

Este repositorio contiene la solución definitiva para desplegar Greenbone OpenVAS Community Edition en Kali Linux usando Docker Compose. Se han reparado los errores de dependencias circulares y los conflictos de puertos del archivo oficial.

## 🚀 Instrucciones de Instalación

Abre tu terminal y ejecuta los siguientes comandos en orden:

```bash
# 1. Actualizar el sistema e instalar Docker
sudo apt update
sudo apt install -y docker.io

# 2. Habilitar Docker y refrescar la sesión actual
sudo systemctl enable docker --now
sudo usermod -aG docker $USER && su $USER

# 3. Instalar la herramienta Docker Compose
sudo apt install docker-compose

# 4. Clonar este repositorio corregido
git clone https://github.com/cuetooyanethh-web/compose.yaml.git

# 5. Entrar a la carpeta del proyecto
cd compose.yaml

# 6. Descargar las imágenes y levantar el contenedor
docker compose -f compose.yaml pull
docker compose -f compose.yaml up -d
```

## 🔐 Configuración de Acceso (Login)

Para poder iniciar sesión en la interfaz web, debes establecer la contraseña ejecutando este comando en tu terminal:

```bash
docker compose -f compose.yaml exec -u gvmd gvmd gvmd --user=admin --new-password='cueto'
```

### ⚠️ Nota Muy Importante para el Navegador
Debes ingresar usando obligatoriamente **HTTP**. Si intentas usar HTTPS el puerto no va a funcionar y la página no va a abrir.

👉 Dirección de acceso: http://127.0.0.1:9392
