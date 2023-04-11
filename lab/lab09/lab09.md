# Q3
```
(define (over-or-under x y)
	     (cond 
	         ((< x y) -1)
	         ((= x y) 0)
	         (else 1)))
```
# Q4
```
(define (filter f lst)
    (cond 
        ((null? lst) nil)
        ((f (car lst)) (cons (car lst) (filter f (cdr lst))))
        (else (filter f (cdr lst)))))
```

# Q5
```
(define (make-adder num)
	(lambda (x) (+ x num))
)
```

# Q6
```
(cons (cons 1 ()) (cons 2 (cons (cons 3 (cons 4 ())) (cons 5 ()))))

(list (list 1) 2 (list 3 4) 5)

'((1) 2 (3 4) 5)

```

# Q7
```
(define (composed f g)
        (lambda (x) (f (g x)))
)
```

# Q8
```
(define (remove item lst)
	(filter (lambda (x) (not (= item x))) lst)
)
```

# Q9
```
(define (no-repeats s)
  (if (null? s) nil
	  (cons (car s)
		(no-repeats (filter (lambda (x) (not (= x (car s)))) (cdr s)))
	  )
  )
)
```

# Q10
```
(define (substitute s old new)
	(cond 
		((null? s) nil)
		((pair? (car s)) (cons (substitute (car s) old new) (substitute (cdr s) old new)))
		((equal? (car s) old) (cons new (substitute (cdr s) old new)))
		(else (cons (car s) (substitute (cdr s) old new)))
	)
)
```

# Q11
```
(define (sub-all s olds news)
  (if (null? olds) s
	(sub-all (substitute s (car olds) (car news)) (cdr olds) (cdr news))
  )
)
```


















