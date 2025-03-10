# Matura informatyka czerwiec 2024

## Zadanie 7.1 - Zestawienie miesięczne liczby kuracjuszy

**Opis zadania:**  
Utwórz zestawienie łącznej liczby kuracjuszy, którzy przyjechali do uzdrowiska w każdym miesiącu 2023 roku, i sporządź wykres kolumnowy.

### Wskazówki:
1. **Dodanie kolumny z numerem miesiąca:**
   - W Excelu użyj funkcji `MIESIĄC`, aby wyodrębnić numer miesiąca z daty.
   - Przykład formuły:  
   ```excel
   =MIESIĄC(A2)
   ```

2. **Sumowanie liczby kuracjuszy dla każdego miesiąca:**
   - Użyj funkcji `SUMA.JEŻELI`, aby obliczyć sumę przyjazdów dla każdego miesiąca.
   - Przykład formuły dla stycznia (miesiąc 1):  
   ```excel
   =SUMA.JEŻELI(B:B; 1; C:C)
   ```

3. **Tworzenie wykresu kolumnowego:**
   - Zaznacz dane (miesiące i sumy przyjazdów).
   - Wybierz kartę "Wstaw" → "Wykres kolumnowy".
   - Dodaj tytuł wykresu i opisy osi:
     - Oś X: "Miesiąc"
     - Oś Y: "Liczba kuracjuszy"

---

## Zadanie 7.2 - Analiza liczby kuracjuszy

**Opis zadania:**  
Podaj datę, kiedy liczba kuracjuszy po raz pierwszy przekroczyła 11000, oraz datę, kiedy liczba kuracjuszy była największa.

### Wskazówki:
1. **Obliczanie liczby obecnych kuracjuszy każdego dnia:**
   - Dodaj nową kolumnę, która oblicza liczbę obecnych kuracjuszy na podstawie danych.
   - Formuła:  
   ```excel
   =10000 + SUMA(C$2:C2) - SUMA(D$2:D2)
   ```

2. **Znajdowanie daty przekroczenia 11000:**
   - Użyj funkcji `PODAJ.POZYCJĘ`, aby znaleźć pierwszą datę, gdy wartość w nowej kolumnie przekracza 11000.
   - Formuła:  
   ```excel
   =INDEKS(A:A; PODAJ.POZYCJĘ(11001; E:E; 1))
   ```

3. **Znajdowanie maksymalnej liczby kuracjuszy:**
   - Użyj funkcji `MAX`, aby znaleźć największą wartość w kolumnie z liczbą obecnych kuracjuszy.
   - Znajdź odpowiadającą jej datę za pomocą `INDEKS`.
   - Formuła:  
   ```excel
   =INDEKS(A:A; PODAJ.POZYCJĘ(MAX(E:E); E:E; 0))
   ```

---

## Zadanie 7.3 - Zarządzanie wodą w uzdrowisku

**Opis zadania:**  
Oblicz, kiedy zabrakło wody dla wszystkich kuracjuszy oraz ile dni brakowało wody. Podaj minimalną liczbę butelek potrzebnych na początku roku.

### Wskazówki:
1. **Obliczanie dziennego zużycia wody przez kuracjuszy:**
   - Każdy kuracjusz zużywa dziennie $$0,4$$ litra.
   - Formuła na dzienne zużycie:
   ```excel
   =E2 * 0.4
   ```

2. **Symulacja stanu wody:**
   - Oblicz różnicę między wydajnością źródła a potrzebami:
     ```excel
     =3900 - F2
     ```
     Jeśli wynik jest dodatni, oblicz liczbę butelek do magazynowania:
     ```excel
     =ZAOKR.DÓŁ(G2 / 5; 0)
     ```
     Jeśli wynik jest ujemny, odejmij brakującą wodę od zapasu butelek.

3. **Znajdowanie dni z brakiem wody:**
   - Zidentyfikuj dni, kiedy zarówno źródło, jak i zapas butelek nie wystarczały.
   - Formuła warunkowa:
     ```excel
     =JEŻELI(G2+H2<0; "Brak"; "")
     ```

4. **Minimalna liczba butelek na początku roku:**
   - Iteracyjnie zwiększaj początkowy zapas butelek, aż żadnego dnia nie zabraknie wody.

---

## Przydatne formuły

- `SUMA(zakres)` – sumowanie wartości.
- `MAX(zakres)` – maksymalna wartość.
- `MIN(zakres)` – minimalna wartość.
- `ŚREDNIA(zakres)` – średnia arytmetyczna.
- `SUMA.JEŻELI(zakres_kryteriów; kryterium; zakres_sumowania)` – suma spełniająca warunek.
- `JEŻELI(warunek; wartość_jeżeli_prawda; wartość_jeżeli_fałsz)` – warunkowe obliczenia.
- `ZAOKR.DÓŁ(liczba; miejsca)` – zaokrąglanie w dół.
- `INDEKS(tablica; nr_wiersza; [nr_kolumny])` – zwraca wartość z określonego miejsca.
- `PODAJ.POZYCJĘ(szukana_wartość; tablica; [typ_dopasowania])` – zwraca pozycję wartości w tabeli.
