# Data-Proyect-Proyecto-Final
Proyecto final en el que se aplica todo lo aprendido durante el curso Data Analytics

Mi proyecto final trata sobre un modelo de ventas creado en PowerBi a partir de un conjunto de datos almacenado en excel. 
Los datos con los que voy a trabajar provienen de un fichero excel, "Modelo-de-Ventas", que se ha nutrido de información sacada de una base de datos de SQL con ejemplos de clientes, direcciones, productos, vendedores y albaranes. El Modelo desarrollado en PowerBi se nutre conectando a dicho fichero excel.

Para entender mejor el modelo, a continuación describo qué información contiene el fichero excel:
- La Hoja "xerppasm_Clientes" contiene información relativa a clientes: cif, IdCliente, nombre, contacto, pais, cp, población, etc.
- La Hoja "xerppasm_Direccion" contiene información relativa a direcciones: IdDireccion, codigo pais, cp, latitud, longitud, etc.
- La Hoja "xerppasm_Productos" contiene información relativa a productos: IdProducto, nombre, familia, subfamilia, color, etc.
- La Hoja "xerppasm_Vendedor" contiene el detalle de los distintos vendedores: IdVendedor, nombre, codigo vendedor.
- La Hoja "xerppasm_AlbaranesCabeceras" contiene información relativa a albaranes: IdAlbaran, fecha, fecha cierre, fecha vencimiento, nº documento, bruto, etc.
- La Hoja "xerppasm_AlbaranLinea" contiene información relativa a otros aspectos de los albaranes: lineas de cada producto.

  En primer lugar, para construir el modelo de ventas desde cero, entramos en PowerBi y nos conectamos al fichero excel (nuevo origen > excel) para cargar las distintas hojas del fichero que usaremos para crear nuestras dimensiones, hechos y medidas. El siguiente paso será transformar los datos: en cada una de las dimensiones que creemos, tendremos que: renombrar columnas, dar formato a los datos (texto, número, fecha), eliminar duplicados o nulos, elegir las columnas que nos quedaremos para el modelo (la información que sobra no la cargamos), nombrar la tabla y crear un grupo de clasificación donde la incluiremos. Las dimensiones de las que consta el modelo son las siguientes: dClientes, dDirecciones, dProductos, dVendedores, dAlbaranes. Las dimensiones son de tipo cualitativo. Para crear nuestra tabla de hechos, sobre la que calcularemos las medidas, núcleo central del modelo, repetimos los mismos pasos. Nos conectamos al origen excel, cargamos la hoja albaranescabeceras y albaraneslineas que hemos combinado previamente, a través del campo común que poseen - IdAlbaran - y hacemos las pertinentes transformaciones (renombrar columnas, dar formato a los datos (texto, número, fecha), eliminar duplicados o nulos, elegir las columnas que nos quedaremos para el modelo (la información que sobra no la cargamos)).
  El siguiente paso será crear las relaciones para que nuestro modelo funcione correctamente. En primer lugar, en configuración, desactivamos el check de relaciones automáticas y el de fechas automáticas, para tratar esta cuestiones de manera manual y hacerlo de la manera que queremos, acorde a las necesidades de nuestro modelo. En la vista de relaciones, eliminamos todas las relaciones predifinidas, nos creamos una vista por cada tabla de hechos (en nuestro caso sólo tenemos una) y vamos creando las distintas relaciones entre nuestra tabla de hechos y cada una de lasa dimensiones.
  Con esto, ya podríamos empezar a añadir objetos visuales para nuestro análisis, sin embargo, para mejorar el modelo, realizamos antes una serie de acciones que describo a continuación:
  - Marcar nuestra dimensión fechas como tabla de fechas.
  - Categorizar cada uno de nuestros atributos más importantes.
  - Crear jerarquías para las fechas, los clientes y los productos.
  - Ocultar las tablas que no necesitará el usuario que visualice el informe (en este caso nuestra tabla de ventas que nos sirve sólo para hacer los cálculos).
El siguiente paso será crear las distintas medidas que iremos mostrando como objetos visuales. Para ello, creamos una tabla de medidas donde las iremos insertando todas. Adjunto se encuentra un fichero pdf con la relación de las distintas medidas que se han creado.
A partir de este momento, todo lo que he hecho ha sido ir añadiendo objetos visuales que muestran distintos valores o indicadores poniendo en práctica lo aprendido durante el curso.
Me gustaría destacar que, para mi modelo, me he centrado en hacer un análsis de ventas por cliente y por margen comercial, no obstante, se podrían añadir distintos enfoques como por producto o por vendedor.
    
