<div align="center">

# Instituto Tecnológico de Morelia

---

## Ingenieria en Sistemas Computacionales
## Programación Lógica y Funcional

---

### Ejercicios Prolog 22/10/25
### Dylan Barranco Vargas

---

</div>

#### Objetivo 
**Aprender a manipular listas en Prolog mediante ejercicios básicos de definición, acceso, recursión y construcción de predicados.**

---

**Ejercicio 1: Cabeza y cola de una lista**
Define un predicado que permita obtener la cabeza y la cola de una lista
```prolog
cabeza_y_cola([Cabeza|Cola], Cabeza, Cola).
```

Consulta: 
```prolog
?- cabeza_y_cola([a,b,c,d], C, T).
```

**Ejercicio 2: Verificar si un elemento pertenece a una lista**
Crea un predicado pertenece que determine si un elemento se encuentra en una lista.
```prolog
pertenece(X, [X|_]).
pertenece(X, [_|T]) :- pertenece(X, T).
```

Consulta: ?- 
```prolog
pertenece(b, [a,b,c]).
```

**Ejercicio 3: Calcular la longitud de una lista**
Define un predicado longitud que devuelva la cantidad de elementos de una lista.
```prolog
longitud([], 0).
longitud([_|T], N) :-
    longitud(T, N1),
    N is N1 + 1.
```

Consulta: 
```prolog
?- longitud([a,b,c,d], N).
```

**Ejercicio 4: Concatenar dos listas**
Crea el predicado concatenar que una dos listas.
```prolog
concatenar([], L, L).
concatenar([X|L1], L2, [X|L3]) :-
    concatenar(L1, L2, L3).
```

Consulta: 
```prolog
?- concatenar([1,2], [3,4], R).
```

**Ejercicio 5: Invertir una lista**
Escribe un predicado invertir que invierta el orden de los elementos.
```prolog
invertir([], []).
invertir([X|T], R) :-
    invertir(T, RT),
    concatenar(RT, [X], R).
```

Consulta: 
```prolog
?- invertir([a,b,c,d], R).
```

**Ejercicio 6: Obtener el último elemento**
Crea el predicado ultimo que retorne el último elemento de una lista.
```prolog
ultimo([X], X).
ultimo([_|T], X) :-
    ultimo(T, X).
```

Consulta: 
```prolog
?- ultimo([a,b,c,d], X).
```

**Ejercicio 7: Sumar los elementos de una lista numérica**
Define un predicado suma_lista que calcule la suma de los elementos de una lista de números.
```prolog
suma_lista([], 0).
suma_lista([X|T], S) :-
    suma_lista(T, S1),
    S is X + S1.
```

Consulta: 
```prolog
?- suma_lista([2,4,6,8], S).
```

**Ejercicio 8: Eliminar un elemento de una lista**
Crea un predicado eliminar que elimine la primera aparición de un elemento en una lista.
```prolog
eliminar(_, [], []).
eliminar(X, [X|T], T) :- !.
eliminar(X, [Y|T], [Y|R]) :-
    eliminar(X, T, R).
```

Consulta: 
```prolog
?- eliminar(c, [a,b,c,d,c], R).
```

**Ejercicio 9: Duplicar los elementos de una lista**
Escribe un predicado duplicar que duplique cada elemento de una lista.  
```prolog
duplicar([], []).
duplicar([X|T], [X,X|R]) :-
    duplicar(T, R).
```

Consulta: 
```prolog
?- duplicar([a,b,c], R).
```

**Ejercicio 10: Intercalar dos listas**
Crea un predicado intercalar que mezcle los elementos de dos listas alternándolos.  
```prolog
intercalar([], L, L).
intercalar(L, [], L).
intercalar([X|T1], [Y|T2], [X,Y|R]) :-
    intercalar(T1, T2, R).
```

Consulta: 
```prolog
?- intercalar([1,3,5], [2,4,6], R).
```
