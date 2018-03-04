Cornita Nicusor-Razvan, 335CB

Tema a fost realizata utilizand scheletul dat. Algoritmul ales de mine, pe care urmeaza sa il detaliez ulterior, este urmatorul: pentru fiecare sarpe, se cauta coada lui. Apoi, pentru fiecare pas: se fac urmatoarele lucruri: se sterge coada, se muta capul in directia respectiva daca nu are loc coliziune, iar daca are loc coliziune, se reface matricea de la pasul anterior.

Pentru fiecare sarpe, am definit o structura de coord drept coada fiecaruia. Apoi, pentru fiecare sarpe, am inceput cautarea in matrice de la pozitia capului, atribuindu-i cozii pozitia capului. Am verificat daca celula de deasupra, de dedesubt, din stanga sau din dreapta are acelasi encoding cu celula cozii, caz in care am modificat coordonatele cozii in directia respectiva. Facem asta pana cand nu mai gasim o continuare a sarpelui. Pentru a nu ne intoarce la o celula deja vizitata, am creat 4 flaguri pe care le activez in functie de ultima directie de deplasare a cozii.

Pentru fiecare pas, am facut urmatoarele lucruri: Am sters coada sarpelui (fara a modifica coordonatele lui. Ele nu se modifica acum deoarece in caz de coliziune, e necesara cunoasterea ultimei pozitii a cozii), am mutat capul in directia de deplasare a sarpelui si am verificat daca are loc o coliziune. In final, daca nu exista coliziune, modific coordonatele cozii, iar daca exista, sterg capul, refac coada si restabilesc fosta coordonata a capului.

Pentru a verifica scalabilitatea, am rulat programul pe clusterul facultatii, pe 1, 2, 4, respectiv 8 threaduri. Rezultatele medii sunt urmatoarele (in paranteza sunt toate rezultatele):

- 1 thread: 1,45s (1.8861, 1.0979, 1.8865, 0.9304);
- 2 threaduri: 0.95s (1.0638, 0.9523, 0.9310, 0.8928);
- 4 threaduri: 0,8s (0.7580, 0.8273, 0.8617, 0.7540);
- 8 threaduri: 0,46s (0.4722, 0.4699, 0.4624, 0.4671).

In concluzie, cu 1 thread, programul se executa in medie in 1,5 secunde, iar cu 8 threaduri, acest timp se reduce cu o secunda (timpul mediu de 0,5s).


