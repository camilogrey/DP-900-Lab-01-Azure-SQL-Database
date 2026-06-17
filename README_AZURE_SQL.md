Reporte de Laboratorio: Explore Azure SQL Database
Este repositorio contiene las evidencias y el desarrollo del laboratorio práctico 
"Explore Azure SQL Database". 
---
El objetivo principal fue aprovisionar una base de datos relacional en la nube de Microsoft Azure, estructurar tablas mediante lenguaje SQL, poblar el sistema con datos de un concesionario ficticio, realizar consultas avanzadas y limpiar los recursos para evitar costes.

1. Aprovisionamiento de Azure SQL Database
Descripción: Se creó un servidor de bases de datos SQL y una base de datos vacía llamada `Dealership` dentro del grupo de recursos `RG1` utilizando una suscripción de Azure for Students en la región Spain Central.
Configuración clave: Se habilitó el acceso mediante autenticación SQL (usuario/contraseña) y se configuraron las reglas de firewall (Endpoint público) permitiendo que los servicios de Azure y la IP del cliente actual pudieran conectarse al editor de consultas de forma segura.

![Grupo de Recursos Creado en Azure](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20181059.png)

![Detalles de la Base de Datos Dealership](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20184602.png) 

![](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20184745.png)

![](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20185723.png)

---
2. Creación de las Tablas en la Base de Datos
Descripción: Mediante el Query editor (preview) de Azure, se ejecutó una sentencia DDL (`CREATE TABLE`) para definir el esquema relacional del concesionario.
Estructura:
Tabla `Manufacturer`: Almacena marcas de autos con una clave primaria (`ManufacturerID`).
Tabla `Vehicle`: Almacena los vehículos vinculados a su fabricante mediante una clave foránea (`FOREIGN KEY`), garantizando la integridad referencial.
![Creación de Tablas Manufacturer y Vehicle](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20190107.png#:~:text=16%20190008.png-,Captura%20de%20pantalla%202026%2D06%2D16%20190107.png,-Captura%20de%20pantalla)
---
3. Inserción de Datos de Prueba (Data Insertion)
Descripción: Se procedió a poblar las tablas vacías utilizando comandos `INSERT INTO`. Se registraron 4 fabricantes (Toyota, Ford, Volkswagen, Hyundai) y 8 vehículos con sus respectivos atributos (Modelo, Año, Tipo de Carrocería y Precio de Lista).
![Inserción de Datos en las Tablas](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/d3026314fdb392cde764bd1d4578f71b688408f7/Captura%20de%20pantalla%202026-06-16%20190132.png)
---

4. Consultas y Manipulación de Datos (SQL Queries)
A continuación, se presentan las distintas consultas ejecutadas para interrogar a la base de datos:

A. Consulta General de la Tabla Vehículos
Comando: `SELECT * FROM Vehicle;`
Objetivo: Verificar la correcta inserción de los 8 registros de vehículos con todas sus columnas disponibles.
![Consulta General de Vehículos](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/d3026314fdb392cde764bd1d4578f71b688408f7/Captura%20de%20pantalla%202026-06-16%20190221.png)

B. Proyección de Columnas Específicas
Comando: `SELECT ModelName, BodyType, ListPrice FROM Vehicle;`
Objetivo: Filtrar únicamente las columnas legibles y de interés del inventario (Modelo, Tipo y Precio).
![Proyección de Columnas Específicas](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/d3026314fdb392cde764bd1d4578f71b688408f7/Captura%20de%20pantalla%202026-06-16%20190252.png)

C. Filtrado y Ordenamiento con Cláusula WHERE y ORDER BY
Comando: Se aplicó un filtro para obtener vehículos cuyo precio es inferior a $30,000, ordenados de menor a mayor coste.
Resultado destacado: Se obtuvieron 4 registros que cumplen la condición (Elantra, Corolla, Golf, Tucson).

![Filtrado de Vehículos Económicos](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/d3026314fdb392cde764bd1d4578f71b688408f7/Captura%20de%20pantalla%202026-06-16%20190311.png)

D. Combinación de Tablas mediante INNER JOIN
Comando: Unió las tablas `Vehicle` y `Manufacturer` usando la columna común `ManufacturerID`.
Objetivo: Mostrar los datos del coche junto con el nombre del fabricante y su país de origen en una sola vista unificada, ordenados alfabéticamente por la marca.

![Consulta combinada con INNER JOIN](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20190328.png)
---
5. Limpieza de Recursos (Clean up)
Descripción: Para evitar costes imprevistos en la suscripción de Azure, se procedió a eliminar por completo el grupo de recursos `RG1`. Esta acción destruye automáticamente el servidor SQL, la base de datos `Dealership` y sus configuraciones asociadas en un solo paso interactivo de confirmación.

![](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20191330.png)

![](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20191337.png)

![Eliminación del Grupo de Recursos](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/main/Captura%20de%20pantalla%202026-06-16%20191444.png)
