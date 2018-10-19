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
#datos

#Guarda los primeros 10 datos e imprimelos 
primeros_10 <- 
primeros_10
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos

#Guarda los primeros 10 datos e imprimelos 
primeros_10 <- datos[1:10 ,]
primeros_10
```

`@sct`
```{r}
# Mensaje de acierto en el ejercicio.
ex() %>% check_object("primeros_10") %>% check_equal("primeros_10")
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
#datos

#Dibujar el gráfico
mi_grafico <- plot()
mi_grafico
```

`@solution`
```{r}
#Los datos estan cargados aqui		
datos

#Guardar el gráfico en mi_grafico y dibujarlo
mi_grafico <- plot(datos$Severity)
mi_grafico
```

`@sct`
```{r}
ex() %>% check_object("mi_grafico") %>% check_equal("mi_grafico")
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
1. Crear filtro
2. Generar nuevo dataset a partir del antiguo
3. Contar filas

`@hint`


`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#Los datos estan cargados aqui		
#datos 

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
#datos 

#Creamos el filtro
filtro <- datos$Year == 17 

#Generamos el dataset del 2017 a partir del anterior
datos_2017 <- datos[filtro,]

#Contamos filas
nrow(datos_2017)
```

`@sct`
```{r}
ex() %>% check_object("filtro") %>% check_equal("filtro")
ex() %>% check_object("datos_2017") %>% check_equal("datos_2017")
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
#datos

#Guardar tabla de confusion en mi_tabla e imprimirla
mi_tabla <- table()
mi_tabla
```

`@solution`
```{r}
#Los datos estan cargados aqui		
#datos

#Guardar tabla de confusion en mi_tabla e imprimirla
mi_tabla <- table(datos$Severity, datos$Priority)
mi_tabla
```

`@sct`
```{r}
ex() %>% check_object("mi_tabla") %>% check_equal("mi_tabla")
success_msg("Bien!!")
```

---

## Distribucion de estado de reclamacion segun prioridad

```yaml
type: NormalExercise
key: ddd7cba369
xp: 100
```

#Otra matriz de confusion
Esta vez vamos a ver si hay relación entre el estado de la reclamación y la Prioridad que se le ha dado

Además, utilizar comando apply y bucle for para calcular porcentaje de estatus de cada prioridad.

`@instructions`
1. Volver a ejecutar el comando table, con las variables que nos interesan

2. El bucle for tiene la misma estructura que en cualquier lenguaje de programacion
Lo que vamos a hacer es usar la funcion apply para sumar por filas la matriz de confusion y obtener el número total de consultas por cada prioridad.
apply(tabla_confusion, 1 , sum). El uno significa que la operacion que queremos hacer es por filas.
Nota, también se podría expandiendo la matriz replicandola, a una de dimension 4x5

3. Utilizamos el bucle para dividir y calcular el porcentaje.

4. Imprimimos matriz resultante

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
#Los datos estan cargados aqui		
#datos

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
ex() %>% check_object("tabla_confusion") %>% check_equal("tabla_confusion")
ex() %>% check_object("vectores_totales") %>% check_equal("vectores_totales")
ex() %>% check_object("tabla_porcentajes") %>% check_equal("tabla_porcentajes")
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
1. Lo primero es crear un dataset solo con variables numéricas, para ello aplicaremos un filtro a las columnas.
Para ello utilizaremos la funcion "is.numeric", lo malo es que no le podemos pasar una fila entera, porque devuelve FALSE (es un vector, no un número) y hay que recorrer el vector con un bucle.

2. Una vez lo tengamos, utilizamos el comando cor(dataset_numerico), para obtener correlaciones de variables dos a dos

3. Por ultimo, se sacarán unas pequeñas conclusiones.

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
datos_numericos <- datos[, ]

#Ejecutamos el análisis de correlaciones, guardamos los resultados y los imprimimos
correlaciones <- cor()
correlaciones

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

#Ejecutamos el análisis de correlaciones, guardamos los resultados y los imprimimos
correlaciones <- cor(datos_numericos)
correlaciones

#Se puede ver que la mayoria de las variables no guardan ninguna dependencia lineal entre ellas. Solo la del año con la del número del ticket (no significatica, porque el numero de asignacion del ticket es incremental,)
```

`@sct`
```{r}
ex() %>% check_object("datos_numericos") %>% check_equal("datos_numericos")
ex() %>% check_object("correlaciones") %>% check_equal("correlaciones")
success_msg("Bien!!")
```

---

## Multiples Gráficos con LayOut

```yaml
type: NormalExercise
key: e497483a94
xp: 100
```

#Ejemplo de como dibujar varios gráficos usando la herramienta LayOut()

`@instructions`
1. Dividimos la pantalla de gráficos en las porciones que necesitemos (Este caso 4) usando layout(matrix(1:4, ncol = 2, byrow= TRUE))
2. Utilizamos bucle For para dibujar los gráficos según el orden en el que se asignan en layout

`@hint`


`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
#Los datos estan cargados aqui		
#datos

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

`@sample_code`
```{r}
#Los datos que necesitamos son los calculados en el ejercicio 5 y estan en "tabla_porcentajes"

#Creamos el layout, lo guardamos en milayout y lo ejecutamos
mi_layout <- layout()
mi_layout

#Bucle for para dibujar gráficos, cada uno de un color
for (i in 1:nrow(tabla_porcentajes)) {
  plot(tabla_porcentajes[i,], type = "l",  col = i, xlab = "Status")
}

```

`@solution`
```{r}
#Los datos que necesitamos son los calculados en el ejercicio 5 y estan en "tabla_porcentajes"

#Creamos el layout, lo guardamos en milayout y lo ejecutamos
mi_layout <- layout(matrix(1:4, ncol = 2, byrow= TRUE))
mi_layout

#Bucle for para dibujar gráficos, cada uno de un color
for (i in 1:nrow(tabla_porcentajes)) {
  plot(tabla_porcentajes[i,], type = "l",  col = i, xlab = "Status")
}
```

`@sct`
```{r}
ex() %>% check_object("mi_layout") %>% check_equal("mi_layout")
success_msg("Bien!!")
```

---

## Uso de Tapply

```yaml
type: NormalExercise
key: 1d1b6e0047
xp: 100
```

#Vamos a usar la función tapply para ver que trabajadores han atendido a un mayor número de reclamaciones

`@instructions`
1. Calcular el número de trabajadores que hay en el dataset
2. Utilizar tapply para dividir el dataser en grupos según su Responsable.User y calcular la longitud de cada grupo. tapply(datos$Status, datos$Responsible.User, length)
3. Ordenamos el vector resultante
4. Cogemos los 5 resultados con mas llamadas y los dibujamos en un histograma

`@hint`


`@pre_exercise_code`
```{r}
datos <- read.csv(file = "http://assets.datacamp.com/production/repositories/3807/datasets/5f5937e865b0e18f1ce3cc53f52372ece2b8e9fc/datos_sm2m.csv", header = TRUE)
```

`@sample_code`
```{r}
#El nombre de los trabajadores es un factor, con levels sacamos los factores distintos de esa variable y con lenght los contamos
num_trabajadores <- length(levels(datos$Responsible.User))

#Utilizamos la funcion tapply para calcular el numero de reclamaciones que ha atendido cada trabajador
llamadas_trabajador <- tapply()

#Ordenamos la lista resultado
trabajadores_ord <- sort(, decreasing = TRUE) 

#Seleccionamos los 3 primeros
maximos_3 <- trabajadores_ord[]

#Hacemos un plot
barplot(maximos_3)
```

`@solution`
```{r}
#El nombre de los trabajadores es un factor, con levels sacamos los factores distintos de esa variable y con lenght los contamos
num_trabajadores <- length(levels(datos$Responsible.User))

#Utilizamos la funcion tapply para calcular el numero de reclamaciones que ha atendido cada trabajador
llamadas_trabajador <- tapply(datos$Status, datos$Responsible.User, length)

#Ordenamos la lista resultado
trabajadores_ord <- sort(llamadas_trabajador, decreasing = TRUE) 

#Seleccionamos los 5 primeros
maximos_3 <- trabajadores_ord[1:3]

#Hacemos un plot
barplot(maximos_3)
```

`@sct`
```{r}
ex() %>% check_object("num_trabajadores") %>% check_equal("num_trabajadores")
ex() %>% check_object("llamadas_trabajador") %>% check_equal("llamadas_trabajador")
ex() %>% check_object("trabajadores_ord") %>% check_equal("trabajadores_ord")
ex() %>% check_object("maximos_5") %>% check_equal("maximos_5")
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
