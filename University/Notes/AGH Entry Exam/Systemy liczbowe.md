### **Wprowadzenie do systemów liczbowych**

Systemy liczbowe to sposoby reprezentowania liczb za pomocą symboli (cyfr) i określonych zasad. W informatyce kluczowe są systemy o różnych podstawach (np. binarny, ósemkowy, dziesiętny, szesnastkowy), ponieważ komputery operują na bitach (0 i 1), a różne systemy liczbowe ułatwiają pracę z danymi na różnych poziomach abstrakcji.

#### **Dlaczego systemy liczbowe są ważne w informatyce?**

- Komputery używają systemu binarnego ($0$ i $1$) do reprezentacji danych, ponieważ układy cyfrowe operują na stanach logicznych (włączony/wyłączony).
- Systemy ósemkowy i szesnastkowy są wygodne do pracy z danymi binarnymi, ponieważ są ich skróconymi zapisami (np. $1$ cyfra szesnastkowa = $4$ bity).
- Zrozumienie systemów liczbowych pozwala na:
    - Projektowanie algorytmów (np. operacje bitowe, haszowanie).
    - Analizę reprezentacji danych (np. liczby zmiennopozycyjne w IEEE 754).
    - Debugowanie (np. analiza pamięci w systemie szesnastkowym).
    - Optymalizację (np. operacje na bitach zamiast arytmetyki dziesiętnej).

---

### **1. Podstawy systemów liczbowych**

System liczbowy o podstawie $b$ używa $b$ różnych cyfr (symboli) do reprezentowania liczb. Wartość liczby zależy od pozycji cyfr i podstawy systemu.

#### **Definicja ogólna**

Liczba w systemie o podstawie $b$ jest zapisana jako:  
$N = d_n \cdot b^n + d_{n-1} \cdot b^{n-1} + \dots + d_1 \cdot b^1 + d_0 \cdot b^0 + d_{-1} \cdot b^{-1} + \dots$  
gdzie:

- $d_i$ to cyfry w systemie (dla podstawy $b$, $d_i \in {0, 1, \dots, b-1}$),
- $b$ to podstawa systemu,
- $n$ to pozycja cyfry (pozycje ujemne dla części ułamkowej).

#### **Przykłady systemów liczbowych**

1. **System dziesiętny (podstawa $b = 10$)**:
    
    - Cyfry: $0, 1, 2, \dots, 9$.
    - Przykład: $123_{10} = 1 \cdot 10^2 + 2 \cdot 10^1 + 3 \cdot 10^0 = 100 + 20 + 3 = 123$.
    - Używany w codziennym życiu, ale mniej efektywny w komputerach.
2. **System binarny (podstawa $b = 2$)**:
    
    - Cyfry: $0, 1$.
    - Przykład: $1011_2 = 1 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0 = 8 + 0 + 2 + 1 = 11_{10}$.
    - Kluczowy w informatyce, bo odpowiada bitom (0 lub 1).
3. **System ósemkowy (podstawa $b = 8$)**:
    
    - Cyfry: $0, 1, 2, \dots, 7$.
    - Przykład: $17_8 = 1 \cdot 8^1 + 7 \cdot 8^0 = 8 + 7 = 15_{10}$.
    - Używany historycznie, dziś rzadziej, ale przydatny do skróconego zapisu binarnego ($1$ cyfra ósemkowa = $3$ bity).
4. **System szesnastkowy (podstawa $b = 16$)**:
    
    - Cyfry: $0, 1, 2, \dots, 9, A, B, C, D, E, F$ (gdzie $A = 10$, $B = 11$, $\dots$, $F = 15$).
    - Przykład: $1A_{16} = 1 \cdot 16^1 + 10 \cdot 16^0 = 16 + 10 = 26_{10}$.
    - Bardzo popularny w informatyce (np. adresy pamięci, kolory RGB), bo $1$ cyfra szesnastkowa = $4$ bity.

---

### **2. Konwersja między systemami liczbowymi**

Zrozumienie konwersji między systemami jest kluczowe, bo pozwala na przechodzenie między reprezentacjami używanymi przez człowieka (dziesiętny, szesnastkowy) a komputerem (binarny).

#### **2.1. Konwersja z systemu dziesiętnego na inne systemy**

- **Metoda dzielenia przez podstawę** (dla części całkowitej):
    
    1. Dziel liczbę dziesiętną przez podstawę $b$.
    2. Zapisz resztę (cyfrę w systemie $b$).
    3. Powtarzaj dzielenie ilorazu przez $b$, aż iloraz będzie $0$.
    4. Cyfry zapisuj od ostatniej do pierwszej.
- **Przykład: $13_{10}$ na binarny ($b = 2$)**:
    
    - $13 \div 2 = 6$, reszta $1$ (najmniej znacząca cyfra).
    - $6 \div 2 = 3$, reszta $0$.
    - $3 \div 2 = 1$, reszta $1$.
    - $1 \div 2 = 0$, reszta $1$ (najbardziej znacząca cyfra).
    - Wynik: $13_{10} = 1101_2$.
- **Przykład: $26_{10}$ na szesnastkowy ($b = 16$)**:
    
    - $26 \div 16 = 1$, reszta $10$ ($A$).
    - $1 \div 16 = 0$, reszta $1$.
    - Wynik: $26_{10} = 1A_{16}$.
- **Metoda mnożenia przez podstawę** (dla części ułamkowej):
    
    1. Mnoż część ułamkową przez podstawę $b$.
    2. Zapisz część całkowitą wyniku jako cyfrę.
    3. Powtarzaj mnożenie dla części ułamkowej, aż uzyskasz $0$ lub wystarczającą dokładność.
- **Przykład: $0.625_{10}$ na binarny ($b = 2$)**:
    
    - $0.625 \cdot 2 = 1.25$, cyfra $1$.
    - $0.25 \cdot 2 = 0.5$, cyfra $0$.
    - $0.5 \cdot 2 = 1.0$, cyfra $1$.
    - Wynik: $0.625_{10} = 0.101_2$.

#### **2.2. Konwersja z systemu binarnego na inne systemy**

- **Na dziesiętny**: Oblicz wartość zgodnie z wagami pozycji (np. $1011_2 = 1 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0 = 11_{10}$).
- **Na ósemkowy**: Grupuj bity po 3 od prawej, zamień każdą grupę na cyfrę ósemkową.
    - Przykład: $110101_2 = 110 , 101 = 6 , 5 = 65_8$.
- **Na szesnastkowy**: Grupuj bity po 4 od prawej, zamień każdą grupę na cyfrę szesnastkową.
    - Przykład: $110101_2 = 0011 , 0101 = 3 , 5 = 35_{16}$.

#### **2.3. Konwersja między ósemkowym a szesnastkowym**

- Najpierw konwertuj na binarny, potem na docelowy system.
- Przykład: $65_8$ na szesnastkowy:
    - $65_8 = 110 , 101_2 = 0011 , 0101_2 = 35_{16}$.

---

### **3. Reprezentacja ułamków w systemie binarnym (ciąg dalszy)**

Ułamki w systemie binarnym są zapisywane jako suma potęg ujemnych $2$. Każda cyfra po przecinku odpowiada kolejnej ujemnej potędze $2$. Wzór ogólny dla części ułamkowej w systemie binarnym wygląda następująco:  
$N = d_{-1} \cdot 2^{-1} + d_{-2} \cdot 2^{-2} + d_{-3} \cdot 2^{-3} + \dots$
gdzie $d_{-i} \in {0, 1}$ to cyfry binarne po przecinku.

#### **Przykład: $0.101_2$**

- $0.101_2 = 1 \cdot 2^{-1} + 0 \cdot 2^{-2} + 1 \cdot 2^{-3} = \frac{1}{2} + 0 + \frac{1}{8} = 0.5 + 0.125 = 0.625_{10}$.
- Wynik: $0.101_2 = 0.625_{10}$.

#### **Przykład: $0.11_2$**

- $0.11_2 = 1 \cdot 2^{-1} + 1 \cdot 2^{-2} = \frac{1}{2} + \frac{1}{4} = 0.5 + 0.25 = 0.75_{10}$.
- Wynik: $0.11_2 = 0.75_{10}$.

#### **Problemy z dokładnością**

Nie wszystkie ułamki dziesiętne mają skończoną reprezentację w systemie binarnym, co prowadzi do problemów z dokładnością w komputerach:

- **Przykład: $0.1_{10}$ (czyli $\frac{1}{10}$) w systemie binarnym**:
    
    - $0.1 \cdot 2 = 0.2$, cyfra $0$.
    - $0.2 \cdot 2 = 0.4$, cyfra $0$.
    - $0.4 \cdot 2 = 0.8$, cyfra $0$.
    - $0.8 \cdot 2 = 1.6$, cyfra $1$, część ułamkowa $0.6$.
    - $0.6 \cdot 2 = 1.2$, cyfra $1$, część ułamkowa $0.2$.
    - Proces się powtarza: $0.1_{10} = 0.0001100110011\dots_2$ (nieskończony okres).
    - W komputerach (np. IEEE 754) taka liczba jest przybliżana, co prowadzi do błędów zaokrągleń.
- **Dlaczego to ważne?**
    
    - W informatyce liczby zmiennopozycyjne (np. standard IEEE 754) używają binarnej reprezentacji, co oznacza, że liczby takie jak $0.1_{10}$ nie są dokładnie reprezentowane.
    - Przykład: W języku programowania (np. Python, C++) suma $0.1 + 0.2$ nie daje dokładnie $0.3$, tylko przybliżenie (np. $0.30000000000000004$).
    - Rozwiązanie: Używaj bibliotek do arytmetyki precyzyjnej (np. `decimal` w Pythonie) lub analizuj błędy zaokrągleń.

---

### **4. Zaawansowane zagadnienia w systemach liczbowych**

Teraz przejdziemy do bardziej zaawansowanych tematów, które są istotne w informatyce, szczególnie na poziomie akademickim. Te zagadnienia są kluczowe dla zrozumienia, jak systemy liczbowe wpływają na projektowanie algorytmów, optymalizację i analizę danych.

#### **4.1. Systemy kodowania liczb w komputerach**

Komputery używają różnych systemów kodowania do reprezentacji liczb całkowitych i zmiennopozycyjnych. Oto najważniejsze z nich:

- **Kodowanie liczb całkowitych**:
    
    1. **Kod znak-moduł**:
        - Najstarszy sposób: bit znaku ($0$ dla dodatnich, $1$ dla ujemnych) i moduł liczby.
        - Przykład: Dla $8$-bitowego systemu, $+5 = 00000101$, $-5 = 10000101$.
        - Problem: Dwie reprezentacje zera ($+0 = 00000000$, $-0 = 10000000$), trudności w operacjach arytmetycznych.
    2. **Kod uzupełnień do dwóch (U2)**:
        - Najpopularniejszy w komputerach. Używany do reprezentacji liczb ujemnych.
        - Dla $n$-bitowego systemu:
            - Liczby dodatnie: standardowa reprezentacja binarna.
            - Liczby ujemne: odwróć wszystkie bity i dodaj $1$ (lub odejmij od $2^n$).
        - Przykład: $-5$ w $8$-bitowym U2:
            - $+5 = 00000101$.
            - Odwróć bity: $11111010$.
            - Dodaj $1$: $11111011 = -5$.
        - Zalety: Jedna reprezentacja zera, łatwe operacje arytmetyczne (dodawanie, odejmowanie).
        - Przykład: $3 + (-5)$ w U2:
            - $3 = 00000011$, $-5 = 11111011$.
            - Dodaj: $00000011 + 11111011 = 00000010 = -2_{10}$.
- **Kodowanie liczb zmiennopozycyjnych (IEEE 754)**:
    
    - Standard IEEE 754 definiuje format dla liczb zmiennopozycyjnych (np. `float`, `double`).
    - Struktura: bit znaku, wykładnik, mantysa.
    - Przykład dla `float` (32 bity):
        - $1$ bit znaku ($0$ dodatni, $1$ ujemny).
        - $8$ bitów wykładnika (z przesunięciem, np. $127$ dla `float`).
        - $23$ bity mantysy (część ułamkowa, z implicite $1$ na początku).
    - Przykład: $0.625_{10}$ w IEEE 754:
        - $0.625_{10} = 0.101_2 = 1.01_2 \cdot 2^{-1}$ (mantysa: $1.01$, wykładnik: $-1$).
        - Znak: $0$ (dodatni), wykładnik: $-1 + 127 = 126 = 01111110_2$, mantysa: $010000\dots0$ (23 bity).
        - Wynik: $0 , 01111110 , 010000\dots0$.
    - Problemy: Niedokładność dla ułamków (np. $0.1_{10}$), przepełnienie, niedomiar.

---

### **5. Zastosowania systemów liczbowych w informatyce**

Systemy liczbowe mają szerokie zastosowanie w informatyce. Oto kilka kluczowych obszarów:

#### **5.1. Operacje bitowe**

- Operacje bitowe (AND, OR, XOR, NOT, przesunięcia) są szybkie i używane w optymalizacji algorytmów.
- Przykład: Sprawdzenie, czy liczba $n$ jest parzysta:
    - $n & 1 = 0$ (parzysta), $n & 1 = 1$ (nieparzysta).
    - Wyjaśnienie: $n & 1$ sprawdza najmniej znaczący bit ($0$ dla parzystych, $1$ dla nieparzystych).
- Przykład: Przesunięcie bitowe w lewo ($n \ll k$) mnoży $n$ przez $2^k$.
    - $5 \ll 1 = 101_2 \ll 1 = 1010_2 = 10_{10}$.

#### **5.2. Adresowanie pamięci**

- Adresy pamięci są zapisywane w systemie szesnastkowym, bo $1$ cyfra szesnastkowa = $4$ bity.
- Przykład: Adres $0x1A3F$ w systemie szesnastkowym:
    - $1A3F_{16} = 0001 , 1010 , 0011 , 1111_2 = 1 \cdot 16^3 + 10 \cdot 16^2 + 3 \cdot 16^1 + 15 \cdot 16^0 = 6719_{10}$.
- W systemach 32-bitowych maksymalny adres to $2^{32} - 1 = FFFFFFFF_{16}$, w 64-bitowych $2^{64} - 1$.

#### **5.3. Kodowanie znaków**

- **ASCII (American Standard Code for Information Interchange)**:
    
    - Używa $7$ bitów na znak, rozszerzone do $8$ bitów (1 bajt) dla zgodności z systemami komputerowymi.
    - Zakres: $0-127$ (np. $65_{10} = 01000001_2 = 'A'$, $97_{10} = 01100001_2 = 'a'$).
    - Ograniczenia: Brak obsługi znaków spoza alfabetu łacińskiego (np. znaki diakrytyczne, chińskie).
    - Przykład: Słowo "ABC" w ASCII:
        - $A = 65_{10} = 01000001_2$, $B = 66_{10} = 01000010_2$, $C = 67_{10} = 01000011_2$.
        - Wynik: $01000001 , 01000010 , 01000011_2$.
    - **Pokrewne**: Rozszerzone ASCII ($8$ bitów, $0-255$), ale nadal ograniczone.
- **UTF-8 (Unicode Transformation Format - 8-bit)**:
    
    - Rozszerzenie ASCII, obsługuje wszystkie znaki Unicode (ponad $143,000$ znaków).
    - Zmienna długość: $1-4$ bajty na znak.
    - Przykład: Znak "A" ($U+0041$) w UTF-8:
        - $1$ bajt: $01000001_2$ (taki sam jak ASCII).
    - Przykład: Znak "ą" ($U+0105$) w UTF-8:
        - $2$ bajty: $C4 , 85_{16} = 11000100 , 10000101_2$.
    - Zalety: Kompatybilność z ASCII, efektywność dla znaków łacińskich, obsługa znaków międzynarodowych.
    - **Dlaczego to ważne?** UTF-8 jest standardem w Internecie (np. HTML, JSON), a zrozumienie jego binarnej reprezentacji pozwala na analizę danych tekstowych i debugowanie.
- **UTF-16 i UTF-32**:
    
    - UTF-16: Zmienna długość ($2$ lub $4$ bajty), używana w systemach Windows.
    - UTF-32: Stała długość ($4$ bajty), mniej efektywna, ale prosta w implementacji.
    - **Pokrewne**: Problemy z endiannością (big-endian vs little-endian), np. $U+0105$ w UTF-16:
        - Big-endian: $01 , 05_{16}$, little-endian: $05 , 01_{16}$.

#### **5.4. Optymalizacja algorytmów za pomocą operacji bitowych**

- Operacje bitowe są szybsze niż operacje arytmetyczne, ponieważ są realizowane bezpośrednio przez procesor.
- **Przykłady optymalizacji**:
    
    1. **Sprawdzenie parzystości**:
        - Zamiast $n % 2 == 0$, użyj $n & 1 == 0$ (parzysta) lub $n & 1 == 1$ (nieparzysta).
        - Wyjaśnienie: $n & 1$ sprawdza najmniej znaczący bit ($0$ dla parzystych, $1$ dla nieparzystych).
    2. **Mnożenie i dzielenie przez potęgi $2$**:
        - Zamiast $n \cdot 2^k$, użyj $n \ll k$ (przesunięcie w lewo).
        - Zamiast $n / 2^k$, użyj $n \gg k$ (przesunięcie w prawo, dla liczb dodatnich).
        - Przykład: $5 \ll 2 = 101_2 \ll 2 = 10100_2 = 20_{10}$ (czyli $5 \cdot 2^2$).
    3. **Maski bitowe**:
        - Używane do wyodrębniania bitów, np. $n & 00001111_2$ wyciąga $4$ najmniej znaczące bity.
        - Przykład: $n = 29_{10} = 00011101_2$, $n & 00001111_2 = 00001101_2 = 13_{10}$.
    4. **Flipy bitowe (XOR)**:
        - $n \oplus 1$ zmienia ostatni bit ($0 \to 1$, $1 \to 0$).
        - Przykład: $5 = 101_2$, $5 \oplus 1 = 101_2 \oplus 001_2 = 100_2 = 4_{10}$.
    
    - **Dlaczego to ważne?** Operacje bitowe są kluczowe w algorytmach kryptograficznych (np. AES), kompresji danych i optymalizacji w grach komputerowych.

#### **5.5. Systemy liczbowe w analizie pamięci**

- Adresy pamięci są zapisywane w systemie szesnastkowym, bo $1$ cyfra szesnastkowa = $4$ bity, co ułatwia analizę.
- **Przykład: Adres $0x1A3F$**:
    - $1A3F_{16} = 0001 , 1010 , 0011 , 1111_2 = 1 \cdot 16^3 + 10 \cdot 16^2 + 3 \cdot 16^1 + 15 \cdot 16^0 = 6719_{10}$.
- W systemach 32-bitowych maksymalny adres to $2^{32} - 1 = FFFFFFFF_{16}$, w 64-bitowych $2^{64} - 1$.
- **Pokrewne**: Endianność (big-endian vs little-endian):
    - Big-endian: Najbardziej znaczący bajt na początku (np. $1234_{16} = 12 , 34$).
    - Little-endian: Najmniej znaczący bajt na początku (np. $1234_{16} = 34 , 12$).
    - Przykład: Liczba $305419896_{10} = 12345678_{16}$:
        - Big-endian: $12 , 34 , 56 , 78$.
        - Little-endian: $78 , 56 , 34 , 12$.
    - **Dlaczego to ważne?** Endianność wpływa na przesyłanie danych w sieciach i debugowanie pamięci.

---

### **6. Zaawansowane systemy liczbowe i ich zastosowanie**

Teraz przejdziemy do bardziej zaawansowanych systemów liczbowych, które mogą być istotne w informatyce, szczególnie w kontekście algorytmów i optymalizacji.

#### **6.1. System Graya**

- System Graya to kod binarny, w którym kolejne liczby różnią się tylko jednym bitem.
- Przykład: Kod Graya dla $0-7_{10}$:
    - $0 = 000$, $1 = 001$, $2 = 011$, $3 = 010$, $4 = 110$, $5 = 111$, $6 = 101$, $7 = 100$.
- **Zastosowanie**:
    - Minimalizacja błędów w transmisji danych (np. w enkoderach obrotowych).
    - Optymalizacja w algorytmach wyszukiwania (np. wieże Hanoi).
- **Konwersja binarny $\to$ Gray**:
    - $G = B \oplus (B \gg 1)$, gdzie $B$ to liczba binarna.
    - Przykład: $5_{10} = 101_2$, $101 \gg 1 = 010$, $101 \oplus 010 = 111_2$ (kod Graya dla $5$).

#### **6.2. System BCD (Binary-Coded Decimal)**

- Każda cyfra dziesiętna jest kodowana na $4$ bitach (np. $0 = 0000$, $1 = 0001$, $\dots$, $9 = 1001$).
- Przykład: $123_{10}$ w BCD:
    - $1 = 0001$, $2 = 0010$, $3 = 0011$.
    - Wynik: $0001 , 0010 , 0011_2$.
- **Zastosowanie**:
    - Wyświetlacze cyfrowe (np. kalkulatory, zegary).
    - Systemy finansowe (dokładność bez zaokrągleń binarnych).
- **Pokrewne**: Rozszerzone BCD (np. kod 8421, 2421), problemy z efektywnością pamięci.
#### **6.3. Systemy liczbowe w kryptografii**

- W kryptografii (np. RSA, ECC) używa się systemów liczbowych do operacji na dużych liczbach całkowitych i modularnych. Systemy binarne i szesnastkowe są kluczowe dla efektywności obliczeń.
    
- **RSA (Rivest-Shamir-Adleman)**:
    
    - Klucz publiczny i prywatny są generowane na podstawie dużych liczb pierwszych ($p$, $q$).
    - Operacje modularne: $c = m^e \mod n$ (szyfrowanie), $m = c^d \mod n$ (deszyfrowanie).
    - Przykład: Jeśli $m = 5$, $e = 7$, $n = 33$, to $c = 5^7 \mod 33$.
        - $5^7 = 78125$, $78125 \mod 33 = 14$.
        - Wynik: $c = 14$.
    - **Dlaczego systemy liczbowe są ważne?** Operacje na dużych liczbach (np. $2^{2048}$) są wykonywane w systemie binarnym, a wyniki są zapisywane w systemie szesnastkowym dla czytelności.
    - **Pokrewne**: Algorytm szybkiego potęgowania modularnego (np. $a^b \mod n$ w $O(\log b)$), reprezentacja binarna dużych liczb (np. $2^{2048} = 1 , 000\dots0_2$).
- **ECC (Elliptic Curve Cryptography)**:
    
    - Używa punktów na krzywych eliptycznych nad ciałami skończonymi (np. $GF(2^m)$ lub $GF(p)$).
    - Operacje: Mnożenie punktu przez skalar, dodawanie punktów.
    - Przykład: Punkt $P = (x, y)$ na krzywej $y^2 = x^3 + ax + b \mod p$.
    - **Dlaczego systemy liczbowe są ważne?** Operacje w ciałach skończonych wymagają binarnej reprezentacji (np. $GF(2^8)$ w AES).
    - **Pokrewne**: Systemy binarne w ciałach Galois, optymalizacja obliczeń w kryptografii (np. algorytmy Montgomery'ego).
- **Hashowanie**:
    
    - Funkcje haszujące (np. SHA-256) operują na bitach, a wyniki są zapisywane w systemie szesnastkowym.
    - Przykład: SHA-256 dla "ABC" daje wynik w systemie szesnastkowym (np. $BA7816BF8F01CFEA\dots$).
    - **Dlaczego to ważne?** Zrozumienie binarnej reprezentacji pozwala na analizę kolizji i optymalizację funkcji haszujących.

#### **6.4. Systemy liczbowe w kompresji danych**

- **Kodowanie Huffmana**:
    
    - Używa binarnych kodów o zmiennej długości, przypisanych na podstawie częstotliwości znaków.
    - Przykład: Dla alfabetu ${A, B, C}$ z częstotliwościami ${0.5, 0.3, 0.2}$:
        - $A = 0$, $B = 10$, $C = 11$.
    - **Dlaczego to ważne?** Binarna reprezentacja pozwala na efektywną kompresję (np. pliki ZIP, JPEG).
    - **Pokrewne**: Kodowanie arytmetyczne, kodowanie LZW, analiza entropii ($H = -\sum p_i \log_2 p_i$).
- **Kodowanie RLE (Run-Length Encoding)**:
    
    - Zapisuje sekwencje powtórzeń w systemie binarnym.
    - Przykład: $AAAAABBB = A5B3$ w systemie binarnym (np. $01000001 , 00000101 , 01000010 , 00000011$).
    - **Dlaczego to ważne?** Prosta kompresja, używana w formatach graficznych (np. BMP).

#### **6.5. Systemy liczbowe w analizie numerycznej**

- **Błędy zaokrągleń**:
    
    - W systemie binarnym niektóre ułamki dziesiętne (np. $0.1_{10}$) są nieskończone ($0.000110011\dots_2$), co prowadzi do błędów w obliczeniach.
    - Przykład: $0.1 + 0.2 \neq 0.3$ w IEEE 754 (wynik: $0.30000000000000004$).
    - **Dlaczego to ważne?** Analiza błędów zaokrągleń jest kluczowa w obliczeniach naukowych i finansowych.
    - **Pokrewne**: Arytmetyka precyzyjna (np. biblioteka GMP), analiza stabilności numerycznej algorytmów.
- **Liczby zmiennopozycyjne w IEEE 754**:
    
    - Dokładność zależy od liczby bitów mantysy (np. $23$ bity dla `float`, $52$ bity dla `double`).
    - Przykład: $0.625_{10} = 1.01_2 \cdot 2^{-1}$, mantysa: $1.01$, wykładnik: $-1$.
    - **Dlaczego to ważne?** Zrozumienie binarnej reprezentacji pozwala na analizę przepełnień i niedomiarów.
    - **Pokrewne**: Specjalne wartości w IEEE 754 (np. NaN, $\pm \infty$), analiza błędów w algorytmach numerycznych.

---

### **Przykładowe zadania do samodzielnego rozwiązania**

#### **Przykładowe zadania do samodzielnego rozwiązania (ciąg dalszy)**

1. **Ułamki**:
    - Znajdź binarny zapis $0.875_{10}$ i $0.2_{10}$. Analizuj, dlaczego $0.2_{10}$ nie ma skończonej reprezentacji binarnej.
        - **Rozwiązanie dla $0.875_{10}$**:
            - $0.875 \cdot 2 = 1.75$, cyfra $1$.
            - $0.75 \cdot 2 = 1.5$, cyfra $1$.
            - $0.5 \cdot 2 = 1.0$, cyfra $1$.
            - Wynik: $0.875_{10} = 0.111_2$.
            - Wyjaśnienie: $0.111_2 = 1 \cdot 2^{-1} + 1 \cdot 2^{-2} + 1 \cdot 2^{-3} = 0.5 + 0.25 + 0.125 = 0.875_{10}$.
        - **Rozwiązanie dla $0.2_{10}$**:
            - $0.2 \cdot 2 = 0.4$, cyfra $0$.
            - $0.4 \cdot 2 = 0.8$, cyfra $0$.
            - $0.8 \cdot 2 = 1.6$, cyfra $1$, część ułamkowa $0.6$.
            - $0.6 \cdot 2 = 1.2$, cyfra $1$, część ułamkowa $0.2$.
            - Proces się powtarza: $0.2_{10} = 0.00110011\dots_2$ (nieskończony okres).
            - Wyjaśnienie: $0.2_{10}$ nie ma skończonej reprezentacji binarnej, bo $\frac{1}{5}$ nie jest potęgą $2$. W IEEE 754 prowadzi to do błędów zaokrągleń.
2. **Operacje bitowe**: Zaimplementuj w Pythonie funkcję sprawdzającą, czy liczba $n$ jest potęgą $2$, używając operacji bitowych.
    
    - **Rozwiązanie**:
        - Liczba $n$ jest potęgą $2$, jeśli ma dokładnie jeden bit ustawiony na $1$ (np. $2 = 10_2$, $4 = 100_2$, $8 = 1000_2$).
        - Warunek: $n & (n-1) == 0$ i $n > 0$.
        - Wyjaśnienie: $n-1$ ustawia wszystkie bity po pierwszym $1$ na $1$, a $n & (n-1)$ zeruje ten bit, jeśli $n$ jest potęgą $2$.
        - Kod:
```python
     def is_power_of_two(n):
                return n > 0 and (n & (n - 1)) == 0
        print(is_power_of_two(8))  # True (1000_2)
        print(is_power_of_two(10))  # False (1010_2)
```
            
- **Kodowanie znaków**: Zakoduj słowo "HI" w ASCII i UTF-8. Analizuj różnice.
    
    - **Rozwiązanie**:
        - ASCII: $H = 72_{10} = 01001000_2$, $I = 73_{10} = 01001001_2$.
            - Wynik: $01001000 , 01001001_2$.
        - UTF-8: Kompatybilne z ASCII dla znaków $0-127$.
            - Wynik: $01001000 , 01001001_2$ (taki sam jak ASCII).
        - Analiza: UTF-8 używa $1$ bajtu dla znaków ASCII, ale dla znaków spoza ASCII (np. "ą") używa $2-4$ bajtów, co pozwala na obsługę Unicode.
- **Kryptografia**: Oblicz $5^7 \mod 33$ za pomocą algorytmu szybkiego potęgowania modularnego.
    
    - **Rozwiązanie**:
        - $7_{10} = 111_2$, więc rozbijamy na potęgi: $5^1$, $5^2$, $5^4$.
        - $5^1 \mod 33 = 5$.
        - $5^2 \mod 33 = 25$.
        - $5^4 \mod 33 = 25^2 \mod 33 = 625 \mod 33 = 31$.
        - $5^7 = 5^1 \cdot 5^2 \cdot 5^4 = 5 \cdot 25 \cdot 31 \mod 33$.
        - $5 \cdot 25 = 125 \mod 33 = 26$.
        - $26 \cdot 31 = 806 \mod 33 = 14$.
        - Wynik: $5^7 \mod 33 = 14$.
    - **Dlaczego to ważne?** Algorytm szybkiego potęgowania modularnego ($O(\log e)$) jest kluczowy w RSA i ECC.