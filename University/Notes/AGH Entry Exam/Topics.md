### **1. Podstawy systemów komputerowych i reprezentacji danych***

1. **[[Systemy liczbowe]]**:
    - Konwersja między systemami liczbowymi (dziesiętny, binarny).
    - Reprezentacja ułamków w systemie binarnym (np. $1/8 = 0.001$ w systemie binarnym).
    - **Pokrewne**: Konwersja między systemami o różnych podstawach (np. ósemkowy, szesnastkowy), reprezentacja liczb w systemie Graya.
2. **Kodowanie informacji**:
    - Ilość informacji w słowach o określonej liczbie znaków (entropia, prawdopodobieństwo znaków).
    - Kod ASCII: zakres kodowania ($0-127$), ograniczenia.
    - Kodowanie UTF-8: zastosowanie, kodowanie znaków UNICODE.
    - **Pokrewne**: Kodowanie BCD (Binary-Coded Decimal), kodowanie UTF-16 i UTF-32, entropia Shannona ($H = -\sum p_i \log_2 p_i$).
3. **Reprezentacja liczb w komputerze**:
    - Liczby stałopozycyjne: kod uzupełnień do dwóch (U2), cechy kodu U2 (np. brak podwójnej reprezentacji zera).
    - Liczby zmiennopozycyjne:
        - Struktura: mantysa, wykładnik, bit znaku.
        - Standard IEEE 754 (pojedyncza i podwójna precyzja, liczba bitów mantysy i wykładnika).
        - Dokładność liczb zmiennopozycyjnych: zależność od liczby bitów mantysy ($2^{-n}$).
        - Zakres reprezentacji: największa i najmniejsza liczba w systemie.
        - Obliczanie dokładności w cyfrach dziesiętnych (np. mantysa $20$ bitów: $\approx 10$ cyfr).
    - Minimalna liczba bitów do reprezentacji liczb zmiennopozycyjnych w danym zakresie i z określoną dokładnością.
    - **Pokrewne**: Rozszerzenia IEEE 754 (np. $80$-bitowa precyzja), problemy z przepełnieniem i niedomiar ($2^{128}$), kodowanie liczb w systemie znak-moduł.
4. **Bramki logiczne**:
    - Operacje logiczne realizowane przez bramki (AND, OR, NOT, NAND, NOR).
    - Działanie bramki NAND (iloczyn logiczny i negacja).
    - Realizacja wyrażeń boolowskich za pomocą kombinacji NAND i NOR (np. $p \land q = \sim (p \text{ NAND } q)$).
    - **Pokrewne**: Bramki XOR i XNOR, minimalizacja układów logicznych (np. metoda Karnaugh), projektowanie układów kombinacyjnych i sekwencyjnych.
5. **Przechowywanie informacji cyfrowej**:
    - Rola przerzutników w przechowywaniu danych (np. rejestry).
    - Stos systemowy: zastosowanie (np. zarządzanie wywołaniami funkcji, przechowywanie zmiennych lokalnych).
    - **Pokrewne**: Pamięć podręczna (cache), pamięć wirtualna (stronicowanie, segmentacja), rejestry procesora, pamięć RAM i ROM.
6. **Wskaźniki i adresowanie pamięci**:
    - Rozmiar zmiennej typu wskaźnik (np. $4$ bajty, adresowalna pamięć: $2^{32}$ bajtów).
    - Błędy związane z odwołaniami poza obszar tablicy (błędy wykonania, nie zawsze sygnalizowane).
    - **Pokrewne**: Wskaźniki w różnych językach programowania (np. C, C++), zarządzanie pamięcią (alokacja dynamiczna, wycieki pamięci), adresowanie w systemach 64-bitowych ($2^{64}$ bajtów).

### **2. Algorytmy i struktury danych**

1. **Podstawy algorytmów**:
    - Definicja algorytmu (uporządkowany zbiór operacji).
    - Złożoność algorytmiczna:
        - Notacja $O$ (np. $O(n^2)$, $O(n \log n)$, $O(n)$).
        - Interpretacja złożoności (np. liczba porównań w sortowaniu $O(n^2)$).
    - **Pokrewne**: Notacje $\Omega$ i $\Theta$, złożoność pamięciowa algorytmów (np. $O(n)$ dla quicksort), analiza amortyzowana (np. dynamiczne tablice).
2. **Metody sortowania**:
    - Złożoność czasowa metod sortowania:
        - $O(n^2)$: metoda bąbelkowa, metoda prostego wstawiania (stabilność).
        - $O(n \log n)$: quicksort, mergesort (błędne przypisanie metody licznikowej).
        - $O(n)$: metoda licznikowa (błędne przypisanie, faktycznie $O(n + k)$).
    - Ekstensywność sortowania (zależność czasu od rozmiaru tablicy).
    - Stabilność sortowania (np. metoda prostego wstawiania).
    - **Pokrewne**: Sortowanie przez zliczanie, sortowanie kubełkowe ($O(n)$), sortowanie przez kopcowanie (heapsort, $O(n \log n)$), analiza przypadków (najlepszy, średni, najgorszy).
3. **Wyszukiwanie w tablicach**:
    - Wyszukiwanie sekwencyjne (dla posortowanych i nieposortowanych tablic).
    - Haszowanie: kolizje adresowe (np. identyczne klucze).
    - **Pokrewne**: Wyszukiwanie binarne ($O(\log n)$), haszowanie z otwartym adresowaniem, haszowanie z łańcuchami, funkcje haszujące (np. modulo, mnożenie).
4. **Drzewa binarne**:
    - Drzewa BST (Binary Search Tree): definicja, właściwości.
    - Drzewa AVL: definicja (balansowanie, różnica rozmiarów poddrzew $\leq 1$).
    - Złożoność wyszukiwania w drzewach AVL (logarytmiczna, $O(\log n)$).
    - Drzewa binarne pełne: liczba węzłów na $N$ poziomach ($2^N - 1$).
    - Przeglądanie drzew binarnych (możliwość bez wskazania na ojca).
    - **Pokrewne**: Drzewa czerwono-czarne (balansowanie, $O(\log n)$), drzewa B i B+ (zastosowanie w bazach danych), drzewa trie (wyszukiwanie prefiksów), drzewa segmentowe (złożoność $O(\log n)$).
5. **Grafy**:
    - Drzewo rozpinające: definicja, liczba wierzchołków i krawędzi ($n-1$ krawędzi).
    - Cykle Hamiltona w grafie pełnym ($K_n$, liczba cykli: $\frac{(n-1)!}{2}$).
    - **Pokrewne**: Algorytmy DFS i BFS (złożoność $O(V + E)$), najkrótsza ścieżka (Dijkstra, Bellman-Ford, $O(V \log V)$, $O(VE)$), maksymalny przepływ (Ford-Fulkerson), grafy skierowane i nieskierowane.

### **3. Języki programowania i formalne**

1. **Podstawy języków formalnych**:
    - Definicja języka formalnego (zbiór ciągów znaków, nie zapis algorytmów w blokach).
    - **Pokrewne**: Języki regularne, wyrażenia regularne, relacja z automatami skończonymi.
2. **Składnia i semantyka języków programowania**:
    - Syntaktyka: reguły budowy poprawnych instrukcji.
    - Semantyka: znaczenie instrukcji (różnice między syntaktyką a semantyką).
    - **Pokrewne**: Gramatyki bezkontekstowe, parsery LR i LL, semantyka operacyjna, analiza składniowa.
3. **Notacja EBNF**:
    - Znaczenie nawiasów w EBNF (np. $<\text{element}>$ – element opcjonalny).
    - **Pokrewne**: Rozszerzona notacja BNF, zastosowanie w kompilatorach, relacja z gramatykami formalnymi.
4. **Odwrotna Notacja Polska (ONP)**:
    - Zasady zapisu wyrażeń w ONP (brak nawiasów).
    - Obliczanie wyrażeń w ONP (np. $2 , 3 , 4 , 5 , + , * , + = 25$).
    - Nawiasy w ONP (brak potrzeby, błędne przypisanie ${}$).
    - **Pokrewne**: Notacja postfiksowa i prefiksowa, konwersja między notacjami (np. z infiksowej na ONP), stos w obliczeniach ONP, zastosowanie w kompilatorach i kalkulatorach.
### **4. Matematyka: analiza matematyczna**

1. **Ciągi i granice**:
    - Obliczanie granic ciągów (np. $a_n = \frac{3n+3}{2+5+8+\dots+(3n-1)}$).
    - Granice funkcji trygonometrycznych (np. $\lim_{x \to 0} \frac{\sin(x)}{x} = 1$).
    - Granice logarytmiczne (np. $\lim_{x \to +\infty} \frac{\ln(x^2 - 1)}{\ln(x - 1)}$).
    - **Pokrewne**: Szeregi liczbowe (np. $\sum_{n=0}^{\infty} r^n = \frac{1}{1-r}$ dla $|r| < 1$), testy zbieżności (Cauchy'ego, d'Alemberta), granice funkcji wielu zmiennych (np. $\lim_{(x,y) \to (0,0)} \frac{xy}{x^2 + y^2}$), szeregi potęgowe.
2. **Pochodne**:
    - Obliczanie pochodnych funkcji trygonometrycznych (np. $f(x) = \frac{\sin(x)}{\sin(x) + \cos(x)}$, $f'(x) = \frac{\cos(x)(\sin(x) + \cos(x)) - \sin(x)(\cos(x) - \sin(x))}{(\sin(x) + \cos(x))^2}$).
    - Pochodne funkcji logarytmicznych i wykładniczych (np. $f(x) = \ln(e^{-x} + 1)$, $f'(x) = \frac{-e^{-x}}{e^{-x} + 1}$).
    - **Pokrewne**: Pochodne cząstkowe wyższych rzędów (np. $\frac{\partial^2 f}{\partial x \partial y}$), reguła L'Hôpitala (np. $\lim_{x \to 0} \frac{\sin(x)}{x}$), pochodne kierunkowe, gradient funkcji ($ \nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right) $).
3. **Ekstrema funkcji wielu zmiennych**:
    - Znajdowanie minimów i maksimów (np. $f(x, y) = 2x^2 + y^2 - 5xy$, minimum w $(0, 0)$ – błędne, należy sprawdzić pochodne cząstkowe: $\frac{\partial f}{\partial x} = 4x - 5y$, $\frac{\partial f}{\partial y} = 2y - 5x$).
    - **Pokrewne**: Test drugiej pochodnej dla funkcji wielu zmiennych (macierz Hesjanu, $\det(H)$), ekstrema warunkowe (metoda Lagrange'a, np. $f(x, y)$ przy warunku $g(x, y) = c$), analiza siodeł.
4. **Całki**:
    - Całki oznaczone (np. $\int_0^\pi x \sin(x) , dx = \pi$).
    - Całki nieoznaczone (np. $\int (x^2 + x) , dx = \frac{x^3}{3} + \frac{x^2}{2} + C$).
    - Całki wielokrotne (np. $\iiint_\Omega , dz , dx , dy$, gdzie $\Omega = {(x, y, z) \in \mathbb{R}^3 : |x| + |y| \leq 1, (z-3)(z+3) \leq 0}$, wartość: $6$).
    - **Pokrewne**: Całki podwójne w układzie biegunowym (np. $\iint_R x^2 + y^2 , dA$), całki potrójne w układzie sferycznym, twierdzenie Greena, twierdzenie Stokesa, całki niewłaściwe (np. $\int_0^\infty e^{-x} , dx$).

### **5. Matematyka: algebra liniowa**

1. **Liczby zespolone**:
    - Postać wykładnicza liczb zespolonych (np. $2e^{i\pi/3} = 1 + i\sqrt{3}$, $2 + 2i = 2\sqrt{2} e^{i\pi/4}$).
    - Rozwiązanie równań zespolonych (np. $\frac{z+1}{z-1} = (i-1)^2$, rozwiązanie: $z = \frac{21}{13} + \frac{1}{13}i$).
    - Pierwiastki zespolone (np. pierwiastki stopnia 2 z $4i$: $\sqrt{2} + i\sqrt{2}$ oraz $-\sqrt{2} - i\sqrt{2}$).
    - **Pokrewne**: Wzory de Moivre'a ($(\cos \theta + i \sin \theta)^n = \cos(n\theta) + i \sin(n\theta)$), równania zespolone wyższych stopni (np. $z^3 = i$), analiza zespolona (np. funkcje analityczne).
2. **Wektory i bazy**:
    - Warunki na bazę przestrzeni $\mathbb{R}^4$ (np. liniowa niezależność wektorów: ${(1, 1, \alpha, \alpha), (1, \alpha, 1, 1), (\alpha, \alpha, 1, 1), (1, \alpha, 1, \alpha)}$, warunek: $\alpha \neq 0$).
    - Współrzędne wektora w danej bazie (np. wektor $(2, 4, 1)$ w bazie ${(1, 1, 1), (-1, 1, 1), (1, -1, 1)}$, współrzędne: $(3, -\frac{1}{2}, -\frac{3}{2})$).
    - **Pokrewne**: Ortogonalność wektorów (np. proces Grama-Schmidta), podprzestrzenie wektorowe, wymiar przestrzeni, baza ortonormalna, rzut wektora na podprzestrzeń.
3. **Macierze**:
    - Wyznaczniki macierzy (np. macierz $3 \times 3$: $\begin{bmatrix} 1 & 0 & 1 \ 0 & 1 & 0 \ 1 & 1 & 1 \end{bmatrix}$, wyznacznik: $0$; macierz $A \in \mathbb{R}^{n \times n}$, gdzie $A^T A = -A$, wyznacznik ujemny dla $n$ parzystego).
    - Rząd macierzy (np. macierz $4 \times 4$: $\begin{bmatrix} 1 & 0 & 1 & 1 \ 0 & 1 & 0 & 1 \ 0 & 0 & 0 & 1 \ 0 & 0 & 0 & 0 \end{bmatrix}$, rząd: $3$; macierz $\begin{bmatrix} 1 & 2 & -1 & -2 \ 1 & 2 & 1 & 0 \ -1 & -2 & 4 & 5 \end{bmatrix}$, rząd: $3$).
    - Wartości własne odwzorowań liniowych (np. $f: \mathbb{R}^2 \to \mathbb{R}^2$, $f(x, y) = (x + y, 3x - y)$, wartości własne: $\lambda = 1, 2$).
    - Pole powierzchni obrazu odwzorowania liniowego (np. $f: \mathbb{R}^2 \to \mathbb{R}^2$, $f(x, y) = (x - y, 2x + 2y)$, $\Omega = {(x, y) \in \mathbb{R}^2 : |x| + |y| \leq 1}$, pole obrazu: $16$).
    - **Pokrewne**: Rozkład macierzy (LU, QR, SVD), macierze dodatnio określone (test Sylvestera), macierze hermitowskie i unitarne, normy macierzy (Frobeniusa, spektralna), twierdzenie o rzędzie i defekcie
### **6. Rachunek prawdopodobieństwa i statystyka**

1. **Problemy kombinatoryczne i geometryczne**:
    - Prawdopodobieństwo tworzenia trójkąta z losowego podziału odcinka na 3 części (warunki na trójkąt, np. suma dwóch boków większa od trzeciego: $a + b > c$,
	- Prawdopodobieństwo tworzenia trójkąta z losowego podziału odcinka na 3 części (warunki na trójkąt, np. suma dwóch boków większa od trzeciego: $a + b > c$, $a + c > b$, $b + c > a$).
	- Prawdopodobieństwo zdarzeń w eksperymentach losowych (np. losowanie pudełek z ciastkami, zastosowanie wzoru Bayesa: $P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$).
	- **Pokrewne**: Prawdopodobieństwo geometryczne (np. losowy punkt w kole, kwadracie), kombinatoryka (permutacje, kombinacje, $\binom{n}{k}$), zasada szufladkowa Dirichleta, problemy z urnami i kulami.
2. **Zmienne losowe**:
    - Wartość oczekiwana zmiennej losowej (np. różnica oczek w rzucie dwiema kostkami: $X = |X_1 - X_2|$, większa liczba oczek: $X = \max(X_1, X_2)$).
    - Mediana zmiennej losowej (np. mediana większej liczby oczek w rzucie dwiema kostkami: $\text{mediana} = 5$).
    - Gęstość rozkładu zmiennej losowej (np. określenie stałej $c$ dla funkcji gęstości: $f(x) = \begin{cases} c x^2 & \text{dla } x \geq 2 \ 0 & \text{dla } x < 2 \end{cases}$, gdzie $\int_{-\infty}^{\infty} f(x) , dx = 1$).
    - Dystrybuanta rozkładu (np. rozkład jednostajny na przedziale $[1, 4]$, dystrybuanta w punkcie $x = 3$: $F(x) = \frac{x - 1}{4 - 1}$ dla $x \in [1, 4]$).
    - **Pokrewne**: Wariancja i odchylenie standardowe zmiennej losowej ($Var(X) = E[(X - E[X])^2]$), momenty zmiennej losowej (np. $E[X^k]$), funkcje charakterystyczne, transformata Laplace'a.
3. **Rozkłady prawdopodobieństwa**:
    - Rozkłady dyskretne: dwumianowy ($P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}$), Poisson ($P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}$).
    - Rozkłady ciągłe: normalny ($f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$, symetryczny), jednostajny ($f(x) = \frac{1}{b-a}$ dla $x \in [a, b]$).
    - Symetria rozkładów (np. standardowy rozkład normalny: $\mu = 0$, $\sigma = 1$).
    - Zastosowanie rozkładów w modelowaniu (np. liczba goli w meczu – rozkład Poisson, nie normalny).
    - **Pokrewne**: Rozkład wykładniczy ($f(x) = \lambda e^{-\lambda x}$ dla $x \geq 0$), rozkład gamma, rozkład beta, rozkład $\chi^2$, rozkład t-Studenta, rozkład F, rozkłady wielowymiarowe (np. normalny wielowymiarowy).
4. **Testy diagnostyczne i Bayes**:
    - Czułość i swoistość testu diagnostycznego (czułość: $P(\text{pozytywny} | \text{chory})$, swoistość: $P(\text{negatywny} | \text{zdrowy})$).
    - Prawdopodobieństwo choroby przy pozytywnym wyniku testu (wzór Bayesa: $P(\text{chory} | \text{pozytywny}) = \frac{P(\text{pozytywny} | \text{chory}) \cdot P(\text{chory})}{P(\text{pozytywny})}$).
    - Prawdopodobieństwo bliźniąt jednojajowych (proporcja w populacji: $P(\text{jednojajowe}) = 0.08$).
    - **Pokrewne**: Wartość predykcyjna dodatnia (PPV) i ujemna (NPV), analiza ROC (krzywa charakterystyki odbiornika), prawdopodobieństwo warunkowe w złożonych eksperymentach, testy wielokrotne.
5. **Statystyka i regresja liniowa**:
    - Model liniowy $Y = \beta_0 + \beta_1 X + \varepsilon$:
        - Testy istotności predyktorów (p-wartość: $p < 0.05$ oznacza istotność).
        - Statystyki dopasowania modelu: RSE ($\text{RSE} = \sqrt{\frac{\sum (y_i - \hat{y}_i)^2}{n-2}}$), $R^2$ ($R^2 = 1 - \frac{\text{SSR}}{\text{SST}}$).
    - Rozkłady odniesienia w testach statystycznych (np. rozkład normalny dla współczynników regresji: $N(0, \sigma^2)$).
    - Przedziały ufności dla parametrów modelu liniowego (np. $\beta_1 \pm t_{\alpha/2} \cdot SE(\beta_1)$).
    - **Pokrewne**: Regresja wieloraka ($Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \varepsilon$), analiza wariancji (ANOVA), testy t-Studenta, testy $\chi^2$, testy F, estymacja parametrów (MLE, metoda momentów), analiza reszt.
### **7. Logika matematyczna i rachunek zdań**

1. **Podstawy logiki**:
    - Operacje logiczne: negacja ($\sim p$), koniunkcja ($p \land q$), alternatywa ($p \lor q$), implikacja ($p \Rightarrow q$), równoważność ($p \Leftrightarrow q$).
    - Funktory specjalne: binegacja ($p \downarrow q = \sim (p \land q)$), dysjunkcja Sheffera ($p | q = \sim (p \land q)$).
    - Realizacja wyrażeń logicznych za pomocą binegacji i dysjunkcji Sheffera (np. $p \land q = (p | p) | (q | q)$).
    - **Pokrewne**: Algebra Boole'a (prawa de Morgana), minimalizacja funkcji boolowskich (np. metoda Quine-McCluskey), logika trójwartościowa (prawda, fałsz, nieokreślone), logika rozmyta.
2. **Formuły rachunku zdań**:
    - Wartościowanie formuł ($\omega(\alpha)$):
        - Wartościowanie koniunkcji ($\omega(\alpha_1 \land \alpha_2) = \min(\omega(\alpha_1), \omega(\alpha_2))$).
        - Wartościowanie alternatywy ($\omega(\alpha_1 \lor \alpha_2) = \max(\omega(\alpha_1), \omega(\alpha_2))$).
    - Postać normalna formuł:
        - Koniunkcyjna postać normalna (CNF): koniunkcja alternatyw (np. $(p \lor q) \land (\sim p \lor r)$).
        - Alternatywna postać normalna (DNF): alternatywa koniunkcji (np. $(p \land \sim q) \lor (q \land \sim q)$).
    - Tautologie: warunki na tautologię w CNF (np. każda alternatywa zawiera zmienną i jej negację: $p \lor \sim p$).
    - **Pokrewne**: Logika pierwszego rzędu (kwantyfikatory $\forall$, $\exists$), dowody formalne (dedukcja naturalna), twierdzenie o niezupełności Gödla, logika modalna ($\Box p$, $\Diamond p$), logika temporalna (LTL, CTL).
3. **Analiza zdań logicznych**:
    - Wartość logiczna zdań warunkowych (np. "Jeśli $A$ jest poprawne, to dane są niewłaściwe": $A \Rightarrow \sim D$).
    - Wnioskowanie logiczne na podstawie prawdziwości zdań (np. analiza implikacji: $\sim (A \land B) \Rightarrow (\sim A \lor \sim B)$).
    - Fałszywość formuł w zależności od wartości zmiennych (np. $\sim (\alpha \downarrow \beta) \Rightarrow (\alpha \land \beta)$).
    - **Pokrewne**: Wnioskowanie automatyczne (algorytmy rezolucji, unifikacja), zastosowanie logiki w weryfikacji programów, analiza sprzeczności w systemach logicznych, dowody przez sprzeczność, analiza paradoksów logicznych (np. paradoks kłamcy).