---
layout: default
title: SecureConnection
nav_order: 3
parent: WavesPolska
permalink: /secure-connection

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

---

## Połączenie z WXPL SecureConnection

### Windows

Pobierz OpenVPN GUI, zainstaluj go i umieść profil w folderze 'config' w katalogu OpenVPN, np. w 'C:\Program Files\OpenVPN\config'. Po zaimportowaniu, połącz się z serwerem VPN w systemie Windows, uruchamiając OpenVPN GUI z uprawnieniami administratora, klikając prawym przyciskiem myszy na ikonę w zasobniku systemowym i klikając "Connect".

### Android

Zainstaluj aplikację OpenVPN Connect, wybierz 'Import' z rozwijanego menu w prawym górnym rogu ekranu głównego, wybierz katalog na swoim urządzeniu, w którym przechowywany jest plik .ovpn i wybierz plik. Połącz się wybierając profil pod 'OpenVPN Profile' i naciskając 'Connect'.

### Linux

Zainstaluj OpenVPN używając menedżera pakietów (w tym przykładzie APT). Teraz, jako użytkownik root, utwórz folder /etc/openvpn/client i uniemożliw nikomu poza rootem wejście do niego (musisz to zrobić tylko za pierwszym razem):

```yaml
apt install openvpn
mkdir -p /etc/openvpn/client
chown root:root /etc/openvpn/client
chmod 700 /etc/openvpn/client
```

Przenieś konfigurację i połącz się (wprowadź hasło):

```yaml
mv whatever.ovpn /etc/openvpn/client/.
openvpn /etc/openvpn/client/whatever.ovpn
```

Naciśnij CTRL-C, aby się rozłączyć.

### Mac

Możesz użyć klienta OpenVPN, takiego jak Tunnelblick. Oto przewodnik jak zaimportować konfigurację.

### iOS

Zainstaluj aplikację OpenVPN Connect. Następnie przejdź do aplikacji, do której skopiowałeś plik .ovpn, wybierz plik, znajdź ikonę lub przycisk 'Share' lub 'Open with' i wybierz opcję otwarcia za pomocą aplikacji OpenVPN.

\
\
\
*Zaproponuj zmiany poprzez portal [GitHub](https://github.com/wxpl/wxpl.github.io) lub skontaktuj się pisząc na [email](mailto:contact@wxpl.club) lub [Telegram](https://t.me/waves_polska).*
