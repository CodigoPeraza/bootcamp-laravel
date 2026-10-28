<div align="center">

# Bootcamp Laravel — Chirper

**Aplicación base de Laravel 10 con autenticación completa, perfil de usuario y frontend moderno con Tailwind y Vite.**

![Laravel](https://img.shields.io/badge/Laravel_10-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP_8.1+-777BB4?style=for-the-badge&logo=php&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

</div>

## Descripción

Repositorio de práctica del bootcamp de Laravel. El proyecto Laravel real se encuentra en la carpeta [`chirper/`](chirper/) y parte del scaffold de **Laravel Breeze**, que proporciona autenticación, verificación de correo, recuperación de contraseña y gestión de perfil.

El objetivo es documentar el proceso de aprendizaje del framework y dejar una base sólida sobre la que construir funcionalidades adicionales, como publicaciones de tipo *chirp*.

> Este repositorio contiene la base de autenticación y perfil creada con Breeze. La funcionalidad de publicaciones todavía no está implementada.

## Funcionalidades incluidas

- Registro de usuarios.
- Inicio y cierre de sesión.
- Verificación de correo electrónico.
- Recuperación y restablecimiento de contraseña.
- Confirmación de contraseña para acciones sensibles.
- Edición de perfil (nombre y correo).
- Actualización de contraseña.
- Eliminación de cuenta con confirmación.
- Dashboard protegido por autenticación.
- Vistas con Blade, Tailwind CSS y Alpine.js.
- Compilación de assets con Vite.
- Pruebas de autenticación y perfil con PHPUnit.

## Stack técnico

| Área | Tecnología |
| --- | --- |
| Framework | Laravel 10 |
| Lenguaje | PHP 8.1+ |
| Autenticación | Laravel Breeze + Sanctum |
| Plantillas | Blade |
| Estilos | Tailwind CSS |
| Interactividad | Alpine.js |
| Bundler | Vite |
| Base de datos | MySQL / MariaDB (o SQLite) |
| Pruebas | PHPUnit 10 |

## Estructura

```text
bootcamp-laravel/
├── chirper/                 # Proyecto Laravel
│   ├── app/
│   │   ├── Http/Controllers/Auth/   # Controladores de autenticación
│   │   ├── Http/Controllers/        # Perfil y controladores base
│   │   ├── Http/Requests/           # Validación de formularios
│   │   └── Models/User.php
│   ├── database/migrations/         # Tablas de usuarios y tokens
│   ├── resources/views/             # Vistas Blade y componentes
│   ├── routes/web.php               # Rutas principales
│   ├── routes/auth.php              # Rutas de autenticación
│   └── tests/Feature/               # Pruebas de autenticación y perfil
└── README.md
```

## Requisitos

- PHP 8.1 o superior con las extensiones habituales de Laravel.
- Composer.
- Node.js y npm.
- MySQL/MariaDB o SQLite.

## Instalación

```bash
cd chirper
composer install
cp .env.example .env
php artisan key:generate
```

### Configurar MySQL

Crea la base de datos:

```sql
CREATE DATABASE laravel;
```

Ajusta las credenciales en `chirper/.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```

### Alternativa con SQLite

```bash
touch database/database.sqlite
```

En `chirper/.env`:

```env
DB_CONNECTION=sqlite
```

Después ejecuta las migraciones:

```bash
php artisan migrate
```

## Ejecutar el proyecto

```bash
cd chirper
npm install
npm run dev
```

En otra terminal:

```bash
php artisan serve
```

La aplicación estará disponible en `http://127.0.0.1:8000`.

Para compilar los assets de producción:

```bash
npm run build
```

## Rutas principales

| Ruta | Descripción |
| --- | --- |
| `/` | Página de bienvenida |
| `/register` | Registro de usuario |
| `/login` | Inicio de sesión |
| `/dashboard` | Panel protegido |
| `/profile` | Edición y eliminación de perfil |
| `/forgot-password` | Recuperación de contraseña |

## Pruebas

```bash
cd chirper
php artisan test
```

La suite cubre inicio y cierre de sesión, registro, verificación de correo, recuperación de contraseña, confirmación de contraseña y actualización de perfil.

## Decisiones técnicas destacadas

- **Laravel Breeze** como punto de partida para tener un flujo de autenticación completo y mantenible.
- **Blade + componentes** para reutilizar layouts, botones, modales y campos de formulario.
- **Form Requests** para centralizar la validación de login y actualización de perfil.
- **Tailwind CSS + Alpine.js** para una interfaz moderna sin introducir un framework SPA.
- **Vite** para un ciclo de desarrollo rápido y builds optimizados.
- **Pruebas funcionales con PHPUnit** que validan los flujos críticos de autenticación.

## Siguientes pasos

- Implementar el modelo y CRUD de publicaciones (*chirps*).
- Añadir relaciones entre usuarios y publicaciones.
- Incorporar políticas de autorización.
- Agregar pruebas para las nuevas funcionalidades.
- Documentar el despliegue en un entorno real.

## Autor

**Francisco Javier Peraza** · [GitHub](https://github.com/CodigoPeraza) · [contacto.peraza@gmail.com](mailto:contacto.peraza@gmail.com)
