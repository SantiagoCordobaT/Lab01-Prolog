#1)

pertenece(X, [X | _]).
pertenece(X, [_ | Cola]) :- pertenece(X, Cola).

#2)

mi_longitud([], 0).
mi_longitud([_ | Cola], N) :- mi_longitud(Cola, N_Cola), N is N_Cola + 1.

#3)

concat([], L, L).
concat([X|L1], L2, [X|L3]) :- concat(L1, L2, L3).

#4) 

fibo(0,0).
fibo(1,1).
fibo(N, R) :- N > 1, N1 is N - 1, N2 is N - 2, fibo(N1, R1), fibo(N2, R2), R is R1 + R2.

l_fibo(0, [0]).
l_fibo(N, LF) :- N > 0, N1 is N - 1, l_fibo(N1, LAnt), fibo(N, VActual), append(LAnt, [VActual], LF).

#5)

reverso([], []).
reverso([Head | Tail], R) :- reverso(Tail, TailInv), append(TailInv, [Head], R).

#6)

reverso([], []).
reverso([Head | Tail], R) :- reverso(Tail, TailInv), append(TailInv, [Head], R).

palindroma(Lista) :- reverso(Lista, Lista).