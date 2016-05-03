# MySQL Optimize Table

The OPTIMIZE command reorganizes the physical storage backing a table and its associated index data. This reduces storage overall and improves I/O when using the table. The storage engine determines the type of optimize done. On InnoDB tables, optimize instread does a recreate and analyze on the table. You usually want to optimize a table after any substantional interaction with the table whether that be an INSERT, DELETE, or UPDATE.
