#+TITLE:postgres sql

* list databases

#+NAME: list
#+BEGIN_SRC shell
  psql -U postgres -h localhost -p <port> -l
#+END_SRC

* create database

#+NAME: create_db
#+BEGIN_SRC shell
  createdb -U postgres -h localhost -p <port> <db_name>
#+END_SRC

