---
layout: default
title: NSBT
nav_order: 21
parent: Neutrino
permalink: /nsbt

---

# NSBT

{: .no_toc }

<details closed markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Token Neutrino lub NSBT (skrót od Neutrino System Base Token) to token rekapitalizacyjny i zarządzający systemem Neutrino.
\
Jako token rekapitalizacyjny, NSBT zapewnia stabilność rezerw zabezpieczeń w głównym smart kontrakcie Neutrino. Nowe tokeny NSBT są wydawane w celu zablokowania WAVES w kontrakcie, służąc jako dodatkowe zabezpieczenie i ubezpieczając system przed deficytem. Kiedy wartość tokenów WAVES w USDN spada, pozwala to użytkownikom spekulować na parametrze Backing Ratio (BR).

## Krzywa emisji NSBT

Cena emisyjna NSBT, czyli cena, za którą inteligentny kontrakt sprzedaje NSBT za WAVES, jest określana przez krzywą emisyjną, która jest powiązana ze Współczynnikiem Wsparcia i podażą NSBT. Wzór na cenę emisyjną to: 

![01-nsbt](/images/01-nsbt.png)

gdzie
М = maksymalna podaż NSBT
S = całkowita bieżąca podaż NSBT
K = dodatkowy współczynnik oparty na BR i innych parametrach:

![02-nsbt](/images/02-nsbt.png)

a = parametr w BR
b = współczynnik wygładzający, który zapobiega gwałtownym skokom stawek w momencie wdrożenia.

Kiedy Backing Ratio spada lub pojawia się deficyt (BR<1), a aktualny fundusz rezerwowy nie jest wystarczający, by zrekompensować spadek wartości zabezpieczenia, NSBT służy jako obligacja. Traderzy kupują NSBT za WAVES za pomocą inteligentnego kontraktu, oczekując zwrotu w przyszłości, gdy BR zostanie odzyskany. Kiedy BR osiągnie 1,5 lub 150% nadwyżki, cena emisyjna NSBT gwałtownie wzrasta, a ponieważ maksymalna możliwa podaż tokenów jest ograniczona do 2,8 miliona tokenów, cena emisyjna rośnie wykładniczo, co zapewnia rezerwy z dodatkowym zabezpieczeniem chroniącym cały system przed deficytem.

![03-nsbt](/images/03-nsbt.png)

Zakup NSBT poprzez smart kontrakt odbywa się za pomocą funkcji buyNsbt(). Interfejs, który to umożliwia, jest dostępny na [Waves.Exchange](https://waves.exchange).

## Governance

Jako token zarządzający, NSBT ułatwia głosowanie przy wydawaniu nowych aktywów Neutrino lub aktualizacji funkcji i parametrów protokołu. Zarządzanie odbywa się za pośrednictwem oficjalnej [strony Neutrino](https://governance.neutrino.at).

## Stakowanie NSBT

NSBT jest aktywem stakowalnym umożliwiającym posiadaczom zarabianie na opłatach za transakcje swapowe WAVES<>USDN. Opłaty za transakcje swapowe są gromadzone w puli, a następnie codziennie rozdzielane pomiędzy stakerów NSBT. Opłaty są zbierane w USDN dla swapów WAVES na USDN oraz w WAVES dla swapów USDN na WAVES. Nagrody są wypłacane codziennie do portfeli Waves stakerów NSBT. 
\
Aby stakować NSBT, musisz wysłać tokeny do smart kontraktu. Można to zrobić poprzez interfejs [Waves.Exchange](https://waves.exchange).
Wielkość nagrody za stakowanie NSBT zależy od wolumenu wymian WAVES<>USDN oraz udziału salda stakującego użytkownika w całkowitej ilości stakowanych NSBT. Okres obliczeniowy wynosi 1 440 bloków, co odpowiada około 24 godzinom. Po wygaśnięciu 1440 bloków opłaty za swap zaczynają być rozdzielane między stakerów NSBT. System dystrybucji wykorzystuje parametr IPB (dochód na blok). Aby go obliczyć, całkowity dochód okresu (całkowity dochód za okres obliczeniowy) jest dzielony przez 1,440 bloków:
\
IPB = całkowity dochód okresu / okres obliczeniowy.
\
Aby obliczyć udział IPB (udział dochodu przypadającego na blok), system dystrybucji określa saldo stawki każdego użytkownika w każdym bloku i dzieli tę wartość przez sumę wszystkich sald stawki:
\
*Udział IPB = saldo stawek użytkownika w bloku / suma wszystkich stawek w bloku*