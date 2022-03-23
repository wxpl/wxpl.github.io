---
layout: default
title: SecureConnection
nav_order: 102
parent: Bonus
permalink: /bonus/secure-connection

---

# WavesPolska – SecureConnection

## Czym jest WXPL SecureConnection?

WXPL SecureConnection to usługa VPN (Virtual Private Network) z zaimplementowanym mostem DNS. Usługa ta, ma na celu, przede wszystkim zabezpieczenie połączenia internetowego w trakcie korzystania z WavesExchange. Działanie jest podobne do popularnych serwisów takich jak ProtonVPN, NordVPN czy PrivateInternetAccess.

W trakcie połączenia, system jest odcięty od wszystkich znanych domen, które narażają użytkownika na wyciek jakichkolwiek poufnych informacji.

Korzystamy z kombinacja adlist. Szczegółowa lista dostępna [TUTAJ](https://github.com/wxpl/wxpl.github.io/blob/main/docs/wxpl-sc-adlist.txt).

W ramach dopełnienia powyższej listy, zostały dodane również filtry Regex:
```yaml
^ad([sxv]?[0-9]*|system)[_.-]([^.[:space:]]+\.){1,}|[_.-]ad([sxv]?[0-9]*|system)[_.-]
^(.+[_.-])?adse?rv(er?|ice)?s?[0-9]*[_.-]
^(.+[_.-])?telemetry[_.-]
^adim(age|g)s?[0-9]*[_.-]
^adtrack(er|ing)?[0-9]*[_.-]
^advert(s|is(ing|ements?))?[0-9]*[_.-]
^aff(iliat(es?|ion))?[_.-]
^analytics?[_.-]
^banners?[_.-]
^beacons?[0-9]*[_.-]
^count(ers?)?[0-9]*[_.-]
^mads\.
^pixels?[-.]
^stat(s|istics)?[0-9]*[_.-]
```

## Sposób działania:

![](/images/wxpl-secureconnection.svg)
W momencie nawiązania połączenia z Serwerem SecureConnection, twoje połączenie internetowe jest przepuszczane w całości przez bramkę, która korzysta z DNS-bridge blokującego blisko trzy miliony szkodliwych domen, aby Internet odbierany przez Twój komputer był tak bezpieczniejszy, jak to możliwe. Zalecane jest aby korzystać z bezpiecznego połączenie przede wszystkich na systemach operacyjnych, które szczególnie narażone są na szkodliwe oprogramowanie i niebezpieczne skrypty internetowe (min. Microsoft Windows, Android, iOS)

Dla wyższego poziomu anonimowości wykorzystaliśmy również technologię Unbound. Jest to walidujący, rekursywny i buforujący resolver DNS firmy NLnet Labs. Lokalizacja Twojego publicznego IP również zostaje zamaskowana.

**Funkcje Unbound:**

- Caching resolver z prefetchingiem popularnych elementów przed ich wygaśnięciem
- Przekierowanie i serwer DNS over TLS, z walidacją domen
- DNS over HTTPS
- Minimalizacja nazw zapytań
- Agresywne wykorzystanie DNSSEC-Validated Cache
- Strefy autorytetu, dla lokalnej kopii strefy głównej
- DNS64
- DNSCrypt
- DNSSEC validating
- Podsieć klienta EDNS

---

SecureConnection jest dostępny bezpłatnie, wyłącznie dla członów społeczności Waves, którzy posiadają środki (minimum 10 WAVES) stakowane na oficjalnym nodzie WavesPolska.

**Adres naszego Node:**

```3PHG2a8SXDe1uUtuKyieLAxhEksGkkqvrEw```{: .fs-6 }

*Środki z mintingu nowych bloków zostaną przeznaczone na rozwój i wsparcie projektu WavesPolska.*

Na podstawie id transakcji wydawane są certyfikaty umożliwiające połączenie przez **WavesPolska SecureConnection**

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*
