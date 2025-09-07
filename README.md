# Data-Proyect-Proyecto-Final
Proyecto final en el que se aplica todo lo aprendido durante el curso Data Analytics

Mi proyecto final trata sobre un modelo financiero creado en PowerBi a partir de un conjunto de datos almacenado en excel. 
Los datos con los que voy a trabajar provienen de dos fuentes distintas (información del Plan General Contable Español, extraída de internet; información relativa a la contabilidad de una empresa extraída de un ejemplo de datos almacenados en SQL que utilicé en un ejercico de otro curso formativo). El Modelo desarrollado en PowerBi se nutre conectando a dicho fichero excel.

Para entender mejor el modelo, a continuación describo qué información contiene el fichero excel:
- La Hoja "Companies" contiene información relativa a la empresa: ID Empresa, Nombre de la Empresa y Grupo Empresa.
- La Hoja "General Ledger Accounts" contiene la información relativa a las cuentas del plan general contable español: las distintas categorías de cuentas (Financiación básica, Inmovilizado, Inventario, Acreedores y deudores, Cuentas Financieras, Compras y gastos, Ventas e ingresos), con sus dos subniveles correspondientes.
- La Hoja "Financial Statements" contiene información relativa a los distintos Estados Contables.
- La Hoja "General Ledger Entry" contiene el detalle de los distintos asientos contables de la empresa.
- La Hoja "Type Entry" contiene información relativa a los tipos de asientos: ID Asiento, Nombre Asiento.
- La Hoja "SubAccounts" contiene información relativa a las distintas subcuentas contables que tiene la empresa.

  En primer lugar, cargamos las tablas de excel en PowerBi y hacemos las transformaciones convenientes: cambiar formatos a número, fecha y texto en los casos que sea necesario, extraer los primeros caracteres de las columnas relativas a los códigos de las subcuentas contables y unirlas con el ID Empresa en los casos que corresponda para poder cruzar los datos de varias tablas a través de este campo, etc. Dichas transformaciones han sido desarrolladas directamente con PowerQuery (este trabajo lo podría haber hecho en SQL o Python, pero como gracias a mi experiencia laboral pasada sé hacer el tratamiento directamente en PowerBi, lo he hecho desde dicha herramienta - espero que se me convalide con el requisito de tratar datos en Python o SQL ya que el lenguaje DAX es muy parecido).
  En segundo lugar, he creado una tabla calendario que me permita hacer análisis temporales. A continuación, he creado tablas, columnas calculadas y medidas para los distintos KPIs que quiero presentar. El siguiente paso es establecer todas las relaciones en las distintas tablas para que el modelo funcione correctamente.
  A partir de ahí, sólo quedaba insertar los distintos objetos visuales para mi análisis.
  
