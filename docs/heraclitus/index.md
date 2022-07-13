---
layout: default
title: Project Heraclitus
nav_order: 3
has_children: true
permalink: /heraclitus

---

![image](/images/heraclitus-block.png)
\
\

# Przedstawiamy The Heraclitus Project

{: .no_toc }

[![Twitter](/images/twitter.svg)](https://twitter.com/heraclitus_tci){:target="_blank"}  [![Telegram](/images/telegram.svg)](https://t.me/heraclitus_project){:target="_blank"}  [![Medium](/images/medium.svg)](https://medium.com/@heraclitus_project){:target="_blank"} 

**The Heraclitus Project** to zbiór **stokenizowanych derywatów** włączających w swoją wartość **procent składany** *(Tokenized Compound Interest, **TCI**)* 

TCI daje inwestorom możliwość konsolidowania nagród z tokenów takich jak sNSBT, sVIRES, sWX oraz tokenów LP bezpośrednio w wartości stokenizowanego procentu składanego (TCI).

Dzięki takiemu rozwiązaniu inwestor otrzymuje zbywalny token, który w swojej wartości uwzględnia odsetki złożone z regularnej dystrybucji nagród łącznie z wartością bazowego aktywa (BA). Dodatkowo, regularne auto-buy tworzy presję zakupową dla danego aktywa bazowego, zwiększając również w ten sposób wolumen transakcji.

<details closed markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Mintowane wartości BA_TCI

Mintowana wartość BA_TCI jest tworzona na podstawie stosunku ilości tokenu bazowego w stakingu do ilości aktywów BA_TCI w obiegu. Procent składany w puli jest naliczany po każdej dystrybucji nagród (nie częściej jak co 24h) i dodawany do puli w skarbcu, przy czym dodatkowe BA_TCI nie jest emitowane. Dzięki takiemu mechanizmowi wartość wcześniej wymintowanego BA_TCI wzrasta, odzwierciedlając stan skarbca smart kontraktu.

![](/images/tci-math-01.png)

> *gdzie:*
> 
>  ***BA_TCI** to stokenizowany procent składany + aktywo bazowe*
> 
>  ***BA Supply** to stan aktywa bazowego w skarbcu sc*

W każdym momencie można wymienić swoje udziały na aktywa bazowe lub na USDN, tzn. wymienić posiadane aktywa BA_TCI na aktywa tokenu bazowego lub na USDN po nowym, wyższym kursie.

Aby ułatwić swobodny obrót BA_TCI powstanie Market Maker na WavesExchange, który będzie oferował obrót zgodnie z ceną ze smart kontraktu.

Różnica w cenie BA_TCI w momencie rozpoczęcia i zakończenia stakowania będzie stanowić Twój dochód. Różnica ta, do aktywa bazowego może być **wyłącznie dodatnia**.

## Cena BA_TCI

Cena stokenizowanego procentu składanego jest formułowana następująco:

![](/images/tci-math-02.png)

> *gdzie:*
> 
>  ***BA Price** to kurs / cena aktywa bazowego*
> 
>  ***BA** to aktywo bazowe*
> 
>  ***TCI** to stokenizowany procent składany*

BA_TCI w smart kontrakcie zawsze będzie odzwierciedlać cenę aktywa bazowego + skonsolidowane aktywo bazowe zakupione z dystrybuowanych nagród BA. Należy pamiętać, że będzie to w pełni przejrzyste i weryfikowalne w łańcuchu Waves.

**UWAGA:** BA_TCI to stokenizowany procent składany. W związku z czym, derywat BA_TCI podlega swobodnej zbywalności, na tej samej zasadzie, jak każdy inny token w ekosystemie Waves. Twórcy projektu nie są w stanie kontrolować, przewidzieć czy regulować otwartego rynku DEX na Waves Exchange.

## Uproszczony przykład działania

Stakując instrument bazowy sNSBT, smart kontrakt wydaje derywat sNSBT_TCI reprezentujący udział stakowanego sNSBT w skarbcu TCI. Następnie po każdej dystrybucji nagród, które wydawane są z pochodnej sNSBT, zostaje automatycznie dokupiona dodatkowa ilość sNSBT, zwiększając tym samym wartość tokenu sNSBT_TCI. 

Częstotliowść automatycznego procentu składanego jest uzależniona od częstotliwości dystrybuowanych nagród z sNSBT.

![](/images/tci-diagram.png)

Poniższa tabela przedstawia proces generowania nowych derywatów sNSBT_TCI przez okres 8 dni, przy założeniu +1% wartości procentu składanego co 24h.

| Day | Staking sNSBT | Total sNSBT staked | sNSBT\_TCI per 1 sNSBT | sNSBT\_TCI issued | sNSBT\_TCI in circulation | sNSBT Treasury Supply | +1% CI per 24h (sNSBT auto-buy) |
|:--- |:------------- |:------------------ |:---------------------- |:----------------- |:------------------------- |:--------------------- |:------------------------------- |
| 0   | 1,0000        | 1,0000             | 1,0000                 | 1,0000            | 1,0000                    | 1,0000                | 1,0100                          |
| 1   | 2,0000        | 3,0000             | 0,9967                 | 1,9802            | 2,9802                    | 3,0100                | 3,0401                          |
| 2   | 4,0000        | 7,0000             | 0,9803                 | 3,9212            | 6,9014                    | 7,0401                | 7,1105                          |
| 3   | 8,0000        | 15,0000            | 0,9706                 | 7,7647            | 14,6661                   | 15,1105               | 15,2616                         |
| 4   | 16,0000       | 31,0000            | 0,9610                 | 15,3757           | 30,0418                   | 31,2616               | 31,5742                         |
| 5   | 32,0000       | 63,0000            | 0,9515                 | 30,4469           | 60,4887                   | 63,5742               | 64,2100                         |
| 6   | 64,0000       | 127,0000           | 0,9420                 | 60,2909           | 120,7796                  | 128,2100              | 129,4921                        |
| 7   | 128,0000      | 255,0000           | 0,9327                 | 119,3879          | 240,1675                  | 257,4921              | 260,0670                        |

1. W **dniu 4** Dawid zastakował 16 sNSBT przez smart kontrakt sNSBT_TCI.
2. Na podstawie tego depozytu, smart kontrakt wydał Dawidowi 15,3757 sNSBT_TCI, którego wartość odpowiada udziałowi 16 sNSBT w skarbcu sNSBT_TCI.
3. 24h po zastakowaniu sNSBT w puli, nastąpiła dystrybucja nagród z sNSBT (gNSBT). Smart kontrakt automatycznie zamienił USDN z dystrybucji na sNSBT po rynkowym kursie.
4. Wartość 15,3757 sNSBT_TCI, które posiada Dawid są teraz warte 16,16 sNSBT. Tokeny, które posiada Dawid zwiększyły swoją wartość zgodnie ze wzorem określającym cenę BA_TCI.

![](/images/cover-final.jpg)

## Pierwsze publikacje

Mamy przyjemność potwierdzić, że jako pierwszy zostanie opublikowany derywat **sNSBT_TCI**. Aktywacja smart kontraktu zostanie poprzedzona artykułem wyjaśniającym mechanikę działania.

W najbliższym czasie jest planowana również publikacja [roadmapy](https://wxpl.club/tci-roadmap) **The Heraclitus Project**. Mamy nadzieję zostać ciepło przyjęci w społeczności ekosystemu Waves.

Jeśli zainteresowała Cię nasza propozycja, zapraszamy na profil na [Twitterze](https://twitter.com/heraclitus_tci), [Grupę](https://t.me/heraclitus_project) oraz [Kanał](https://t.me/heraclitus_project_channel) na Telegramie.

Cieszymy się, że jesteś z nami!

## FAQ

### Co to jest BA_TCI?

**BA_TCI** to skrót określający stokenizowany procent składany aktywa bazowego np. sNSBT_TCI.

**BA** to skrót od *"Base Asset"*.

**TCI** to skrót od *"Tokenized Compound Interest"*.

### Czym jest derywat?

Derywat (ang. derivative) to rodzaj instrumentu finansowego, niebędącego papierem wartościowym, którego wartość uzależniona jest od aktywa bazowego.

### Jak formowana jest cena stokenizowanego procentu składanego?

Odpowiedź znajdziesz [TUTAJ](https://wxpl.club/heraclitus#cena-ba_tci).

### Po co uwzględniać procent składany w tokenie?

Stokenizowany procent składany zwalnia inwestora z konieczności ręcznego reinwestowania zysku generowanego przez instrument bazowy oraz daje możliwość posiadania aktywa, które jako token może zostać reinwestowane we wszystkie produkty w systemie Waves DeFi (pule płynności, protokoły pożyczkowe, algorytmy handlujące itp.)

### Jak zostanie rozwiązany problem różnicy w kursie BA_TCI i ceny w smart kontrakcie?

We wczesnym etapie tworzenia rynku TCI, zostaną aktywowane algorytmy Market Maker, które automatycznie będą sprzedawać i skupywać tokeny TCI po cenie ze smart kontraktu. W trakcie rozwoju projektu, oraz stabilizacji rynku zostanie uruchomiona dodatkowa możliwość zamiany dowolnego BA_TCI na jego równowartość ze skarbca, po cenie ze smart kontraktu - na podobnej zasadzie jak Neutrino Swap. Takie rozwiązanie zostanie zaimplementowane z wykorzystaniem tokenu, oferowanego w IDO, który poza funkcją Governance, będzie miał również funkcjonalność podobną do tej, jaką ma token NSBT w protokole Neutrino.

### Kolejne pytania zostaną uzupełnione po publikacji artykułu.

\
\
\
Waves Polska obejmuje patronatem **The Heraclitus Project**. Informacje o nowościach oraz zmianach będą publikowane na stronie [wxpl.club](https://wxpl.club/heraclitus).