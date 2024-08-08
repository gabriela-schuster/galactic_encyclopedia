#+title: eel
#+filetags: :python:ell:

* running simple html in window:                                       :html:
#+begin_example python
  import eel


  eel.init('web') # use web folder for files
  eel.start('index.html', size=(850, 400), port=0) # 0 means python will choose a free ephemeral port
#+end_example

*** in the web/index/html file:
#+begin_example html
  <link rel='text/javascript' href='./eel.js'>
#+end_example


* exporting python functions to javascript
in the main python file:
#+begin_example python
  import eel
  import random


  @eel.expose
  def get_number():
      return random.randint(1, 100)

  eel.init('web')
  eel.start('index.html', size=(850, 400), port=0)
#+end_example

in the html:
#+begin_example html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=\, initial-scale=1.0">
      <title>Document</title>
      <script rel='text/javascript' src='./eel.js'></script>
  </head>
  <body>

  </body>

  <script>
      eel.get_number()(function (data) {
          console.log(data)
      })
  </script>

  </html>
#+end_example


* exporting javascript functions to python
in the main python file:
#+begin_example python
  import eel
  import random

  value = eel.print_number(random.randint(1, 100))

  eel.init('web')
  eel.start('index.html', size=(850, 400), port=0)
#+end_example

in the html:
#+begin_example html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=\, initial-scale=1.0">
      <title>Document</title>
      <script rel='text/javascript' src='./eel.js'></script>
  </head>
  <body>

  </body>

  <script>
      eel.expose(print_number)
      function print_number(data) {
          console.log(data)
      })
  </script>

  </html>
#+end_example
