1. Estructura del proyecto

La estructura es así:

extra-addons/
 └── dummy_module/
      ├── __init__.py
      ├── __manifest__.py
      └── .gitkeep
Dockerfile
README.md

Rellenas el manifest y dockerfile

2. Configurar el repositorio

Entra a  https://render.com
Crea una cuenta (puedes usar GitHub para vincular tu repo).
Sube tu proyecto a GitHub o GitLab.
Se puede tambien hacer desde un respositorio ajeno mediante el enlace de Github

3. Desplegar en Render

Haz clic en "New +" → "Web Service"

Configura:
Name: lo que quieras.
Region: la más cercana a ti.
Branch: por ejemplo main.
Environment: Docker.
Intance Type: Starter o Free (si quieres probar).

4. Crear base de datos

 En el panel principal (Dashboard), haz clic en “New +”Selecciona “PostgreSQL”
 Espera a que Render cree la base

Tardará unos segundos.

Cuando termine, verás una página con detalles como:
Internal Database URL
External Database URL
Host
User
Password
Database name
Port (5432)
Guarda las credenciales

Render te mostrará algo parecido a esto:

Internal Database URL:
postgres://odoo_user:12345password@dpg-abcdefg12345-db.internal:5432/odoo_db

Importante: Copia y guarda esta información.
La necesitarás para conectar tu contenedor (por ejemplo, tu Dockerfile o tus variables de entorno).

5. Configurar base de datos

En tu servicio web (tu contenedor de Odoo, por ejemplo), ve a la pestaña Environment y agrega estas variables:

Variable	Valor
DB_HOST	dpg-abcdefg12345-db.internal
DB_PORT	5432
DB_USER	odoo_user
DB_PASSWORD	12345password
DB_NAME	odoo_db

6. Final

   Espera un rato sobre 5 minutos mas o menos y lo tendras, accede a la URL y lo tendras
