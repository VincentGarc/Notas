Crear un calculo con filtro de alguna medida

```py
Total Sales Amount CALCULATE = CALCULATE([Total Sales Amount], dimProduct[Color] = "Blue")
```

Crear tabla de calendario
```py
Calendar Table = ADDCOLUMNS(
    CALENDARAUTO(),
    "Year", YEAR([Date]),
    "Mounth", MONTH([Date]),
    "Month_Name", FORMAT([Date],"MMM"))
```

Crear un filtro
```py
filtro = FILTER(dimProduct, dimProduct[Color] = "Blue")
```

Crear columna con calculo de otras 
```py
End Result = facInternetSales[Sales Amount EUR] * factInternetSales[Muliplier]
```

Iterar 
```py
Iterator SUMX =SUMX(factInternetSales, factInternetSales[Sales Amount EUR] * 2)
```

Relacionado y Relacionable
```py
Iterator SUMX = SUMX(
   FILTER(factInternetSales, RELATED(dimCustomer[Age Buckets]) = "50 Plus"), factInternetSales[Sales Amount EUR])
