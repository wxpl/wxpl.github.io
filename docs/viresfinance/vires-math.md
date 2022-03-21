---
layout: default
title: Matematyka gVires
nav_order: 42
parent: ViresFinance
permalink: vires-math

---

# VIRES, gVIRES i czas połowiczny

<details open markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Istota matematyki jest prosta: W dowolnym momencie konta tracą połowę swojego aktualnego zaangażowania w ciągu 6 miesięcy. Algorytm opiera się na [formule rozpadu połowicznego](https://pl.wikipedia.org/wiki/Czas_po%C5%82owicznego_rozpadu):

Biorąc pod uwagę, że użytkownik `u` posiada zobowiązanie `Vu,t0` postaci tokenów Vires w czasie `t0`,

![](/images/gvires-math-1.png)

gdzie `λ` oznacza szybkość rozpadu (czas połowicznego zaniku):

![](/images/gvires-math-2.png)

## Przykład dla 1 uczestnika

Na przykład, użytkownik X1 zablokował 100 Vires 1 stycznia 2022 roku. Moc zarządzania użytkownika zaczyna się zmniejszać, a jego tokeny zaczynają się odblokowywać:

| Date            | gVires        | Nadal zablokowane VIRES | Odblokowane VIRES |
|:--------------- |:------------- |:----------------------- |:----------------- |
| Sty 2022, 00:00 | 100.00 gVires | 100.00 VIRES            | 0.00 VIRES        |
| Lut 2022        | 89.09 gVires  | 89.09 VIRES             | 10.91 VIRES       |
| Mar 2022        | 79.37 gVires  | 79.37 VIRES             | 20.63 VIRES       |
| Kwi 2022        | 70.71 gVires  | 70.71 VIRES             | 29.29 VIRES       |
| Maj 2022        | 63.00 gVires  | 63.00 VIRES             | 37.00 VIRES       |
| Cze 2022        | 56.12 gVires  | 56.12 VIRES             | 43.88 VIRES       |
| Lip 2022        | 50.00 gVires  | 50.00 VIRES             | 50.00 VIRES       |
| ...             | ...           | ...                     | ...               |
| Sty 2023        | 25.00 gVires  | 25.00 VIRES             | 75.00 VIRES       |
| ...             | ...           | ...                     | ...               |
| Lip 2023        | 12.50 gVires  | 12.50 VIRES             | 87.50 VIRES       |
| ...             | ...           | ...                     | ...               |
| Sty 2024, 00:00 | 6.25 gVires   | 0.00 VIRES              | 100.00 VIRES      |
| ...             | ...           | ...                     | ...               |

![](/images/gvires-math-3.png)

Jak pokazano powyżej,

- Odblokowanie rozpoczyna się natychmiast po zablokowaniu VIRES,
- W ciągu pół roku ilość gVires użytkownika zmniejsza się o połowę; również połowa VIRES może zostać wycofana,
- Po dwóch latach pojawia się klif: użytkownik może teraz wycofać wszystkie pozostałe vires (6,25% początkowej blokady), ale jeśli tego nie zrobi, nadal będzie miał prawo głosu, władzę i wpływy (przy kontynuacji rozkładu);

## Przykład dla wielu uczestników

Rynki Vires.finance pobierają część odsetek, które płacą pożyczkobiorcy. Wartość "Udziału w protokole" można znaleźć pod każdym składnikiem aktywów na stronie szczegółów aktywów. Ogólnie rzecz biorąc, może ona być różna dla różnych rynków, a konfiguracja tej wartości należy do zarządzających. Przyjrzyjmy się przykładowi:

- Pożyczkobiorcy na rynku USDC pożyczyli 100 mln USC za 36,5% APR,
- Dlatego pożyczkobiorcy na rynku USDC muszą dziś zapłacić 100 000 USDC odsetek,
- Udział w protokole dla USDC wynosi 10%, dlatego też rządy otrzymują dziś 10 000 USDC,
- Alice i Bob zablokowali wczoraj po 100 VIRES, co daje w sumie 200 gVires (o 100 gVires każdy), więc Alice i Bob otrzymali dziś po 5 000 USDC;

Dzień 0:

| Użytkownik | VIRES w systemie | gVires | już odblokowane | Udział w przychodach |
|:---------- |:---------------- |:------ |:--------------- |:-------------------- |
| Alice      | 100 VIRES        | 100.00 | 0.00            | 50%                  |
| Bob        | 100 VIRES        | 100.00 | 0.00            | 50%                  |

Teraz, po pół roku, gVires uległy rozpadowi:

- Alice ma 50 gVires, Bob ma 50 gVires (z łącznej liczby 100), więc nadal dzielą się strumieniem przychodów 50-50%,

| Użytkownik | VIRES w systemie | gVires | już odblokowane | Udział w przychodach |
|:---------- |:---------------- |:------ |:--------------- |:-------------------- |
| Alice      | 100 VIRES        | 50.00  | 50.00           | 50%                  |
| Bob        | 100 VIRES        | 50.00  | 50.00           | 50%                  |

![](/images/gvires-math-4.png)

- Przychodzi Dave i blokuje 100 VIRES, co daje mu 100 gVires:

| Użytkownik | VIRES w systemie | gVires | już odblokowane | Udział w przychodach |
|:---------- |:---------------- |:------ |:--------------- |:-------------------- |
| Alice      | 100 VIRES        | 50.00  | 50.00           | 25%                  |
| Bob        | 100 VIRES        | 50.00  | 50.00           | 25%                  |
| Dave       | 100 VIRES        | 100.00 | 0.00            | 50%                  |

Dave zobowiązuje się dwa razy więcej niż Alice, więc otrzymuje dwa razy większy przychód niż ona: tego dnia Alice otrzymuje 2500 USDC, - Bob otrzymuje 2500 USDC, - Dave otrzymuje 5000 USDC;

![](/images/gvires-math-5.png)

Jak pokazano w przykładach, gVires jest proporcjonalne do całkowitej ilości VIRES zablokowanych przez danego użytkownika.

W każdej chwili każdy inny użytkownik może ponownie zablokować swoją stawkę.

Oto, jak zmienia się sytuacja, gdy Alicja zdecyduje się ponownie zablokować swoje VIRES:

| Użytkownik | VIRES w systemie | gVires | już odblokowane | Udział w przychodach |
|:---------- |:---------------- |:------ |:--------------- |:-------------------- |
| Alice      | 100 VIRES        | 100.00 | 0.00            | 40%                  |
| Bob        | 100 VIRES        | 50.00  | 50.00           | 20%                  |
| Dave       | 100 VIRES        | 100.00 | 0.00            | 40%                  |

![](/images/gvires-math-6.png)

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*
