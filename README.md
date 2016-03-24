# PgDumpforRedshift

This pg_dump.c is an enhancedment to postgres pgdump to dump the schema of redshift database. The following two commands should be run to dump schema of redshift database to a test.sql. The -z option do analyze the sortkey and distkey. The -s option dumps the schema.

PGPASSWORD=test123 /usr/local/pgsql/bin/pg_dump -z --host=xxx.redshift.amazonaws.com   --dbname=test   --port=5439 --username=postgres

PGPASSWORD=test123 /usr/local/pgsql/bin/pg_dump -s --host=xxx.redshift.amazonaws.com   --dbname=test   --port=5439 --username=postgres >test.sql

Added following two new functions pg_dump.c

static char* getRedshiftAttr(Archive *fout,char *tableName);
static char* getRedshiftCompression(Archive *fout,char *tableName, char *attr);
