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
+ Integrante 2. Rol: Colaborador 1
+ Integrante 3. Rol: Colaborador 2

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
   
9. El colaborador 1 debe ejecutar el código actualizado y dar conclusiones sobre cada uno de los subconjuntos de datos

## Segunda parte

En construcción...

### Subsección 1: Prueba de Bechdel

La prueba de Bechdel es un método que se usa para evaluar la representación de las mujeres en películas, series u otras obras narrativas. Para aprobarla, la obra debe cumplir tres criterios: (1) tener al menos dos personajes femeninos con nombre, (2) que estos personajes conversen entre sí en algún momento, y (3) que su diálogo no gire en torno a un hombre (por ejemplo, relaciones románticas o familiares). Fue propuesta por Alison Bechdel, destacando la falta de desarrollo de personajes femeninos en muchas producciones, aunque no mide la calidad ni la igualdad de género de manera exhaustiva.

**Actividad 1:** Cargue en un objeto de R el contenido del archivo "prueba_bechdel.csv"

En dicho dataframe se tienen algunas columnas como:

budget_2013: Presupuesto en dólares ajustados a la inflación de 2013

domgross_2013: Recaudación nacional (EE.UU.) en dólares ajustados a la inflación de 2013

intgross_2013: Recaudación internacional total (es decir, mundial) en dólares a la inflación de 2013

En la columna `clean_test` encontrará los valores

ok = Pasa la prueba
dubious = Se duda si pasa la prueba
men = Las mujeres sólo hablan acerca de hombres
notalk = Las mujeres no se hablan entre sí
nowomen = menos de dos mujeres

**Actividad 2:** Use alguna de las funciones case_when o if_else de {dplyr} para cambiar los valores de la columna `clean_test`

ok -> pasa
dubious -> dudosamente
men -> discurso_hombres
no_talk -> silencio
nowomen -> sin_mujeres

**Actividad 3:** Use alguna de las funciones case_when o if_else de {dplyr} para cambiar los valores de la columna `binary`

FAIL -> no_pasa
PASS -> si_pasa

**Actividad 4:** Haga una gráfica con funciones de {ggplot2} que muestre la composición de observaciones que sí pasaron y no pasaron la prueba de Bechdel

**Actividad 5:** Haga una gráfica con funciones de {ggplot2} que muestre la composición de observaciones que sí pasaron y no pasaron la prueba de Bechdel, con respecto al año

**Actividad 6:** Haga una gráfica con funciones de {ggplot2} que muestre la composición de observaciones que pasaron, dudosamente, sólo hablaban de hombres, no hablaban entre sí y no hay mujeres.

**Actividad 7:** Haga una gráfica con funciones de {ggplot2} que muestre la composición de observaciones que pasaron, dudosamente, sólo hablaban de hombres, no hablaban entre sí y no hay mujeres, con respecto al año.

**Actividad 8:** Haga una gráfica con funciones de {ggplot2} que muestre la relación entre el presupuesto de la obra con la ganancia de la obra en función de si paso o no la prueba de Bechdel. ¿Puede hacer algún tipo de afirmación?

**Actividad 9:** Haga dos gráficas adicionales con funciones de {ggplot2} que considere interesantes.

### Subsección 2: ¿Aerolíneas seguras?

Se usará el conjunto de datos `airline_safety` de la librería {fivethirtyeight}

`datos <- fivethirtyeight::airline_safety`

Actividad 1: Con funciones de la librería {dplyr} para obtener el número total de incidentes, número total de accidentes fatales y el número total de muertes en el periodo de 1985 a 2014.

Actividad 2: Obtenga las 10 aerolíneas que han tenido el mayor número de incidentes. Haga una visualización que permita identificar a éstas. ¿Hay algún cambio en este top 10 antes y después del año 2000?

Actividad 3: Obtenga las 10 aerolíneas que han tenido el menor número de incidentes. Haga una visualización que permita identificar a éstas. ¿Hay algún cambio en este top 10 antes y después del año 2000?

Actividad 4: Obtenga las 10 aerolíneas que han tenido el mayor número de muertes. Haga una visualización que permita identificar a éstas. ¿Hay algún cambio en este top 10 antes y después del año 2000?

Actividad 5: Obtenga las 10 aerolíneas que han tenido el menor número de muertes. Haga una visualización que permita identificar a éstas. ¿Hay algún cambio en este top 10 antes y después del año 2000?

*Importante:* Sus visualizaciones deben tener formato suficientemente bueno para publicar en alguna revista.




