# Wyklad no. 1
## Tablice routingu

Łączone:

-   automatycznie - sieci bezposrdenio polaczone z routerem
-   recznie
-   dynamicznie

Dla recznych i dynamicznych typow mamy:

-   budowa:
    -   ip_route
    -   adres_sieci
    -   maska
    -   nastepny_skok:
-   typy:
    -   routing "distance vector" (RIPv1, RIPv2)
    -   routing "link-state" (OSPF)

## Pakiety TCP

TCP to złożony, połączeniowy protokół, którego użycie ma gwarantować niezawodne dostarczenie danych oraz kontrolę przepływu. W procesie enkapsulacji, do nagłówka TCP dodawanych jest aż 20 bajtów danych sterujących, ale tego wymaga niezawodność TCP. Aplikacje korzystające z tego protokołu to przeglądarki internetowe, programy pocztowe czy programy do przesyłania plików. Wzór segmentu TCP widzicie poniżej. Liczby w nawiasach oznaczają ilość bitów, zarezerwowaną dla danego pola.

*Nagłówek TCP:*
![naglowek tcp](naglowek-tcp.jpeg)

- **Port źródłowy** – port aplikacji, z której wysłano dane.
- **Port docelowy** – port aplikacji, do której wysłano dane.
- **Numer sekwencyjny** – numer ostatniego bajtu w segmencie.
- **Numer potwierdzenia** – numer następnego bajtu oczekiwanego przez odbiorcę.
- **Długość** - długość całego segmentu TCP.
- **Bity kodu (flagi)** – informacje kontrolne dotyczące segmentu.
- **Okno** - ilość danych jaka może zostać przesłana bez potwierdzenia.
- **Suma kontrolna** – używana do sprawdzania poprawności przesłanych danych.
- **Wskaźnik pilności** – używany tylko kiedy ustawiona jest flaga URG.