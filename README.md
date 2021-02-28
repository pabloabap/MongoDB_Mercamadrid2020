# Creación de base de datos de Mercamadrid y realización de consultas con MongoDB 
## Introducción
En este proyecto he trabajado sobre el **volumen y precio de productos comercializados en Mercamadrid de enero a septiembre de 2020**. Los datos han sido obtenidos del [portal de datos abiertos del Ayuntamiento de Madrid]. 


Mercamadrid es el centro de abastecimiento y distribución de alimentos frescos más importante de España y un referente internacional. Fue fundado en 1982 y actualmente cuenta con 222 hectareas dedicadas a la comercialización de frutas, verduras, carnes y pescados al por mayor.


Los datos vienen en CSV por lo que he hecho ciertos cambios para convertirlos a formato [JSON (mercamadrid2020.json)][código JSON] y poder sacar más partido de ellos. En total son 33.644 registros y 8 campos.

[portal de datos abiertos del Ayuntamiento de Madrid]:https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=a4df993ae322b610VgnVCM1000001d4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default
[código JSON]: https://github.com/pabloabap/JSON-Mercamadrid2020/blob/main/mercamadrid2020.json


### Estructura del conjunto de datos
	
1. **fechaVenta**:	Momento de recopilación de los datos. Partido en año y mes </br>
	+ **año**:	El año de la toma de datos es 2020 </br>
	+ **mes**:	De enero a septiembre en formato número </br>
2. **codVariedad**:	Código de producto vendido. Lo partimos en  codFam y codProd </br>
	+ **codFam**:	Clasifica los productos según familias. En base a observaciones: </br>
     		- CA: Vacuno </br>
      		- CB: Ovino</br>
     		- CC: Porcino</br>
     		- CE: Avicola, conejo, perdiz y codorniz</br>
      		- CG: Vacuno</br>
      		- CH: Ovino (incluye producto congelado)</br>
      		- CI: Porcino (incluye producto congelado)</br>
      		- CK: Codorniz, conejo, pavo, perdiz y pollo</br>
      		- F1: Fruta y frutos secos</br>
      		- F2: Hortalizas, tubérculos y setas</br>
      		- F3: Patatas</br>
      		- P4: Pescado fresco</br>
      		- P5: Marisco fresco</br>
      		- P6: Pescado y marisco congelado</br>
  	+ **codProd**:	Código del producto dentro de la familia</br>      
3. **descVar**:	Descripción del producto vendido</br>
4. **origen**:	Código de origen del producto. Del 1 al 52 corresponde al número de provincia de España. Por encíma, hacen referencia a distintos paises.</br>
5. **descOrigen**:	Descripción del origen del producto</br>
6. **kg**:	Kilos vendidos en la franja de tiempo</br>
7. **precio**:	Precios/kg registrados en el periodo separados en:</br>
   + **freq**:	Precio más frecuente registrado en el periodo</br>
   + **max**:	Precio máximo registrado del periodo</br>
   + **min**:	Precio mínimo registrado del periodo</br>
8. **tags**:	Etiquetas clasificadoras de cada registro (elaboración propia)</br>

## Importacion
Importo archivo JSON por linea de comandos e inserto 4 registros de forma manual.

## Consultas
### De busqueda
1. Comprobar que los registros tienen el campo precio relleno.
2. Encontrar los productos de enero 2020 con precio.freq entre 0.01€ y 0.20€ y ordenarlos por ascendentemente por precio.freq.
3. Encontrar los tegistro con una etiqueta (tags) para pensar posibles etiquetas a añadir.
### De actualización
1. Crear una nueva columna que sea TRUE si el producto es nacional (clave "origen" menor a 54).
### De proyección
1. Consultar las claves "descOrigen" y "tags" de cada registro.
### De agregación
1. Agrupar la canditad (Kg) de producto vendido en Mercamadrid por lugar de origen y ordenar descendentemente en función de la cantidad.
2. Top 10 productos con más kg vendidos de origen valenciano y su cantidad.
3. Conocer los 10 lugares de origen que llevan más cantidad de un único producto y mostrar el producto del que se trata.
4. Ventas anuales en Mercamadrid por mes y ordenadas descendentemente por facturación.
5. Ventas anuales de producto, kg vendidos y ordenadas descendentemente por facturación.
6. Conocer cúantos productos diferentes se venden por categoría ("codFam").
7. Producto más caro de cada familia de producto.
8. Productos internacionales ordenados descendentemente por ventas (kg).
9. Kg de mercancía de origen nacional vs origen internacional.
10. Top 10 importadores y cantidad importada.
11. Obtener todos los peces con la categoría "RIO" en su clave "tags" y ordenar por "precio.freq" descendentemente. 


