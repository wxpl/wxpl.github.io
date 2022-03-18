---
layout: default
title: Farming
nav_order: 33
parent: SwopFi
permalink: /swop-farming

---

<details open markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Dodawanie płynności

Możesz zainwestować w wybraną przez siebie pulę i stać się dostawcą płynności. W zamian otrzymujesz token reprezentujący Twój udział w puli. Wycofując swoją płynność, otrzymujesz również część opłat zgromadzonych w puli, a także nagrody za staking USDN/NSBT/EURN oraz leasing WAVES proporcjonalny do Twojego udziału.

⚠️ Ważne jest, by zrozumieć ryzyko związane z dostarczaniem płynności. Zapoznaj się z naszym artykułem [Jak działają tokeny akcji w Swop.fi?](https://medium.com/swop-fi/how-do-share-tokens-aka-lp-tokens-work-in-swop-fi-106fa65b909e)

Istnieją dwie możliwości dodania płynności:

1. Uzupełnij pulę obydwoma tokenami w takim samym stosunku, w jakim znajdują się one na smart kontrakcie.
2. Uzupełnienie puli jednym tokenem. Jest to opłacalne, jeśli cena różni się od aktualnej ceny rynkowej z powodu przesunięcia sald tokenów w puli. Jeśli w puli nie ma wystarczającej ilości tokena X, a więc jest on droższy, warto go zdeponować. Opcja ta jest obecnie dostępna tylko dla puli USDT-USDN i USDC-USDN.

### Uzupełnij za pomocą obu tokenów

Upewnij się, że masz wystarczającą ilość obu tokenów i co najmniej 0,005 WAVES (które nie są dzierżawione), aby zapłacić opłatę sieciową.

1. Podłącz swój portfel za pomocą Waves Keeper lub Waves Exchange.
2. W menu bocznym wybierz Farming → Liquidity.
3. Wybierz pulę do uzupełnienia i przejrzyj informacje o puli. Kliknij Dodaj płynność.
4. Określ ilość jednego z tokenów, które chcesz dodać. Ilość drugiego tokena zostanie obliczona automatycznie.
5. Kliknij przycisk Dostarcz i podpisz transakcję.

Stosunek tokenów w puli może się nagle zmienić tuż przed uzupełnieniem z powodu dużych wymian. Jeśli współczynnik tokenów w twoim uzupełnieniu różni się od współczynnika tokenów w puli o więcej niż wynosi tolerancja poślizgu, transakcja zostanie anulowana. Możesz uzupełnić pulę z nowym współczynnikiem. Możesz też zmienić domyślną wartość tolerancji poślizgu w ustawieniach.

💡 Stakuj swoje tokeny akcji (LP), aby otrzymać nagrodę za farming w SWOP.

![](/images/swop-liquidity.png)

### Uzupełnij za pomocą pojedynczego tokena (USDT-USDN, USDC-USDN)

Minimalna kwota do uzupełnienia to 5 USDC/USDN/USDT.

1. Podłącz swój portfel za pomocą Waves Keeper lub Waves Exchange.
2. W menu bocznym wybierz Farming → Liquidity.
3. Wybierz pulę do uzupełnienia i przejrzyj informacje o puli. Kliknij Dodaj płynność.
4. Zaznacz pole wyboru Pool only one token. Określ ilość tokena, którą chcesz dodać.
5. Kliknij przycisk Supply i podpisz transakcję.

💡 Stakuj swoje tokeny akcji (LP), aby otrzymać nagrodę za farming w SWOP.

## Usuwanie płynności

W każdej chwili możesz otrzymać odpowiedni udział w płynności bazowej w zamian za swoje tokeny udziałów, w całości lub w części. Otrzymasz oba tokeny w takim samym stosunku, w jakim znajdują się one w danej chwili w puli, włączając w to skumulowane opłaty i nagrody za staking USDN/NSBT/EURN oraz leasing WAVES, proporcjonalnie do Twojego udziału.

1. Podłącz swój portfel za pomocą Waves Keeper lub Waves Exchange.
2. Jeśli masz stakowane tokeny udziałów, uwolnij je:
    2.1. W menu bocznym wybierz Farming → Farming SWOP.
    2.2. Znajdź pulę, w którą zainwestowałeś. Kliknij Unstake.
    2.3. Określ ilość tokenów akcji, które chcesz wycofać.
    2.4. Kliknij przycisk Unstake i podpisz transakcję.
3. W menu bocznym wybierz Farming → Liquidity.
4. Wybierz pulę, z której chcesz wycofać środki. Kliknij Usuń płynność.
5. Określ ilość tokenów akcji. Zobaczysz, jakie ilości tokenów z puli otrzymasz.
6. Kliknij Wypłać i podpisz transakcję.

## Farming SWOP

Kiedy zapewniasz płynność, możesz zdobyć nagrodę za farmę w SWOP poprzez staking swoich tokenów akcji.

1. Podłącz swój portfel za pomocą Waves Keeper lub Waves Exchange.
2. W menu bocznym wybierz Farming → Farming SWOP.
3. Znajdź pulę, w którą zainwestowałeś. Pod nazwą tokena akcji kliknij Stake.
4. Określ ilość tokenów akcji, które chcesz postawić.
5. Kliknij Stake i podpisz transakcję.

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*