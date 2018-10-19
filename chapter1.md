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
#Los datos estan cargados aqui		
datos

#Imprime los primeros 10 datos

```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos

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
#Los datos estan cargados aqui		
datos

#Dibujar el gráfico
plot()
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos

#Dibujar el gráfico
plot(datos$Severity)
```

`@sct`
```{r}
success_msg("Correcto.")
```

---

## Primer filtro en R

```yaml
type: NormalExercise
key: 181e4525c6
xp: 100
```

#Aplicación de un filtro

Los datos corresponden a datos de reclamaciones del 2017 y 2018
Queremos calcular el número de reclamaciones de 2017

Vamos a quedarnos solo con las filas que queremos, y vamos a hacer una operacion sencilla sobre ellas (Contar nº de filas)
Para ello creamos un filtro:

filtro <- datos$Year == 17 
Que dará como resultado TRUE donde las filas cumplan la condicion y FALSE donde no

Creamos un dataset nuevo con los datos del 2017:
datos_2017 <- datos[filtro,]

Contamos el número de filas del nuevo dataset
nrow(datos_2017)

`@instructions`
1º Crear filtro
2ª Generar nuevo dataset a partir del antiguo
3º Contar filas

`@hint`


`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Los datos estan cargados aqui		
datos 

#Creamos el filtro
filtro <- 

#Generamos el dataset del 2017 a partir del anterior
datos_2017 <- datos

#Contamos filas
nrow(datos_2017)
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos 

#Creamos el filtro
filtro <- datos$Year == 17 

#Generamos el dataset del 2017 a partir del anterior
datos_2017 <- datos[filtro,]

#Contamos filas
nrow(datos_2017)
```

`@sct`
```{r}
success_msg("Bien!!")
```

---

## Tablas de Confusión en R

```yaml
type: NormalExercise
key: 2f70b37bae
xp: 100
```

#Crear tablas de confusión en R
##Motivación
Muchas veces, cuando queremos comparar dos variables que son factores, es decir, son variables discretas finitas, es muy útil el uso de tablas de confusión, además, son muy fáciles de usar.
##Ejemplo de uso
Queremos ver si para nuestros datos, hay una relación entre la prioridad que se le da a cada reclamacion, con la severidad de la misma

`@instructions`
El ejercicio es muy simple, simplemente hay que utilizar el comando table(variable1, variable2)
Las variables tienen que ser discretas.

`@hint`
table(datos$Priority, datos$Severity)

`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Los datos estan cargados aqui		
datos

#Imprimir tabla de confusion
table()
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos 

#Imprimir tabla de confusion
table(datos$Severity, datos$Priority)
```

`@sct`
```{r}
success_msg("Bien!!")
```

---

## Matriz de confusión y función apply

```yaml
type: NormalExercise
key: ddd7cba369
xp: 100
```

#Otra matriz de confusion
Esta vez vamos a ver si hay relación entre el estado de la reclamación y la Prioridad que se le ha dado

Además, utilizar comando apply y bucle for para calcular porcentaje de estatus de cada prioridad.

`@instructions`
Volver a ejecutar el comando table, con las variables que nos interesan

El bucle for tiene la misma estructura que en cualquier lenguaje de programacion
Lo que vamos a hacer es usar la funcion apply para sumar por filas la matriz de confusion y obtener el número total de consultas por cada prioridad.
apply(tabla_confusion, 1 , sum). El uno significa que la operacion que queremos hacer es por filas.
Nota, también se podría expandiendo la matriz replicandola, a una de dimension 4x5

Utilizamos el bucle para dividir y calcular el porcentaje.

Imprimimos matriz resultante

`@hint`


`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Los datos estan cargados aqui		
datos

#Imprimir tabla de confusion y la guardamos
tabla_confusion <- table()

#Uso de la funcion apply
vector_totales <- apply(tabla_confusion, 1 , sum)

#Bucler for
tabla_porcentajes <- matrix(1:20, ncol = 5)
for (i in 1: nrow(tabla_confusion)) {
  tabla_porcentajes[i,] <- tabla_confusion[i, ] / vector_totales[i]
}

#Imprimimos la tabla
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos

#Imprimir tabla de confusion y la guardamos
tabla_confusion <- table(datos$Priority, datos$Status)

#Uso de la funcion apply
vector_totales <- apply(tabla_confusion, 1 , sum)

#Bucler for
tabla_porcentajes <- matrix(1:20, ncol = 5)
for (i in 1: nrow(tabla_confusion)) {
  tabla_porcentajes[i,] <- tabla_confusion[i, ] / vector_totales[i]
}

#Imprimimos la tabla
tabla_porcentajes
```

`@sct`
```{r}
success_msg("Bien!!")
```

---

## Análisis de Correlaciones

```yaml
type: NormalExercise
key: 9102149933
xp: 100
```

#Análisis de Correlaciones
##Motivación
Vamos a comprobar si las variables numéricas tienen una dependencia lineal mediante el calculo de sus correlaciones

`@instructions`
Lo primero es crear un dataset solo con variables numéricas, para ello aplicaremos un filtro a las columnas.
Para ello utilizaremos la funcion "is.numeric", lo malo es que no le podemos pasar una fila entera, porque devuelve FALSE (es un vector, no un número) y hay que recorrer el vector con un bucle.
Una vez lo tengamos, utilizamos el comando cor(dataset_numerico), para obtener correlaciones de variables dos a dos
Por ultimo, se sacarán unas pequeñas conclusiones.

`@hint`


`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Los datos, como siempre, estan en la variable "datos"

#Creamos un filtro para seleccionar las variables que nos interesan
filtro_columnas <- c(1:ncol(datos))
for (i in 1 : ncol(datos)){
  filtro_columnas[i] <- is.numeric(datos[3, i]) 
}

#Aplicamos el filtro a el dataset
datos_numericos <- datos[, filtro_columnas]

#Ejecutamos el análisis de correlaciones
cor(datos_numericos)

#Se puede ver que la mayoria de las variables no guardan ninguna dependencia lineal entre ellas. Solo la del año con la del número del ticket (no significatica, porque el numero de asignacion del ticket es incremental,)
```

`@solution`
```{r}
#Los datos, como siempre, estan en la variable "datos"

#Creamos un filtro para seleccionar las variables que nos interesan
filtro_columnas <- c(1:ncol(datos))
for (i in 1 : ncol(datos)){
  filtro_columnas[i] <- is.numeric(datos[3, i]) 
}

#Aplicamos el filtro a el dataset
datos_numericos <- datos[, filtro_columnas]

#Ejecutamos el análisis de correlaciones
cor(datos_numericos)

#Se puede ver que la mayoria de las variables no guardan ninguna dependencia lineal entre ellas. Solo la del año con la del número del ticket (no significatica, porque el numero de asignacion del ticket es incremental,)
```

`@sct`
```{r}
success_msg("Bien!!")
```

---

## Prueba de tipo de ejercicio Test con consola

```yaml
type: MultipleChoiceExercise
key: b63a9931b6
xp: 50
```

Calcular el numero de respuestas inmediatas (Response.time.s = 0). Los datos, como siempre, estan en la variable "datos"

`@possible_answers`
1. 2498
2. [3043]
3. 4578
4. 1439

`@hint`
nrow(datos[(datos$Response.time..s. == 0), ])

`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sct`
```{r}
success_msg("Bien!!")
```

---

## Ejercicio Test normal

```yaml
type: PureMultipleChoiceExercise
key: 3d4706d93e
xp: 50
```

¿Cual de las siguientes lineas nos da un diagrama de sectores de la distribucion del status según la prioridad? (Ejercicio 5)

`@hint`
pie

`@possible_answers`
1. [pie(tabla_porcentajes[1,])]
2. plot(table_porcentajes[1, ], type = "sector")
3. sector(tabla_porcentajes[1,])

`@feedback`
success_msg("Bien!!")
fail_msg("Mal")
