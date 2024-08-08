#+TITLE:python OS module

* running commands in shell                                       :python:OS:
store in a var like:
#+BEGIN_EXAMPLE python
output = os.popen('ifcongig').read())
#+END_EXAMPLE

or just run it with:
#+BEGIN_EXAMPLE python
os.system('ls')
#+END_EXAMPLE

* change directory
#+BEGIN_EXAMPLE python
os.chdir('/home')
#+END_EXAMPLE

* check files existence                                 :files:python:OS:
returns true or false
#+BEGIN_EXAMPLE python
os.path.isFile('err.log')
#+END_EXAMPLE


* removing files                                        :files:remove:python:OS:
#+BEGIN_EXAMPLE python
os.remove('err.log')
#+END_EXAMPLE
