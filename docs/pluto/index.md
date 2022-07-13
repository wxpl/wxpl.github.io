---
layout: default
title: Pluto
nav_order: 8
has_children: true
permalink: /pluto

---

![image](/images/00-pluto.png)

Pluto to innowacyjny projekt waluty rezerwowej. Jest to instrument finansowy odporny na rynki niedźwiedzia, który zapewnia długoterminowy i planowany wzrost ceny rynkowej danego aktywa.

<details open markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Skarbiec

Główną metryką protokołu jest wzrost wartości zabezpieczenia każdego tokena PLUTO.

Zabezpieczenie jest realizowane przez Skarbiec (Treasury), gdzie parametry są kontrolowane przez głosowanie, a także mogą zmieniać się automatycznie w zależności od danych rynkowych. Model matematyczny Plutona skupia się głównie na wzroście Treasury. Jest on zbudowany z myślą o tym celu.

Wzrost Skarbu napędzany jest przez środki użytkowników PLUTO. Użytkownicy mogą zdefiniować ten wzrost za pomocą mechanizmu uwalniania PLUTO. Mechanizm ten zakłada, że Skarb Państwa jest wydawany tylko w przypadku, gdy cena tokena PLUTO spadnie poniżej ceny oparcia. Takie podejście gwarantuje, że cena rynkowa nigdy nie osiąga poziomu poniżej ceny zabezpieczonej.

Co najmniej 80% Skarbu Państwa stanowią stablecoiny. stablecoiny są wykorzystywane do wydobywania płynności na rynkach pieniężnych, takich jak [ViresFinance](https://vires.finance). Treasury obejmuje również tokeny dostawców płynności w puli macierzystej PLUTO, megapulę uruchomioną w serwisie Puzzle Swap.

Lista wspieranych aktywów może zostać rozszerzona w drodze głosowania przeprowadzonego przez stakerów. Mimo to ich udział w Skarbie nigdy nie może przekroczyć 20%, aby zapewnić stabilność dostarczania płynności.

## Model cenowy napędzany przez Skarbiec

Model PLUTO oparty jest na kilku kluczowych parametrach matematycznych, które zapewniają stabilność systemu, a także kursu PLUTO.
Tymi parametrami są: **Backed Price (Min Price)**, **Market Price** oraz **Max price**.

![image](/images/01-pluto.png)

Definicje:
**Total Supply** - liczba wyemitowanych PLUTO
**Treasury Value** - równowartość aktywów w Skarbie Państwa w USDN

Stąd:
**Backed Price (Min Price)** = Treasury Value / Total Supply.
**Market Price** = cena PLUTO do USDN na rynku.
**Max Price** = Backed Price * K, gdzie K jest liczbą ustaloną przez głosowanie, domyślna wartość to 3.
**Pluto Growth Factor** = Cena Rynkowa / Cena Wsparcia.

Pluto Growth Factor pokazuje korelację ceny rynkowej PLUTO z rzeczywistą ceną zabezpieczoną. Teoretycznie Pluto Growth Factor ma ograniczone granice, nie powinien wychodzić poza zakres: [100%, 100%*K]. Za optymalną wielkość Growth Factor uważa się centralny punkt tego przedziału, czyli 200%.

Cena PLUTO nigdy nie jest zbyt wysoka, balansując pomiędzy Ceną Wsparcia a Ceną Maksymalną. PLUTO jest zaprojektowane jako waluta rezerwowa, więc takie podejście zapewnia stabilny wzrost w długim okresie czasu. PLUTO ma gwarancję, że jego cena nie spadnie o więcej niż (K-1)/K.

Co ważne, Backed Price jest praktycznie wartością nie malejącą. W stabilnym pegu stablecoinów ryzyko downside'u Backed Price wynosi 20%, pod warunkiem, że wszystkie niestabilne coiny w kasetach spadną cenowo do 0.

### Przykład

Załóżmy, że Skarbiec składa się z 1 miliona USDN yield na Vires, również 500K PLUTO jest emitowane.
Oznacza to, że cena bazowa PLUTO = 1000 / 500 = 2 USDN.

Na rynku PLUTO jest notowane po 4 USDN, więc Plutonowy Współczynnik Wzrostu = 100 * 4 / 2 = 200%. 200% to podstawowa wartość, przy której staking przynosi regularne zyski, a bonus startowy jest najbardziej atrakcyjny dla nowych użytkowników.

Cena rynkowa może jednak ulegać wahaniom. Na przykład, cena PLUTO może przekroczyć 6 USDN, tym samym przekraczając Cenę Maksymalną. W takim przypadku nowe tokeny PLUTO zostaną wyemitowane przez protokół. Nowe tokeny są następnie sprzedawane za USDN, a USDN zostaną dodane do Skarbu, zwiększając tym samym jego rozmiar.

Alternatywnie, jeśli cena rynkowa PLUTO spadnie poniżej Ceny Wsparcia, środki Skarbu posłużą do wykupu PLUTO, aby zabezpieczyć jego cenę przed zejściem jeszcze niżej.

W ten sposób zbyt gwałtowne wahania rynkowego kursu walutowego działają na korzyść Skarbu Państwa. Takie podejście gwarantuje stabilność systemu i utrzymuje jego zachowanie na tyle przewidywalne, że PLUTO jest niezawodną walutą rezerwową.

Kupując PLUTO, użytkownik może liczyć na to, że jego cena rynkowa nie spadnie poniżej Ceny Wsparcia poza pewnymi egzotycznymi zjawiskami, takimi jak run na banki czy deprecjacja stablecoinów.

## PLUTO Minting

Podstawowym mechanizmem emisji tokenów PLUTO jest onboarding. Użytkownik może wymienić jeden z obsługiwanych tokenów LP na Plutona po cenie rynkowej i otrzymać Bonus Onboardingowy.

Bonus Onboardingowy ma imponującą wielkość. Użytkownik otrzymuje tokeny PLUTO natychmiast po cenie rynkowej. Te tokeny mogą być odblokowane po okresie lock-up z bonusami onboarding APY zapisanymi w PLUTO.

Okres blokady i wielkość APY zależą od współczynnika wzrostu w momencie uwolnienia:

![image](/images/02-pluto.png)

Określone APY nalicza się od liczby PLUTO, które użytkownik wystawił, podczas dni blokady. Po zakończeniu okresu blokady, PLUTO są automatycznie konwertowane na regularne stakingi i nadal przynoszą stabilne odsetki.

Czas trwania blokady, jak również premia startowa mogą być zmienione w zależności od warunków rynkowych i poprzez głosowanie. Jeśli Czynnik Wzrostu jest poniżej 110%, tj. jeśli Cena Rynkowa < Backed Price * 1.1 onboarding jest niemożliwy, a użytkownicy mogą jedynie kupić token z rynku, podczas gdy jego cena jest wystarczająco korzystna.

### Alokacja Funduszu Rozwoju

Fundusz Rozwoju Projektu zostanie utworzony przez Dev Team, aby sponsorować dalsze doskonalenie waluty rezerwowej PLUTO. Ważne jest, aby każdy token PLUTO, który otrzyma Fundusz, był wspierany. Dlatego na ten cel zostanie wybite dodatkowe 0,24% do 1,72% wszystkich PLUTO wypłaconych uczestnikom onboardingu. Ta opłata zostanie wysłana do portfela zespołu i zostanie automatycznie stakowana.

## PLUTO Buyback

W celu stymulowania wzrostu monety przy niskich wartościach współczynnika wzrostu PLUTO, presja zakupowa jest realizowana poprzez mechanizm automatycznego wykupu.

Część funduszy onboardingowych służy do odkupienia PLUTO z megapuli podczas Puzzle Swap. Część, która jest przeznaczona na wykup, a nie dodawana do Skarbu Państwa, jest określana przez zmienną Buyback Ratio i może ulec zmianie w zależności od nastrojów rynkowych i głosowania.

![image](/images/03-pluto.png)

Tabela zależności wskazuje, że im bliżej PLUTO spada do swojej "podłogi", czyli do wartości Ceny Wsparcia, tym więcej środków przeznaczanych jest na Buyback, aby zapewnić odsunięcie ceny od "podłogi".

Co ważne, Buyback nie powoduje spadku Ceny Wsparcia. Wskaźnik Buyback jest tak dostosowany, aby wykupić jak najwięcej przy wartościach Growth Factor na poziomie 110-130%.

### Przykład

Załóżmy, że cena rynkowa PLUTO wynosi 5 USDN, a cena wsparcia = 3 USDN. Oznacza to, że współczynnik wzrostu wynosi 166%.
Użytkownik wnosi 10000 USDN do mennicy PLUTO poprzez onboarding. 4440 USDN zostanie wykorzystane do natychmiastowego Buyback, a pozostałe 5560 USDN zostanie przekazane do Skarbu Państwa.

Użytkownik otrzyma około (10000 / 5.02) 1992 PLUTO, uwzględniając wpływ ceny wynikający z Buyback. Te 1992 PLUTO automatycznie trafią do onboardingu na 9 dni z 1798% APY. W ten sposób użytkownik będzie mógł wykupić (1992 * 1.0752) 2141,9 PLUTO na koniec okresu lock-up.

## Staking PLUTO

W celu wdrożenia funkcji zarządzania i zachęcenia posiadaczy PLUTO, zostanie wprowadzona zasada stakingu bez blokady. Oznacza to, że staking PLUTO lub unstaking są dozwolone w każdym momencie.

Nagroda za staking będzie składać się z dwóch części: Bezwarunkowej Nagrody oraz dodatkowej Motywacyjnej Nagrody za staking.

Bezwarunkowa APY jest równa APY z protokołu. Zachęta APY jest ustalana na podstawie Stopy Wzrostu Skarbu oraz limitu wskazanego przez użytkownika w głosowaniu:

`Incentive Staking Reward = min(max(Incentive Staking Rate, Voted Incentive))`, zatem max Incentive Staking Rate wynosi:

![image](/images/04-pluto.png)

### Przykład

Załóżmy, że w Skarbcu znajduje się równowartość 100 milionów USDN, generując roczny dochód w wysokości 20%, co daje 20 milionów rocznie. Wszyscy użytkownicy postawili 10 milionów PLUTO z istniejących 20 milionów.

Zabezpieczenie rośnie o 20% rocznie kosztem APY Skarbu. Przy wykorzystaniu tylko połowy dostępnych PLUTO, pozwala to na bezwarunkowy zysk ze stakingu w wysokości 20% * 2 = 40%.

Istnieje również emisja motywacyjna. Załóżmy, że w wyniku głosowania ustalono, że wynosi ona 60%. Ponownie, w zależności od udziału stakowanych PLUTOs, rzeczywista APY motywacyjna wynosi 120%.

W takim scenariuszu całkowity zysk ze stakingu PLUTO wyniesie 40 + 120 = 160% rocznie bez lock-up'u. Zysk ten jest mierzony w PLUTO niezależnie od wzrostu Ceny Wsparcia, tzn. zakłada się, że rzeczywisty wzrost kapitału w ciągu roku jest wyższy niż APY.

## Dlaczego Pluton jest zrównoważony

Kluczowym celem protokołu jest zwiększenie wartości zabezpieczenia każdego PLUTO (tj. Backed Price), co pobudza wzrost Ceny Maksymalnej i równowagę Ceny Rynkowej.

W tym celu protokół musi zapewnić, że podczas stakowania i onboardingu wygenerowany udział we wzroście wartości skarbowej powinien zawsze przekraczać frakcję, o którą wzrasta całkowita podaż PLUTO w jednostce czasu. Czyli, matematycznie, Reguła Wzrostu PLUTO to:

![image](/images/05-pluto.png)

Jeśli rozbijemy wzrost Skarbu Państwa i wzrost bicia monet na składowe, powinniśmy otrzymać co następuje:

![image](/images/06-pluto.png)

W związku z tym, aby zapewnić wzrost, Protokół powinien przeprowadzać onboarding w taki sposób, aby wielkość frakcji onboardingowej Skarbca mogła rosnąć szybciej niż wielkość zagregowanego wyniku PLUTO w postaci skumulowanych odsetek onboardingowych, aby zapewnić miejsce na opłacenie stakingu motywacyjnego.

Jest to możliwe dzięki temu, że onboarding odbywa się po cenie Rynkowej*(1-premium), podczas gdy koszt Skarbca za token jest równy Cenie Wsparcia.
Dlatego protokół zawsze trzyma się zasady, że Cena Wsparcia <= Cena Rynkowa*(1-premium).

Wzrost Ceny Wsparcia zależy od zagregowanych parametrów Onboardingu, Stakingu, APY Skarbu Państwa i Wykupu Obligacji. Oblicza się go jako:

![image](/images/07-pluto.png)

Opierając się na modelu wdrażającym systematyczny wzrost Ceny Wsparcia, PLUTO staje się monetą z trwałym wzrostem wbudowanym w jej zasadę. W ten sposób PLUTO jest odporną na sezon niedźwiedzi walutą rezerwową, która tworzy zachętę do wzrostu płynności w ekosystemie.

\
\
\

---

Żródło: [Pluto Paper](https://mirror.xyz/0x409981e2C0370AA0790CCd4AC90F1143D2a01886/WU_eUFiXRHTFa-dCxsDeRNjFJLbF-awO47bjVUY7VTo)
