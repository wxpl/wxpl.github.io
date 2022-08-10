---

layout: default
title: USDN vs UST
nav_order: 7
parent: Neutrino
permalink: /usdn-vs-ust

---

# USDN vs UST

![](https://miro.medium.com/max/809/1*0itGD8O_rxVfg3q_1EQs7Q.png)

Od czasu krachu UST/LUNA pojawiło się wiele pytań dotyczących rentowności algorytmicznych stablecoinów, w tym USDN, należącego do Waves Protocol.

Chcemy wyjaśnić krytyczne różnice między USDN a UST, aby wyjaśnić, w jaki sposób USDN jest specjalnie zaprojektowany, aby uniknąć potencjalnej spirali śmierci i zapewnić użytkownikom zrównoważone zyski.

Aby zrozumieć różnice między mechanizmami działania UST i USDN, prześledźmy, jak działają oba te mechanizmy.

## Jak działał mechanizm UST/LUNA

UST wykorzystywał prostą funkcję "mint and burn" pomiędzy UST a tokenem LUNA. Użytkownicy mogli spalić LUNA o wartości 1 USD i otrzymać w zamian 1 UST i na odwrót.

Mechanizm ten stwarzał możliwość arbitrażu, aby utrzymać UST na poziomie 1 USD. Jeśli UST spadł poniżej 1 USD, arbitrażyści mogli kupić 1 UST za mniej niż 1 USD i spalić go w zamian za LUNA o wartości 1 USD.

Ta zachęta do zysku z arbitrażu była jedynym mechanizmem utrzymującym UST na stałym poziomie.

![](https://miro.medium.com/max/809/1*CMiAnltGADN6OC5bN2QRcg.png)

Niestety, nie trwało to długo. Gdy kapitalizacja rynkowa LUNA spadła poniżej kapitalizacji rynkowej UST, nastąpiła spirala śmierci. Stało się tak dlatego, że gdy UST zaczęły tracić na wartości, posiadacze stracili zaufanie i spalili swoje UST na rzecz nowo wybitych LUNA, a następnie natychmiast zaczęli sprzedawać swoje LUNA tak szybko, jak tylko mogli, aby je spieniężyć.

Ponieważ wybijano coraz więcej LUNA, podaż wymknęła się spod kontroli, a przy tak dużej liczbie sprzedających, wraz z nią zaczęła spadać kapitalizacja rynku. Im niższa była kapitalizacja rynkowa, tym mniej mechanizm był w stanie bronić kołka UST, co zakończyło się tragicznym krachem dla tych, którzy pozostali przy życiu.

## Jak działa mechanizm USDN?

USDN działa w inny sposób. W system USDN zaangażowane są trzy tokeny: USDN, WAVES i NSBT (token zarządzający Neutrino).

Główna różnica między UST/LUNA a USDN/WAVES polega na tym, że nie jest możliwe wybicie nieograniczonej ilości WAVES lub USDN. Ilość USDN/WAVES, którą można wybić, jest ograniczona na dwa główne sposoby:

1. Po pierwsze, inaczej niż w przypadku LUNA, WAVES wymieniane na USDN NIE są spalane, a zamiast tego są blokowane w inteligentnym kontrakcie Neutrino. Oznacza to, że przy wymianie z USDN z powrotem na WAVES, całkowita ilość jest ograniczona przez ilość zablokowaną w kontrakcie. Nie można wybić nieograniczonej ilości nowych WAVES, jak to miało miejsce w przypadku LUNA.

2. Po drugie, ilość USDN, na jaką użytkownik może wymienić WAVES w ciągu jednego dnia, jest ograniczona ilością NSBT, które posiada i stawia. Stakerzy NSBT otrzymują gNSBT, a ilość posiadanych gNSBT dyktuje, ile WAVES/USDN może być wymienione w ciągu dnia.

Poniższa tabela ilustruje przykłady, ile WAVES/USDN można wymienić każdego dnia w oparciu o limity NSBT:

![](https://miro.medium.com/max/809/1*9XSeu2DR4USh7k4ZffnFow.png)

## Rekapitalizacja USDN

Jedną z największych różnic między UST a USDN są przemyślane środki bezpieczeństwa, które zostały wprowadzone, aby utrzymać peg USDN w scenariuszu, w którym kapitalizacja rezerw WAVES spadnie poniżej kapitalizacji rynkowej USDN.

Zespół Neutrino nieustannie pracuje nad utrzymaniem stabilności USDN, wprowadzając różne mechanizmy w zależności od warunków rynkowych.

Początkowo zakładano, że w przypadku spadku USDN BR (backing ratio) poniżej 1, mechanizm dokapitalizowania WAVES aktywuje sprzedaż NSBT.

![](https://miro.medium.com/max/809/1*Ds9wdR4GlWnyyEocjm446w.png)

Podczas sprzedaży użytkownicy mogli kupować NSBT z kontraktu z rabatem, dopóki kapitalizacja rynkowa nie przekroczy progu bezpieczeństwa. Stworzyło to zachętę do zysku dla arbitrażystów, aby podnieść kapitalizację rynkową rezerw WAVES z powrotem powyżej USDN.

Później wprowadzono mechanikę czynnika księżycowego, co było niezwykle korzystne dla posiadaczy NSBT i rezerw USDN, jednak w rezultacie 95% NSBT zostało wyemitowanych. Oznacza to, że MAX podaż NSBT nie wystarcza inwestorom do dokapitalizowania systemu podczas szczególnie złych warunków rynkowych, jakich doświadczamy obecnie. Zespół Neutrino współpracuje ze społecznością, aby poprawić mechanikę rekapitalizacji poprzez wprowadzenie nowego tokena rekapitalizującego. Zostało to zaproponowane jako część szerszego planu ekosystemu Waves DeFi i od tego czasu zostało zaktualizowane w oparciu o informacje zwrotne od społeczności zawarte w tym artykule.

## Dystrybucja nagród za staking

Kolejną wadą UST w porównaniu z USDN jest sposób generowania i wykorzystania nagród. W przypadku UST większość użytkowników wpłacała środki na Anchor, który obiecywał blisko 20% APY. Jednak taki zysk był niemożliwy do utrzymania, ponieważ był on finansowany bezpośrednio przez zespół Terra/Luna.

W przeciwieństwie do tego, nagrody oferowane za stakowanie USDN są wynikiem działania algorytmu konsensusu Leased Proof of Stake (LPoS) w Waves blockchain.

Stakerzy USDN otrzymują zysk w oparciu o dzierżawione, zabezpieczone rezerwy WAVES. Jest to w pewnym sensie podobne do innych blockchainów Proof of Stake, które oferują nagrody za staking. Przeczytaj ten artykuł, aby dowiedzieć się więcej o specyfice stakingu.

Zespół Neutrino stale monitoruje warunki rynkowe i odpowiednio konfiguruje dystrybucję nagród za tyczenie. Na przykład w obecnych warunkach zabezpieczamy ryzyko finansowe, inwestując w protokół, aby uczynić go bezpiecznym. Połowę wygenerowanego zysku inwestujemy w rezerwy, część zysku przeznaczamy na zakup CRV, aby zrównoważyć peg, a część zysku nadal rozdajemy stakerom.

## Podsumowanie różnic

Podsumowując, oto kluczowe różnice między USDN a UST:

* LUNA używana do wybijania UST została spalona, podczas gdy WAVES używana do wybijania USDN jest zamknięta w inteligentnym kontrakcie

* Nieograniczone ilości LUNA/UST mogą być wybijane bez żadnych środków bezpieczeństwa

* Wymiana USDN jest ograniczona do ilości WAVES zablokowanych w kontrakcie, co oznacza, że nie można wybijać nieograniczonych ilości jak w przypadku LUNA, co spowodowało ich spiralę śmierci

* Stakerzy NSBT mają dzienne limity ilości WAVES/USDN, które mogą wymieniać.

* Kiedy kapitalizacja rynku rezerw WAVES spadnie poniżej kapitalizacji rynku USDN, automatycznie zaczyna działać mechanizm rekapitalizacji NSBT. Istnieje również dalsza propozycja społeczności, by wzmocnić ten mechanizm.

* Dochód wypłacany stakerom UST w Anchor Protocol został stworzony w dużej mierze ze skarbu fundacji Luna, dochód USDN pochodzi z nagród generowanych przez algorytm konsensusu LPoS Wave.


---

Źródło:

[USDN vs UST: Understanding the Differences
](https://medium.com/neutrinoteam/usdn-vs-ust-understanding-the-differences-d58c950dd22)