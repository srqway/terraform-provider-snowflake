
# snowflake_table_grant

<!-- These docs are auto-generated by code in main.go, run by with make docs. Manual edits will be overwritten. -->
**Note**: The snowflake_table_grant resource creates exclusive attachments of grants.
		Across the entire Snowflake account, all of the tables to which a single grant is attached must be declared
		by a single snowflake_table_grant resource. This means that even any snowflake_table that have the attached
		grant via any other mechanism (including other Terraform resources) will have that attached grant revoked by this resource.
		These resources do not enforce exclusive attachment of a grant, it is the user's responsibility to enforce this.
		
#### properties

|     NAME      |  TYPE  |                                                                                                                                                DESCRIPTION                                                                                                                                                 | OPTIONAL | REQUIRED  | COMPUTED | DEFAULT  |
|---------------|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|-----------|----------|----------|
| database_name | string | The name of the database containing the current or future tables on which to grant privileges.                                                                                                                                                                                                             | false    | true      | false    | <nil>    |
| on_future     | bool   | When this is set to true and a schema_name is provided, apply this grant on all future tables in the given schema. When this is true and no schema_name is provided apply this grant on all future tables in the given database. The table_name and shares fields must be unset in order to use on_future. | true     | false     | false    | false    |
| privilege     | string | The privilege to grant on the current or future table.                                                                                                                                                                                                                                                     | true     | false     | false    | "SELECT" |
| roles         | set    | Grants privilege to these roles.                                                                                                                                                                                                                                                                           | true     | false     | false    | <nil>    |
| schema_name   | string | The name of the schema containing the current or future tables on which to grant privileges.                                                                                                                                                                                                               | true     | false     | false    | <nil>    |
| shares        | set    | Grants privilege to these shares (only valid if on_future is unset).                                                                                                                                                                                                                                       | true     | false     | false    | <nil>    |
| table_name    | string | The name of the table on which to grant privileges immediately (only valid if on_future is unset).                                                                                                                                                                                                         | true     | false     | false    | <nil>    |