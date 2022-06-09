---
layout: default
title: Neutrino Node
nav_order: 22
parent: Neutrino
permalink: /neutrino-node

---

**Instalujemy Node LPoS Waves - decentralizacja Neutrino Protocol**

<iframe width="560" height="315" src="https://www.youtube.com/embed/6G8QVI3uuDE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<details open markdown="block">
  <summary>
    Spis Treści
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Wybór VPS / self hosting

<a href="https://www.digitalocean.com/?refcode=caf4ad4a3a31&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=badge"><img src="https://web-platforms.sfo2.cdn.digitaloceanspaces.com/WWW/Badge%201.svg" alt="DigitalOcean Referral Badge" /></a>

## Wstępna konfiguracja serwera

[Oficjalna strona dokumentacji Waves](https://docs.waves.tech/en/)

Połącz się ze swoim serwerem:

```
ssh root@your-vps-public-ip
```

Zaktualizuj system Ubuntu:

```
sudo apt update && sudo apt upgrade -y
```

Zainstaluj środowisko Java:

```
sudo apt install openjdk-11-jre
```

## Instalacja i konfiguracja Waves Node

Oprogramowanie Walidatora Waves Node, Wersja 1.4.6 (Mainnet):

[github.com/wavesplatform/Waves/releases](https://github.com/wavesplatform/Waves/releases)

Pobierz oprogramowanie walidatora:

```
wget https://github.com/wavesplatform/Waves/releases/download/v1.4.6/waves_1.4.6_all.deb
```

Zainstaluj oprogramowanie walidatora:

```
sudo apt install ./waves_1.4.6_all.deb
```

Sprawdź status serwisu:

```
sudo systemctl status waves
```

Wyedytuj plik konfiguracyjny:

```
sudo nano /etc/waves/waves.conf
```

Przykładowy szablon pliku konfiguracyjnego:

```
waves {

  wallet {
    # Password to protect wallet file
    password = "BTC!4ndMayB3W4veS2"

    # Wallet seed as BASE58 string
    seed = "neverGonanGive7iyupNeverGonnalet*HYoudownDon354CryB4b444333"
  }

  blockchain {
    # Blockchain type: TESTNET | MAINNET | STAGENET | CUSTOM
    type = MAINNET
  }

  rest-api {
    # Enable/disable REST API
    enable = yes

    # Network address to bind to
    bind-address = "0.0.0.0"

    # Port to listen to REST API requests
    port = 6869

    # Hash of API key string
    api-key-hash = "2y49rehwf9485yr"
  }

  network {
    node-name = "your-waves-node"
    declared-address = "123.456.789.101:6868"
    bind-address = "192.168.3.234"
    port = 6868
  }

  features {
    auto-shutdown-on-unsupported-feature = no
    supported = [17]
  }

  rewards {
    desired = 700000000
  }

  # Uncomment to enable the gRPC extension
  # extensions += com.wavesplatform.api.grpc.GRPCServerExtension
}
```

Uruchom walidator Waves po raz pierwszy:

```
sudo systemctl enable --now waves
```

Sprawdź status procesu walidatora:

```
journalctl -u waves.service -f
```

## Chain bootstrap

[blockchain.wavesnodes.com](http://blockchain.wavesnodes.com)

Zainstaluj tmux:

```
sudo apt install tmux
```

Uruchom nową konsolę:

```
tmux new -s blockchain
```

Pobierz blockchain:

```
wget http://blockchain.wavesnodes.com/blockchain_last.tar
```

Wyjdź z powłoki tmux, poprzez kombinację klawiszy `ctrl+B` a następnie naciśnięcie klawisza `D`.

Zatrzymaj proces walidatora Waves:

```
sudo systemctl stop waves
```

Usuń niekompletne dane łańcucha:

```
sudo rm -rdf /var/lib/waves/data.
```

Po pobraniu pełnego archiwum łańcucha. Zdekompresuj baze danych:

```
tar -xvf blockchain_last.tar -C /var/lib/waves/
```

Uruchom proces walidatora:

```
sudo systemctl start waves
```

Node łańcucha Waves został zainstalowany, skonfigurowany oraz zaktualizowany. Gratulacje!

## Aplikowanie o udział w decentralizacji Neutrino

[Adres Smart Kontraktu do obsługi node'ów Neutrino](https://wavesexplorer.com/address/3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE/tx)

[Smart Contract dapp interface](https://waves-dapp.com/3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE)

## Automatyzacja wypłaty

Zainstaluj środowisko Python:

```
sudo apt install build-essential python3-dev python3-pip python3-testresources -y
```

Zainstaluj Pywaves do obsługi skryptu:

```
pip install pywaves
```

pobierz gotowy skrypt:

```
wget https://raw.githubusercontent.com/waves-exchange/neutrino-utilities/main/neutrino_nodes/payment.py
```

Dostosuj skrypt do swoich potrzeb:

```
nano payment.py
```

Przykład wyedytowanego skryptu:

```
import pywaves as pw
import datetime as dt

pw.setNode('https://node.heraclitus.space', chain='mainnet')
myAddress = pw.Address(privateKey='your_node_private_key') # klucz prywatny Twojego node'a
dappAddress = '3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE'
beneficiaryAddress = '3P_your_beneficiary_address' # adres na który chcesz otrzymać wypłatę 5% z mintingu
fee = pw.DEFAULT_INVOKE_SCRIPT_FEE
amount = myAddress.balance() - fee
result = myAddress.invokeScript(dappAddress, 'distributeMinerReward', params=[{"type": "string", "value": beneficiaryAddress}], payments=[{"assetId": None, "amount": amount}], feeAsset = None, txFee=fee)
now = dt.datetime.now()
print(now.strftime("%Y-%m-%d %H:%M:%S"))
print(result)
```

Skrypt jest gotowy do egzekwowania kodu. Możesz spróbować czy działa odpalając go ręcznie:

```
python3 payment.py
```

**Automatyzacja procesu**

Aby zautomatyzować egzekwowanie skryptu wykorzystamy `cron job`. Proponuję aby automatyzację wykonywać co 12h.

Otwórz cron tab:

```
crontab -e
```

W ostatniej lini podaj cron job pod automatyzację:

```
0 */12 * * * /usr/bin/python3 /path-to-your-script/payment.py > /root/payment.log
```

Zamień `/path-to-your-script/payment.py` na lokalizację, w której znajduje się `payment.py`. Jeśli jesteś root'em to skrypt prawdopodobnie znajduje się tu: `/root/payment.py`

`/root/payment.log` zapisuje output ze skryptu. Stwórzmy teraz ten plik:

```
touch /root/payment.log
```

lokalizacja może być dowolna. Sam zdecyduj.

Jeśli chcesz zautomatyzować proces wypłaty w inny sposób, pomocny może okazać się [Crontab.guru](https://crontab.guru/every-12-hours), szybki oraz prosty edytor kodów pod cron jobs.

Wszystko gotowe.

Monitoruj czy zadania cron są wykonywane poprawnie, bez błędów. Przydatna może okazać się usługa [Cronitor](https://cronitor.io/cron-job-monitoring).

Gratuluję! Jesteś operatorem Node'a Neutrino!

--- 

**Przytatne linki:**

* [wxpl.club](https://wxpl.club)

* [medium.com/@heraclitus_project](https://medium.com/@heraclitus_project)

* [medium.com/neutrinoteam/help-neutrino-to-decentralize-usdn-reserves-and-make-12k-year-f5813fb84ee2](https://medium.com/neutrinoteam/help-neutrino-to-decentralize-usdn-reserves-and-make-12k-year-f5813fb84ee2)

* [docs.waves.tech](https://docs.waves.tech)

* [blockchain.wavesnodes.com](http://blockchain.wavesnodes.com)

* [github.com/wavesplatform/Waves/releases](https://github.com/wavesplatform/Waves/releases)

* [Oficjalna strona dokumentacji Waves](https://docs.waves.tech/en/)

* [Adres Smart Kontraktu do obsługi node'ów Neutrino](https://wavesexplorer.com/address/3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE/tx)

* [Smart Contract dapp interface](https://waves-dapp.com/3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE)

* [Pywaves Stats](https://dev.pywaves.org/generators-monthly/)

* [Payout script in python](https://github.com/waves-exchange/neutrino-utilities)

* [Crontab.guru](https://crontab.guru/every-12-hours)
