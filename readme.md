# PRACTICA_01_FMR
Práctica 1 
# Práctica 01: Manejo de Git

## Descripción del Proyecto

Este repositorio contiene la práctica de manejo de Git para la clase de Gestión de Integración de Código.  
El proyecto consiste en crear una pequeña página web y gestionar sus cambios mediante el uso de ramas, merges, resolución de conflictos y un archivo `.gitignore` para ignorar la carpeta de logs.

## Estructura del Repositorio

- **index.html**: Página principal que incluye la estructura básica, el navbar y, en versiones posteriores, la inclusión del script.
- **page_a.html**: Página A, que en una de las ramas contiene una tabla 2x3.
- **page_b.html**: Página B, con contenido base y, en una rama, una tabla 2x3.
- **styles/style.css**: Hoja de estilos con cambios en los colores de headers y párrafos según las ramas (inicialmente, headers en rojo, luego en amarillo en `feature_2` y finalmente en verde en `main`).
- **scripts/script.js**: Archivo JavaScript que inicialmente realiza una suma (posteriormente corregida a resta en la rama `fix_1`).
- **.gitignore**: Archivo que ignora la carpeta `logs`.
- **logs/**: Carpeta local que contiene archivos de log (no se versionan).
- **readme.md**: Este documento.

## Integrantes

- **Miembro 1**: David Fregoso Luna  
- **Miembro 2**: Jose Manuel Montero Ruiz  
- **Miembro 3**: Bryan Romo González

## Ramas y Funcionalidades

- **main**: Rama principal que contiene la carga inicial y los cambios finales.
- **feature_1**: Rama en la que se agregó el navbar a `index.html` y se incorporó la tabla en `page_a.html`.
- **feature_2**: Rama en la que se modificaron los estilos en `styles/style.css` (cambio de color a amarillo) y se añadió una tabla en `page_b.html` y una imagen en `index.html`.
- **fix_1**: Rama creada para corregir errores (cambio de la suma a resta en `scripts/script.js`) y revertir el commit erróneo de eliminación del navbar.

## Comandos Clave Utilizados

```bash
# Clonar el repositorio
git clone https://github.com/DavidFregoso/PRACTICA_01_FMR.git

# Navegar al directorio del proyecto
cd "C:\Users\david\OneDrive - ITESO\8 OCTAVO SEMESTRE\GESTION DE INTEGRACION DE CODIGO\PRACTICA_01_FMR"

# Agregar archivos y hacer commit en main (carga inicial)
git add .
git commit -m "Carga inicial de archivos y anexos completados"

# Crear y trabajar en la rama feature_1 (agregar navbar y tabla en page_a.html)
git checkout -b feature_1
# (Editar index.html para incluir el navbar)
git add index.html
git commit -m "Agregar navbar en index.html en feature_1"
git push origin feature_1

# Crear y trabajar en la rama feature_2 (modificar estilos y agregar tabla en page_b.html)
git checkout -b feature_2
# (Editar styles/style.css para cambiar a amarillo y agregar estilos de tabla)
git add styles/style.css
git commit -m "Modificar estilos en feature_2"
# (Editar page_b.html para agregar la tabla y index.html para la imagen)
git add page_b.html index.html
git commit -m "Agregar tabla en page_b.html y imagen en index.html en feature_2"
git push origin feature_2

# Volver a main y fusionar cambios
git checkout main
git merge feature_1
git merge feature_2
git push origin main

# Crear la rama fix_1 para correcciones
git checkout -b fix_1
# (Editar scripts/script.js para cambiar la suma por una resta)
git add scripts/script.js
git commit -m "Cambiar suma a resta en script.js en fix_1"
git push origin fix_1

# Fusionar fix_1 en main
git checkout main
git merge fix_1
git push origin main

# Resolver conflictos y usar revert (si fue necesario, por ejemplo, para restaurar el navbar)
git checkout feature_1
git revert <HASH_DEL_COMMIT_ERRÓNEO>
git push origin feature_1
git checkout main
git merge feature_1
git push origin main
