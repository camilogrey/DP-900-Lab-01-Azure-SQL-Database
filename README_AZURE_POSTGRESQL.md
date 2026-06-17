# Reporte de Laboratorio: Configuración de Azure Database for PostgreSQL

Este repositorio documenta el desarrollo práctico del laboratorio **"Creación y uso de una base de datos en Azure Database for PostgreSQL"**. El objetivo principal fue aprovisionar y estructurar un servidor de base de datos relacional basado en el motor PostgreSQL utilizando el modelo de despliegue de Servidor Flexible dentro del entorno cloud de Microsoft Azure.

---

## 1. Búsqueda y Selección del Recurso
* **Descripción:** Tras acceder al Portal de Azure con credenciales administrativas, se ingresó al Marketplace para localizar el motor de datos.
* **Acción:** Se realizó la búsqueda del término `azure database for postgresql`, identificando la solución oficial publicada por Microsoft para el despliegue de instancias administradas.

![Búsqueda del Recurso en el Marketplace](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/431e20198bbcfc8ead53dc1452530152d5bfd190/Captura%20de%20pantalla%202026-06-17%20175237.png)

---

## 2. Configuración de Acceso y Reglas de Red (Networking)
* **Descripción:** Establecimiento de los parámetros de conectividad y seguridad perimetral para el servidor.
* **Detalles clave:**
  * Se habilitó el **Acceso público** (*Public access*).
  * Se configuraron reglas de firewall restrictivas mediante la opción **Agregar dirección IP del cliente actual** (*Add current client IP address*).
  * Esto asocia la IP pública activa (`213.0.69.114`) para habilitar la comunicación exclusiva hacia el puerto estándar `5432` desde la ubicación local.

![Configuración de Reglas de Firewall](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/431e20198bbcfc8ead53dc1452530152d5bfd190/Captura%20de%20pantalla%202026-06-17%20175525.png)

---

## 3. Revisión Final de Parámetros de Infraestructura
* **Descripción:** Validación integral de los costos, dimensiones de cómputo y credenciales del administrador asignadas previo a la fase de aprovisionamiento.
* **Especificaciones del sistema:**
  * **Suscripción:** Azure for Students.
  * **Grupo de recursos:** `RG1`.
  * **Nombre del servidor:** `rg1server`.
  * **Login administrativo:** `camilo`.
  * **Ubicación:** Spain Central.
  * **Cómputo y Almacenamiento:** Capa Burstable (B2s, 2 vCores, 4 GiB RAM, 32 GiB de almacenamiento, P4 IOPS).
  * **Versión del motor:** PostgreSQL 18.

![Revisión de Parámetros de Configuración](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/431e20198bbcfc8ead53dc1452530152d5bfd190/Captura%20de%20pantalla%202026-06-17%20175833.png)

---

## 4. Implementación Completada en la Nube
* **Descripción:** Ejecución y seguimiento del proceso de despliegue automatizado por parte de la plataforma de Azure.
* **Resultado:** El asistente arrojó la confirmación de éxito (*Your deployment is complete*), listando los metadatos de inicio del entorno y habilitando el acceso directo a la consola del recurso.

![Despliegue de Servidor Flexible Completado](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/431e20198bbcfc8ead53dc1452530152d5bfd190/Captura%20de%20pantalla%202026-06-17%20180505.png)

---

## 5. Panel de Control General del Recurso Activo
* **Descripción:** Inspección del estado operativo general y los puntos de conexión del servidor PostgreSQL.
* **Propiedades validadas:**
  * **Estado:** Ready (Listo).
  * **Endpoint:** `rg1server.postgres.database.azure.com`.
  * **Configuración activa:** Nivel Burstable optimizado para entornos de desarrollo y pruebas.

![Panel de Administración Essentials de PostgreSQL](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/431e20198bbcfc8ead53dc1452530152d5bfd190/Captura%20de%20pantalla%202026-06-17%20180524.png)

---

## 6. Limpieza de Entorno y Eliminación de Recursos
* **Descripción:** Ejecución de las tareas de desmontaje de infraestructura al finalizar el laboratorio para evitar consumos residuales de créditos.
* **Acción:** Se seleccionó el grupo de recursos `RG1` dentro del administrador de recursos para proceder con su eliminación completa, lo que destruye el servidor flexible `rg1server` de forma simultánea.

![Eliminación de Infraestructura y Grupo de Recursos](https://github.com/camilogrey/DP-900-Lab-01-Azure-SQL-Database/blob/431e20198bbcfc8ead53dc1452530152d5bfd190/Captura%20de%20pantalla%202026-06-17%20181052.png)
