---
layout: default
title: AMA
nav_order: 37
parent: SwopFi

---

![Swop AMA](https://miro.medium.com/max/1400/1*a0ux2i8s2ueKXp0qrYGT8w.jpeg)
*Poniższy artykuł jest przetłumaczoną wersją udokumentowanego AMA z marca 2021.
Niewielka część materiału została poprawiona o aktualne informacje (grudzień 2021).*

**Jak wygląda proces publikacji nowych par oraz jak wygląda strategia Swop.fi w celu przyciągnięcia 
większej płynności? Jakie są kryteria dla projektu, który ma być notowany i jak Swop.fi wybiera projekty, 
które mają być notowane, aby konkurować z innymi platformami AMM?**

Zespół Swop.fi skupił się na początkowym notowaniu najważniejszych aktywów, które przyciągną znaczną płynność i uwagę społeczności - wszystkie główne aktywa Waves. Uruchomiliśmy również pule z USDT i USDC, dwoma aktywami, które wiemy, że są ważne w ekosystemach Ethereum i BSC. Nowe aktywa będą notowane, ale skupimy się na przyciąganiu płynności, a społeczność będzie miała wpływ na przyszłe notowania.
Drugie pytanie dotyczy dodania właściwych par, które przyciągają płynność. Ale, co ważniejsze, wiele osób obecnie dodaje płynność do puli Swop.fi z powodu wysokich zwrotów, jakie uzyskują. Bardzo prosty interfejs i wysokie zwroty naprawdę przyciągają użytkowników do puli, i to był pomysł - uruchomić token administracyjny i dać każdemu uczciwą szansę uczestnictwa. Rozdaliśmy 1 milion tokenów SWOP, aby zachęcić wczesnych dostawców płynności, które zostaną udostępnione w ciągu jednego roku, i jest jeszcze 1 milion SWOP, które zostaną rozdane w ciągu pierwszego roku działalności. W tej chwili, to z pewnością działa, ponieważ istnieje ponad 40 milionów dolarów w płynności zablokowanej na Swop.fi. Ważne jest, aby zrozumieć, że umieszczając płynność w pulach, zarabiasz pieniądze na różne sposoby. Wszystkie pule mają USDN lub EURN jako jeden z aktywów, z wyjątkiem jednej puli, WAVES-BTC. Staking USDN płaci 8-15% bazowego APY. Następnie dostawcy płynności pobierają część opłat swapowych, które generuje każda pula (pozostała część jest przeznaczana na zakup tokenów SWOP z puli SWOP/USDN). Następnie, możesz postawić swoje tokeny udziałów, które w niektórych innych usługach są określane jako tokeny LP, na farmę tokenów SWOP. I wreszcie, możesz postawić na szali swoje zagrabione tokeny SWOP i otrzymać nagrodę za zarządzanie.

**SWOP jest tokenem administracyjnym: użytkownicy będą mogli głosować za jego pomocą na główne 
ustawienia całego systemu Swop.fi. Na czym to dokładnie polega?**

SWOP jest centralnym tokenem w systemie Swop.fi. Możesz zarabiać SWOP poprzez staking swoich tokenów udziałów. Jeśli dostarczasz płynność do jednej z puli, otrzymujesz tokeny akcji z inteligentnego kontraktu. Można je deponować i w ten sposób zarabiać SWOP. Można je deponować i w ten sposób zarabiać SWOP. Oznacza to, że możesz zarabiać SWOP tylko poprzez udział w działaniu serwisu. W dłuższej perspektywie, większość ważnych decyzji w Swop.fi będzie podejmowana poprzez głosowanie za pomocą tokenów SWOP. Posiadacze SWOP będą mieli prawo decydować o tym, co dalej ze Swop.fi, głosując na parametry systemu, zmiany w wagach puli lub przyszły rozwój technologiczny.

**Swop.fi działa w oparciu o model AMM. Jaka jest różnica między tradycyjną giełdą typu order-book a AMM?**

Aby wymienić aktywa A należące do posiadacza 1 na aktywa B należące do posiadacza 2 na tradycyjnej giełdzie opartej na księdze zleceń, potrzeba kilku rzeczy. Po pierwsze, potrzebny jest nadzór nad aktywami, który może być scentralizowany lub zdecentralizowany. Następnie potrzebny jest mechanizm dopasowujący - system, który tworzy duży przegląd wszystkich zleceń kupna i sprzedaży utworzonych przez użytkowników, a jeśli dwa zlecenia pasują do siebie, wykonuje je. Wreszcie, potrzebny jest mechanizm rozliczeniowy - system, który przenosi zamienione aktywa do nowychwłaścicieli. Problem polega na tym, że płynność dla konkretnej pary tokenów, dostępna w tradycyjnym arkuszu zleceń giełdy, któryjest po prostu dużym dziennikiem wszystkich otwartych zleceń kupna i sprzedaży, jest rozłożona na różne ceny. W rezultacie, jeśli użytkownik chce sprzedać dużą ilość danego aktywa, doświadczy poślizgu, co oznacza, że niektóre tokeny zostaną sprzedane po niższej wartości niż aktualna cena rynkowa, ponieważ w arkuszu zleceń nie ma wystarczającej ilości zleceń dla tej wielkości transakcji.
Dlatego też, handel oparty na księdze zleceń jest świetny dla traderów szukających elastyczności w wyborze cen, ale nie tak dobry dla głębokości płynności. AMM działa odwrotnie, ponieważ płynność nie znajduje się już w księdze zamówień z różnymi cenami, ale jest umieszczona w puli. jeśli ceny się zmieniają, ceny w całej puli ulegają zmianie. Jeśli ktoś chce kupić lub sprzedać, może kupić (w ramach określonych limitów formuły cenowej) tak dużo jak chce, tak długo jak jest wystarczająca płynność w puli (więc nie wychodzi z równowagi, jak w przypadku 100 tokenów X i 0 tokenów Y). Tworzy to znacznie większą głębię płynności w unikalny, w pełni zdecentralizowany sposób.
Na AMM użytkownik uzyskuje lepszą płynność w zamian za to, że nie jest już w stanie z góry określić ceny swojej oferty. Tymczasem dostawcy płynności mają zachętę do deponowania swoich monet w puli i zbierania nagród.W rezultacie, AMM oferują bardziej efektywny i atrakcyjny finansowo model, który działa dla każdego, zarówno małych jak i dużych traderów.

**Czy Swop.fi oferuje niższe opłaty i większą prędkość w porównaniu do platform działających na Ethereum?**

Swop.fi działa w oparciu o protokół Waves, który dzięki swojej wysokiej przepustowości oferuje minimalne opłaty w wysokości 0.005 WAVES, czyli mniej więcej 0.09$ (stan na Grudzień 2021).
Średnia prędkość dodania transakcji do łańcucha Waves wynosi zaledwie 3-5 sekund, nawet przy minimalnej opłacie. Niewielkie opłaty i wysoka prędkość są głównymi elementami doświadczenia użytkownika na Swop.fi, ponieważ różnice w stosunku do innych protokołów, takich jak Ethereum, są ogromne. Wysłanie transakcji na Ethereum może kosztować od 40 dolarów wzwyż i zająć kilka minut. Oprócz gorszego doświadczenia użytkownika, zwiększa to 
prawdopodobieństwo poślizgu - sytuacji, w której czyjaś transakcja jest zapisywana w łańcuchu przed Twoją, zmieniającparametry Twojej transakcji.

**Jakie są najważniejsze cele projektu Swop.fi w 2021 roku?**

Jednym z głównych celów jest custom pools, czyli możliwość uruchomienia własnych puli (pool). Będzie to najprostszy sposób, aby stworzyć rynek dla swojego tokena, ponieważ nie będzie kłopotów z tworzeniem zleceń na giełdzie i nie będą wymagane żadne specjalne umiejętności.Za pomocą zaledwie kilku kliknięć będziesz mógł dodać np. pule swojego tokena w parze z popularnymi 
kryptowalutami, takimi jak WAVES, USDN czy BTC. Wszystko, czego potrzebujesz, to posiadanie tokenów do zdeponowania. Po utworzeniu, pule będą działać samodzielnie.Kolejnym ważnym celem jest API Swop.fi. Kiedy podstawowa funkcjonalność Swop.fi będzie już gotowa, zamierzamy wdrożyć API, które dostarcza danych dla naszych rynków, takich jak płynność, wolumen, ceny itp. Dane te mogą być wykorzystane na różne sposoby, w tym do reprezentacji naszego projektu na DappRadar, CoinMarketCap i CoinGecko.Najważniejszym punktem naszego planu na 2021 rok jest zaoferowanie naszym użytkownikom dostępu do płynności między łańcuchami. Będą oni w stanie dodawać i usuwać płynność bezpośrednio z kont na innych blockchainach. Interakcja między kontem użytkownika a inteligentnym kontraktem Swop.fi będzie odbywać się za pośrednictwem bramek opartych na protokole komunikacji między-łańcuchowej Gravity. Ta cecha sprawi, że Swop.fi stanie się usługą z głównym nurtem.Ponadto, uruchomiona zostanie funkcja głosowania, inteligentne kontrakty będą audytowane w celu zapewnienia ich bezpieczeństwa, a także dodana zostanie obsługa Ledger.

**Swop.fi zawiera wiele zalet i korzyści, ale czy jest wystarczająco bezpieczny dla użytkowników?**

Bezpieczeństwo Swop.fi jest zapewnione przez użycie języka inteligentnych kontraktów Ride. Ride jest jednym z najbezpieczniejszych języków dla inteligentnych kontraktów. Ponadto, wkrótce zostaną przeprowadzone audyty inteligentnych kontraktów. Wyniki przeprowadzonych audytów, dostępne na: https://swop.fi/about

**Jaki jest rynek docelowy? Czy jest to projekt globalny?**

Swop.fi jest z pewnością projektem globalnym i nie jest skierowany do żadnej konkretnej społeczności lokalnej.

**Czy tokeny ERC-20 zostaną wkrótce dodane do puli Swop.fi?**

Tokeny ERC-20, USDT i USDC, są już dostępne na Swop.fi. Są to tokeny opakowane z Waves.Exchange, więc jeśli Waves.Exchange, zespół Gravity lub inne zespoły wprowadzą więcej tokenów ERC-20 do ekosystemu Waves, mogą one również pojawić się na Swop.fi. Więcej tokenów ERC-20 pojawi się na Swop.fi w przyszłości, ale wymogiem jest tutaj posiadanie bramek do ekosystemu Waves. Głęboka integracja z innymi łańcuchami jest planowana na pierwszą połowę 2022

**Czy istnieją sposoby na ulepszenie AMM? Jak Swop.fi poradzi sobie z obecnymi ograniczeniami AMM, takimi
jak dźwignia, shorty i nietrwała strata? Czy planowane jest wprowadzenie ksiąg zleceń on-chain?**

Istnieje wiele pomysłów i trwających badań Swop.fi na te tematy. W tej chwili księgi zamówień on-chain nie wyglądają jak nic nowego i właściwie nie są potrzebne, ponieważ główną cechą AMM jest handel bez żadnych ksiąg zamówień. Jeśli wolisz tradycyjny handel z książką zleceń, użyj Waves.Exchange. Jeśli chodzi o nietrwałą stratę, jest to wada, ale niestety nie możemy jej w pełni uniknąć ze względu na charakter i konstrukcję AMM. Produkty takie jak dźwignia i shorty pojawią się w ekosystemie Waves na szczycie istniejących protokołów, ale niekoniecznie jako część Swop.fi.

**Jaka jest różnica w dostarczaniu płynności do puli USDT / USDN i USDTLP / USDN?**

USDT to Tether USD, który jest bardzo dobrze znany w przestrzeni kryptowalutowej. Waves.Exchange oferuje usługę depozytu dla USDT, opartą na Ethereum dApps, jak Curve czy Uniswap. Tak więc, kiedy deponujesz USDT, otrzymujesz tokeny USDTLP, a te tokeny mogą być wykorzystane do zapewnienia płynności na Swop.fi. Mówiąc prościej, możesz zdeponować USDT, aby zarobić około ~50% rocznie, otrzymać USDTLP i użyć tych tokenów do zapewnienia płynności na Swop.fi, aby zarobić jeszcze więcej.

**Istnieje pięć głównych problemów dominujących w kryptografii i blockchain: nadmierna zmienność, 
bezpieczeństwo, skalowalność, interoperacyjność, szybkość transakcji. Jak Swop.fi planuje przezwyciężyć te problemy?**

Protokół Waves, na którym opiera się Swop.fi, ma na celu rozwiązanie tych problemów: jego przepustowość jest więcej niż wystarczająca, transakcje są bardzo szybkie (3-5 sekund) i tanie (około $0,09), podczas gdy inteligentne kontrakty są bezpieczne, dzięki nie-Turingowemu kompletnemu językowi Ride, zaprojektowanemu przez zespół rozwoju protokołu Waves. Aby zwalczyć problemy związane ze zmiennością, Swop.fi obsługuje różne pary handlowe, pozwalając inwestorom na dywersyfikację swoich oszczędności.

**Obecnie depozyt (staking) jest bardzo popularnym tematem. Wyjaśnijmy korzyści płynące z SWOP staking.**

Istnieje funkcjonalność depozytu dla tokena SWOP. Jego posiadacze mogą deponować swoje aktywa na stronie Governance > Staking, z aktualnym APY wynoszącym około 14%. Skąd pochodzą te przychody? 40% opłat w każdej parze handlowej jest wykorzystywane jako opłata za zarządzanie w celu odkupienia tokenów SWOP (nie więcej niż 1% puli) i rozprowadzenia ich wśród deponentów SWOP. Umożliwia to dodatkowy nacisk na kupno i sprawia, że system jest stabilny.

**Jaki wpływ ma SWOP na system Swop.fi? Jakie są korzyści dla posiadaczy SWOP?**

Posiadacze SWOP mogą głosować nad parametrami systemu, na przykład nad wagami puli, oraz wpływać na kierunki rozwoju produktu. Jednocześnie SWOP jest opłacalny dla inwestorów, pozwalając im uzyskać APY do 50% na depozytach i do ~200% na zasilaniu płynności puli.

**Czy możemy wystawić nasz własny token na Swop.fi?**

Jak wspomniano powyżej, funkcja niestandardowej puli jest obecnie w fazie rozwoju i będzie dostępna za kilka miesięcy. Wierzymy, że ten krok znacznie zwiększy popularność Swop.fi i przyciągnie więcej interesujących projektów wraz z ich społecznościami.

*Źródło: [https://medium.com/swop-fi/swop-fi-explained-23316b447b39](https://medium.com/swop-fi/swop-fi-explained-23316b447b39)*

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*
