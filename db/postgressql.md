

* creating database
#+BEGIN_EXAMPLE
createdb -h <host> -p <5432> -U <postgres> <dbname>
#+END_EXAMPLE

* deleting database
#+BEGIN_EXAMPLE
dropdb -h <host> -p <5432> -U <postgres> <dbname>
#+END_EXAMPLE

* importing from .sql file
db must already exist
#+BEGIN_EXAMPLE
 psql -h <localhost> -p <5432> -U <postgres> -f <file> <dbname>
#+END_EXAMPLE
