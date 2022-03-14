---

layout: default
title: FAQ
nav_order: 17
parent: WavesExchange
permalink: /wx-faq

---

# WavesExchange - FAQ
{: .no_toc }

<details closed markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Rejestracja i logowanie

### **Dlaczego polecacie mi używać konta e-mail?**

Użycie konta e-mail jest najbezpieczniejszą metodą uwierzytelniania, ponieważ nie wymaga przesyłania seed. Wysyłanie seed zawsze wiąże się z ryzykiem jego przechwycenia. Jeśli osoby trzecie przejmą Twoje seed, stracisz swoje środki. Należy zauważyć, że konta seed nie są mniej bezpieczne niż konta e-mail, ale tylko wtedy, gdy użytkownik jest pewny bezpieczeństwa swoich działań, rozumie czym jest seed i jak działa blockchain. Konta seed są przeznaczone dla bardziej doświadczonych użytkowników.

Ponadto, korzystając z konta e-mail, zawsze można szybko przywrócić dostęp, jeśli zapomni się hasła.

W przeciwieństwie do konta seed, z konta e-mail można korzystać w różnych przeglądarkach i na różnych urządzeniach, bez konieczności importowania go za każdym razem.

### **Jaka jest różnica między rejestracją za pomocą e-maila a rejestracją za pomocą nasion, klucza prywatnego lub pliku Keystore?**

Rejestrując się za pomocą e-maila, możesz uzyskać dostęp do swojego konta z dowolnego urządzenia (z wyjątkiem autentycznej aplikacji mobilnej Waves.Exchange) z dowolnej przeglądarki, po prostu podając ten e-mail jako login i podając hasło.

W przypadku rejestracji przy użyciu Seed, klucza prywatnego lub pliku Keystore, rejestracja następuje tylko dla tego urządzenia i tylko dla tej przeglądarki. W rezultacie użytkownik będzie zmuszony do utworzenia hasła i zaimportowania konta za każdym razem, gdy wyczyści pamięć podręczną lub użyje nowego urządzenia albo przeglądarki. Nie zalecamy stosowania tej metody, ponieważ za każdym razem, gdy podajesz swoje nasiona, klucz prywatny lub plik Keystore File, mogą one zostać przechwycone.

### **Nie otrzymałem wiadomości z kodem weryfikacyjnym. Co mam zrobić?**

W takim przypadku musisz się upewnić, że podczas rejestracji poprawnie podałeś swój adres e-mail. Spróbuj też sprawdzić folder spamu. Być może wiadomość tam trafiła.

### **Próbuję się zalogować i otrzymuję komunikat "Nie masz żadnych zaimportowanych kont nasion. Przejdź na stronę Zarejestruj się i utwórz konto". Co to oznacza?**

Taki komunikat możesz zobaczyć tylko wtedy, gdy próbujesz zalogować się na swoje konto seed.

Może się on pojawić w następujących przypadkach:
- Wcześniej utworzyłeś konto seed, ale potem być może wyczyściłeś pamięć podręczną przeglądarki lub zacząłeś używać nowej przeglądarki lub urządzenia. W takim przypadku musisz zaimportować poprzednio utworzone konto.

- Zostałeś zarejestrowany przez e-mail i nie masz konta seed. W takim przypadku musisz przejść na stronę logowania przez e-mail.

### **Utworzyłem wcześniej konto seed i chcę go używać w innej przeglądarce. Jak mogę je zaimportować?**

Jeśli chcesz używać swojego konta seed w innej przeglądarce, musisz najpierw utworzyć hasło dostępu. Następnie możesz zaimportować istniejące konto, podając swoje seed.

### **Czy mogę przywrócić dostęp do mojego konta seed przez e-mail?**

Niestety, nie jest to możliwe. Konta seed nie są powiązane z adresami e-mail. Nikt poza Tobą nie ma dostępu do Twojego seed i dlatego nie może ich odzyskać.

Jeśli jednak zapomniałeś hasła do konta, ale pamiętasz nasiona, możesz przywrócić dostęp do konta. W tym celu należy skorzystać z linku "Nie pamiętasz hasła?", który znajduje się pod formularzem logowania.

### **Jak przywrócić dostęp do mojego konta e-mail?**

Aby przywrócić dostęp do konta e-mail, należy wprowadzić adres e-mail, który został użyty podczas rejestracji. Następnie musisz wymyślić nowe hasło i potwierdzić jego zmianę za pomocą kodu weryfikacyjnego, który zostanie wysłany na Twój adres e-mail.

## Wpłaty i wypłaty

### **Jak dokonać wpłaty na Waves.Exchange?**

Możesz wpłacić środki na Waves.Exchange, przenosząc je z kont Waves.Exchange lub z innych platform i portfeli.

Aby to zrobić, przejdź na stronę wpłat i wykonaj poniższe kroki:

1. Wybierz aktywa, które chcesz wpłacić.

2. Wybierz metodę wpłaty. W zależności od aktywa wybranego w kroku 1, platforma zaproponuje dostępne sposoby wpłaty środków.
a) Dla wewnętrznych przelewów pomiędzy kontami Waves.Exchange wybierz kartę (metodę wpłaty) z sieci Waves.
b) Aby zażądać środków z portfela MetaMask, wybierz kartę MetaMask w wymaganej sieci.
c) Aby wysłać środki z sieci zewnętrznych (platform i portfeli), wybierz kartę sieci, z której chcesz dokonać wpłaty.

Każda karta ma zapisaną sieć (czasem standard tokena lub typ adresu).

3. Zwróć uwagę na ważne kwestie:
- Sieć, którą wybierzesz, musi być zgodna z siecią platformy, z której wypłacasz środki. Jeśli wybierzesz niewłaściwą sieć, stracisz swoje środki.
- Jeśli wybrana zostanie sieć lub fork sieci Ethereum (ETH), standard tokena musi być zgodny ze standardem tokena na platformie, z której wypłacasz środki.
- Istnieje minimalna kwota depozytu dla przelewów z sieci zewnętrznej. Jeśli prześlesz mniejszą kwotę, stracisz swoje środki.

4. Wyślij środki na wskazany adres.

W przypadku MetaMask, wprowadź kwotę depozytu i potwierdź działania w MetaMask.

### **Jak zmienić sieć w MetaMask?**

1. W portfelu MetaMask otwórz konto i przejdź do strony z ustawieniami.
2. Wybierz sieć z menu i kliknij 'nowa sieć'*.
3. Określ ustawienia sieci i zapisz je.

Następnie w nagłówku portfela możesz szybko zmienić sieci, których potrzebujesz.

*Sieć Waves nie może byćjeszcze dodana do MetaMask.*

### **Jak mogę wypłacić środki z portfela Waves.Exchange?**

Aby to zrobić, przejdź na stronę wypłat i wykonaj poniższe kroki:

1. Wybierz aktywa, które chcesz wypłacić.

2. Wklej adres, na który chcesz wysłać aktywa.

3. Wybierz sieć. Sieć jest często wykrywana automatycznie, ale czasami podany adres może odpowiadać kilku sieciom.

Upewnij się, że platforma, na którą wypłacasz środki, obsługuje wpłacanie tych środków i wybraną sieć.

4. Wprowadź kwotę, którą chcesz wypłacić (bez uwzględnienia opłat).

Uwaga:

opłaty są podane osobno poniżej (na saldzie musi być wystarczająca ilość środków na pokrycie tych opłat);
istnieje minimalna kwota wypłaty w przypadku przelewów do sieci zewnętrznej.

5. Sprawdź, czy pola zostały wypełnione poprawnie i potwierdź akcję.

### **Jaka jest opłata za wpłatę/wypłatę?**

Nie pobieramy żadnych opłat za wpłaty.

Jeśli dokonujesz wpłaty z sieci zewnętrznej, uważnie przeczytaj zasady i opłaty obowiązujące na platformie, z której wypłacasz środki. Po odliczeniu wszystkich opłat, kwota przelewu musi być większa niż minimalna kwota depozytu Waves.Exchange. Jeśli prześlesz mniejszą kwotę, stracisz swoje środki.

Opłaty za wypłatę środków mogą się różnić w zależności od wybranego aktywa i sieci, do której chcesz wypłacić środki.

Aktualne opłaty oraz minimalne kwoty wpłat i wypłat z zewnętrznego blockchaina znajdziesz [tutaj](https://waves.exchange/gatewayfees).

### **Kiedy wpłyną środki?**

Status procesu wpłaty/wypłaty możesz sprawdzić na [stronie transakcji](https://waves.exchange/wallet/transactions).

Czas przetwarzania przelewów zewnętrznych może wynosić do 60 minut. Jeśli po tym czasie środki nie zostaną otrzymane, skontaktuj się z supportem.

### **Przekazałem mniej niż minimalna kwota wskazana w interfejsie. Jak uzyskać/zwrócić środki?**

Przykro nam, ale przelewy poniżej kwoty minimalnej nie mogą zostać wpłacone ani zwrócone.

Nie wysyłaj kolejnej transakcji z kwotą mniejszą niż minimalna, by "przepchnąć" poprzednią. Transakcje nie są sumowane i stracisz środki z dwóch transakcji.

### **Jakie sieci, standardy tokenów i typy adresów obsługuje Waves.Exchange?**

Sieci, standardy tokenów i typy adresów, które obsługuje Waves.Exchange, zależą od wybranego aktywa.

Aby zobaczyć aktualne informacje, przejdź na stronę depozytu i wybierz aktywo.
Platforma zaproponuje dostępne metody wpłaty (karty, na których zapisana jest sieć, standard tokena lub typ adresu).

W przypadku wypłaty środków platforma obsługuje te same sieci, standardy tokenów i typy adresów.

### **Nie masz wystarczająco dużo Waves lub innych aktywów, by zapłacić za opłatę sieciową lub bramową?**

Aby zapłacić opłatę sieciową, możesz kupić Waves na giełdzie lub zapłacić opłatę sieciową za pomocą aktywów sponsorowanych.

Aby uiścić opłatę bramkową, możesz kupić potrzebne aktywa na giełdzie lub zmniejszyć kwotę wypłaty.



\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*