# Subvec and Partition-by Tutorial

## Examples and exercise on `subvec`

```clojure

;; Function 1, subvec: subvec is a function which takes a vector and 1 or 2 numbers, 1st (start) 
;; 2nd (end). function looks like 

(subvec [1 2 3 4 5] 2 4) ;; returns [3 4]
  
;; The function returns the values as a vector of the given indices, starting with the first 
;; given number and up to but not including the 2nd given number. Index 2 returns 3 (remember
;; vectors start with 0 as the first index), index 3 returns 4, so the full output would be 
;; [3 4]. If you dont put in a number for the ending index: 

(subvec [1 2 3 4 5] 2) ;; returns [3 4 5]

;; it goes until the end of the vector and the output would be [3 4 5]. If the indices are the same, 
;; for example 

(subvec [1 2 3 4 5] 1 1) ;; returns []

;; this means that there are no numbers between index 1 and 1, meaning that the output is an empty vector []

;; Question 1: Write a function that will take a vector of size n, and returns the subvector 0-n/2, n/2 rounded
;; down

;; Suggested tests (in core_test.clj):

(deftest test-one
  (testing "Testing the solution to the first problem."
    (is (= [0 1] (solution-1 [0 1 2 3 4])))
    (is (= [0 1 2] (solution-1 [0 1 2 3 4 5])))))
```

## EXamples and exercise for `partition-by`

```clojure

;; Function 2, partition-by: partition-by takes a predicate and a list/vector and paritions them when the
;; predicate returns a new value

(partition-by even? [2 1 4 6 5 7]) ;; returns ((2) (1) (4 6) (5 7))

;; would return ((2) (1) (4 6) (5 7)). Notice how it only groups things that are in order rather than 
;; anything that is even in the whole vector. The function also works with strings: 

(partition-by count ["hi" "as" "dog" "cat" "computer"]) ;; returns (("hi" "as") ("dog" "cat") ("computer"))

;; will return (("hi" "as") ("dog" "cat") ("computer")). If the collection is empty: 

(partition-by even? []) ;; returns ()

;; If the collection never changes 

(partition-by even? [2 4 6 8]) ;; returns ((2 4 6 8))

;; It will return a lazy sequence containing the whole collection

;; Question 2: Write a function that takes a vector and a number, and partitions till you reach a number less
;; than or equal to that number

;; Suggested tests (in core_test.clj):

(deftest test-two
  (testing "Testing the solution to the second problem."
    (is (= '((0 0) (3) (1 2)) (solution-2 [0 0 3 1 2] 3)))
    (is (= '((0 0 3 2 1)) (solution-2 [0 0 3 2 1] 4))))) 

```
