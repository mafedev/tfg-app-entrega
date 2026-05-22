# Memora

## Descripción general

Memora es una aplicación móvil de apoyo y seguimiento para personas diagnosticadas con Alzheimer u otras enfermedades neurodegenerativas. Su objetivo principal es facilitar la organización de la vida diaria del paciente mediante recordatorios personalizados, así como ayudar a los cuidadores en la gestión y supervisión de rutinas, medicación, citas médicas, alergias y prescripciones.

La aplicación está pensada para mejorar la calidad de vida del paciente y reducir la carga del cuidador, permitiendo un seguimiento estructurado y centralizado de toda la información relevante.

## Arquitectura del sistema

El proyecto está dividido en tres partes principales:

### Frontend (Flutter)

Aplicación móvil desarrollada en Flutter, encargada de la interfaz de usuario y la experiencia del paciente y cuidador.

- Gestión de autenticación  
- Visualización de rutinas, medicación y citas  
- Sistema de notificaciones  
- Lectura por voz (TTS)  
- Interfaz adaptada para personas mayores  
- Rol paciente / cuidador  
- Seguimiento de actividades  

### Backend (Spring Boot)

API REST desarrollada en Spring Boot, encargada de toda la lógica de negocio y comunicación con la base de datos.

- Autenticación mediante JWT  
- Gestión de usuarios (paciente y cuidador)  
- Gestión de rutinas, medicación, citas y alergias  
- Relación paciente–cuidador  
- Control de permisos y roles  
- Servicios REST para la aplicación móvil  

### Base de datos (PostgreSQL)

Base de datos relacional utilizada para el almacenamiento persistente de toda la información del sistema.

- Usuarios y relaciones  
- Pacientes y cuidadores  
- Rutinas diarias  
- Medicación y prescripciones  
- Citas médicas  
- Alergias y registros médicos  

## Funcionamiento general

El sistema funciona bajo una arquitectura cliente-servidor:

1. El cuidador registra y gestiona la información del paciente desde la aplicación.  
2. El backend (Spring Boot) procesa la lógica y almacena los datos en PostgreSQL.  
3. El paciente recibe recordatorios y puede visualizar su rutina diaria desde la app Flutter.  
4. Las notificaciones ayudan al paciente a seguir su medicación y actividades programadas.  
5. Todo el sistema está sincronizado mediante una API REST.  

## Roles del sistema

### Paciente

- Visualiza su rutina diaria  
- Recibe recordatorios de medicación y citas  
- Consulta su información personal  
- Puede utilizar la app en modo asistido sin cuenta  

### Cuidador

- Gestiona la información del paciente  
- Crea y modifica rutinas  
- Añade medicación, citas y alergias  
- Supervisa el estado del paciente  

## Tecnologías utilizadas

### Frontend

- Flutter  
- Dart  
- flutter_local_notifications  
- flutter_tts  
- table_calendar  
- shared_preferences  

### Backend

- Java 17  
- Spring Boot 3  
- Spring Security + JWT  
- Spring Data JPA  
- Hibernate  
- Maven  

### Base de datos

- PostgreSQL  

## Instalación y ejecución

### Backend

```bash
git clone <repo-backend>
cd backend
./mvnw spring-boot:run
```

### Frontend
```bash
git clone <repo-frontend>
cd frontend
flutter pub get
flutter run
```

### Configuración

El frontend requiere un archivo .env en la raíz del proyecto:

```bash
API_BASE_URL=http://10.0.2.2:8080/api
```

### Objetivo del proyecto

El objetivo de Memora es proporcionar una herramienta tecnológica accesible y sencilla que ayude a personas con Alzheimer a mantener su rutina diaria, al mismo tiempo que facilita el trabajo de los cuidadores mediante una gestión centralizada y organizada.

### Nota final

Este proyecto no pretende sustituir el cuidado humano, sino servir como herramienta de apoyo para mejorar la organización, la seguridad y la calidad de vida del paciente.