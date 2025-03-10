# Arkusze kalkulacyjne 
## Adresowanie komórek w Excelu

### Adresowanie względne

Adresowanie względne to podstawowy sposób odwoływania się do komórek w Excelu. 

- **Jak działa?**  
  Używa standardowych oznaczeń kolumn (litery) i wierszy (liczby), np. `A1`, `B2`, `C3`.  
  Przy kopiowaniu lub przeciąganiu formuły, Excel automatycznie dostosowuje adresy komórek względem miejsca, do którego formuła została skopiowana.

- **Kiedy używać?**  
  Gdy chcesz, aby formuła automatycznie dostosowywała się do nowej lokalizacji.

- **Przykład:**  
  1. W komórce `D1` wpisujemy formułę: `=A1+B1`
  2. Przeciągamy tę formułę do komórki `D2`
  3. Formuła w `D2` automatycznie zmieni się na: `=A2+B2`

---

### Adresowanie bezwzględne

Adresowanie bezwzględne "zamraża" odwołanie do konkretnej komórki.

- **Jak działa?**  
  Używa znaku `$` przed literą kolumny i/lub numerem wiersza, np. `$A$1`.  
  Odwołanie pozostaje niezmienne niezależnie od miejsca, do którego formuła została skopiowana.

- **Kiedy używać?**  
  Gdy chcesz zawsze odwoływać się do tej samej, konkretnej komórki.

- **Przykład:**  
  1. W komórce `D1` wpisujemy formułę: `=$A$1+B1`
  2. Przeciągamy tę formułę do komórki `D2`
  3. Formuła w `D2` będzie wyglądać tak: `=$A$1+B2`

---

### Adresowanie mieszane

Adresowanie mieszane to kombinacja adresowania względnego i bezwzględnego.

- **Jak działa?**  
  - `$A1` - kolumna A jest stała, numer wiersza może się zmieniać.
  - `A$1` - numer wiersza 1 jest stały, litera kolumny może się zmieniać.

- **Kiedy używać?**  
  Gdy chcesz zablokować tylko kolumnę lub tylko wiersz.

- **Przykład:**  
  Jeśli w formule wpiszesz `$A1`, a następnie skopiujesz ją do innego wiersza, odwołanie do kolumny A pozostanie stałe, ale numer wiersza zmieni się odpowiednio.

---

## Podstawowe formuły w Excelu

### Formuły matematyczne

- **`=SUMA(zakres)`** – Sumuje wartości w podanym zakresie.  
  Przykład: `=SUMA(A1:A10)`  

- **`=ŚREDNIA(zakres)`** – Oblicza średnią arytmetyczną wartości w zakresie.  
  Przykład: `=ŚREDNIA(B1:B20)`  

- **`=MIN(zakres)` i `=MAX(zakres)`** – Znajdują najmniejszą i największą wartość w zakresie.  
  Przykład: `=MIN(C1:C50)`, `=MAX(C1:C50)`  

- **`=ZAOKR(liczba; liczba_cyfr)`** – Zaokrągla liczbę do określonej liczby miejsc po przecinku.  
  Przykład: `=ZAOKR(A1; 2)`  

- **`=POTĘGA(liczba; potęga)`** – Podnosi liczbę do potęgi.  
  Przykład: `=POTĘGA(2; 3)` zwróci wartość `8`.

---

### Formuły logiczne

- **`=JEŻELI(warunek; wartość_jeżeli_prawda; wartość_jeżeli_fałsz)`** – Sprawdza warunek i zwraca różne wartości zależnie od wyniku.  
  Przykład: `=JEŻELI(A1>10; "Wysoka"; "Niska")`

- **`=ORAZ(warunek1; warunek2; ...)`** – Zwraca PRAWDA, jeśli wszystkie warunki są spełnione.  
  Przykład: `=ORAZ(A1>0; A1100)`

---

### Formuły tekstowe

- **`=ZŁĄCZ.TEKSTY(tekst1; tekst2; ...)`** – Łączy teksty z wielu komórek w jeden ciąg znaków.  
  Przykład: `=ZŁĄCZ.TEKSTY(A1; " "; B1)`  

- **`=LEWY(tekst; liczba_znaków)`** – Zwraca określoną liczbę znaków z lewej strony tekstu.  
  Przykład: `=LEWY(A1; 3)`  

- **`=PRAWY(tekst; liczba_znaków)`** – Zwraca określoną liczbę znaków z prawej strony tekstu.  
  Przykład: `=PRAWY(A1; 3)`

---

### Formuły wyszukiwania

- **`=WYSZUKAJ.PIONOWO(szukana_wartość; tabela; nr_kolumny; [dokładne_dopasowanie])`** – Wyszukuje wartość pionowo w tabeli i zwraca wynik z określonej kolumny.  
  Przykład: `=WYSZUKAJ.PIONOWO(A1; B1:D10; 2; FAŁSZ)`

- **`=INDEKS(tablica; nr_wiersza; [nr_kolumny])`** – Zwraca wartość z określonego miejsca w tabeli (wiersz/kolumna).  
  Przykład: `=INDEKS(A1:C10; 2; 3)`

- **`=PODAJ.POZYCJĘ(szukana_wartość; tablica; [typ_dopasowania])`** – Zwraca pozycję wartości w tabeli (numer wiersza lub kolumny).  
  Przykład: `=PODAJ.POZYCJĘ(A1; B1:B10; 0)`

---

### Formuły daty i czasu

- **`=DZIŚ()`** – Zwraca bieżącą datę (bez godziny).  
  Przykład: `=DZIŚ()`  

- **`=TERAZ()`** – Zwraca bieżącą datę i godzinę.  
  Przykład: `=TERAZ()`  

- **`=ROK(data)`** – Zwraca rok z podanej daty.  
  Przykład: `=ROK(A1)`

## Rozwiązania
- [grudzień 2024](https://github.com/Kajkitsu/maturaarkusze/blob/master/12_2024/)
- [czerwiec 2024](https://github.com/Kajkitsu/maturaarkusze/blob/master/06_2024/)
