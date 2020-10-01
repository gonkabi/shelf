# R tips

## Contents
<!--ts-->
   * [R tips](#r-tips)
      * [Contents](#contents)
      * [Data Shaping](#data-shaping)
         * [Change column position](#change-column-position)
         * [Select multiple columns and execute](#select-multiple-columns-and-execute)
         * [Separate a column into columns by key](#separate-a-column-into-columns-by-key)
      * [Visualize: ggplot2](#visualize-ggplot2)
         * [Change angles of x-axis labels](#change-angles-of-x-axis-labels)

<!-- Added by: shota, at: Thu Oct  1 14:35:39 JST 2020 -->

<!--te-->

## Data Shaping
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
### Separate a column into columns by key
Use tidyr::separate
```
> before %>% head(3)
# A tibble: 6 x 3
  cell_type sample     score
  <chr>     <chr>      <dbl>
1 B cell    Sick_64  0.0172
2 B cell    Sick_87  0.00718
3 B cell    Sick_105 0.0286

> after <- before %>%
+     separate(sample, into = c("Condition", "Sample_ID"), sep = "_", remove = FALSE)

> after %>% head(3)
# A tibble: 6 x 5
  cell_type sample   Condition Sample_ID   score
  <chr>     <chr>    <chr>     <chr>       <dbl>
1 B cell    Sick_64  Sick      64        0.0172
2 B cell    Sick_87  Sick      87        0.00718
3 B cell    Sick_105 Sick      105       0.0286
```

## Visualize: ggplot2
### Change angles of x-axis labels
Use theme() as following.
```
theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust = 1))
```

## Visualize: Color Palettes
### Library & Function
Recommended palettes are following:

* ggthemes::scale_fill_tableau(): if colors <= 20
* ggsci::scale_fill_ucscgb(): if colors > 20

