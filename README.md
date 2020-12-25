# JSON-Mercamadrid: volumen y precio de productos comercializados (enero2020-septiembre 2020)
JSON creado a partir de datos abiertos aportados por Mercamadrid con modificaciones personales para practicar consultas con MongoDB.
Tabla de datos con 33.644 registros y 8 campos (3 tipo objeto y uno tipo array)

## ESTRUCTURA DEL CONJUNTO DE DATOS	
	
1. **fechaVenta**:	Momento de recopilación de los datos. Partido en año y mes </br>
	+ **año**:	El año de la toma de datos es 2020 </br>
	+ **mes**:	De enero a septiembre en formato número </br>
2. **codVariedad**:	Código de producto vendido. Lo partimos en  codFam y codProd </br>
	+ **codFam**:	"Clasifica los productos según familias. En base a observaciones: </br>
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


