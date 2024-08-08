#+title: Starting with regex

* basic
#+BEGIN_SRC js
    // g -> global, search all ocurrences
    // i -> case insensitive
    // () -> group
    // | -> OR
    const text = "João comeu feijão ontem joão";
    // [0] is 'João comeu', [1] is 'João', [2] is 'comeu'
    const regExp1 = /(João|maria)( comeu)/i;
    const found = regExp1.test(text);
    console.log(found)
    // if used with g, the behaviour changes
    const details = regExp1.exec(text);
    const new_text = text.replace('/João/gi', 'Felipe')
    console.log(details)
#+END_SRC

#+RESULTS:
#+begin_example
true
[
  'João comeu',
  'João',
  ' comeu',
  index: 0,
  input: 'João comeu feijão ontem joão',
  groups: undefined
]
undefined
#+end_example

* Quantificators
#+BEGIN_SRC js
  const text = "João comeu feijão ontem joão";
  const regExp1 = /(João|maria)( comeu)/i;
  console.log(text.match(regExp1))
#+END_SRC

#+RESULTS:
: ['João comeu '(\, 'João) '(\, 'comeu) '(\, index:) 0 (\, input:) 'João comeu feijão ontem joão '(\, groups:) undefined]
