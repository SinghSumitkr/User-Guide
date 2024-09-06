WITH column_info AS (
    SELECT 
        t.table_catalog AS database_name,
        t.table_schema AS schema_name,
        t.table_name,
        c.column_name,
        'No' AS is_partition_column
    FROM 
        information_schema.tables t
    JOIN 
        information_schema.columns c 
    ON 
        t.table_schema = c.table_schema 
        AND t.table_name = c.table_name
    WHERE 
        t.table_type = 'BASE TABLE'
),
partition_info AS (
    SELECT 
        table_catalog AS database_name,
        table_schema AS schema_name,
        table_name,
        column_name,
        'Yes' AS is_partition_column
    FROM 
        information_schema."columns"
    WHERE 
        column_name IN (
            SELECT 
                partition_key 
            FROM 
                information_schema.partitions
        )
)
SELECT 
    ci.database_name,
    ci.schema_name,
    ci.table_name,
    ci.column_name,
    COALESCE(pi.is_partition_column, ci.is_partition_column) AS is_partition_column
FROM 
    column_info ci
LEFT JOIN 
    partition_info pi 
ON 
    ci.database_name = pi.database_name 
    AND ci.schema_name = pi.schema_name 
    AND ci.table_name = pi.table_name 
    AND ci.column_name = pi.column_name
ORDER BY 
    ci.database_name, ci.schema_name, ci.table_name, ci.column_name;
