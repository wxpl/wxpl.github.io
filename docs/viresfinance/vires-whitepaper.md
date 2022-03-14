---
layout: default
title: Whitepaper
nav_order: 43
parent: ViresFinance
---
![ViresFinance](/images/vires-logo.png)

# ViresFinance Whitepaper
Protokół rynku pieniężnego dla Waves Ecosystem
## 1. Wprowadzenie

Vires.Finance to protokół rynku pieniężnego typu peer-to-contract zbudowany na Waves Blockchain:
Implementuje on strategię opartą na puli, gdzie pożyczki nie muszą być indywidualnie negocjowane i dopasowywane (jak w strategii opartej na P2P), ale raczej warunki udzielania i zaciągania pożyczek są określane przez sam protokół, który algorytmicznie odkrywa stopy procentowe ("cenę pieniądza") poprzez równowagę pomiędzy podażą a popytem.

## 2. Protokół

Vires.Finance jako protokół opisuje algorytm pożyczania aktywów pod zastaw innych aktywów. Zastawianie innych aktywów jako zabezpieczenia. W wielu aspektach jest on podobny do protokołów pożyczkowych dostępnych na innych łańcuchach.

**2.1. Dostarczanie aktywów**

Aktywa dostarczane na rynek są reprezentowane przez "tokeny LP(liquidity provider)", nazywanych vTokenami, które są automatycznie stakowane przy depozycie. Ponieważ rynek pieniężny nalicza odsetki, które są funkcją popytu na pożyczkę, vTokeny stają się wymienialne na rosnącą ilość aktywów bazowych, np. zarabiając na odsetkach. odsetki.

**2.2. Pożyczanie aktywów**

Stakowane vTokeny mogą być użyte jako zabezpieczenie pożyczki z protokołu. Każdy rynek rynek posiada współczynnik zabezpieczenia, w zakresie od 0 do 1, który reprezentuje część wartości wartości aktywów bazowych, która może być pożyczona. Suma wartości sald konta, pomnożona przez współczynniki zabezpieczenia, równa się zdolność kredytowa użytkownika. Użytkownicy są w stanie zaciągać pożyczki do wysokości, ale nie przekraczając swojej zdolności kredytowej.

**2.3. Ryzyko i likwidacja**

Jeżeli wartość niespłaconych pożyczek na koncie przekracza zdolność kredytową użytkownika, część niespłaconych pożyczek może zostać spłacona w zamian za zwrot. zdolność kredytową, część pożyczki może zostać spłacona w zamian za vToken użytkownika, po aktualnej cenie rynkowej pomniejszonej o dyskonto likwidacyjne. likwidacyjnej. Zachęca to ekosystem arbitrażystów do szybkiego działania w celu zmniejszenia kredytobiorcy i wyeliminować ryzyko związane z protokołem. Proporcja, którą można kwalifikująca się do zamknięcia, współczynnik zamknięcia, to część pożyczonych aktywów, którą można być spłacona i wynosi od 0 do 1, np. 25%. Proces likwidacji może być wywoływany do momentu, gdy pożyczka użytkownika będzie mniejsza niż jego zdolność kredytowa (w odniesieniu do progu likwidacji).

**2.4. Model stopy procentowej**

Stopa procentowa kredytu `I` dla danego składnika aktywów a jest funkcją jego wykorzystania `U` , które jest parametryzowane dla każdego składnika aktywów:
![01](/images/01_vires-formula.png)
![02](/images/02_vires-formula.png)

**2.4.1. Dynamika Rynku**

Przy każdym wystąpieniu transakcji, Indeks Stopy Procentowej dla danego składnika aktywów jest aktualizowany w celu skompensowania odsetek od poprzedniego indeksu, używając odsetek za dany okres, denominowane przez `r * t`, obliczone przy użyciu stopy procentowej per-block:
![03](/images/03_vires-formula.png)
Odpowiednio,
![04](/images/04_vires-formula.png)
oraz,
![05](/images/05_vires-formula.png)
Zatem `λ`, mieszcząca się w przedziale od 0 do 1, reprezentuje współczynnik rezerwy, zapewniając, że część naliczonych odsetek zostanie zatrzymana (odłożona) jako rezerwa.

**2.4.2. Bodziec płynnościowy**

Zysk z oprocentowania pożyczek jest dzielony pomiędzy właścicieli vTokenów (oraz stakerzy). Model stopy procentowej motywuje dostawców do zapewnienia większej płynności w okresach ekstremalnego popytu na aktywa, ponieważ kiedy to się dzieje, stopy procentowe rosną. Niewykorzystana część depozytów, które mogą być stakowane w ramach ich protokołów hosta w ramach Waves, są stakowane.

## 3. Implementacja i architektura

Opisane mechanizmy są zaimplementowane jako system połączonych ze sobą inteligentnych kontraktów inteligentnych kontraktów rozmieszczonych na blockchainie Waves, opisanych na poniższym diagramie.

**3.1. Zdolność pożyczkowa**

Za każdym razem, gdy użytkownik wpłaca środki do rezerwy tokenów, może zdecydować, czy chce wykorzystać chce wykorzystać depozyt tokenów jako zabezpieczenie. Zdolność użytkownika do zaciągania pożyczek jest definiowana jako suma ważona wszystkich jego aktywów, wykorzystywanych jako zabezpieczenie:
![05](/images/06_vires-formula.png)
gdzie
- `Ltv` jest wyrażonym w procentach stosunkiem wartości kredytu do wartości nieruchomości,
- `C (u,a)` jest opcją użycia jako zabezpieczenia ustaloną przez użytkownika,
- `Price a` to cena aktywa `a` podana przez wyrocznię (oracle);
\
![diagram](/images/vires-smartcontract.svg)


**3.2. Próg likwidacji**

Wykorzystana zdolność kredytowa użytkownika u (BCU u ) jest definiowana jako suma ważona wszystkich jego aktywów, wykorzystywanych jako zabezpieczenie:
![05](/images/07_vires-formula.png)
gdzie `LT` oznacza wartość progu likwidacji dla każdego składnika aktywów, z zakresu od 0 do 1.

**3.3. Czynnik kondycji i likwidacja**

Każdy użytkownik musi zwrócić uwagę na **czynnik zdrowia** *(health factor)* swojego portfela. W istocie, czynnik zdrowia jest stosunkiem `BC u` i `BCU u` . Jeśli współczynnik zdrowia użytkownika spadnie poniżej pewnej wartości, likwidatorzy mogą wkroczyć i poprawić kondycję użytkownika poprzez przejęcie części depozytu i kredytu z niezdrowego konta. W ten sposób przywracany jest współczynnik zdrowia użytkownika, ale aby zachęcić likwidatorów do utrzymywania ogólnego stanu systemu, likwidator musi być w stanie poprawić współczynnik zdrowia użytkownika. do utrzymania ogólnego zdrowia systemu, stosowana jest kara likwidacyjna (np. 10%).

Formalnie, likwidacja dla użytkownika staje się dostępna, gdy `BC u` ≤ `BCU u`.

**3.4. Oprocentowane tokeny**

Jeśli aktywo nie jest używane jako zabezpieczenie, użytkownik może stworzyć oprocentowane vtokeny, reprezentujące jego udział w całkowitym depozycie aktywów, który rośnie w czasie jako zadłużenie. Oprócz ustanowienia rynku wtórnego dla depozytów, vtokeny mogą być wykupione za tę część rosnącego depozytu (opisanego w punkcie 2.4.1) i wykorzystane do zasilenia konta użytkownika.
\
\
\
\
\
*Źródło: [ViresFinance Whitepaper](https://github.com/viresfinance/protocol/blob/main/vires-finance-whitepaper-1.0.pdf)*

\
\
\
\
\
*Zaproponuj zmiany porzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/wavesexchange_polska).*