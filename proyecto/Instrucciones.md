# Proyecto de fin de módulo

El proyecto final se realizará en **equipos de 3 personas**. Las tres personas tendrán que crear repositorios: dos personas en local y una en remoto. El repositorio remoto se considerará como un repositorio colaborativo, en el que las 3 personas trabajarán.

## Primera parte

Se documenta mediante screenshots en un archivo de Google Doc (i.e. un archivo de Word de Google).

Cada persona tomará uno de los siguientes roles:

1. Administrador del repositorio: Creará el repositorio en GitHub, añade contenido y resuelve posibles conflictos. Primer persona del equipo ordenada alfabéticamente por apellido paterno.

2. Colaborador 1: Clona el repositorio, añade contenido y realiza una contribución. Segunda persona del equipo ordenada alfabéticamente por apellido paterno.

3. Colaborador 2: Modifica el contenido y resuelve posibles conflictos. Tercera persona del equipo ordenada alfabéticamente por apellido paterno.

Instrucciones:

1. Configuración inicial (administrador del repositorio)

En GitHub, el administrador del repositorio crea un repositorio privado llamado colaboracion-git-equipo-n, donde n es el número de su equipo. Por ejemplo, si mi equipo es el 5, mi repositorio privado se llamará "colaboracion-git-equipo-5"

Agrega un archivo README.md con una breve descripción del proyecto.

Agrega a los otros dos colaboradores y al usuario EduardoSelimMM con permisos de escritura.

Comparte la URL del repositorio con los colaboradores.

Sube al repositorio el archivo "datos_proyecto.csv"

Crea, desde GitHub, el archivo "proyecto_final.Rmd" con el siguiente contenido

```
---
title: "Proyecto final módulo 1"
author: "Equipo - n"
output: html_document
---

# Integrantes:

+ Integrante 1. Rol: Administrador
+ Integrante 2. Rol: Colaborador
+ Integrante 3. Rol: Colaborador

```{r}
library(dplyr)
library(readr)
library(ggplot2)

mis_datos <- readr::read_csv("datos_proyecto.csv")
```

2. Clonar el repositorio (Colaboradores 1 y 2, Administrador)

Cada colaborador debe clonar el repositorio en su máquina:

```
git clone https://github.com/usuario/ccolaboracion-git-equipo-n.git
```

3. Colaborador 1: Desde su máquina crear chunks de código R en el archivo "proyecto_final.Rmd" (que obtuvo del Administrador) que calculen la media de x, la media de y, la desviación estándar de x, la desviación estándar de y, la correlación de Pearson entre x y y, PARA CADA SUBCONJUNTO, usando ciclos for. Hacer commit y push del código al repositorio del administrador y hacer un pull request.

4. Colaborador 2: Desde su máquina crear chunks de código R en el archivo "proyecto_final.Rmd" (que obtuvo del Administrador) que calculen la media de x, la media de y, la desviación estándar de x, la desviación estándar de y, la correlación de Pearson entre x y y, PARA CADA SUBCONJUNTO, usando verbos de la librería {dplyr}. Debe corregir la línea `author: "Equipo - n"` con el número correcto de equipo y agregar los nombres completos de los integrantes en la sección de `# Integrantes`. Hacer commit y push del código al repositorio del administrador y hacer un pull request.

5. Administrador del equipo. Desde su máquina crear chunks de código R en el archivo "proyecto_final.Rmd" (que obtuvo del Administrador) que trafiquen con ggplot las parejas de valores (x,y) DE CADA SUBCONJUNTO. Hacer commit y push del código al repositorio del administrador y revisar los pull requests de los colaboradores 1 y 2.

6. Obtener la versión actualizada del repositorio (Colaboradores 1 y 2, Administrador)

7. Cada colaborador debe hacer pull (jalar) el contenido actualizado del repositorio a su máquina. Los 3 archivos .Rmd de cada computadora deben ser idénticos entre sí.
