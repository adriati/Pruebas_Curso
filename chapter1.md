---
title: 'Template Chapter 1'
description: 'This is a template chapter.'
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
## Vamos a darle un formato menos feo al contexto

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
