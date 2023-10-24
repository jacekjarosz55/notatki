TODO: uprościć

## Moduły konstrukcyjne
### Magistrale zewnętrzne

Procesor posiada trzy rodzaje magistral:
- **danych** – zazwyczaj o długości słowa maszynowego procesora,
- **adresową** – determinującą rozmiar pamięci jaką może procesor zaadresować,
- **kontrolną** – służącą do: przesyłania poleceń dla procesora, komunikacji z różnymi układami komputera, sterowania zapisem do i odczytem z pamięci oraz urządzeń we/wy.
### Rejestry

**Rejestry** służą do przechowywania wartości, jakie są produktami wykonania instrukcji procesora. Konstrukcyjnie rejestr jest pamięcią statyczną, wykonaną z przerzutników (typu D).
Procesor w rejestrach przechowuje:
- argumenty i wyniki operacji arytmetycznych i logicznych,
- wartości stałe (tylko do odczytu)
- adresy pamięci,
- dane aplikacji,
- dane kontrolne.
Zazwyczaj rejestry łączy się w bloki (ang. registers fields), posiadające wspólne wejścia i wyjścia (magistrale) oraz wejścia sterujące.
W nowoczesnych procesorach rejestry potrafią samodzielnie wykonywać złożone operacje arytmetyczno-logiczne.
### Układ arytmetyczny i rejestr stanu

Układ arytmetyczno-logicznych (ALU) jest modułem wykonującym w procesorze obliczenia. Nowoczesne procesory posiadają od kilku do kilkunastu ALU na jeden rdzeń, dzięki czemu możliwe jest realizowane zadań optymalizacyjnych.

Zazwyczaj ALU wykonuje operacje:
- arytmetyczne: dodawanie, odejmowanie, mnożenie …
- logiczne: sumę logiczną, iloczyn logiczny, negację …
- inkrementację / dekrementację,
- wyliczenie na żądanie bitów stanu.

W typowych konstrukcjach układ ALU oblicza również pewne dodatkowe dane, charakteryzujące wynik, np. informujące że wynikiem jest wartość zero. Takie informacje znajdują się w rejestrze stanu (statusu).

Informacje z rejestru stanu wpływają na decyzje podejmowane przez procesor odnośnie wykonania instrukcji z różnych grup rozkazów, w szczególności skoków warunkowych.




