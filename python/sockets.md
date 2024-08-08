#+TITLE:sockets
#+FILETAGS: :python:sockets:

* create sockets                                                     :create:
#+begin_src python
  import socket

  server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  server.bind(('', 1234))
  server.listen(5)
  input(f'the sock is listening\nsocket: {server}')
#+end_src

breaking down:
+ =AF_INET=: ipv4
+ =SOCK_STREAM=: TCP
+ bind: sockets config
  + '': ip list (empty means everyone)
  + 1234: port which it will run on
+ listen: how many hosts can connect to the socket at the same time


* receive data                                                       :receive:data:
#+begin_src python
  import socket

  server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  server.bind(('', 1238))
  server.listen(5)

  # here a client should connect to the socket,
  # accept the connection
  client, addr = server.accept()
  print(f'communicating with {addr}')

  while True:
      data = client.recv(2048).decode()
      print(f'server got {data}')
      if data == 'exit':
          client.close()
          break
      client.sendall('thank you'.encode())

  server.close()
#+end_src


* send data                                                    :send:data:
#+begin_src python
  import socket

  client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  client.connect(('127.0.0.1', 1238))

  while True:
      data = 'send data'
      client.sendall(data.encode())

      response = client.recv(2048).decode()
      print(f'server responded with: {response}')

#+end_src

