# Santa Rita Conectada

## Aplicación Android

Aplicación móvil nativa que forma parte del sistema de gestión comunitaria **Santa Rita Conectada**.

Actúa como el cliente principal para los vecinos, consumiendo la API REST del backend para la visualización de comunicados y la recepción de alertas en tiempo real.

Este proyecto requiere el [Backend en Laravel](https://github.com/ghernandezsotodev/santa-rita-conectada) para funcionar.

---

## Arquitectura y Stack Tecnológico

La aplicación está construida utilizando el patrón arquitectónico **MVVM (Model-View-ViewModel)**, garantizando una separación entre la capa de datos, la lógica de presentación y la interfaz de usuario.

| Componente | Tecnología |
|---|---|
| Lenguaje | Kotlin |
| UI Toolkit | Jetpack Compose |
| Arquitectura | MVVM (Model-View-ViewModel) |
| Consumo de API | Retrofit 2 + OkHttp |
| Programación Asíncrona | Kotlin Coroutines |
| Notificaciones Push | Firebase Cloud Messaging (FCM) |

---

## Funcionalidades Principales

### Autenticación Segura

Inicio de sesión mediante tokens JWT proporcionados por el backend para la autenticación de los usuarios.

### Feed de Comunicados

Visualización de noticias, comunicados y eventos comunitarios.

### Notificaciones Push

Recepción de alertas en tiempo real mediante **Firebase Cloud Messaging (FCM)** para avisos y comunicaciones de la directiva.

### Gestión de Subsidios

Interfaz para que los vecinos puedan revisar el estado de sus postulaciones y consultar los requisitos correspondientes.

---

## Instalación y Configuración Local

### 1. Clonar el repositorio

Clona el repositorio de la aplicación:

```bash
git clone https://github.com/ghernandezsotodev/santa-rita-conectada-app.git
```

### 2. Abrir el proyecto

Abre el proyecto clonado utilizando **Android Studio**.

### 3. Configurar Firebase

Para habilitar las funcionalidades que utilizan Firebase:

1. Crea un proyecto en Firebase.
2. Registra la aplicación Android dentro del proyecto de Firebase.
3. Descarga tu archivo `google-services.json`.
4. Coloca el archivo dentro del directorio:

```text
app/
└── google-services.json
```

> El archivo `google-services.json` debe corresponder al proyecto de Firebase configurado para la aplicación.

### 4. Configurar la URL del Backend

Modifica la constante `BASE_URL` utilizada por el cliente de **Retrofit** para que apunte a la instancia del backend Laravel que utilizarás durante el desarrollo.

Por ejemplo:

```kotlin
const val BASE_URL = "http://TU_SERVIDOR:PUERTO/"
```

La URL debe apuntar al servidor donde se encuentra disponible la API REST del backend.

### 5. Sincronizar el proyecto

Sincroniza el proyecto con **Gradle** desde Android Studio para descargar las dependencias necesarias.

### 6. Ejecutar la aplicación

Conecta un dispositivo Android o inicia un emulador y ejecuta la aplicación desde Android Studio.

---

## Requisitos

Para ejecutar el proyecto localmente se requiere:

- Android Studio.
- JDK compatible con la configuración del proyecto.
- Android SDK.
- Gradle, administrado mediante el proyecto.
- Un dispositivo Android físico o un emulador.
- Backend de Santa Rita Conectada disponible para las solicitudes de la API.
- Proyecto de Firebase configurado para las funcionalidades de FCM.

---

## Integración con el Backend

La aplicación móvil consume los servicios proporcionados por el backend mediante una API REST.

La comunicación entre los componentes se estructura de la siguiente manera:

```text
Aplicación Android
       |
       | HTTP / API REST
       v
Backend Laravel 12
       |
       +------------------+
       |                  |
       v                  v
    MySQL 8              FCM
 Base de Datos      Notificaciones Push
```

El backend es responsable de proporcionar los datos y servicios utilizados por la aplicación móvil, mientras que Firebase Cloud Messaging permite la recepción de notificaciones push.

---

## Arquitectura de la Aplicación

La aplicación utiliza **MVVM (Model-View-ViewModel)** como patrón arquitectónico principal.

La estructura conceptual es:

```text
┌─────────────────────────────┐
│            View             │
│       Jetpack Compose       │
└──────────────┬──────────────┘
               │
               v
┌─────────────────────────────┐
│         ViewModel           │
│     Lógica de Presentación  │
└──────────────┬──────────────┘
               │
               v
┌─────────────────────────────┐
│            Model            │
│  Datos / API / Repositorios │
└──────────────┬──────────────┘
               │
               v
┌─────────────────────────────┐
│       Backend Laravel       │
│          API REST           │
└─────────────────────────────┘
```

La interfaz se desarrolla utilizando **Jetpack Compose**, mientras que Retrofit, OkHttp y Kotlin Coroutines gestionan la comunicación y las operaciones asíncronas.

---

## Tecnologías Utilizadas

- **Kotlin:** lenguaje principal de desarrollo.
- **Jetpack Compose:** toolkit utilizado para la construcción de la interfaz de usuario.
- **MVVM:** patrón arquitectónico de la aplicación.
- **Retrofit 2:** cliente HTTP para el consumo de la API REST.
- **OkHttp:** biblioteca utilizada para la comunicación HTTP.
- **Kotlin Coroutines:** manejo de operaciones asíncronas.
- **Firebase Cloud Messaging:** sistema de notificaciones push.
- **Android Studio:** entorno de desarrollo.

---

## Resumen

Santa Rita Conectada para Android proporciona a los vecinos una aplicación móvil para interactuar con los servicios de la plataforma comunitaria.

La aplicación integra:

- Autenticación mediante JWT.
- Visualización de comunicados.
- Consulta de información comunitaria.
- Notificaciones push mediante FCM.
- Consulta de postulaciones y subsidios.
- Comunicación con el backend mediante API REST.
- Interfaz desarrollada con Jetpack Compose.
- Arquitectura MVVM.
