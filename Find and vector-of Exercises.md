# Find and vector-of Exercises

## Examples and exercise on `find`

```clojure

;; Function 1: find

;; (find m kk)
;; returns the key entry in a map if it exists otherwise it returns nil

;; Case 1: passing an argument that is not a map

(println (find ["vector" "for example"] :a))

;; Case 2: finding map entry based off key
(def scores {:timberwolves 119 :nuggets 93 :knicks 108 :hawks 109})
(find scores :timberwolves)
;; => [:timberwolves 119]

;; Case 3 (Edge): Empty Map
(find {} :a)
;; => nil

```

## Exercise and tests for `find`

```clojure

;; Exercise function 1:
;; Write a function get-entry-details that takes a collection
;; and a target key. If the entry exists it should return
;; "Found [key] with value [value]"
;; and if it doesn't exist it should return
;; "Item not found"

(deftest test-get-entry-details
  (testing "get-entry-details function"
    (is (= (get-entry-details {:a 3 :b 4 :c 6 :d 7} :a) "Found :a with value 3"))
    (is (= (get-entry-details {:hairline "nonexistent" :eyebrow "non-existent"} :canthal_tilt) "Item not found"))
    (is (= (get-entry-details {} :nail) "Item not found"))))
```

## Examples for `vector-of`

```clojure
;; Function 2: vector-of


;; (vector-of type), (vector-of type items)
;; creates a vector of a specified type and if items are provided, initializes it with the given items

;; case 1 (edge): creating a vector of a type without items

(vector-of :int)
;; => []

;; case 2: creating a float type vector with some items

(vector-of :float 1.0 2.0 3.0) ;; => [1.0 2.0 3.0]


;; case 3 : inputting a float in int vector

(vector-of :int 1 2 3.9)
;; => [1 2 3]   ;; gets truncated to int


```
## Exercise and tests for `vector-of`

```clojure

;; Exercise function 2
;; Write a function that takes a collection and creates an int vector from it.


(deftest test-make-int-vector
  (testing "make-int-vector function"
    (is (= (make-int-vector [1 2 3]) [1 2 3]))
    (is (= (make-int-vector [2 3.5 4.5]) [2 3 4]))
    (is (= (make-int-vector []) []))))

```
