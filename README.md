# WowMaker | Microsoft SQL to Snowflake Export Utility



Windows export utility to automatically transfer entire set of tables from Microsoft SQL server to Snowflake

* Tool requires Snowflake_ODBC_driver Win64 to be installed on the machine before it can run.

[Download SQL_to_Snowflake Installer](https://github.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/raw/main/MsSQL_To_Snowflake.zip)


[Snowflake Win64 ODBC Driver Download](https://sfc-repo.snowflakecomputing.com/odbc/win64/latest/index.html)

- <strong>11/21/2020 - Updated V6 with following changes</strong>
  - Added Windows Authentication support for SQL connection
  - Added max file size option for exporting chucks for large table exports (10, 25, 50, 75 & 100 MB)
  - Added Option to Enable/Disable client side file compression (gzip) prior to uploading to Snowflake
  - Enhanced logic to reduce redundant SQL create schema commands.
  - Fixed an issue with Column names with spaces.
  - Fixed an issue displaying status for tables with 0 records

This utility will automatically move tables (in full) from a Ms SQL server to Snowflake. All you have to do is select a list of tables from SQL server and point to an existing Snowflake account & a database with proper user cridentials to create schemas & tables.



The tool will do the following for each table:
- Generate a DDL & Create the table in Snowflake.
- Auto map proper datatypes.
- Perform date type conversion

if COPY DATA is checked (checked by default)
- Export the data into files in 10MB batches into a temp folder.
- Create an internal stage in the target Snowflake database & Upload the files
- Copy the uploaded files into the proper table in snowflake.

![Image of SQL to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/SQL_2_Snowflake_Screenshot.png)


