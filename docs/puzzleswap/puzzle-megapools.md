---
layout: default
title: Mega Pools
nav_order: 1
parent: PuzzleSwap
---

![](/images/03-puzzle.png)

## Mega Pule

Serwisy DeFi osiągają swoje stopy zwrotu poprzez wydobywanie płynności, co oznacza emisję nowego tokena i rozprowadzanie go wśród inwestorów. W przeciwieństwie do tego, model puli Puzzle Swap pozwala na uzyskanie wysokiego pułapu rentowności przy jednoczesnym pominięciu nieskończonego bicia tokenów. Niezależność inwestorów od ceny i emisji tokenów sprawia, że jest to bardzo zrównoważone rozwiązanie.
Co zatem zapewnia rentowność? Przede wszystkim prowizje. Dostawcy płynności otrzymują wynagrodzenie za każdą transakcję, a jest ich bardzo dużo. Wysoki wolumen można wytłumaczyć matematyką stojącą za mega pulami, która faworyzuje arbitrażystów i traderów. 
Pojedyncza transakcja może spowodować zawarcie 3-5 innych transakcji, co zwiększy wolumen obrotu, a w konsekwencji prowizje dostawców płynności.

Wysoka stopa zwrotu nie jest jednak podstawową zaletą mega puli. Istnieje również mniej oczywista, ale integralna zaleta.

### Jak to działa?

Mega pule, wraz z Agregatorem Puzzle, są kluczowymi elementami systemu Puzzle Swap.
Klasyczny model AMM zakłada, że w jednej puli znajdują się tylko dwa aktywa, które są wymieniane między sobą. Puzzle Swap wykorzystuje inny model AMM, który obsługuje do 10 aktywów w jednej puli, ponieważ do wywołania skryptu na Waves można dołączyć maksymalnie 10 płatności. Takie pule nazywamy mega pulami.

**Co sprawia, że mega pula jest wyjątkowa?**

Użytkownicy korzystają z wygody bezpośredniej wymiany pomiędzy dowolnymi parami tokenów w puli.
Każda transakcja wpływa nie tylko na cenę dwóch wymienianych tokenów, ale także na ceny innych tokenów w puli, co stwarza ciągłe możliwości dla arbitrażystów.
W ten sposób jedna transakcja może spowodować 3-5 innych transakcji, co zwiększa wolumen obrotu, a w konsekwencji opłaty. Dlatego też inwestowanie w mega pule okazuje się bardziej efektywne niż w przypadku tradycyjnych puli.
Oprócz wysokiej stopy zwrotu, model mega puli zmniejsza ryzyko dostawców płynności: dywersyfikują oni swoje portfele i jednocześnie ograniczają ich zmienność. Podobny instrument w tradycyjnych finansach nazywany jest indeksem - papierem wartościowym o wartości opartej na wszystkich aktywach bazowych.

**Wagi tokenów**

Wagi tokenów w puli są ustalane w momencie tworzenia puli i nigdy się nie zmieniają. Waga tokena to wartość płynności w danym tokenie (w USDN) w stosunku do całkowitej wartości płynności puli.

Przykład puli, Waves DeFi:

np. w puli  Waves DeFi :
WAVES i PUZZLE mają wagę po 20%.
USDN mają wagę 15%
EGG i USDT mają wagę po 10%
Pozostałe tokeny mają wagę 5% każdy.

![](/images/04-puzzle.png)

Gdy użytkownik wymienia na przykład WAVES na EGG (wydaje WAVES i otrzymuje EGG), ilość tych tokenów w puli zmienia się, zmieniają się też kursy, a wagi tokenów pozostają takie same.

**Matematyka zamiany:**
Formuła, na której opierają się mega pule, została zaproponowana przez  Balancer:

![](/images/05-puzzle.png)

> Gdzie:
> `t` to zakres tokenów w puli
> `Bt` to saldo tokena w puli
> `Wt` to znormalizowana waga tokena
> `V` jest stałą w przypadku zamiany

**Przykład:** Pula EGG zawiera 80% EGG i 20% USDN. Gdy aktualne salda są takie, jak na poniższym rysunku, wartość `V` oblicza się następująco:

![](/images/06-puzzle.png)

![](/images/07-puzzle.png)

Jak udowodnił Balancer w swoim Whitepaper, w momencie gdy użytkownik wydaje token `i`, aby otrzymać token `o`, kwota wyjściowa jest obliczana w następujący sposób:

![](/images/08-puzzle.png)

> Gdzie:
> `Ao` - ilość tokenów wyjściowych;
> `Bo` - początkowe saldo tokenów wyjściowych w puli;
> `Wo` - znormalizowana waga tokena wyjściowego;
> `Ai` - ilość tokenów wejściowych;
> `Bi` - początkowe saldo tokenów wejściowych;
> `Wi` - znormalizowana waga tokena wejściowego
> 
> Kwota, którą użytkownik faktycznie otrzymuje, nie wynosi `Ao`, lecz `Ao` jest pomniejszona o opłatę (fee).

## Opłaty

Dla obecnie istniejących mega puli opłata swapowa wynosi 2% kwoty wyjściowej:

1,2% trafia do dostawców płynności

0,8% trafia do PUZZLE stakers.

Opłata jest dość wysoka, więc dostawcy płynności i stakerzy korzystają z wysokiej APY. Jednocześnie agregator Puzzle uczciwie wyszukuje najbardziej opłacalne trasy wymiany dla traderów i często okazuje się, że wymiana na Puzzle jest tańsza nawet po uwzględnieniu opłaty.

Użytkownicy protokołu mają już możliwość dodawania własnych mega puli i ustalania opłaty w wysokości od 0,5% do 3%.

## Zapewnianie płynności

Istnieją dwie możliwości dodania płynności do mega puli.
Pierwszy poprzez dodanie wszystkich potrzebnych w puli tokenów. Powinieneś mieć wszystkie tokeny z puli w swoim portfelu; następnie możesz zainwestować wartość w każdy token proporcjonalną do jego wagi. Serwis oblicza odpowiednie ilości tokenów, wystarczy przesunąć suwak, aby ustawić procent maksymalnej wartości, jaką możesz zainwestować.
Na przykład, jeśli masz 1 EGG o aktualnej wartości 250 USD i tylko 50 USDN. Możesz dodać maksymalnie 0,8 EGG (lub 200 USD, co stanowi 80% wartości depozytu) i 50 USDN (20% wartości). Jeśli zdecydujesz się zainwestować 50% maksimum, dołożysz 0,4 EGG i 25 USDN.

![](/images/09-puzzle.png)

Drugi posiadając jeden token ustalony przez serwis. Na przykład USDN dla Waves DeFi Pool lub EGG dla Egg Pool. Ta opcja jest tylko dla Twojej wygody, więc nie musisz trzymać wszystkich tokenów w swoim portfelu przed dostarczeniem płynności. Pamiętaj jednak, że token, który wpłacasz, jest konwertowany (za opłatą) na inne tokeny z puli, więc Twoja inwestycja może podlegać wahaniom cen.
Wycofując płynność, otrzymujesz z powrotem wszystkie tokeny z puli, bez względu na to, jakiej opcji użyłeś do zapewnienia płynności.

### Dochód dla dostawców płynności

Za każdym razem, gdy dochodzi do zamiany, mega pula rozdziela opłatę (domyślnie 1,2%) pomiędzy dostawców płynności. Dla Twojej wygody, większość opłaty jest przeliczana na USDN; reszta pozostaje w tokenie, w którym została pobrana. Możesz więc uzyskać dochód we wszystkich tokenach z puli. Pracujemy nad przeliczeniem 100% opłat na USDN.

Możesz odebrać swoje zarobki, kiedy tylko chcesz.

## Ukryta siła mega puli

Można zapytać, co może być ważniejsze niż 1500% APY? Nasza odpowiedź brzmi: bezpieczeństwo inwestycji. Model mega puli pozwala Ci jednocześnie zdywersyfikować portfel i ograniczyć jego zmienność.

W ten sposób, zapewniając płynność w mega pulach na Puzzle Swap, nie tylko otrzymujesz zwrot z inwestycji, ale także nowy token puli zabezpieczony wszystkimi aktywami depozytowymi.

W tradycyjnych finansach istnieje podobny instrument zwany indeksem - papier wartościowy, którego wartość opiera się na wszystkich aktywach bazowych.

W porównaniu z tradycyjnymi finansami, Puzzle Swap ma swoje zalety również tutaj! Zgodnie z zasadami DeFi, cena indeksu mega puli jest ustalana algorytmicznie i nie zależy od pośredników, którzy mogą nią manipulować. Wartość takiego indeksu opiera się wyłącznie na wartości aktywów wchodzących w skład puli.
Na przykład, w puli Farms 2 znajduje się 9 różnych typów tokenów o łącznej wartości 112 500 USD. Te tokeny zostaną zamienione na 222 tokeny indeksowe. Konto na powyższym zrzucie ekranu posiada 1,87 tokenów indeksowych, co stanowi równowartość 947$.

Obecnie wszystkie tokeny indeksowe są automatycznie stakowane, aby zarobić APY w puli. Wyobraź sobie jednak, że tokenami indeksowymi można by handlować lub po prostu przechowywać je w swoim portfelu - tu dopiero zaczyna się cała zabawa!

## Niestandardowe mega pule

Puzzle swap oferuje tworzenie własnych niestandardowych mega puli. Pule niestandardowe powinny być szczególnie atrakcyjne dla dużych inwestorów, którzy tworzą pulę w celu maksymalizacji korzyści ze swojego portfela. Mianowicie, dostosowują skład puli i uzyskują najwyższą możliwą APY dzięki wykorzystaniu swojej płynności.

Jednak celem zespołu Puzzle jest nie tylko stworzenie wygodnego narzędzia finansowego dla wielorybów, ale także zapewnienie możliwości zarabiania mniejszym inwestorom i nowym graczom. Jeśli jesteś dobrze zorientowany w świecie DeFi, to stworzenie własnej mega puli jest szansą na zbudowanie ciekawej kombinacji tokenów i przyciągnięcie dużych inwestorów, dzięki czemu możesz zarabiać na prowizji dla właściciela puli.

\
\
\
Materiał opracowany przez [QQryq](https://twitter.com/q_qryq), na podstawie [dokumentacji PuzzleSwap](https://medium.com/@puzzleswap)