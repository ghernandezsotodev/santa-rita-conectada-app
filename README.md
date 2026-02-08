# Santa Rita Conectada – Aplicación Android

Aplicación móvil desarrollada en Android que consume la API REST del sistema Santa Rita Conectada. Permite a los usuarios visualizar comunicados, postular a subsidios y recibir notificaciones push en tiempo real.

## Stack Tecnológico

- Kotlin
- Android SDK
- Arquitectura MVVM
- Retrofit (consumo de API REST)
- Firebase Cloud Messaging (FCM)
- Jetpack Compose

## Funcionalidades

- Autenticación de usuarios
- Visualización de comunicados
- Recepción de notificaciones push
- Postulación a subsidios
- Interfaz adaptada a dispositivos móviles

## Arquitectura

La aplicación sigue el patrón MVVM para separar la lógica de negocio, la gestión de datos y la interfaz de usuario.  
Se comunica con el backend Laravel mediante peticiones HTTP a una API REST.

## Configuración

1. Clonar el repositorio
2. Abrir el proyecto en Android Studio
3. Configurar Firebase (archivo `google-services.json`)
4. Ejecutar la aplicación en emulador o dispositivo físico

## Backend relacionado

Este proyecto funciona en conjunto con el repositorio backend:
👉 https://github.com/ghernandezsotodev/santa-rita-conectada

## Autor

Gonzalo Hernández Soto  
Proyecto de Tesis – Ingeniería en Informática Empresarial  
Año 2025
