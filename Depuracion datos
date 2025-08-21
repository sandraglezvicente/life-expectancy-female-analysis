# Paso 1: Cargar librerías necesarias
library(tidyverse)

# Paso 2: Importar el archivo CSV
datos <- read_csv("Datos/life_expectancy_female.csv")

# Paso 3: Inspección inicial
glimpse(datos)         # Ver estructura del dataset
summary(datos)         # Resumen estadístico
head(datos)            # Primeras filas

# Paso 4: Manejo de valores faltantes
# Ver cuántos valores NA hay por columna
colSums(is.na(datos))

# Eliminar filas completamente vacías (si las hubiera)
datos <- datos %>% drop_na()

# Paso 5: Transformar de formato wide a formato long
# Convertimos las columnas de años en una sola columna 'year'
datos_largos <- datos %>%
  pivot_longer(cols = -country, names_to = "year", values_to = "life_expectancy") %>%
  mutate(year = as.integer(year))

# Paso 6: Guardar el dataset depurado
write_csv(datos_largos, "Datos/base_depurada.csv")
