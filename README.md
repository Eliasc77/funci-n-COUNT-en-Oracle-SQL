# funci-n-COUNT-en-Oracle-SQL
#### se utiliza para trabajar con registros especificos de una tabla

```sql
create table medicamentos(
  codigo number(5),
  nombre varchar2(20),
  laboratorio varchar2(20),
  precio number(6,2),
  cantidad number(3),
  fechavencimiento date not null,
  numerolote number(6) default null,
  primary key(codigo)
 );

--insertar datos en la tabla
 insert into medicamentos
  values(120,'Sertal','Roche',5.2,1,to_date('01/02/2015','dd/mm/yyyy'),123456);
 insert into medicamentos 
  values(220,'Buscapina','Roche',4.10,3,to_date('01/02/2016','dd/mm/yyyy'),null);
 insert into medicamentos 
  values(228,'Amoxidal 500','Bayer',15.60,100,to_date('01/05/2017','dd/mm/yyyy'),232566);
 insert into medicamentos
  values(324,'Paracetamol 500','Bago',1.90,20,to_date('01/02/2018','dd/mm/yyyy'),null);
 insert into medicamentos 
  values(587,'Bayaspirina',null,2.10,null,to_date('01/12/2019','dd/mm/yyyy'),556999); 
 insert into medicamentos 
  values(789,'Amoxidal jarabe','Bayer',null,null,to_date('15/12/2019','dd/mm/yyyy'),null);
  
  select * from medicamentos ;
  
  ```
 | codigo            | nombre           |   laboratorio   |  precio   |  cantidad   |  fechavencimiento  | numerolote |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:| -----------:
 | 120 | Sertal |  Roche   | 5.2   | 1  | 01/02/2020| 123456 |
 | 220 | Buscapina |  Roche   | 4.1   | 3 | 01/02/2016|  (null)|
 | 228 | Amoxidal 500 |  Bayer   | 15.6  | 100 | 01/05/2017| 232566 |
 | 324 | Paracetamol 500 |  Bago   | 1.9   | 20 | 01/02/2018| (null)|
 | 587 | Bayaspirina |  (null)   | 2.10   | (null) | 01/12/2019| 556999 |
 | 789 | Amoxidal jarabe |  Bayer   | (null)   | (null) | 15/12/2019| (null)|

```sql
select count(*) as cantidad from medicamentos;
```

| cantidad|
| --------: | 
| 6 |
___ 

```sql
select count(laboratorio) as cantidad from medicamentos;
```
| cantidad|
| --------: | 
| 5 |
##### quiere decir que existen 5 registros de laboratorio, pero como hay un valor null la funcion count lo ignora es por ello q existe solo 5.

___
```sql
select count(precio) as con_precio , count (cantidad) as con_cantidad from medicamentos;
```
| con_precio| con_cantidad|
| --------: | ---------:|
| 5 | 4|

___
```sql
select count(fechavencimiento) from medicamentos;
```

| COUNT(Fechavencimiento)|
| --------: | 
| 6 |

