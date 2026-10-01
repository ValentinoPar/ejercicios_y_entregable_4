# sql-select-fundamentals
¿Por qué es mala práctica usar SELECT * en producción?
Rendimiento: trae todas las columnas aunque solo necesites dos o tres. En tablas grandes, eso desperdicia memoria y hace la consulta más lenta.
Mantenibilidad: si mañana se agrega una columna nueva a la tabla, todas las consultas con SELECT * la van a traer sin que nadie la haya pedido, pudiendo romper reportes que esperaban un número fijo de columnas.
SELECT * sirve para explorar una tabla rápido, pero no para dejarlo en un reporte que corre todos los días.
¿Por qué son importantes los alias para un stakeholder no técnico?
Porque le ponen al resultado el nombre que esa persona entiende, sin que tenga que saber cómo se llama la columna en la base de datos.
Ejemplo: SELECT total_amount FROM sales; devuelve la columna como total_amount. Con SELECT total_amount AS monto_total FROM sales;, el resultado ya llega encabezado monto_total — listo para leer en Excel o Power BI, sin que finanzas tenga que preguntar qué significa.
