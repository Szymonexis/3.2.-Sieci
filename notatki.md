# Wyklad no. 1
## Tablice routingu

Budowane:

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

## Konfiguracja RIP

*Broadcastami* wysylane sa informacje o aktualnej *tablicy routingu* danego routera za pomoca protokolu *UDP*. W ten sposob routery dzialajace na *RIP* sa w stanei dolaczyc taka informacje o tablicy routingu i powiekszyc swoja tablice o dodatkowe informacje. 

> ⚠ **Do tablicy routingu ostaja dodane tylko hopy routerow sasiadujacych**


Kazda sciezka posiada swoj koszt - jezeli router otrzyma od innego routera informacje o mniej kosztownej sciezce, to dana sciazka zostaje zmieniona na ta o mniejszym koszcie.

Istnienie danej sciezki jest powtwierdzane co 30 sekund - jezeli po 6 probach nie nie dojdzie do odpowiedzi, dana sciezka zostaje zmaknieta (aka. usunieta z tablicy routingu na danym routerze)

Kiedy dochodzi do zmain w tablicy routingu?
1. Kiedy aktualnie podlaczone urzadzenia i ich adresy zostana zmienione (bezposrednie lacze)
2. Kiedy juz istniejaca sciezka zmieni swoj koszt **(od routera sasiadujacego)**
3. Kiedy pojawi sie nowa sciezka **(od routera sasiadujacego)**

> ⚠ Na nastepne zajecia\
> Powtorzyc RIP i OSPF :3
