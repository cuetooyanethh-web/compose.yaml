# Instalador de OpenVAS Corregido por Cueto

Este repositorio contiene la solución definitiva al despliegue de Greenbone OpenVAS Community Edition en Docker, reparando errores de dependencias, bucles de bases de datos y bloqueos en los puertos.

## 🚀 Instrucciones de Instalación Pasó a Paso

Abre tu terminal en Kali Linux y ejecuta estos tres comandos en orden:

```bash
# 1. Clonar el repositorio completo en tu máquina
git clone https://github.com/cuetooyanethh-web/openvas-docker-fix.git

# 2. Entrar a la carpeta del proyecto que se acaba de descargar
cd openvas-docker-fix

# 3. Levantar todos los contenedores en segundo plano con Docker
docker compose up -d
```

## 🔐 Configuración de Acceso Inicial

Una vez que los contenedores estén corriendo, recuerda cambiar la contraseña del administrador con este comando:

```bash
docker compose exec -u gvmd gvmd gvmd --user=admin --new-password='admin'
```

Finalmente, abre tu navegador e ingresa usando **HTTP** (sin la S):
👉 `http://127.0.0.1:9392`
