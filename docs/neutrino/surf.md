---
layout: default
title: SURF
nav_order: 3
parent: Neutrino
permalink: /surf

---

![](/images/01-surf.png)

**SURF** (Smart Utility Recapitalization Feature) to nowy token zaprojektowany w celu poprawy mechaniki rekapitalizacji rezerw USDN.

Rezerwy WAVES wspierają istniejącą podaż stablecoina USDN. Każdy token WAVES przekazany do inteligentnego kontraktu w zamian za USDN jest utrzymywany jako zabezpieczenie w celu wsparcia USDN. Backing Ratio (BR) to wartość WAVES na kontrakcie vs. wartość podaży USDN. Trzy zmienne wpływają na BR: ilość wyemitowanych USDN, cena rynkowa WAVES oraz ilość WAVES na kontrakcie smart.

Na przykład, jeśli wartość rezerw jest niewystarczająca, aby pokryć całą wartość stablecoina dokładnie o połowę, to BR wynosi 50%. Z drugiej strony, jeśli kapitalizacja rezerw jest wyższa od podaży o 50%, wtedy BR wynosi 150%.

Token SURF pomoże osiągnąć równowagę BR i zapewni dodatkowe zachęty dla społeczności i inwestorów.

**Długa historia w skrócie:**

* SURF staje się dostępny do zakupu, gdy BR jest niższy niż 100%.
* Cena SURF będzie równa BR, tj. 50% BR = SURF $0.50 USDN
* Staked SURF daje pasywny dochód i inne korzyści
* Kiedy BR wzrośnie powyżej 115%, SURF zostanie automatycznie zamieniony na USDN w stosunku 1:1.

## Dlaczego warto używać SURF i jak zarobić na nim najwięcej?

SURF staje się dostępny do zakupu (emisji poprzez smart contract) poprzez zablokowanie USDN lub WAVES na smart contract tylko wtedy, gdy BR (Backing Ratio) jest <100%.

Zablokowany WAVES jest dodawany do istniejących rezerw, aby zapewnić dodatkową kapitalizację dla rezerw USDN i zwiększyć BR. Zablokowany USDN jest spalany, co zmniejsza całkowitą podaż USDN w obiegu i również zwiększa BR.

![](/images/02-surf.png)

Zakup SURF za USDN jest nieco bardziej opłacalny niż zakup za WAVES, natomiast zakup za WAVES ma większy wpływ na wartość BR. Do obliczania ceny SURF stosuje się następujące wzory.

Przy zakupie za USDN:
![](/images/03-surf.png)

przy zakupie za WAVES:
![](/images/04-surf.png)

> gdzie:
> R (rezerwa) - oznacza wielkość rezerw WAVES zabezpieczających podaż USDN
> S (supply) - oznacza całkowitą podaż USDN w obiegu
> price - to cena WAVES w USDN.

Cena SURF emitowanego poprzez smart contract zależy od aktualnego BR i ilości, którą chcesz kupić, więc im więcej kupujesz, tym wyższa staje się średnia cena SURF.
Najlepszym momentem na zakup SURF jest czas, kiedy BR jest niski.

### Przykład

Załóżmy, że cena WAVES wynosi ~5,6 USDN, natomiast BR wynosi aż 17%, co oznacza, że cena kontraktowa SURF wynosi 0,17 USDN. Ilość WAVES w rezerwach wynosi 22 071 844 przy łącznej podaży 727 068 652 USDN. (w tym przykładzie, ze względu na stosunkowo małe liczby, pomińmy wpływ ceny, co oznacza, że im więcej SURF kupujesz, tym wyższy staje się BR i średnia cena zakupu SURF).

Jeśli wydasz $10,000 w WAVES na zakup SURF, otrzymasz ~58,820 SURF i zwiększysz obecny BR o 0.00137%.
Jeśli wydasz $10,000 w USDN na zakup SURF, otrzymasz ~58,822 SURF i zwiększysz obecny BR o 0.00023%.

![](/images/05-surf.png)

## Stejkuj Twoje SURF, aby uzyskać wszystkie korzyści z posiadania gNSBT (otrzymasz 1 gNSBT za 300* SURF) i więcej:

* Uzyskaj możliwość swapowania WAVES↔USDN. Twoja dzienna Max Kwota Swapu zależy od Twojego udziału w gNSBT. Wykorzystaj funkcję swap, aby uzyskać dodatkowy zysk na arbitrażu, jeśli cena USDN na giełdach spadnie poniżej 1$.
* Otrzymuj regularne nagrody w zależności od udziału w gNSBT i dziennych opłat za wymianę (Protocol Fees). Odbierz nagrody w dowolnym momencie.
* Zdobądź prawo głosu, aby wpłynąć na decyzje dotyczące protokołu Neutrino. Ze względów bezpieczeństwa, stakerzy SURF otrzymują prawo głosu z opóźnieniem 20,160 bloków ( ~2 tygodnie).
* Uzyskaj zysk, gdy BR jest >115%, a Twój stak SURF zostanie automatycznie zamieniony na USDN w stosunku 1:1.

*Później ta wartość będzie regulowana za pomocą głosowania społeczności.*

## Jak działa automatyczna konwersja?

1) Kiedy BR osiągnie 115%, zostanie uruchomiona automatyczna konwersja SURF na USDN.

2) System zmniejsza BR o 10%, aby wyemitować dodatkowe USDN na spłatę posiadaczy SURF, dzięki czemu BR spada do 105%.

![](/images/06-surf.png)

> gdzie:
> R (reserve) - oznacza wielkość rezerw WAVES zabezpieczających podaż USDN
> S (supply) - oznacza całkowitą podaż USDN w obiegu
> price - cena WAVES w USDN

Nowo wyemitowana kwota USDN jest przechowywana na kontrakcie (dopóki nie zostanie zażądana), aby spłacić wszystkich posiadaczy SURF poprzez konwersję procentu (p%) ich staked SURF na USDN. Procent spłaty jest oparty na całkowitej ilości wyemitowanych SURF i ilości dodatkowo wyemitowanych USDN.

3) Użytkownicy, którzy postawią swoje SURF, otrzymają automatycznie procent p% z postawionej kwoty SURF zamieniony na USDN.

![](/images/07-surf.png)

> gdzie:
> supplySURF - oznacza całkowitą dostawę obiegową SURF

4) Użytkownicy, którzy nie posiadają SURF podczas automatycznej konwersji, nadal będą mogli otrzymać swoje USDN poprzez stakowanie SURF, ponieważ kontrakt wydaje USDN dla wszystkich użytkowników, którzy posiadają SURF, nie tylko dla stakerów. Jednak jedynym sposobem na uzyskanie przeliczonej kwoty SURF jest postawienie go na stosie.

5) Powstała w ten sposób przeliczona kwota pozostaje na kontrakcie, więc użytkownicy mogą ją w każdej chwili zażądać. Wszystkie skonwertowane SURFy są spalane.

6) Kiedy postawiona kwota SURF jest zmniejszona z powodu konwersji, wtedy kwota gNSBT również zostaje zmniejszona.

7) Stakerzy SURF mogą obliczyć ile USDN otrzymają podczas cyklu konwersji według następującego wzoru:

![](/images/08-surf.png)

> gdzie:
> SSA - to Twoja stakowana kwota SURF

8) Istnieje duże prawdopodobieństwo, że konwersja wszystkich SURFów zajmie kilka cykli auto konwersji. Proces powtarza się za każdym razem, gdy BR trafi na 115%, aż cała podaż SURFów zostanie przekonwertowana na USDN.

## SURF vs. NSBT. Który z nich jest lepszy?

W tej chwili, większość podaży NSBT jest zamknięta w długoterminowym stakingu. W momencie pisania tego artykułu, ponad 96% całkowitej podaży NSBT zostało wybite, a ponad 88% jest stakowane. W rezultacie, trudno jest kupić NSBT. Dodatkowo, cena inteligentnego kontraktu ciągle rośnie z powodu mechaniki Moon Factor.

Tymczasem stakerzy NSBT nadal osiągają codzienne zyski i używają swapów do arbitrażu i innych celów.

Inwestowanie w SURF to łatwy sposób dla społeczności Neutrino i nowych inwestorów, aby wspierać protokół Neutrino i uzyskać te same korzyści, co stakerzy NSBT. Na dodatek, nowy produkt zapewnia również świetny zwrot z inwestycji (ROI), gdy BR się poprawi. Zakup SURF przy bardzo niskim BR może dać nawet większy zysk niż stakerzy NSBT mogą uzyskać za tę samą wydaną kwotę.

### Przykład

Załóżmy, że BR wynosi aż 20%; oznacza to, że cena kontraktowa SURF wynosi 0,20 USDN. (w tym przykładzie, ze względu na stosunkowo małe liczby, pomińmy wpływ ceny, co oznacza, że im więcej SURF-u kupujesz, tym wyższy staje się BR i średnia cena zakupu SURF-u).

Wydajesz 10.000 USDN, aby kupić 50.000 SURF, następnie stawiasz je i otrzymujesz 166,6 gNSBT oraz wszystkie związane z tym korzyści.

![](/images/09-surf.png)

Jeśli wydasz tę samą kwotę 10.000 USDN na zakup NSBT (przy obecnej cenie rynkowej=19 USDN), otrzymasz 526 NSBT, co przy stawce dałoby 526 gNSBT.

Pamiętaj, że w przyszłości mechanika Moon Factor może zasadniczo zwiększyć cenę NSBT. Ponadto, jeśli cena WAVES wzrośnie, to cena NSBT będzie rosła wykładniczo. Z drugiej strony, cena SURF rośnie liniowo.

Kiedy BR przekroczy 115%, Twoje 50.000 SURF zostanie ostatecznie automatycznie zamienione na 50.000 USDN, dzięki czemu zarobisz x5 swojej pierwotnej inwestycji. Istnieje możliwość, ale nie ma gwarancji, że przy takim BR, cena NSBT stanie się x5. Najprawdopodobniej nie, dopóki BR nie będzie wystarczająco wysoki, aby spłacić wszystkich stakerów SURF.

![](/images/10-surf.png)

*APR tokenów SURF i NSBT opiera się na zebranych opłatach za protokół, więc wartość referencyjna zależy od kwot i częstotliwości swapów WAVES↔USDN oraz czasu istnienia tokena.*

*Wartości referencyjne obliczane są w oparciu o dzień 29 lipca 2022 roku: BR=20%, cena SURF 0,20 USDN, cena NSBT 19 USDN.*

## Wniosek

Powyższy przykład pokazuje, że tokeny NSBT i SURF są bardzo podobne, ale żaden z nich nie jest jednoznacznym liderem. Biorąc pod uwagę zwrot z inwestycji (gdy BR staje się wysoki), token SURF zakupiony przy niskim BR może zapewnić nawet większy zysk niż NSBT. Potencjalne zyski tokena SURF są łatwe do obliczenia i zrozumienia; plus, przychodzi ze wszystkimi korzyściami posiadania gNSBT bez opłaty ustakingowej. SURF token dodaje unikalny i godny uwagi atut do tokenomiki Neutrino, zapewniając dodatkową możliwość wpływu społeczności Neutrino i nowych inwestorów na rozwój protokołu. Token SURF przyczyni się do stabilności i bodźców bezpieczeństwa systemu i ustanowi Neutrino jako najsilniejszy algorytmiczny stabilny protokół aktywów.

**Zakup SURF, aby osiągnąć swój zysk i wspierać ekosystem!**

[![](/images/11-surf.png)](https://neutrino.at/buy/SURF){:target="_blank"}

---
reference: [What is SURF and why is it important for the Neutrino ecosystem?
](https://medium.com/neutrinoteam/what-is-surf-and-why-is-it-important-for-the-neutrino-ecosystem-8962c2230049) 