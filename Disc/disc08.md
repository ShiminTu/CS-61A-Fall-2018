### 4.1
```
(define (factorial x)
	(if (> x 0) 
		(* x (factorial (- x 1))) 1
	)
)
```

### 4.2
```
(define (fib n)
	(cond 
		((= n 1) 0)
		((= n 2) 1)
		(else (+ (fib (- n 1)) (fib (- n 2))))
	)
)
```

### 5.1
```
(define (concat a b)
	(cond 
		((null? a) b)
		(else (cons (car a) (concat (cdr a) b)))
	)
)
```

### 5.2
```
(define (replicate x n)
	(if (= n 1) (cons x nil)
		(cons x (replicate x (- n 1)))
	)
)
```

### 5.3
```
(define (uncompress s)
	(if (null? s) nil 
		(concat (replicate (car (car s)) (car (cdr (car s)))) (uncompress (cdr s)))
	) 
)
```

### 5.4
```
(define (map fn lst)
	(if (null? lst) nil
		(cons (fn (car lst)) (map fn (cdr lst)))
	)
)
```
### 5.5
```
(define (deep-map fn lst)
	(cond
		((null? lst) nil)
		((list? (car lst)) (cons (deep-map fn (car lst)) (deep-map fn (cdr lst))))
		(else (cons (fn (car lst)) (deep-map fn (cdr lst))))
	)
)
```

### 