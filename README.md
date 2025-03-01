
## Adresowanie komórek w Excelu

### Adresowanie względne

Adresowanie względne to podstawowy sposób odwoływania się do komórek w Excelu. 

- Używa standardowych oznaczeń kolumn (litery) i wierszy (liczby), np. A1, B2, C3
- Przy kopiowaniu lub przeciąganiu formuły, Excel automatycznie dostosowuje adresy komórek

Przykład:
1. W komórce D1 wpisujemy formułę: `=A1+B1`
2. Przeciągamy tę formułę do komórki D2
3. Formuła w D2 automatycznie zmieni się na: `=A2+B2`

### Adresowanie bezwzględne

Adresowanie bezwzględne "zamraża" odwołanie do konkretnej komórki.

- Używa znaku $ przed literą kolumny i/lub numerem wiersza
- Odwołanie pozostaje niezmienne niezależnie od miejsca skopiowania formuły

Przykład:
1. W komórce D1 wpisujemy formułę: `=$A$1+B1`
2. Przeciągamy tę formułę do komórki D2
3. Formuła w D2 będzie wyglądać tak: `=$A$1+B2`

### Adresowanie mieszane

Adresowanie mieszane to kombinacja adresowania względnego i bezwzględnego.

- `$A1` - kolumna A jest stała, numer wiersza może się zmieniać
- `A$1` - numer wiersza 1 jest stały, litera kolumny może się zmieniać

## Podstawowe formuły w Excelu

### Formuły matematyczne

- `=SUMA(zakres)`: Sumuje wartości w podanym zakresie
  Przykład: `=SUMA(A1:A10)`

- `=ŚREDNIA(zakres)`: Oblicza średnią arytmetyczną
  Przykład: `=ŚREDNIA(B1:B20)`

- `=MIN(zakres)` i `=MAX(zakres)`: Znajdują najmniejszą i największą wartość
  Przykład: `=MIN(C1:C50)`, `=MAX(C1:C50)`

- `=ZAOKR(liczba; liczba_cyfr)`: Zaokrągla liczbę do określonej liczby miejsc po przecinku
  Przykład: `=ZAOKR(A1; 2)`

- `=POTĘGA(liczba; potęga)`: Podnosi liczbę do potęgi
  Przykład: `=POTĘGA(2; 3)` zwróci 8

### Formuły logiczne

- `=JEŻELI(warunek; wartość_jeżeli_prawda; wartość_jeżeli_fałsz)`
  Przykład: `=JEŻELI(A1>10; "Wysoka"; "Niska")`

- `=ORAZ(warunek1; warunek2; ...)`: Zwraca PRAWDA, jeśli wszystkie warunki są spełnione
  Przykład: `=ORAZ(A1>0; A1100)`

### Formuły tekstowe

- `=ZŁĄCZ.TEKSTY(tekst1; tekst2; ...)`: Łączy teksty z wielu komórek
  Przykład: `=ZŁĄCZ.TEKSTY(A1; " "; B1)`

- `=LEWY(tekst; liczba_znaków)`: Zwraca określoną liczbę znaków z lewej strony tekstu
  Przykład: `=LEWY(A1; 3)`

- `=PRAWY(tekst; liczba_znaków)`: Zwraca określoną liczbę znaków z prawej strony tekstu
  Przykład: `=PRAWY(A1; 3)`

### Formuły wyszukiwania

- `=WYSZUKAJ.PIONOWO(szukana_wartość; tabela; nr_kolumny; [dokładne_dopasowanie])`
  Przykład: `=WYSZUKAJ.PIONOWO(A1; B1:D10; 2; FAŁSZ)`

- `=INDEKS(tablica; nr_wiersza; [nr_kolumny])`
  Przykład: `=INDEKS(A1:C10; 2; 3)`

- `=PODAJ.POZYCJĘ(szukana_wartość; tablica; [typ_dopasowania])`
  Przykład: `=PODAJ.POZYCJĘ(A1; B1:B10; 0)`

### Formuły daty i czasu

- `=DZIŚ()`: Zwraca bieżącą datę
  Przykład: `=DZIŚ()`

- `=TERAZ()`: Zwraca bieżącą datę i godzinę
  Przykład: `=TERAZ()`

- `=ROK(data)`: Zwraca rok z podanej daty
  Przykład: `=ROK(A1)`
