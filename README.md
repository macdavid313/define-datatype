# define-datatype
port of define-datatype from EOPL, code modified from [chenyukang/eopl](https://github.com/chenyukang/eopl/blob/master/libs/define-datatype.scm).

## Example usage
```scheme
(import (define-datatype))

(define-datatype shape shape?
  (rectangle
   (width flonum?)
   (length flonum?))
  (circle
   (radius flonum?)))

(define area
  (lambda (s)
    (cases shape s
           (rectangle (width length) (fl* width length))
           (circle (radius) (fl* 3.1415926 radius radius)))))

(define s1 (rectangle 2.0 3.0))
s1 ;; => (rectangle 2.0 3.0)
(shape? s1) ;; =? #t
(area s1) ;; => 6.0

(define s2 (circle 3.0))
s2 ;; => (circle 2.0 3.0)
(shape? s2) ;; =? #t
(area s2) ;; => 28.274333400000003
```
