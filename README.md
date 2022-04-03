# Alias-EnUnaConsulta-Oracle
#### un alias en sql es una asignacion de nombre que se le da a un campo para su mejor comprensión al momento de realizar una consulta.
##### Esto es util cuando queremos extreaer un reporte de la base de datos para ser presentado a algún interesado que no tengo porque saber los nombres reales de los campos de la tabla.

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
 #### utilizamos as para dar un alias a un acampo
 
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
 
