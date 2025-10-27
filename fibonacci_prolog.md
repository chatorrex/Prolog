<div align="center">

# Instituto Tecnológico de Morelia

---

## Ingenieria en Sistemas Computacionales
## Programación Lógica y Funcional

---

### Serie de Fibonacci en Prolog
### Dylan Barranco Vargas

---

</div>

#### Objetivo 
**Aprender a utilizar recursión en Prolog mediante la generación de la serie de Fibonacci hasta un número especificado por el usuario.**

---



**Caso base: los dos primeros terminos**
```prolog
fibonacci(0, 0).
fibonacci(1, 1).
```

**Regla recursiva para calcular el enesimo término**
```prolog
fibonacci(N, F) :-
    N > 1,
    N1 is N - 1,
    N2 is N - 2,
    fibonacci(N1, F1),
    fibonacci(N2, F2),
    F is F1 + F2.
```

**Mostrar la serie hasta un número dado**
```prolog
serie_fibonacci(Limite) :-
    mostrar_fibonacci(0, Limite).
```

**Caso base: cuando ya se alcanzó el límite**
```prolog
mostrar_fibonacci(N, Limite) :-
    N > Limite, !.
```

**Caso recursivo: imprime el valor y sigue calculando**
```prolog
mostrar_fibonacci(N, Limite) :-
    fibonacci(N, F),
    write(F), write(' '),
    N1 is N + 1,
    mostrar_fibonacci(N1, Limite).
```

**Consulta**
```prolog
?- serie_fibonacci(10).
```
