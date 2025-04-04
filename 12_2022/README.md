# EKOdom

## 1. Dzień tygodnia

**Formuła:**  
`=DZIEŃ.TYG(A2)`

**Opis:**  
- Funkcja `DZIEŃ.TYG` oblicza numer dnia tygodnia dla daty zapisanej w komórce A2.
- Przyjęto domyślny system numeracji, w którym niedziela to 1, a środa – dzięki czemu ma numer 4 (stąd w kolejnej formule warunek `C2=4`). Żarcik o "katolickim" liczeniu dni odnosi się właśnie do tego, że tydzień zaczyna się od niedzieli.


## 2. Zużycie wody

**Formuła:**  
`=JEŻELI(C2=4;260;190)`

**Opis:**  
- Formuła sprawdza, czy wartość w komórce C2 (wynik funkcji DZIEŃ.TYG) wynosi 4, co odpowiada środzie.
- Jeżeli tak, zużycie wody wynosi 260 l, gdyż tego dnia rodzina wykonuje dodatkowe prace.
- W pozostałych dniach zużycie wynosi 190 l.


## 3. Dni bez wody

**Formuła:**  
- Pierwszy wiersz: `1`  
- Kolejne wiersze: `=JEŻELI(B3=0;1+E2;0)`

**Opis:**  
- W pierwszym dniu zakładamy licznik równy 1.
- Dla kolejnych dni licznik „dni bez wody” (odnoszący się do braku naturalnych opadów) działa następująco:  
  • Jeśli w B3 (retencja opadów) wynosi 0, do poprzedniej wartości liczby dni bez opadów (E2) dodajemy 1.  
  • Jeśli retencja jest inna niż 0, licznik resetuje się do 0.
- Dzięki temu można śledzić, ile dni z rzędu nie wystąpiły opady, co jest kluczowe dla harmonogramu podlewania ogródka.

---

## 4. Podlewanie ogródka

**Formuła:**  
- W okresie od 1.04 do 30.09:  
  `=JEŻELI(ORAZ(MOD(E92;5)=0;E92>=5);300;0)`  
- Poza tym okresem:  
  `0`

**Opis:**  
- Podlewanie ogródka odbywa się tylko w okresie od 1 kwietnia do 30 września, kiedy to panują cieplejsze warunki.
- Formuła sprawdza, czy liczba dni bez opadów (wartość w E92) jest jednocześnie:  
  • Co najmniej 5 (E92>=5)  
  • Wielokrotnością 5 (MOD(E92;5)=0)
- Gdy oba warunki są spełnione, zużycie wody na podlewanie wynosi 300 l. W przeciwnym przypadku woda nie jest używana na ten cel.


## 5. Suma zużycia

**Formuła:**  
`=D2+F2`

**Opis:**  
- Obliczenie łącznego zużycia wody danego dnia odbywa się poprzez dodanie:  
  • Zużycia standardowego (np. 190 l lub 260 l, wartość w D2)  
  • Zużycia wynikającego z podlewania ogródka (F2).


## 6. Stan zbiornika

**Formuła:**  
- Pierwszy wiersz:  
  `=5000-G2`  
- Pozostałe wiersze:  
  `=JEŻELI(H2-G3+B3>=0;H2-G3+B3;0)`

**Opis:**  
- Na początku, tj. 1.01.2022 rano, zbiornik ma 5000 l wody. Po zużyciu (G2) otrzymujemy stan na koniec dnia.
- W kolejnych dniach stan zbiornika obliczany jest według wzoru:  
  • Wartość poprzedniego stanu (H2)  
  • Minus suma zużycia w danym dniu (G3)  
  • Plus dzisiejsza retencja opadów (B3)
- Jeśli wynik jest mniejszy od 0, oznacza to, że woda z retencyjnego zbiornika została wyczerpana, a brak został uzupełniony wodą pobraną z sieci. Wówczas stan zbiornika ustala się na 0.


## 7. Pobranie wody z sieci

**Formuła:**  
`=JEŻELI(G3>(H2+B3);G3-(H2+B3);0)`

**Opis:**  
- Formuła porównuje zapotrzebowanie na wodę danego dnia (G3) ze sumą dostępnej w zbiorniku (H2) oraz retencją opadów (B3).
- Jeśli zapotrzebowanie jest większe, obliczana jest różnica – oznacza to ilość wody pobranej z sieci wodociągowej.
- Gdy dostępna woda wystarczy, funkcja zwraca 0.


## 8. Dni, w których zabrakło wody

**Formuła:**  
`=LICZ.JEŻELI(I2:I366;">0")`

**Opis:**  
- Funkcja `LICZ.JEŻELI` zlicza ilość dni, w których wystąpiło pobranie wody z sieci (czyli tam, gdzie wartość w kolumnie I jest większa niż 0).
- Wynik wskazuje, ile dni w roku zdarzyło się, że zbiornik nie był w stanie zaspokoić zużycia.


## 9. Łącznie pobrano wody z sieci

**Formuła:**  
`=SUMA(I2:I366)`

**Opis:**  
- Funkcja `SUMA` dodaje wszystkie wartości z kolumny I, obliczając łączną ilość wody pobranej z sieci wodociągowej w danym okresie.
