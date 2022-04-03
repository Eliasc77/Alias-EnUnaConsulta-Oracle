# Alias-EnUnaConsulta-Oracle
#### un alias en sql es una asignacion de nombre que se le da a un campo para su mejor comprensión al momento de realizar una consulta.
##### Esto es util cuando queremos extreaer un reporte de la base de datos para ser presentado a algún interesado que no tengo porque saber los nombres reales de los campos de la tabla.

> Recordemos que los alias en sql son utilizaods simplemente para consultas realizado a la bd, este prefijo no funciona para cambiar el nombre del campo que se decida al momento de realizar actualziaciones en las tablas.
___

 ```sql
select * from articulos;
```
 
 | CODIGO            | NOMBRE           |  DESCRIPCION   |   PRECIO   | CANTIDAD   |
 | ------------------|:----------------:|---------------:|-----------:|-----------:|
 | 1            | impresora           |  Epson Stylus C45   |   1500   |    4       |
 | 2            | impresora           |  Epson Stylus C85   |   1500   |     11     |
 | 3            | impresora           |  Samsung 14   |   1500   |    24  |
 | 4            | teclado           |  ingles Biswal   |   1500   |    3   |
 | 8            | impresora           |  Dell   |   1500   |  11    |
 
 ___
 #### utilizamos el prefijo 'as' para dar un alias a un campo, se coloca luego del campo a cambiar y colocando un termino al nombre de la consulta
 
```sql
select nombre, descripcion, precio , cantidad as existente
from articulos;
```
| NOMBRE           |  DESCRIPCION   |   PRECIO   | EXISTENTE   |
|:----------------:|---------------:|-----------:|-----------:|
| impresora           |  Epson Stylus C45   |   1500   |    4       |
| impresora           |  Epson Stylus C85   |   1500   |     11     |
| impresora           |  Samsung 14   |   1500   |    24  |
| teclado           |  ingles Biswal   |   1500   |    3   |
| impresora           |  Dell   |   1500   |  11    |
 
___

#### aplicar un 15% descuento a cada uno de los articulos y que se muestre en un campo que se desgloce el precio de los articulos con el descuento

```sql
select nombre, descripcion, precio - ( precio * 0.15) as  descuento 
from articulos;
```

| NOMBRE           |  DESCRIPCION   |   DESCUENTO   |
|:----------------:|---------------:|-----------:|
| impresora           |  Epson Stylus C45   |   1,275   |
| impresora           |  Epson Stylus C85   |   1,275   |
| impresora           |  Samsung 14   |   1,275   |
| teclado           |  ingles Biswal   |   1,275   |
| impresora           |  Dell   |   1,275   |

___

> mostrar el precio de las impresoras con un 20% aumentado

```sql
select nombre, descripcion, precio + ( precio * 0.20) as  recargo
from articulos
where nombre = 'impresora';
```
| NOMBRE           |  DESCRIPCION   |   RECARGO   |
|:----------------:|---------------:|-----------:|
| impresora           |  Epson Stylus C45   |   1,800   |
| impresora           |  Epson Stylus C85   |   1,800    |
| impresora           |  Samsung 14   |   1,800    |
| impresora           |  Dell   |   1,800    |
___
