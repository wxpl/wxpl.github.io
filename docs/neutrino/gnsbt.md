---

layout: default
title: Governance gNSBT
nav_order: 21
parent: Neutrino
permalink: /nsbt-governance

---

[Protokół Neutrino](https://neutrino.at) został uruchomiony w 2019 roku i od tego czasu przeszedł sporo zmian. Jedną z nich było dodanie funkcji stakowania NSBT, która umożliwiła otrzymywanie pasywnego dochodu w kilku tokenach jednocześnie, a mianowicie: USDN (stablecoin), WAVES oraz tokenach DeFo.

Rok 2022 można nazwać rokiem Neutrino, ponieważ protokół przejdzie szereg zmian, aby osiągnąć długo oczekiwany cel - decentralizację. Pierwszym krokiem w tym kierunku jest zmiana mechaniki działania NSBT i operacji swap. Zanim jednak opiszemy nową mechanikę, podsumujmy wyniki z 2021 roku, ponieważ w niektórych przypadkach liczby mówią same za siebie.

1. Stakerzy NSBT zarobili w 2021 roku ponad 26,5 miliona dolarów! Rozdano 23.4M USDN, 52.8k WAVES, 1.58M EURN i inne aktywa DeFo.
2. 3000 użytkowników wzięło udział w stakingu NSBT.
3. Top 5 najlepszych zarobków stakerów NSBT w 2021 roku:
	3P2u***WHMd: $2,654,285
	3P5L***a9gY: $2,037,442
	3PE2***hwXa: 1 380 715 USD
	3PD9***Usdy: 1 196 840 USD
	3P8T***2F3K: 1 197 680 USD

Żałujesz, że nie masz NSBT? Nadal masz możliwość kupna na [Waves.Exchange](https://waves.exchange).

4. W momencie pisania tego artykułu USDN ma kapitalizację rynkową wynoszącą prawie pół miliarda dolarów.
5. Token USDN jest wspierany przez ~43 000 000 WAVES.
6. W 2021 roku dokonano 20 000 wymian (nie licząc wymiany z węzła Neutrino) na łączną kwotę 1,2 miliarda dolarów!

W tym miejscu komentarze są zbędne. Teraz porozmawiajmy o zmianach.

## Krótki opis zmian
{: .no_toc }

<details open markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Aktualizacja obejmuje zmiany w logice dwóch głównych komponentów Neutrino:
1. NSBT staking i gNSBT:
- Stakerzy NSBT otrzymują "głosy" (gNSBT) w proporcji 1 do 1
- posiadacze gNSBT otrzymują nagrody - procent od zebranych opłat swapowych WAVES ↔ USDN (opłata za protokół)
- głosowanie w protokole Neutrino odbywa się za pomocą gNSBT
- wyodrębnienie NSBT pociąga za sobą opłatę - procent od wyodrębnionej kwoty NSBT na krzywą opłaty (funkcja półokresu)
- automatyczne wypłaty nagród za wystawianie NSBT są anulowane.

2. WAVES ↔ USDN swapy:
- anulowano mechanikę losowego opóźnienia swapów, teraz swapy będą następować prawie natychmiast, z opóźnieniem 1 bloku
- wymiana jest dostępna tylko dla posiadaczy gNSBT (stakerów NSBT)
- ilość gNSBT użytkownika określa dzienną (24-godzinną) maksymalną ilość wymian
- użytkownik może dokonać wymiany tylko raz na dobę (24 godziny).

Przeczytaj poniższy artykuł, aby uzyskać więcej informacji.

## **Staking NSBT i gNSBT**
{: .no_toc }

### **Podmiot gNSBT**
Wprowadziliśmy nową jednostkę - gNSBT - aby rozdzielić saldo "głosów" użytkowników i saldo NSBT. Głosy (gNSBT) będą używane podczas procesu zarządzania.

Właściciele gNSBT otrzymują nagrody - procent od zebranych opłat swapowych (opłat za protokół). Wysokość nagrody jest proporcjonalna do udziału użytkownika w gNSBT. Podczas tyczenia/wycofywania NSBT, ilość gNSBT użytkownika jest przeliczana.

Stakowanie NSBT jest przenoszone na nowy kontrakt (nowy adres w sieci Waves). W obecnym kontrakcie na stakowanie NSBT, wprowadzanie (stakowanie) nowych użytkowników zostanie wyłączone, a usuwanie stakowania będzie dostępne na czas nieokreślony (ze starą opłatą za usuwanie stakowania w wysokości 0.005 WAVES). Użytkownicy starego kontraktu nie będą już otrzymywać nagród za tyczenie NSBT, co powinno ich zachęcić do samodzielnej migracji. Jeśli chodzi o interakcję użytkownika z UI, migracja będzie przebiegać następująco:

- użytkownik wchodzi na stronę Waves.Exchange i odblokowuje NSBT ze starego kontraktu
- użytkownik wchodzi na oficjalną stronę Neutrino i wystawia NSBT na nowych warunkach.

### **Tylko właściciele gNSBT mogą głosować w protokole Neutrino**

Implementacja głosowania w protokole Neutrino jest kolejnym etapem rozwoju po wprowadzeniu nowej mechaniki stakowania i wymiany NSBT.

Będzie można uzyskać "głosy" (gNSBT) tylko poprzez staking NSBT, który nakłada na użytkownika bonusy i pewne ograniczenia (patrz Opłata za rozstawienie NSBT)

### **Opłata za odblokowanie NSBT**

Obecnie wiele systemów wprowadza blokadę tokenów, aby ograniczyć ich obieg i nadać im dodatkową wartość. Podaż NSBT jest ograniczona do ~2.8M tokenów (Moon Factor) i nie wymaga mechanizmu blokującego. Jednakże Moon Factor ma również wadę, która ma negatywny wpływ na główną funkcję NSBT - dokapitalizowanie kontraktu Neutrino. W celu złagodzenia negatywnego wpływu czynnika księżycowego, zamiast blokady wprowadzamy opłaty za rozkucie NSBT.

Opłata ta opiera się na następujących zasadach:

1. opłata jest pobierana w tokenie NSBT
2. zebrane opłaty są przesyłane z powrotem do kontraktu NSBT.

Zasady te pomogą zmniejszyć bieżącą podaż NSBT (S). Poprzez zmniejszenie S, cena NSBT w kontrakcie również spadnie, co będzie stymulować zakup NSBT z kontraktu, a w rezultacie uzyskamy niezbędny obieg NSBT w systemie.
Wprowadzenie opłaty za wycofanie NSBT z systemu jest skomplikowanym krokiem, ponieważ konieczne jest zachowanie równowagi pomiędzy interesami użytkowników i protokołu.
Z jednej strony, duża opłata odstraszy użytkowników od tyczenia, a z drugiej strony, bardzo mała opłata może nie przynieść pożądanego efektu. W związku z tym, aby osiągnąć kompromis, opracowaliśmy trzecią zasadę:

3. wielkość opłaty stanowi funkcjonalną zależność (krzywą) od t - czasu trwania stakowania NSBT. Tak więc, im wcześniej użytkownik odłącza NSBT, tym większa jest implikowana opłata i odwrotnie

### **Krzywa opłat**

Jako krzywa opłat zostanie użyta funkcja półokresu o okresie T=6 miesięcy. Możliwe będzie dostosowanie tego okresu w drodze głosowania.

![](/images/gnsbt-0.png)
> gdzie
> `stakingDuration` oznacza czas utrzymywania NSBT w stakingach
> `T` oznacza okres półtrwania.

Graficznie przedstawia się to w następujący sposób:

![](/images/gnsbt-1.png)

Taka zależność funkcjonalna, z jednej strony jest podobna do tokenów blokujących, jednak nie nakłada na użytkownika ścisłego ograniczenia w postaci braku możliwości odebrania tokena. Nie daje też pełnej swobody, gdyż przez pierwsze miesiące opłata jest dość duża. Jednak przy znacznym wzroście ceny NSBT na rynku, użytkownik ma możliwość pominięcia opłaty, jeśli zysk uzyskany ze sprzedaży przekroczy opłatę za odestakowanie.

Poniżej przedstawiono krzywą opłat dla użytkownika, który stakuje 1000 NSBT:

![](/images/gnsbt-2.png)

- jeśli użytkownik odstakuje NSBT w ciągu 1 miesiąca (43 200 bloków), kontrakt pobierze 89,09% opłaty, co oznacza, że użytkownik otrzyma tylko 109.101 z 1000 NSBT, podczas gdy pozostała kwota zostanie zwrócona do kontraktu NSBT i będzie dostępna do zakupu przez innych użytkowników.
- jeśli użytkownik odkupi NSBT w ciągu 20 miesięcy (864 000 bloków), kontrakt pobierze opłatę w wysokości 9,92%, co oznacza, że użytkownik otrzyma 900.787 z 1000 NSBT, a pozostała kwota zostanie zwrócona do kontraktu NSBT i będzie dostępna do kupienia przez innych użytkowników.

### **Automatyczne wypłaty nagród za stakowanie NSBT zostają anulowane**

Protokół Neutrino zawsze dążył do całkowitej decentralizacji. Zrobiliśmy kolejny krok w kierunku osiągnięcia tego celu. Teraz użytkownicy będą mogli ręcznie odbierać nagrody. Aby otrzymać nagrodę w wysokości skumulowanych opłat protokołu, użytkownicy będą musieli wysłać transakcję invoke do blockchain. Należy również pamiętać, że odbieranie nagród za wymianę DeFo będzie możliwe dopiero po całkowitym przeniesieniu wymiany DeFo na RideV5, do tego czasu nagrody będą gromadzone w kontrakcie.

### **WAVES ↔ Swapy USDN**

Czas trwania operacji swap jest jednym z głównych tematów dyskusji w społeczności. Obecna aktualizacja oferuje rozwiązanie kompromisowe, które zakłada ograniczenie ilości operacji swap i umożliwia szybką wymianę w 1 bloku bez losowości. Wyeliminowanie losowości jest ważnym krokiem w kierunku pełnej decentralizacji protokołu.

Wprowadzenie limitu wymiany jest skomplikowanym procesem. Aby go wyjaśnić, musimy odpowiedzieć na następujące pytania:
- do czego służy swap limit?
- w jaki sposób użytkownik może uzyskać limit swapowy?
- jak długo obowiązuje limit?
- czy istnieją wyjątki?

Odpowiedzi znajdziesz w poniższym opisie.

### **Do czego służy limit wymiany?**

Na początku istnienia protokołu, operacja swap była postrzegana jako narzędzie, które traderzy mogli wykorzystać do arbitrażu USDN pomiędzy giełdami i kontraktem. Jednak w miarę rozwoju protokołu stało się jasne, że głównym celem powinno być zapewnienie stabilności rezerw samego kontraktu. W związku z tym pojawiły się niepożądane zmiany: losowość i wydłużenie czasu operacji swap.

Zmiany wprowadzone przez NEP-102 koncentrują się na dostosowaniu protokołu do nowych zasad:
- minimalizacji arbitrażu kontraktowego
- skupieniu się na stabilności rezerw
- pozbyciu się niepopularnych i scentralizowanych rozwiązań

**NEP-102 jest jednym z kroków prowadzących do osiągnięcia stabilności protokołu**

Aby osiągnąć powyższe zasady, wprowadzamy **następujące zmiany do operacji swapowych:**
- tylko właściciele gNSBT (NSBT stakerzy) mogą wykonywać zamiany
- kwota gNSBT użytkownika określa maksymalną kwotę zamiany
- operacja zamiany zajmuje 1 blok
- użytkownik może dokonać wymiany (albo WAVES → USDN albo USDN → WAVES) tylko raz na dobę (24 godziny / 1440 bloków)
- Więcej szczegółów na temat limitów można znaleźć w poniższym opisie.

### **Definicje limitów**

Maksymalny limit użytkownika (limitMax) - to maksymalna kwota w USDN, którą użytkownik może wymienić w ciągu 24 godzin (1 440 bloków). LimitMax zależy od ilości posiadanych przez użytkownika gNSBT. LimitMax można obliczyć według następującego wzoru:

![](/images/gnsbt-3.png)

> gdzie
> `gnsbtAmount` jest kwotą gNSBT należącą do użytkownika
> `a` oznacza stawkę, którą można dostosować w drodze głosowania
> `e` jest liczbą Eulera

**Limit wydatkowany na operację (limitSpentByOperation)** dla kierunku WAVES→USDN wykorzystywana jest wynikowa kwota wymiany USDN, dla kierunku USDN→WAVES wykorzystywana jest kwota zamienionych USDN.

Na podstawie powyższych definicji możemy utworzyć zestaw poniższych reguł opisujących mechanikę działania limitu:
- limitMax jest taki sam dla wszystkich kierunków (WAVES → USDN oraz USDN → WAVES)
- użytkownik może wykonać tylko jedną operację swap w ciągu doby (24 godziny / 1440 bloków) i musi być spełniony warunek: limitSpentByOperation <= limitMax

### **Przykład obliczania limitu**

Załóżmy, że a = 0.00000003 wówczas zależność pomiędzy limitMax a ilością gNSBT przedstawia się następująco:

| ilość gNSBT | max. limit USDN |
|:------------|:----------------|
| 10000       | 2075.49         |
| 25000       | 24862.15        |
| 50000       | 162678.43       |
| 100000      | 1064440.17      |
| 200000      | 6964862.43      |
| 300000      | 20898728.07     |
| 400000      | 45572602.59     |
| 600000      | 136744901.66    |
| 800000      | 298191403.75    |
| 1000000     | 545910257.58    |

Na poniższym diagramie przedstawiono możliwości użytkownika w zakresie wykonywania operacji zamiany z uwzględnieniem ograniczeń.

![](/images/gnsbt-5.png)

Ten artykuł opisuje jeden z pierwszych kroków na długiej drodze do decentralizacji protokołu Neutrino. Realizacja pomysłów omówionych powyżej nie potrwa długo, a bardzo oczekiwana, pełnoprawna funkcja głosowania pojawi się już wkrótce.

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*