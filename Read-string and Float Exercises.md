# Read-string and Float Exercises

## Examples and exercise on `read-string`

```clojure

; Function 1: Read-string
; Explanation: 
; This function reads a string and converts it into a number
; It takes (read-string  s) where s is the string you want to convert to a number
(read-string "954")  ; 954
(read-string "8")  ; 8
; Most useful when you need a number type when reading data
; It is good practice to put clojure.edn in the namespace for better clarity.

```

## Exercise and tests for `read-string`

```clojure

;; Exercise function 1:
; create a function called read-vector that uses the read-string 
; function to read the strings in the vector and convert them to a vector of numbers

(deftest read-vector-exercise
  (testing "read-vector function"
    (is (= [95 31 -12] (read-vector vector1)))
    (is (= '() (read-vector vector2)))))
```

## Examples for `float`

```clojure
; Function 2: Float
; Explanation:
; This function takes a fraction and converts into a decimal
; It takes (float  n) where n is the number your trying to convert
(float  3/4) ;0.75
(float  1.2222223) ; 1.2222223
;(float ) ; syntax error
; Most useful when you want numbers to be more readable


```
## Exercise and tests for `float`

```clojure

; create a function that takes two integers that outputs a decimal point number of their ratio
; function must be called ratio-magic.


; for the sake of sanity we did not include tests with more precision because of bit pattern mismatch.
; this would require an additional line in the namespace as well as bloating the tests. 

(deftest ratio-magic-exercises
  (testing "ratio-magic function"
    (is (= 0.75 (ratio-magic 3 4)))
    (is (== -0.75 (ratio-magic -3 4)))))

```
