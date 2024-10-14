# Examen Empleado - Anthony Freyret

Este proyecto es una aplicación de gestión de empleados que permite realizar las operaciones básicas de un CRUD (Crear, Leer, Actualizar y Eliminar) sobre empleados. Está desarrollado con **Spring Boot**, **Spring Data JPA**, **Thymeleaf**, y **MySQL** como base de datos.

## Características
- Listar empleados con todos sus atributos.
- Buscar empleados por DNI.
- Crear nuevos empleados.
- Editar los detalles de los empleados existentes.
- Eliminar empleados.
  
## Requisitos previos
Antes de ejecutar este proyecto, asegúrate de tener instalados los siguientes componentes:
- **Java 11** o superior.
- **Maven**.
- **MySQL** (base de datos).

## Configuración de base de datos
1. Crea una base de datos en MySQL llamada `empresa`.
2. Ejecuta el siguiente script SQL para crear las tablas necesarias:

sql
CREATE DATABASE IF NOT EXISTS empresa;

USE empresa;

-- Crear la tabla de área
CREATE TABLE tb_area (
    area_id INT AUTO_INCREMENT PRIMARY KEY,
    nombre_area VARCHAR(45) NOT NULL
);

-- Crear la tabla de empleado
CREATE TABLE tb_empleado (
    dni_empleado CHAR(8) PRIMARY KEY,
    nombre_empleado VARCHAR(45) NOT NULL,
    apellido_empleado VARCHAR(45) NOT NULL,
    fecha_nacimiento DATE NOT NULL,
    direccion VARCHAR(45),
    correo VARCHAR(45),
    area_id INT,
    FOREIGN KEY (area_id) REFERENCES tb_area(area_id)
);

-- Insertar datos de prueba
INSERT INTO tb_area (nombre_area) VALUES ('Recursos Humanos'), ('Ventas'), ('Tecnología');

INSERT INTO tb_empleado (dni_empleado, nombre_empleado, apellido_empleado, fecha_nacimiento, direccion, correo, area_id)
VALUES
('12345678', 'Juan', 'Pérez', '1985-05-20', 'Av. Siempre Viva 123', 'juan.perez@mail.com', 1),
('87654321', 'Ana', 'Martínez', '1990-11-12', 'Calle Falsa 456', 'ana.martinez@mail.com', 2);


spring.datasource.url=jdbc:mysql://localhost:3306/empresa?useSSL=false
spring.datasource.username=root1
spring.datasource.password=123456
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true


git clone https://github.com/tu-usuario/examen-empleado-anthonyfreyret2.git

### Explicación de las secciones:
- **Descripción del proyecto**: Una breve descripción de lo que hace la aplicación.
- **Requisitos previos**: Lista del software necesario para ejecutar el proyecto.
- **Configuración de la base de datos**: Instrucciones para configurar la base de datos MySQL.
- **Instrucciones de instalación y ejecución**: Guía sobre cómo clonar el proyecto, importarlo y ejecutarlo.
- **Uso**: Breve explicación de cómo usar la aplicación.
- **Tecnologías utilizadas**: Lista de las tecnologías usadas en el proyecto.
- **Contribuciones**: Detalles sobre cómo contribuir al proyecto.
- **Licencia**: Información sobre la licencia del proyecto.

Este archivo README proporciona toda la información que un usuario necesitaría para trabajar con tu proyecto. Puedes adaptarlo según sea necesario.

