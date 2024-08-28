# Go REST API CRUD with PostgreSQL

Este proyecto implementa una API RESTful utilizando Go (Golang) con Gorilla Mux para el enrutamiento, GORM como ORM y PostgreSQL como base de datos. Proporciona operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para usuarios y tareas.

## Características

- Implementación de API RESTful
- Operaciones CRUD para usuarios y tareas
- Integración con base de datos PostgreSQL
- Gorilla Mux para enrutamiento eficiente
- GORM para mapeo objeto-relacional

## Requisitos previos

Antes de comenzar, asegúrate de tener instalado lo siguiente:
- Go (1.16+)
- PostgreSQL
- Git

## Instalación

1. Clona el repositorio:
   ```
   git clone https://github.com/faztweb/go-postgresql-restapi.git
   cd go-postgresql-restapi
   ```

2. Instala las dependencias:
   ```
   go mod tidy
   ```

3. Configura tu base de datos PostgreSQL y actualiza la cadena de conexión en el archivo de configuración correspondiente.

## Configuración

Crea un archivo `.env` en el directorio raíz con el siguiente contenido:

```
DB_HOST=localhost
DB_USER=tu_usuario
DB_PASSWORD=tu_contraseña
DB_NAME=nombre_de_tu_base_de_datos
DB_PORT=5432
```

Ajusta los valores según tu configuración de PostgreSQL.

## Ejecutar la aplicación

Para iniciar el servidor, ejecuta:

```
go run main.go
```

La API estará disponible en `http://localhost:4000` por defecto.

## Endpoints de la API

### Usuarios
- `GET /api/users`: Obtener todos los usuarios
- `GET /api/users/{id}`: Obtener un usuario específico
- `POST /api/users`: Crear un nuevo usuario
- `DELETE /api/users/{id}`: Eliminar un usuario

### Tareas
- `GET /api/tasks`: Obtener todas las tareas
- `GET /api/tasks/{id}`: Obtener una tarea específica
- `POST /api/tasks`: Crear una nueva tarea
- `DELETE /api/tasks/{id}`: Eliminar una tarea

## Ejemplos de uso

### Obtener todos los usuarios
```bash
curl http://localhost:4000/api/users
```

### Crear un nuevo usuario
```bash
curl -X POST http://localhost:4000/api/users \
     -H "Content-Type: application/json" \
     -d '{"FirstName": "John", "LastName": "Doe", "email": "john@gmail.com"}'
```

### Obtener todas las tareas
```bash
curl http://localhost:4000/api/tasks
```

### Crear una nueva tarea
```bash
curl -X POST http://localhost:4000/api/tasks \
     -H "Content-Type: application/json" \
     -d '{"title": "Nueva Tarea", "description": "Descripción de la nueva tarea", "user_id": 1}'
```

## Estructura del proyecto

```
go-postgresql-restapi/
├── db/
│   └── database.go
├── models/
│   ├── user.go
│   └── task.go
├── routes/
│   ├── users.go
│   └── tasks.go
├── main.go
├── go.mod
└── go.sum
```

