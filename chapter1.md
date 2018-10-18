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

# Ver qué datos tenemos
Los os datos pertenecen al sistema de reclamaciones de UDo

Tenemos los datos cargados en la variable datos
Queremos ver por pantalla las primeras 10 líneas para ver que variables tenemos, primera toma de contacto con los datos

`@instructions`
Con "datos [1:10 ,]" imprimimos las primeras 10 columnas

`@hint`
datos [1:10 ,]

`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Imprime los primeros 10 datos

```

`@solution`
```{r}
#Imprime los primeros 10 datos
datos [1:10 ,]
```

`@sct`
```{r}
# Mensaje de acierto en el ejercicio.
success_msg("Correcto.")
```

---

## Primer Gráfico

```yaml
type: NormalExercise
key: ea83e14b1a
xp: 100
```

#¿Como están distribuidas las reclamaciones según su severidad?
Dibujar un histograma del nº de reclamaciones según su serveridad, usando el comando plot


`@instructions`
Podemos construir un histograma con la orden y argumento, el nombre de la column a que queremos utilizar
plot(datos$Severity)

`@hint`
plot(datos$Severity)

`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Dibujar el gráfico
plot()
```

`@solution`
```{r}
#Dibujar el gráfico
plot(datos$Severity)
```

`@sct`
```{r}
success_msg("Correcto.")
```

---

## Ejercicio de carga de datos

```yaml
type: NormalExercise
key: 181e4525c6
xp: 100
```

Imprimir datos importados a ver si Funciona

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}
datos <- read.table ("http://assets.datacamp.com/production/repositories/3807/datasets/712a58e1eb259483c37da46dffbff7ada9241bb3/calcio.txt", header = TRUE)
```

`@sample_code`
```{r}
#Los datos estan cargados aqui		
datos 

#Imprime 5 filas
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos 

#Imprime 5 filas
datos[1:5,]
```

`@sct`
```{r}
success_msg("Por fin !!")
```

---

## Tipo Test

```yaml
type: MultipleChoiceExercise
key: 40b3a65b04
xp: 50
```

Tipo Test

`@possible_answers`
1. Mala
2. [Buena]
3. Mala

`@hint`


`@pre_exercise_code`
```{r}

```

`@sct`
```{r}
success_msg("XD")
```
