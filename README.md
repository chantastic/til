# til
stuff i just learned

## 2017.09.01

**In Ocaml/Reason, every `files` is a `module`.**

Say I have `schoole.re` and it looks like this:

```
/* school.re */
type profession = Teacher | Director;

let person1 = Teacher;
let getProfession person =>
  switch person {
  | Teacher => "A teacher"
  | Director => "A director"
  };
```

Without import/export statements, the above is wrapped as a module `School` and accessible throughout my project.

Consiquently, Ocaml/Reason allows nested modules.

```
/* school.re */
type profession = Teacher | Director;

let person1 = Teacher;
let getProfession person =>
  switch person {
  | Teacher => "A teacher"
  | Director => "A director"
  };

module GPA {...};
module Records = {...};
module Rooms = {...};
```

These are accessible through the `School` module like so: `School.GPA`

#### My initial reaction
As a n00b, this is super weird. It feels unscalable.

However, as a fan of flat organization patterns, I'm cautiously excited.


#### References
[Reason on Modules](https://reasonml.github.io/guide/language/module)  
[What's in a language, Cheng Lou](https://www.youtube.com/watch?v=24S5u_4gx7w)  
