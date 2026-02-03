# Appwrite for Easypanel

Production-ready **Appwrite deployment for Easypanel**, based on the official Appwrite Docker images and adapted to work cleanly with Easypanel's GitHub + Docker Compose flow.

This repository is **not Appwrite source code**. It is a **deployment repository** intended to be used directly from Easypanel.

---

## ✨ Features

* ✅ Compatible with **Easypanel GitHub deployments**
* ✅ Uses **official Appwrite Docker images**
* ✅ Versioned Appwrite (`APPWRITE_VERSION`, default `1.8.1`)
* ✅ Traefik embedded (Easypanel-friendly)
* ✅ MariaDB + Redis included
* ✅ Functions support via OpenRuntimes Executor
* ✅ Persistent volumes
* ❌ No development-only mounts or build steps

---

## 📦 Repository Structure

```
.
├── docker-compose.yml
├── env.example
└── README.md
```

---

## 🚀 Installation (Easypanel)

1. Go to **Easypanel → Create Service → GitHub**
2. Configure:

   * **Owner**: your GitHub username or organization
   * **Repository**: `appwrite-for-easypanel`
   * **Branch**: `main`
   * **Build Path**: `/`
3. Add environment variables using `env.example`
4. Configure a domain pointing to the service
5. Deploy 🚀

---

## ⚙️ Environment Variables

Minimum required variables:

* `_APP_OPENSSL_KEY_V1`
* `_APP_DOMAIN`
* `_APP_DOMAIN_TARGET`
* `_APP_DB_PASS`
* `_APP_DB_ROOT_PASS`
* `_APP_EXECUTOR_SECRET`

Optional:

* `APPWRITE_VERSION` (defaults to `1.8.1`)
* `_APP_DOMAIN_FUNCTIONS` (recommended if using Functions)

All available variables are documented in `env.example`.

---

## 🔄 Upgrading Appwrite

To upgrade Appwrite:

1. Change `APPWRITE_VERSION` in Easypanel
2. Redeploy the service
3. Appwrite will handle database migrations automatically

Always **pin a specific version**. Do not use `latest`.

---

## 🔐 TLS / HTTPS

TLS is expected to be handled by **Easypanel**.

Traefik inside the stack only manages internal routing.

---

## 🧠 Notes

* This setup is optimized for **production**
* No development tools are included
* Safe to fork and reuse

---

## 📄 License

MIT

---

# Appwrite para Easypanel (Español)

Despliegue de **Appwrite listo para producción en Easypanel**, basado en imágenes oficiales y adaptado al flujo GitHub + Docker Compose de Easypanel.

Este repositorio **no contiene el código fuente de Appwrite**. Es un **repositorio de despliegue**.

---

## ✨ Características

* ✅ Compatible con **despliegue GitHub en Easypanel**
* ✅ Usa **imágenes oficiales de Appwrite**
* ✅ Versión configurable (`APPWRITE_VERSION`, por defecto `1.8.1`)
* ✅ Traefik integrado (compatible con Easypanel)
* ✅ MariaDB + Redis incluidos
* ✅ Soporte para Functions (OpenRuntimes Executor)
* ✅ Volúmenes persistentes
* ❌ Sin mounts ni herramientas de desarrollo

---

## 📦 Estructura del Repositorio

```
.
├── docker-compose.yml
├── env.example
└── README.md
```

---

## 🚀 Instalación en Easypanel

1. Ir a **Easypanel → Crear Servicio → GitHub**
2. Configurar:

   * **Propietario**: usuario u organización de GitHub
   * **Repositorio**: `appwrite-for-easypanel`
   * **Rama**: `main`
   * **Ruta de compilación**: `/`
3. Definir variables usando `env.example`
4. Configurar un dominio
5. Desplegar 🚀

---

## ⚙️ Variables de Entorno

Variables mínimas requeridas:

* `_APP_OPENSSL_KEY_V1`
* `_APP_DOMAIN`
* `_APP_DOMAIN_TARGET`
* `_APP_DB_PASS`
* `_APP_DB_ROOT_PASS`
* `_APP_EXECUTOR_SECRET`

Opcionales:

* `APPWRITE_VERSION` (por defecto `1.8.1`)
* `_APP_DOMAIN_FUNCTIONS` (recomendado si usas Functions)

Consulta `env.example` para el listado completo.

---

## 🔄 Actualización de Appwrite

Para actualizar Appwrite:

1. Cambia `APPWRITE_VERSION` en Easypanel
2. Redeploya el servicio
3. Appwrite ejecutará las migraciones automáticamente

Siempre fija una versión. No uses `latest`.

---

## 🔐 HTTPS / TLS

El manejo de TLS/HTTPS se espera que lo haga **Easypanel**.

Traefik solo se usa para ruteo interno.

---

## 🧠 Notas

* Configuración pensada para **producción**
* Sin dependencias de desarrollo
* Puedes forkar y reutilizar libremente

---

## 📄 Licencia

MIT
