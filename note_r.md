# R tips
## dplyr
### Change column position
relocate() change column position.
```
> head(iris)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa

> relocate(iris, Species) %>% head()
  Species Sepal.Length Sepal.Width Petal.Length Petal.Width
1  setosa          5.1         3.5          1.4         0.2
2  setosa          4.9         3.0          1.4         0.2
3  setosa          4.7         3.2          1.3         0.2
4  setosa          4.6         3.1          1.5         0.2
5  setosa          5.0         3.6          1.4         0.2
6  setosa          5.4         3.9          1.7         0.4

> relocate(iris, .after = Sepal.Length, Species) %>% head
  Sepal.Length Species Sepal.Width Petal.Length Petal.Width
1          5.1  setosa         3.5          1.4         0.2
2          4.9  setosa         3.0          1.4         0.2
3          4.7  setosa         3.2          1.3         0.2
4          4.6  setosa         3.1          1.5         0.2
5          5.0  setosa         3.6          1.4         0.2
6          5.4  setosa         3.9          1.7         0.4
```

### Select multiple columns and execute
Try to do mutate() + select() + *your_function()*
```
> inExprData %>% head
# A tibble: 6 x 11
  Gene_Symbol Sick_64 Sick_87 Sick_105 Sick_111 Sick_173 Sick_303 Health_460
  <chr>         <dbl>   <dbl>    <dbl>    <dbl>    <dbl>    <dbl>      <dbl>
1 TSPAN6         0    3.44e-2     0        0       0.355     0         0
2 TNMD           0    0.          0        0       0         0         0
3 DPM1           6.35 8.39e+0    13.1      8.90   20.5      12.9       5.52
4 SCYL3          3.66 7.76e+0     8.40     6.84    4.66      8.99      3.30
5 C1orf112       4.50 5.36e+0    10.0      2.75    3.64      4.34      0.943
6 FGR           83.0  1.59e+2   191.     188.    135.      118.      212.

> useExprData <- inExprData %>%
+     dplyr::mutate(Sum = dplyr::select(., -Gene_Symbol) %>% rowSums(na.rm = TRUE)) %>%
+     relocate(Sum)

> useExprData %>% head
# A tibble: 6 x 12
      Sum Gene_Symbol Sick_64 Sick_87 Sick_105 Sick_111 Sick_173 Sick_303
    <dbl> <chr>         <dbl>   <dbl>    <dbl>    <dbl>    <dbl>    <dbl>
1 3.90e-1 TSPAN6         0    3.44e-2     0        0       0.355     0
2 0.      TNMD           0    0.          0        0       0         0
3 7.57e+1 DPM1           6.35 8.39e+0    13.1      8.90   20.5      12.9
4 5.41e+1 SCYL3          3.66 7.76e+0     8.40     6.84    4.66      8.99
5 3.72e+1 C1orf112       4.50 5.36e+0    10.0      2.75    3.64      4.34
6 2.37e+3 FGR           83.0  1.59e+2   191.     188.    135.      118.
```