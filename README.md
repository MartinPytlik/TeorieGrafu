# TeorieGrafu

Definice grafu
Graf je matematická struktura složená z množiny vrcholů (uzlů) a hran (spojnic) mezi nimi.
Typy grafů:
•	Neorientovaný graf – hrany nemají směr (např. propojení měst silnicemi).
•	Orientovaný graf – hrany mají směr (např. jednosměrné cesty).
•	Ohodnocený graf – každá hrana má přiřazenou hodnotu (např. délku, cenu, čas).
________________________________________
Kostra grafu
Kostra grafu je podmnožina hran neorientovaného grafu, která:
•	propojuje všechny vrcholy,
•	neobsahuje cykly,
•	má minimální součet vah hran (např. při pokládání kabeláže mezi městy).
________________________________________
Matice sousednosti vs. seznam sousedů
•	Matice sousednosti – dvourozměrné pole, kde prvek na pozici [i][j] udává váhu hrany mezi vrcholy i a j. Pokud hrana neexistuje, bývá zde 0 nebo nekonečno. Vhodné pro husté grafy s velkým počtem hran.

•	Seznam sousedů – každý vrchol má svůj vlastní seznam, ve kterém jsou zapsáni sousední vrcholy a váhy hran k nim. Efektivní pro řídké grafy s menším počtem hran.
________________________________________
Reálné příklady využití grafů
•	Navigace a mapy – hledání nejkratších cest (např. Google Maps).
•	Počítačové sítě – přepínání paketů nejrychlejší cestou.
•	Plánování a závislosti úloh – orientované acyklické grafy.
•	Sociální sítě – propojení uživatelů, vliv a dosah.
________________________________________
2. Problém hledání nejkratší cesty
Co znamená „nejkratší cesta“?
Hledání cesty mezi dvěma vrcholy, jejíž součet vah hran je nejmenší (např. nejkratší vzdálenost, nejmenší čas, nejnižší náklady).
Negativní hrany a jejich vliv
•	Umožňují snižovat celkové náklady (např. sleva).
•	Problém: některé algoritmy (např. Dijkstra) s nimi nefungují správně.
•	Pokud je v grafu záporný cyklus, nejkratší cesta není definována – lze jezdit dokola a zkracovat ji do nekonečna.
________________________________________
3. Přehled algoritmů
a) Dijkstrův algoritmus
•	Princip: Greedy přístup – vždy vybíráme nejbližší vrchol. Používá prioritní frontu.
•	Omezení: Nepracuje správně s negativními hranami.
•	Časová složitost:
o	Pomocí haldy (min-heap): O((V + E) log V)
o	V – počet vrcholů, E – počet hran
________________________________________
b) Bellman-Fordův algoritmus
•	Princip: Opakovaná relaxace všech hran (až V−1 iterací).
•	Výhoda: Funguje i při záporných hranách.
•	Detekuje záporné cykly.
•	Časová složitost: O(V·E)
________________________________________
c) Floyd-Warshallův algoritmus
•	Princip: Dynamické programování, pro všechny dvojice vrcholů.
•	Použití: Hledání všech nejkratších cest mezi všemi dvojicemi.
•	Časová složitost: O(V³)
