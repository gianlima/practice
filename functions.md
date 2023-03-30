**Problem:** Column from a data.frame is not found inside a function  
**Solution:** use ``{{ var }}``
```
library(dplyr)

# does not work
get_var <- function(data, column) {
  data %>% select(column)
}

get_var(mtcars, cyl)
#> Error: object 'cyl' not found

# works
get_var <- function(data, column) {
  data %>% select({{ column }})
}

get_var(mtcars, cyl)
#>                     cyl
#> Mazda RX4             6
#> Mazda RX4 Wag         6
#> Datsun 710            4
#> Hornet 4 Drive        6
#> Hornet Sportabout     8
#> ...
```
