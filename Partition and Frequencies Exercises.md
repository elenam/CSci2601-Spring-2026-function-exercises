# Partition and Frequencies Exercises

## Examples and exercise on `partition`

```clojure

;; I chose the function partition, which returns a lazy sequence of lists of n items each, at offsets step apart.

;;First Partition 
;;common use
(println (partition 2 [1 2 3 4]))

;;leftover elements ignored 
(println (partition 3 [1 2 3 4 5]))

;; Edge case: empty input
(println (partition 2 []))
```

## Exercise and tests for `read-string`

```clojure

;; Exercise function 1:
;; write a function that takes a list of numbers and groups them into pairs.

;; Tests (in test_core.clj)

(deftest group-pairs-test
  (testing "checks group pairs"
    (is (= '((1 2) (3 4)) (group-pairs [1 2 3 4])))
    (is (= '() (group-pairs [])))))
```

## Examples for `frequencies`

```clojure

;;Second Function is frequencies
;;frequencies counts how many times each element appears in a sequence and returns a map.

;;common use
(println (frequencies [:a :b :a :c :a]))

;;with numbers 
(println (frequencies [1 2 2 3 3 3]))

;;Edge case:Empty set
(println (frequencies []))

```
## Exercise and tests for `frequencies`

```clojure

;; Write a function that finds the most common element in a list.


;; Tests (in test_core.clj)

 (deftest frequencies-test
   (testing "finds the most common element in  list"
    (is (= 3 (most-common [1 2 2 3 3 3]))))
    (is (= :a (most-common [:a :b :a :c :a]))))

```
