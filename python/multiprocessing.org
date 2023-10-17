#+TITLE:multiprocessing
#+FILETAGS: :python:process:

* simple multi process counter                       :processes:multi:python:
#+BEGIN_EXAMPLE python
def counter(max_range):
    for i in range(max_range):
        print(i)


if __name__ == '__main__':
    for i in range(5):
        p = multiprocessing.Process(target=counter, args=(100,))
        p.start()
#+END_EXAMPLE
