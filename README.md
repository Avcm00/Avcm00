Aquí te explico cada una de las funciones y métodos utilizados en el código que has compartido, divididos en las diferentes etapas:

### 1. **Carga de bibliotecas**
```r
library(tidyverse)
library(scales)
library(ggplot2)
library(fdth)
library(dplyr)
library(e1071)
```
- `tidyverse`: Un conjunto de paquetes de R que facilitan el manejo de datos (incluye `dplyr`, `ggplot2`, entre otros).
- `scales`: Permite escalar datos y formatos numéricos (muy útil para gráficos y escalas).
- `ggplot2`: Paquete de visualización de datos que permite crear gráficos avanzados.
- `fdth`: Paquete para la creación de tablas de frecuencias y otras estadísticas.
- `dplyr`: Paquete que facilita el filtrado, transformación y manipulación de datos en R.
- `e1071`: Paquete que ofrece funciones estadísticas adicionales como la curtosis y la asimetría.

### 2. **Copia de la base de datos**

view(variable)
- `enemdu_persona_2024_07`: Es la base de datos original. Aquí, se crea una copia en `Cop_Software`.
- `View()`: Abre la base de datos en una ventana para visualizarla en una tabla.

### 3. **Resumen de hombres y mujeres**

- `table()`: Crea una tabla de frecuencias para los valores de la variable `p02`, que probablemente represente el género.
- `Res_Genero`: Almacena la tabla de conteo de hombres y mujeres.

### 4. **Cálculo de porcentaje**

- `sum()`: Suma los valores de la tabla `Res_Genero`.
- `round()`: Redondea los resultados del cálculo de porcentajes a dos decimales.

### 5. **Gráfico de pastel**

- `pie()`: Crea un gráfico de pastel (torta) con las frecuencias almacenadas en `Res_Genero`.
- `paste()`: Combina las etiquetas (Hombre, Mujer) con los porcentajes para mostrar en el gráfico.

### 6. **Filtro de datos (personas con sueldos entre $450 y $2500)**

- `filter()`: Filtra las filas de `Cop_Software` donde la variable `p66` (probablemente el sueldo) está entre 450 y 2500.
- `%>%`: Operador pipe, que permite encadenar funciones en R.
- `summary()`: Proporciona un resumen estadístico de la variable `p66` (sueldo).

### 7. **Medidas de tendencia central**
- **Media**:
  
  Calcula el promedio `mean()` de la variable `p66`.

- **Mediana**:
  
  Calcula la mediana  `median()` de la variable `p66`.

- **Moda**:
  
  `mfv()` (del paquete `e1071`) calcula la moda, que es el valor más frecuente.

### 8. **Medidas de dispersión**
- **Varianza**:
  
  calcular la varianza `var()` sueldofiltro de la variable p66 

- **Desviación estándar**:
  
  calcular la desviacion esrtandar `sd()` sueldofiltro de la variable p66

### 9. **Medidas de posición (mínimo, máximo, rango, cuartiles, percentiles)**
- **Mínimo y máximo**:

max() y min()
-
  rango=max-min

- **Cuartiles y percentiles**:
 
  quantile() para calcular cuantiles 

### 10. **Medidas de forma (curtosis y asimetría)**
- **Curtosis**:

  todo guardar en una variable apartec
  calcular `kurtosis()`
kurtosis(  x ,type=1,2)
- **Coeficiente de asimetría**:

\`skewness()`

skewness(variable-fila-nombre de fil)
### 11. **Tabla de frecuencias**
- **Frecuencias**:

calcular tabla de frecuencia `fdt()`
tablas de frecuencia fdt(var,star = min,end=max,h=amplitud)
### 12. **Gráficos basados en la tabla de frecuencias**
plot(Tbl_frecuenci_sueldo, type = "fh")

- `plot()`: Crea gráficos en función del tipo seleccionado:
  - `fh`: Histograma de frecuencias.
  - `fp`: Gráfico de puntos.
  - `rfh`: Frecuencia relativa.

tamanio de la muestra
length(variable)

numero de clase 
Nclase_sueldo = 1 + (3.322*log10(N))
amplitud clase Amplitud_sueldo = rango_sueldo/Nclase_sueldo

