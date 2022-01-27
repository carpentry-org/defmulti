# defmulti

WIP

is a simple attempt at bringing multiple dispatch to Carp (see also
carp-lang/carp#1072).

Because it is a mere macro, the functions only work in call position and
can’t be used in higher-order functions.

## Usage

```clojure
(load "defmulti.carp")

(defmulti addr
  [] 0
  [x] (+ x 1)
  [x y (f +)] (f x y))

(defn main []
  (do
    (println* (addr))
    (println* (addr 1))
    (println* (addr 4 3))
    (println* (addr 4 3 (f -)))
    (println* (addr 4 3 *))))
```

<hr/>

Have fun!
