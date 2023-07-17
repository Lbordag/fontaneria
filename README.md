# fontaneria
Base de Datos de un negocio de materiales de fontaneria, o similar.

Esta base de datos esta formada por por cuatro tablas relacionadas.Se adjunta el script. para ejecutarlo, cargalo en tu MySql y dale al rayo para ejecutarlo. se cargaran las tablas
-	Proveedores
    id_proveedor INT PRIMARY KEY,
    nombre VARCHAR(50),
    direccion VARCHAR(100),
    contacto VARCHAR(30)

-	Productos
    id_producto INT PRIMARY KEY,
    nombre VARCHAR(100),
    descripcion VARCHAR(200),
    precio DECIMAL(8,2),
    id_proveedor INT,
    FOREIGN KEY (id_proveedor) REFERENCES Proveedores(id_proveedor)

-	Clientes
    id_cliente INT PRIMARY KEY,
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    direccion VARCHAR(100),
    email VARCHAR(50)

-	Pedidos
    id_pedido INT PRIMARY KEY,
    id_producto INT,
    id_cliente INT,
    fecha DATE,
 	para que lo veais mas visible os dejo el modelo ER, que son las tablas relacionadas con sus atributos.
 	![modelo er](https://github.com/Lbordag/fontaneria/assets/139263728/c1f95496-c9b0-43d5-b1d0-50b97f6a0ba5)
 	en el scrip ya tines los datos metidos de las tablas, de los cuales tu puedes agregar los tuyo lo crear unos nuevos desde MYSql

  Existe un aconsulta para obtener el numero de pedidos de cada producto, copia y ejecuta en el rayo con plisa.
  
  Selectprecio.nombre, counto(*) as numero_pedidos
From pedidopd, producto pr
Where pd.id producto=pr.idproducto
Group by pr.nombre
Order by numero_pedido asc

he creado un disparador en el que al actualizar la nueva fecha de antigúedad en la casila nueva le sale la edad directamente.

set  new.antiguedad_stock = datediff(curdate(), new.fecha); le sale en días.

Por ultimo, si necesitas ayuda con el moritoneo/rendimiento te dejo el enlace para que consultes mas documentacion.
abre la pestaña de help y copia este texto.
MYSQL Workbench installation failed with Visual C++ 2019 redistributable





 

 

 	
