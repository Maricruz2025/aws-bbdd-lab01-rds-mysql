# Guía paso a paso — Laboratorio RDS MySQL (Lab1)

## Tarea 1 — Crear Security Group para la DB
1. Consola AWS → VPC → Security Groups → Create security group.  
2. Nombre: `DB-Security-Group`  
3. Añadir regla MySQL (3306) con origen `Web Security Group`.  

## Tarea 2 — Crear DB Subnet Group
1. Consola AWS → RDS → Subnet groups → Create.  
2. Nombre: `DB Subnet Group`.  
3. Añadir subredes privadas en dos AZ.

## Tarea 3 — Crear instancia RDS (MySQL Multi-AZ)
1. RDS → Databases → Create.  
2. Engine: MySQL.  
3. Template: Dev/Test.  
4. Multi-AZ.  
5. DB identifier: `lab-db`.  
6. Usuario: `main`.  
7. DB inicial: `lab`.  

## Tarea 4 — Conectar la aplicación web
1. Ingresar a la IP del webserver.  
2. Navegar al enlace RDS.  
3. Insertar endpoint, usuario, password.  
4. Validar CRUD.

