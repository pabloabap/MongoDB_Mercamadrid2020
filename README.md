# JSON-Mercamadrid: volumen y precio de productos comercializados (enero2020-septiembre 2020)
JSON creado a partir de datos abiertos aportados por Mercamadrid con modificaciones personales para practicar consultas con MongoDB.
Tabla de datos con 33.644 registros y 8 campos (3 tipo objeto y uno tipo array)

ESTRUCTURA DEL CONJUNTO DE DATOS	
	
1)fechaVenta:	Momento de recopilación de los datos. Partido en año y mes
    1.1)año:	El año de la toma de datos es 2020
    1.2)mes:	De enero a septiembre en formato número
2)codVariedad:	Código de producto vendido. Lo partimos en  codFam y codProd
    2.1)codFam:	"Clasifica los productos según familias. En base a observaciones:
      - CA: Vacuno
      - CB: Ovino
      - CC: Porcino
      - CE: Avicola, conejo, perdiz y codorniz
      - CG: Vacuno
      - CH: Ovino (incluye producto congelado)
      - CI: Porcino (incluye producto congelado)
      - CK: Codorniz, conejo, pavo, perdiz y pollo
      - F1: Fruta y frutos secos
      - F2: Hortalizas, tubérculos y setas
      - F3: Patatas
      - P4: Pescado fresco
      - P5: Marisco fresco
      - P6: Pescado y marisco congelado"
    2.2) codProd:	Código del producto dentro de la familia
3) descVar:	Descripción del producto vendido
4) origen:	Código de origen del producto. Del 1 al 52 corresponde al número de provincia de España. Por encíma, hacen referencia a distintos paises.
5) descOrigen:	Descripción del origen del producto
6) kg:	Kilos vendidos en la franja de tiempo
7) precio:	Precios/kg registrados en el periodo separados en:
    7.1) freq:	Precio más frecuente registrado en el periodo
    7.2) max:	Precio máximo registrado del periodo
    7.3) min:	Precio mínimo registrado del periodo
8) tags:	Etiquetas clasificadoras de cada registro (elaboración propia)


