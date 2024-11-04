
# Clúster de Hadoop con YARN y Hive

Este proyecto configura un clúster de Hadoop con YARN y Hive usando Docker. Incluye instrucciones para levantar los contenedores y realizar consultas SQL básicas en Hive.

## Prerrequisitos

- Docker
- Docker Compose

## Instrucciones

### 1. Clonar el Repositorio

Primero, clona el repositorio que contiene el archivo `docker-compose.yml` para los contenedores de Hadoop, YARN y Hive:

git clone https://github.com/PabloHerreraTajamar/Hadoop-hive
cd Hadoop-hive

### 2. Levantar los Contenedores
docker-compose up -d

### 3. Acceder al Contenedor de Hive
docker-compose exec hive-server bash

### 4. Iniciar Hive
hive

### 5. Crear una Tabla en Hive
CREATE TABLE Empleados (
    nombre VARCHAR(50),
    apellidos VARCHAR(50)
);

### 6. Insertar Datos en la Tabla
INSERT INTO Empleados (nombre, apellidos) VALUES ('Juan', 'Pérez');
INSERT INTO Empleados (nombre, apellidos) VALUES ('María', 'García');
INSERT INTO Empleados (nombre, apellidos) VALUES ('Carlos', 'López');

### 7. Consultas Básicas en Hive
SELECT * FROM Empleados WHERE apellidos = 'Pérez';
SELECT COUNT(*) AS TotalEmpleados FROM Empleados;
SELECT * FROM Empleados ORDER BY apellidos ASC;
