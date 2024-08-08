#+TITLE:git

* searching commits:
 #+BEGIN_SRC shell
   $git log
 #+END_SRC

 searching
 #+BEGIN_SRC shell
   $git log -g --grep=searchString
 #+END_SRC


* stash
stash
#+BEGIN_SRC shell
  $git stash
#+END_SRC

stash with name
#+BEGIN_SRC shell
  $git stash save "stash name"
#+END_SRC

unstash
#+BEGIN_SRC shell
  $git stash pop
#+END_SRC

apply without removing from stash list
#+BEGIN_SRC shell
  $git stash apply stash@{n}
#+END_SRC

list
#+BEGIN_SRC shell
  $git stash list
#+END_SRC

delete all
#+BEGIN_SRC shell
  $git stash clear
#+END_SRC

selective delete
#+BEGIN_SRC shell
  git stash drop stash@{2}
#+END_SRC

* using token
#+BEGIN_SRC shell
  git remote set-url origin https://your_user:your_token@github.com/your_user/your_repo.git
#+END_SRC
