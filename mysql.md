#+title:MySql

* selecting
#+BEGIN_EXAMPLE
 SELECT * FROM PEOPLE WHERE ID = 1;
#+END_EXAMPLE

* changing encoding
mudando tabela:
#+BEGIN_EXAMPLE
  ALTER DATABASE dbname CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
#+END_EXAMPLE

mudando coluna:
#+BEGIN_EXAMPLE
  ALTER TABLE mytable MODIFY my_col LONGTEXT CHARACTER SET utf8mb4;
#+END_EXAMPLE
