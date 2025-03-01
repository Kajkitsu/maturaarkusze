# Matura informatyka grudzień 2024

## Zadanie 7.1 - Znalezienie dnia o najwyższej produkcji energii

**Opis zadania:**
Podaj dzień, w którym łącznie wytworzono najwięcej energii ze źródeł wiatrowych, oraz dzień, w którym najwięcej energii wytworzono ze źródeł fotowoltaicznych.

### Wskazówki:
1. **Sumowanie danych dla każdego dnia:**
   - Użyj funkcji `SUMA` do zsumowania wartości dla każdego dnia.
   - Przykład formuły: `=SUMA(C2:C25)` (dla źródeł wiatrowych jednego dnia).

2. **Znajdowanie maksimum:**
   - Użyj funkcji `MAX`, aby znaleźć największą wartość.
   - Przykład formuły: `=MAX(D2:D31)`.

3. **Wyszukiwanie daty dla maksimum:**
   - Użyj funkcji `PODAJ.POZYCJĘ`, aby znaleźć pozycję maksymalnej wartości.
   - Następnie użyj funkcji `INDEKS`, aby znaleźć odpowiadającą datę.
   - Przykład: 
     ```excel
     =INDEKS(A2:A31; PODAJ.POZYCJĘ(MAX(D2:D31); D2:D31; 0))
     ```

---

## Zadanie 7.2 - Średnia produkcja energii fotowoltaicznej dla każdej godziny

**Opis zadania:**
Podaj średnią liczbę wyprodukowanych MWh energii ze źródeł fotowoltaicznych dla każdej godziny w dobie i wykonaj wykres kolumnowy.

### Wskazówki:
1. **Obliczanie średniej dla każdej godziny:**
   - Użyj funkcji `ŚREDNIA.JEŻELI`, aby obliczyć średnią wartość dla danej godziny.
   - Przykład formuły: 
     ```excel
     =ŚREDNIA.JEŻELI(B:B; 1; D:D)
     ```
     (dla godziny 1).

2. **Zaokrąglenie wyników:**
   - Użyj funkcji `ZAOKR`, aby zaokrąglić wyniki do dwóch miejsc po przecinku.
   - Przykład: `=ZAOKR(ŚREDNIA.JEŻELI(B:B; 1; D:D); 2)`.

3. **Tworzenie wykresu kolumnowego:**
   - Zaznacz dane (np. godziny i średnie wartości).
   - Wybierz kartę "Wstaw" → "Wykres kolumnowy".
   - Dodaj tytuł wykresu i opisz osie:
     - Oś X: "Godzina"
     - Oś Y: "Średnia produkcja (MWh)"

---

## Zadanie 7.3 - Najdłuższy rosnący przedział czasowy

**Opis zadania:**
Znajdź najdłuższy przedział czasowy, w którym generowanie energii ze źródeł wiatrowych cały czas rosło.

### Wskazówki:
1. **Porównywanie wartości między godzinami:**
   - Dodaj nową kolumnę, która sprawdzi, czy wartość w danej godzinie jest większa od poprzedniej.
   - Przykład formuły w komórce E2: 
     ```excel
     =JEŻELI(C3>C2; 1; 0)
     ```

2. **Zliczanie ciągów rosnących:**
   - Użyj kolumny pomocniczej do identyfikacji długości ciągów rosnących.
   - Możesz użyć funkcji `LICZ.JEŻELI` lub ręcznie zliczać kolejne "1".

3. **Znajdowanie początku i końca przedziału:**
   - Zidentyfikuj pierwszy i ostatni wiersz najdłuższego ciągu "1".
   - Odpowiednie daty i godziny znajdziesz za pomocą funkcji `INDEKS`.

---

## Zadanie 7.4 - Minimalna energia w magazynach

**Opis zadania:**
Podaj, ile najmniej energii powinno być zmagazynowane na początku dnia, aby zapotrzebowanie było zaspokojone przez cały miesiąc.

### Wskazówki:
1. **Obliczanie różnicy między generowaniem a zapotrzebowaniem:**
   - Dodaj nową kolumnę, która obliczy różnicę między generowaną energią a zapotrzebowaniem.
   - Przykład formuły: 
     ```excel
     =C2+D2-E2
     ```

2. **Symulacja stanu magazynu:**
   - Dodaj kolumnę pokazującą stan magazynu po każdej godzinie.
   - Jeśli różnica jest dodatnia, energia jest dodawana do magazynu; jeśli ujemna, energia jest pobierana.
   - Przykład formuły w komórce F2:
     ```excel
     =MAKS(0; F1 + C2 + D2 - E2)
     ```

3. **Znajdowanie minimalnego początkowego poziomu magazynu:**
   - Ustal minimalny poziom początkowy, który pozwoli uniknąć niedoboru energii (przyjmij najniższy stan magazynu jako punkt odniesienia).

---

## Przydatne formuły

- `SUMA(zakres)` – sumowanie wartości
- `MAX(zakres)` – maksymalna wartość
- `MIN(zakres)` – minimalna wartość
- `ŚREDNIA(zakres)` – średnia arytmetyczna
- `ŚREDNIA.JEŻELI(zakres_kryteriów; kryterium; zakres_średniej)` – średnia spełniająca warunek
- `JEŻELI(warunek; wartość_jeżeli_prawda; wartość_jeżeli_fałsz)` – warunkowe obliczenia
- `INDEKS(tablica; nr_wiersza; [nr_kolumny])` – zwraca wartość z określonego miejsca
- `PODAJ.POZYCJĘ(szukana_wartość; tablica; [typ_dopasowania])` – zwraca pozycję wartości w tabeli
