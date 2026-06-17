# Reporte de Laboratorio: Configuración de Azure Database for MySQL

Este repositorio documenta el desarrollo práctico del laboratorio **"Azure Database for MySQL"**. El objetivo principal consistió en aprovisionar y configurar un servidor de base de datos relacional basado en el motor MySQL utilizando el modelo de despliegue de Servidor Flexible dentro de la plataforma de nube Microsoft Azure.

---

## 1. Selección del Tipo de Recurso (Servidor Flexible)
* **Descripción:** Tras ingresar al Portal de Azure y buscar el servicio correspondiente, se accedió a la interfaz de selección de arquitectura de despliegue para el motor de base de datos.
* **Acción:** Se seleccionó la opción de **Servidor Flexible (Flexible server)** mediante el asistente de creación avanzada, ideal para cargas de trabajo que requieren control de ventanas de mantenimiento y optimización de costes.

![Selección de Servidor Flexible](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/509bda6b30ed8cbfb80c88207ed0929d5573b734/Captura%20de%20pantalla%202026-06-17%20171533.png)

---

## 2. Configuración de Parámetros Esenciales del Servidor
* **Descripción:** Configuración detallada de la infraestructura, cómputo y credenciales administrativas del sistema.
* **Detalles técnicos:**
  * **Suscripción:** Azure for Students.
  * **Grupo de recursos:** `RG1`.
  * **Nombre del servidor:** `rg1server`.
  * **Región:** Spain Central.
  * **Versión de MySQL:** 8.4.
  * **Cómputo + Almacenamiento:** Configuración Burstable (B1ms, 1 vCore, 2 GiB RAM, IOPS auto-escalables).
  * **Conectividad:** Acceso público con reglas de firewall restrictivas.

![Revisión de Parámetros de Configuración](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/509bda6b30ed8cbfb80c88207ed0929d5573b734/Captura%20de%20pantalla%202026-06-17%20172557.png)

---

## 3. Implementación y Despliegue del Recurso
* **Descripción:** Validación e inicio del proceso automatizado de aprovisionamiento en los centros de datos de Azure.
* **Resultado:** La plataforma confirmó de manera exitosa la finalización del despliegue (*Your deployment is complete*), detallando el tiempo de inicio, la suscripción asociada y el identificador de correlación.

![Despliegue Completado Exitosamente](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/509bda6b30ed8cbfb80c88207ed0929d5573b734/Captura%20de%20pantalla%202026-06-17%20173107.png)

---

## 4. Exploración y Panel de Administración del Servidor MySQL
* **Descripción:** Acceso directo al recurso recién creado para comprobar su estado de operación activo y sus puntos de conexión.
* **Indicadores validados:**
  * **Estado:** Ready (Listo).
  * **Endpoint:** `rg1server.mysql.database.azure.com`
  * **Login del administrador:** `camilo`
  * **Capa de seguridad:** Conexiones SSL/TLS forzadas bajo la versión 1.2.


---

## 5. Destrucción de Recursos (Limpieza)
* **Descripción:** Como buena práctica en la administración de entornos cloud y para evitar el consumo innecesario de créditos dentro de la suscripción, se procedió con la eliminación completa del grupo de recursos `RG1`.
* **Impacto:** Esta acción remueve de forma definitiva el Servidor Flexible MySQL y todos los elementos dependientes asociados.

![Eliminación del Grupo de Recursos](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/1336144850ebe5cdc354ed398df3fa8e6e277978/Captura%20de%20pantalla%202026-06-17%20174207.png)
