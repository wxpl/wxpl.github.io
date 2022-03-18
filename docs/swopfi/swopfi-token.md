---
layout: default
title: Token
nav_order: 31
parent: SwopFi
permalink: /swop-token
---
<details open markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# SWOP jest tutaj

2021-02-01 [Medium](https://medium.com/swop-fi/what-will-be-the-swop-tokens-price-55921fbe6456)

![](/images/01_swop-is-here.png)

Dziś mamy przyjemność zaprezentować SWOP - token zarządzania protokołem i specjalną zachętę dla dostawców płynności.
1 milon SWOP jest zarezerwowane dla dostawców płynności typu early-bird, którym udało się zapewnić płynność przed startem. Nagroda za early-bird jest obliczana i zapisywana; będzie odblokowywana stopniowo w ciągu roku, jak pisaliśmy wcześniej. Kolejny 1 milion zostanie rozdane w ciągu pierwszego roku jako nagroda za farming SWOP zgodnie z planem emisji.

## Jak zdobyć więcej SWOP-ów

Dodaj płynność do wybranej przez siebie puli. W zamian otrzymasz tokeny udziałów.
Stawiaj swoje tokeny udziałów, by otrzymać nagrodę za farmowanie SWOP. Zobacz sekcję Farmowanie SWOP w naszym przewodniku.
Wykorzystaj swoje dostępne SWOP-y, zarówno z nagrody za farmowanie, jak i nagrody early-bird, by otrzymać nagrodę za zarządzanie. Kiedy nagroda za zarządzanie zostanie ci przyznana, możesz ją również wykorzystać. Zobacz sekcję Stake SWOP w naszym przewodniku.
Pamiętaj, że nie ma zrzutów z powietrza. Nagrodę możesz otrzymać po złożeniu wniosku. Zobacz sekcję Claim SWOP w naszym przewodniku.

![](/images/02_swop-is-here.png)

## SWOP farming: nagroda za zapewnienie płynności

Nagroda farming w SWOP jest przeznaczona dla dostawców płynności, którzy wnieśli swoje tokeny akcji do inteligentnego kontraktu SWOP-farming.

Oto, jak ta nagroda jest rozdzielana:

- Roczna kwota 1 milion SWOP jest dzielona przez liczbę bloków utworzonych w ciągu roku: 365 × 24 × 60 × 60 / 59,84, ponieważ średnie opóźnienie bloku wynosi 59,84 s. Zatem co minutę uwalnianych jest ~1,9 SWOP.
- Ilość SWOP-ów związana z każdym blokiem jest dzielona między pule płynności proporcjonalnie do wagi każdej z nich. Aktualne wagi puli możesz zobaczyć na stronie Informacje o pulach. Są one najpierw określane przez zespół projektowy, a następnie - na podstawie wyników głosowania.
- Ilość SWOP przyznanych dla danej puli jest dzielona między dostawców płynności w puli proporcjonalnie do tokenów akcji, które postawili w smart kontrakcie SWOP-farming.

Ilość SWOP związana z każdym blokiem staje się dostępna natychmiast po pojawieniu się bloku na blockchainie. W każdej chwili możesz zażądać dostępnej części nagrody SWOP-farming, a także postawić swoje tokeny SWOP, by zarządzać protokołem.

Zwróć uwagę, że nowa pula SWOP-USDN jest taka sama jak inne pule: możesz dodać do niej płynności, otrzymać tokeny akcji i stawiać je, by zarobić na nagrodę farming w SWOP.

## Stakowanie SWOP: nagroda za zarządzanie

Nagroda za zarządzanie jest przeznaczona dla tych, którzy postawili swoje tokeny SWOP na stakach.

Oto jak ta nagroda jest rozdzielana:

- Opłaty za zarządzanie (obecnie 40% opłat swapowych ze wszystkich puli płynności) są przeliczane na USDN i wykorzystywane do zakupu SWOP w nowej puli SWOP-USDN. Wykorzystywane są również opłaty za zarządzanie zgromadzone od początku projektu, ale dzienny wolumen wykupu nie może przekroczyć 1% kwoty SWOP w puli.
- Wykupione tokeny SWOP są dzielone między obecnych stakerów SWOP proporcjonalnie do wysokości ich stakedów.

Dzięki temu możesz nadal zarabiać tę nagrodę, nawet jeśli usuniesz płynność. Im więcej swapów ma miejsce, tym więcej opłat za zarządzanie jest pobieranych i tym większa jest całkowita nagroda za zarządzanie.

Nowa część nagrody za zarządzanie staje się dostępna mniej więcej raz na godzinę. Możesz odebrać swoją nagrodę lub stakować ją ponownie.

# Jaka będzie cena tokena SWOP?

2021-02-05 [Medium](https://medium.com/swop-fi/what-will-be-the-swop-tokens-price-55921fbe6456)

![](01_swop-price.png)

*W tym artykule omówimy główne czynniki, które mogą mieć wpływ na cenę tokena SWOP.*

Wiele osób zastanawia się nad ceną tokena SWOP w momencie emisji - kiedy dostawcy płynności zaczną zbierać nagrody w tych tokenach. Cena zostanie ustalona przez rynek, a my nie jesteśmy jasnowidzami, by móc ją przewidzieć. Możemy jednak przedstawić kilka faktów na temat tokena, a użytkownicy będą mogli sami wymyślić jego możliwą cenę.

1. SWOP jest tokenem zarządzania: użytkownicy będą mogli głosować za jego pomocą na najważniejsze ustawienia całego systemu swop.fi. Zasadniczo ma on realną wartość.
2. Cena SWOP jest wspierana przez opłaty swapowe we wszystkich pulach swop.fi: im większa liczba transakcji, tym wyższa cena SWOP.
3. Całkowita podaż tokenów SWOP będzie znacznie ograniczona.

## Funkcje zarządcze

Tokeny SWOP będą potrzebne do zarządzania nagrodami w pulach płynności na późniejszych etapach. W przeciwieństwie do etapu "early bird", w którym dostarczenie płynności do dowolnej puli było nagradzane taką samą ilością tokenów SWOP, na późniejszych etapach nagroda dla każdej puli będzie ustalana w drodze głosowania za pomocą tokenów SWOP. Udział danej puli w całkowitej liczbie głosów będzie odpowiadał proporcji wpływów z opłat wypłacanych jej uczestnikom jako nagrody w ciągu kolejnego tygodniowego okresu.

Poprzez głosowanie będzie można również zmieniać parametry systemu, takie jak wielkość opłat swapowych w pulach. Dodatkowo, żetony SWOP użyte w głosowaniu będą również zbierać nagrody.

## SWOP buyback

40% wpływów z opłat swapowych w pulach swop.fi jest przeznaczane na zakup tokenów SWOP z puli SWOP-USDN, podnosząc cenę SWOP. Codziennie można kupić nie więcej niż 1% wszystkich tokenów SWOP dostępnych w danej puli. Wykupione tokeny SWOP zostaną rozdane jako nagrody za tokeny stakowane do zarządzania.

## Podaż SWOP

W ciągu pierwszego roku od uruchomienia SWOP całkowita podaż będzie stopniowo wzrastać z 0 do 2 mln:

- 1 mln zostanie stopniowo odblokowany dla użytkowników, którzy zapewnili płynność w fazie early bird (kilka pierwszych miesięcy działania serwisu).
- Kolejny 1 mln tokenów będzie stopniowo udostępniany dostawcom płynności jako nagrody.

W ciągu drugiego roku udostępniony zostanie kolejny 1 mln tokenów SWOP. W każdym kolejnym roku podaż SWOP będzie się zmniejszać o 25%.

Ten diagram pokazuje planowaną podaż SWOP na najbliższe 10 lat. W 2031 roku zostanie wyemitowanych około 75 000 nowych tokenów, a całkowita podaż osiągnie około 5,7 mln.

[](/images/02_swop-price.png)

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*