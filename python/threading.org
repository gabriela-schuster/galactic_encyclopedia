#+TITLE:python threads
#+FILETAGS: :python:threads:

* simple threading example
  #+BEGIN_SRC python
  import threading

  def pinger(url):
    os.system(f'ping {url}')

  urls = ['www.google.com', 'www.youtube.com', 'www.reddit.com']

  for url in urls:
    t = threading.Thread(target=pinger, args=(url,))
    t.start()
  #+END_SRC


* wait threads to end                                              :end:wait:
  use .join() funcion of the instance of the executing thread
  #+BEGIN_SRC python
    import threading
    import os


    def pinger(url):
        os.system(f'ping {url} -c 3')

    urls = ['www.google.com', 'www.youtube.com', 'www.reddit.com']
    threads = []

    for url in urls:
        t = threading.Thread(target=pinger, args=(url,))
        threads.append(t)
        t.start()

    for thread in threads:
        t.join()

    print('done!')
  #+END_SRC


* synchronizing threads                                         :synchronize:
** lock                                                               :lock:
 #+BEGIN_SRC python
import threading


def counter(lock, n):
  for i in range(n):
    with lock:
      print(i)

lock = threading.Lock()
for i in range(5):
  threading.Thread(target=counter, args=(lock, 10)).start()
 #+END_SRC

** semaphore                                                     :semaphore:
exactly like lock, but enables multiple threads to execute at the same time
 #+BEGIN_SRC python
import threading


def counter(semaphore, n):
  for i in range(n):
    with semaphore:
      print(i)

semaphore = threading.Semaphore(1) # 1 thread per time
for i in range(5):
  threading.Thread(target=counter, args=(semaphore, 10)).start()
 #+END_SRC
