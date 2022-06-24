---
layout: default
title: Perpetual Futures
nav_order: 61
parent: Tsunami
permalink: /tsunami/futures

---

![futures](/images/futures.png)

## Kontrakty terminowe typu Perpetual Futures

Perpetual Futures to kontrakty rozliczane w gotówce (stablecoin), które nie mają terminu wygaśnięcia. Handel wieczystymi kontraktami futures jest podobny do handlu spot opartego na depozycie zabezpieczającym, z tą różnicą, że do Twojej pozycji nie jest stosowana stopa procentowa.

Cena kontraktu terminowego może odbiegać od ceny aktywów bazowych (ceny indeksu). Jeśli inwestorzy oczekują wzrostu ceny aktywa bazowego, kontrakt terminowy może być sprzedawany z premią. W przeciwnym razie, gdy uczestnicy rynku oczekują, że cena aktywa bazowego spadnie, kontrakt terminowy może być sprzedawany z dyskontem.

Aby cena kontraktu future była zbliżona do ceny indeksu, stosuje się płatność finansującą.

> **Mechanizm finansowania**
> 
> *Co godzinę traderzy z otwartymi długimi lub krótkimi pozycjami wypłacają sobie nawzajem płatność finansującą, w zależności od warunków rynkowych. Jeśli cena kontraktu jest wyższa od ceny spot, inwestorzy z długimi pozycjami płacą inwestorom z krótkimi. Jeśli cena kontraktu jest niższa od ceny spot, shorty będą płacić longom. W ten sposób inwestorzy są zachęcani do zajmowania niepopularnej strony rynku.*

![vAMM](/images/vamm.png)

## Wirtualny AMM (vAMM)

Wirtualny automatyczny animator rynku (vAMM) to system, który zapewnia syntetyczną (lub wirtualną) płynność, umożliwiając traderom kupno i sprzedaż instrumentów pochodnych w całości na blockchainie.

Tradycyjna giełda oparta na AMM ma dwa rodzaje użytkowników: dostawców płynności, którzy dostarczają tokeny, oraz traderów, którzy wymieniają dostępne tokeny. Ceny, po których dochodzi do wymiany, są ustalane na podstawie wzoru matematycznego.

Jak sugeruje "wirtualna" część vAMM, zamiast wymieniać rzeczywiste tokeny, vAMM są używane do wymiany wirtualnych, syntetycznych aktywów, takich jak kontrakty na instrumenty pochodne. Żadne realne aktywa nie są przechowywane wewnątrz samego vAMM; zamiast tego traderzy są w stanie dokonywać transakcji lewarowanych w oparciu o zabezpieczenie przechowywane w skarbcu inteligentnych kontraktów. vAMM służą do wykrywania cen przy operowaniu dźwignią.

Wykorzystanie vAMM jako podstawy dla kontraktów na instrumenty pochodne przynosi następujące korzyści:

1. Nie wymaga dostawców płynności (LP), co pozwala na prowadzenie większej liczby rynków z mniejszymi poślizgami i większą płynnością.
2. Rynek vAMM jest zawsze w pełni zabezpieczony
3. Ze względu na brak wymiany rzeczywistych aktywów, pozwala to na łatwe uruchomienie produktów niezwiązanych z kryptowalutami, takich jak towary i handel NFT

### Przykład

> *W tym przykładzie nie uwzględniono opłat transakcyjnych*

AMM wykorzystuje formułę `x * y = k`. Załóżmy, że cena Waves wynosi 8 USDN za Waves, a vAMM jest inicjalizowany z płynnością początkową 100000.

| USDN   | WAVES | K          |
|:------:|:-----:|:----------:|
| 100000 | 12500 | 1250000000 |

Alicja dokonuje transakcji kupna (long) WAVES z dźwignią x2, wykorzystując jako zabezpieczenie 2000 USDN. W ten sposób strona USDN w puli zwiększy się o 4000. Zgodnie z formułą AMM, k musi pozostać stałe. Obliczmy sumę WAVES, które otrzyma Alicja.

```
104000 * (12500 - x) = 1250000000
x = 480.777
```

Teraz Alicja ma pozycję 480,777 WAVES, a vAMM ma następujący nowy stan:

| USDN   | WAVES    | K          |
|:------:|:--------:|:----------:|
| 104000 | 12019.22 | 1250000000 |

Inny inwestor (Bob) wchodzi i zleca longi na Waves używając 2000 USDN jako zabezpieczenie, ale z dźwignią x3. Ponownie, dodamy dodatkowe 60000 USDN do puli USD i stworzymy nowy stan vAMM oraz wielkość pozycji Boba w następujący sposób:

```
110000 * (12019.2 - x) = 1250000000
x = 655.564
```

Teraz Bob ma pozycję 655,564 Waves, a vAMM ma następujący nowy stan:

| USDN   | WAVES     | K          |
|:------:|:---------:|:----------:|
| 104000 | 11363.656 | 1250000000 |

Alicja zamyka swoją pozycję o wartości 480,777 Waves, więc 480,777 Waves zostaje dodane z powrotem do puli. Ile USDN Alice otrzyma w zamian? Przekonajmy się.

```
(110000 - x) * (11363.656 + 480.777) = 1250000000
x = 4465.19
```

Pamiętaj, że Alicja użyła 4000 USDN jako zabezpieczenia, więc PnL = 4465,19 - 4000 = 465,19. Alicja osiągnęła zysk w wysokości 465,19 USDN. vAMM znajduje się teraz w następującym stanie:

| USDN      | WAVES   | K          |
|:---------:|:-------:|:----------:|
| 105534.81 | 11844.4 | 1250000000 |

Teraz Bob zamyka swoją pozycję o wartości 655,564 WAVES. Ile USDN otrzyma?

```
(105534.81 - x) * (11844.4 + 655.564) = 1250000000
x = 5534.52
```

Pamiętaj, że Bob użył 6000 USDN jako zabezpieczenia. 5534.52 - 6000 = -465.48. Bob poniósł stratę w wysokości 465,48. Zauważ, że zysk Alicji jest dokładnie taki sam jak strata Boba. Dzieje się tak dlatego, że na zdecentralizowanej giełdzie kontraktów terminowych PnL jest rozliczany między inwestorami (a nie między inwestorem a izbą rozliczeniową / brokerem).

## Finansowanie Płatności

Co godzinę traderzy z otwartymi długimi lub krótkimi pozycjami wypłacają sobie nawzajem płatność za finansowanie, w zależności od warunków rynkowych. Jeśli cena kontraktu jest wyższa od ceny indeksu, longi płacą shortom. Jeśli cena kontraktu jest niższa od ceny indeksu, shorty płacą longom. Wielkość wypłaty finansowania jest funkcją różnicy pomiędzy ceną kontraktu a ceną indeksu, jak również wielkości Państwa pozycji. Zachęca to traderów do opowiedzenia się po niepopularnej stronie rynku.

Okresowe płatności finansowe są najczęstszym mechanizmem wykorzystywanym przez giełdy do przeprowadzania perpetual swap. Płatności za finansowanie działają w celu zbliżenia ceny mark (cena na Tsunami) i ceny indeksu (średnia cena z głównych giełd).

Kwota płatności finansującej jest obliczana według wzoru:
![Tsunami Funding Payment](/images/tsunami-funding-payment.png)

Z reguły - im większa różnica między ceną mark a ceną indeksu, tym więcej funduszy zapłacisz otwierając pozycję dywergencyjną, a tym więcej zarobisz otwierając pozycję konwergencyjną.

## Likwidacja

Kontrakty terminowe są instrumentem lewarowanym, co zwiększa zarówno potencjalne zyski, jak i straty. Dzięki vAMM możesz praktycznie pożyczyć dodatkowe środki, aby zwiększyć wielkość pozycji. Handel z wykorzystaniem dźwigni finansowej jest wysoce ryzykownym działaniem, z możliwością likwidacji.

Na przykład, jeżeli otworzysz pozycję lewarowaną x3 z 200 USDN, pozycja początkowa jest warta 600 USDN, a 400 z nich jest pożyczone. Zabezpieczenie w wysokości 200 USDN zostanie w pełni wykorzystane, jeżeli całkowita wartość pozycji spadnie o około 30%.

Likwidacja to mechanizm, służący do zamykania pozycji, które są *"pod wodą" (nie są w stanie utrzymać minimalnego wymaganego depozytu zabezpieczającego)*. Gwałtowny ruch ceny może narazić giełdę na ryzyko, ponieważ straty mogą przekroczyć depozyt zabezpieczający. Dlatego giełda nakłada wymóg minimalnego wskaźnika depozytu zabezpieczającego, aby pomóc w likwidacji podczas niekorzystnych warunków rynkowych.

![Liquidation](/images/tsunami-liquidation.png)

Tsunami używa wskaźnika depozytu zabezpieczającego 8,5% do uruchomienia likwidacji. Jeśli wskaźnik depozytu zabezpieczającego spadnie poniżej 8,5%, wielkość pozycji zostanie zlikwidowana, pozostawiając zabezpieczenie w vAMM jako zysk dla traderów strony przeciwnej.

Likwidacje są przeprowadzane przez boty likwidatorów. Początkowo zespół Tsunami będzie prowadził boty likwidacyjne, później zostaną one otwarte i udostępnione społeczności do prowadzenia botów.

## Fundusz ubezpieczeniowy

Handel z wykorzystaniem dźwigni nieodłącznie wiąże się z pewnym ryzykiem zarówno dla inwestora, jak i dla protokołu. Podczas bardzo zmiennych warunków rynkowych, poślizgi i opóźnienia w realizacji zleceń mogą spowodować, że na niektórych rachunkach po rozliczeniu pojawi się saldo ujemne.

> *Fundusz ubezpieczeniowy to siatka bezpieczeństwa, która utrzymuje wypłacalność protokołu, gdy rachunek ma ujemny wskaźnik marży. Straty z likwidacji takich rachunków są kompensowane przez fundusz ubezpieczeniowy.*

1. Fundusz ubezpieczeniowy jest początkowo zasilany przez zespół
2. Początkowa wielkość funduszu ubezpieczeniowego wynosi 10 000 USD.
3. Tsunami nakłada 1% opłaty od każdej transakcji. Połowa tej opłaty trafia do funduszu ubezpieczeniowego.
4. Dodatkowo, podczas likwidacji część kary likwidacyjnej trafia do funduszu ubezpieczeniowego.