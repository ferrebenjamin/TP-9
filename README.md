**Tabla    Descripción general**

**clientes&#xA0;**&#xA0;  Almacena la información de los clientes que realizan compras. Contiene su nombre, correo electrónico y número de teléfono. Cada cliente se identifica de manera única por el campo id\_cliente.
**facturas**    Registra las facturas emitidas a los clientes. Está vinculada a la tabla clientes mediante la clave foránea id\_cliente y contiene la fecha de emisión. Su clave primaria es id\_factura.

 **productos &#xA0;**&#xA0; Guarda la información de los productos disponibles para la venta, incluyendo su nombre y precio unitario. Cada producto se identifica con id\_producto.
**detalle\_factura**    Representa los productos incluidos en cada factura. Contiene las claves foráneas id\_factura y id\_producto, además de la cantidad vendida. Actúa como tabla intermedia entre facturas y productos, estableciendo una relación muchos a muchos (N:M) entre ambas.

**Descripción del modelo&#xA0;**

El modelo de la base de datos facturación fue diseñado para gestionar el proceso completo de facturación de una empresa.
Su función principal es registrar los datos de los clientes, los productos y las facturas generadas, junto con el detalle de cada producto vendido.

El sistema permite:

Registrar nuevos clientes y sus datos de contacto.

Ingresar productos con su respectivo precio.

Emitir facturas a los clientes.

Registrar el detalle de los productos vendidos en cada factura.

Consultar fácilmente los totales, ventas y relación entre clientes y productos.

**Principales entidades**

**1. Clientes**: representan a las personas o empresas que compran productos.

Atributos: id\_cliente, nombre, email, telefono.

**2. Productos:** artículos que la empresa vende.

Atributos: id\_producto, nombre\_producto, precio.

**3. Facturas:** documentos que registran una venta, vinculando al cliente con los productos comprados.

Atributos: id\_factura, id\_cliente, fecha.

**4. Detalle\_factura:&#x20;**&#x69;ndica los productos que se incluyen en cada factura, junto con la cantidad.

Atributos: id\_detalle, id\_factura, id\_producto, cantidad.

 Relaciones entre las tablas

**Relación    Tipo    Descripción**

clientes → facturas    1 a N    Un cliente puede tener muchas facturas, pero cada factura pertenece a un solo cliente.
facturas → detalle\_factura    1 a N    Una factura puede tener muchos productos, pero cada detalle pertenece a una sola factura.
productos → detalle\_factura    1 a N    Un producto puede estar en varios detalles, pero cada detalle corresponde a un solo producto.

**Forma Normal    Cumple    Justificación**

Primera Forma Normal (1FN)    Todos los atributos son atómicos, no hay campos con listas ni valores repetidos. Cada tabla tiene clave primaria.
Segunda Forma Normal (2FN)    No existen claves compuestas, por lo tanto no hay dependencias parciales. Todos los atributos dependen directamente de la clave primaria.
Tercera Forma Normal (3FN)    No hay dependencias transitivas entre atributos no clave. Cada campo depende únicamente de su clave primaria.

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/4a83b4888d7db82251c427161993b97a7be5185ea43fc505.jpeg)

Primera Forma Normal (1FN)     Todos los atributos son atómicos, no hay campos con listas ni valores repetidos. Cada tabla tiene clave primaria.
Segunda Forma Normal (2FN)    No existen claves compuestas, por lo tanto no hay dependencias parciales. Todos los atributos dependen directamente de la clave primaria.
Tercera Forma Normal (3FN)     No hay dependencias transitivas entre atributos no clave. Cada campo depende únicamente de su clave primaria.
