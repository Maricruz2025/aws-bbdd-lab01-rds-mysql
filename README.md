# Lab1 - Crear servidor de base de datos (Amazon RDS MySQL)

**Autor:** Maricruz Ivanka  
**Repositorio:** aws-bbdd-lab01-rds-mysql  
**Fecha:** (agrega la fecha de realización)

---

## Descripción
Laboratorio práctico donde se implementa una instancia de base de datos MySQL mediante Amazon RDS en despliegue **Multi-AZ**, se configura la seguridad y las subredes, y se conecta una aplicación web cliente para probar operaciones CRUD. Este repositorio documenta los pasos realizados con capturas de pantalla propias, scripts SQL y notas técnicas.

---

## Estructura del repositorio
- `capturas/` — capturas de pantalla propias de la consola y la app.
- `docs/` — guía paso a paso, buenas prácticas y checklist.
- `sql/` — scripts SQL utilizados durante el laboratorio.
- `config/` — plantillas de configuración (variables de entorno).
- `README.md` — este archivo.

---

## Objetivos
1. Lanzar una instancia RDS MySQL con alta disponibilidad (Multi-AZ).  
2. Configurar reglas de seguridad para permitir el acceso del servidor web al puerto MySQL (3306).  
3. Crear un grupo de subredes para RDS con al menos dos AZs.  
4. Conectar la aplicación web al endpoint de RDS y validar operaciones CRUD.

---

## Resumen de tareas y evidencias

### Tarea 1 — Security Group (DB)
- Acción: Creé `DB-Security-Group` en la VPC y permití tráfico MySQL (3306) desde `WebServer-SG`.
- Evidencia: `capturas/task1-security-group.png`

### Tarea 2 — DB Subnet Group
- Acción: Creé `DB Subnet Group` y añadí las subredes privadas `10.0.1.0/24` y `10.0.3.0/24` en distintas AZs.
- Evidencia: `capturas/task2-subnet-group.png`

### Tarea 3 — Instancia RDS Multi-AZ
- Acción: Creé RDS MySQL `lab-db` (db.t3.medium), usuario `main`, base inicial `lab`.
- Evidencia: `capturas/task3-rds-creation.png`, `capturas/task3-endpoint.png`

### Tarea 4 — Conectar app web a RDS
- Acción: Accedí a la aplicación en el WebServer, ingresé el endpoint, usuario y contraseña y verifiqué el CRUD.
- Evidencia: `capturas/task4-webapp-connected.png`

---

## Archivos importantes
- `sql/schema.sql` — esquema de ejemplo usado en la aplicación.
- `config/app_config.env.template` — plantilla para las variables de configuración (NO subir secretos).
- `docs/pasos.md` — paso a paso detallado del laboratorio.

---

## Buenas prácticas y notas
- Nunca subir contraseñas o claves privadas al repositorio.  
- En las capturas, enmascara/edita cualquier endpoint o contraseña antes de subirlas.  
- Proceso documentado para replicabilidad.

---

## Próximos pasos
- Agregar un diagrama propio de arquitectura.
- Agregar documentación de conexión desde mysql client.
- Explorar automatización con Terraform o CloudFormation.

