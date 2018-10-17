---
title: 'Pruebas fáciles'
description: ""
---

## Primer Ejercicio Basico

```yaml
type: NormalExercise
key: c909bf2ad2
lang: r
xp: 100
skills: 1
```

# Hacemos la primera suma

`@instructions`
Suma 3 + 5

`@hint`
No es tan complicado, escribe 3 + 5.

`@pre_exercise_code`
```{r}
# Cargando una libreria
library(MASS)
```

`@sample_code`
```{r}
#Primera suma, suma 3 + 5
```

`@solution`
```{r}
#Primera suma, suma 3 + 5
3 + 5
```

`@sct`
```{r}
# Mensaje de acierto en el ejercicio.
success_msg("Correcto.")
```

---

## Ejercicio con matrices

```yaml
type: NormalExercise
key: ea83e14b1a
xp: 100
```

#Ejercicio con matrices

`@instructions`
Crear uma matriz m, de dimensiones (3x4) y de valores del 1 al 12, ordenados por columnas
Vector de 1:12 creado ya en entorno.

`@hint`
Comando para crear la matriz --> matrix
Incluir en el comando matrix, los argumentos byrow y ncol

`@pre_exercise_code`
```{r}
vector_doce <- 1:12
```

`@sample_code`
```{r}
#Aqui tienes el vector de valores
vector_doce

#Crea la matriz
m <- 

#Muestra la matriz por pantalla

```

`@solution`
```{r}
#Aqui tienes el vector de valores
vector_doce

#Crea la matriz
m <- matrix(vector_doce, byrow = FALSE, ncol = 4)

#Muestra la matriz por pantalla
m
```

`@sct`
```{r}
success_msg("Equilicuá.")
```

---

## Insert exercise title here

```yaml
type: NormalExercise
key: 181e4525c6
xp: 100
```

Hola

`@instructions`
Hola

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
datos <-
```

`@solution`
```{r}
datos <- read.table("datasets/calcio.txt")
```

`@sct`
```{r}
datos
```
