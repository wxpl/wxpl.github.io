---
layout: default
title: Neutrino Node
nav_order: 1
permalink: /bonus/neutrino-node

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

[DigitalOcean](https://digitalocean.com)

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

Oprogramowanie Walidatora Waves Node, Wersja 1.3.15 (Mainnet):

[github.com/wavesplatform/Waves/releases](https://github.com/wavesplatform/Waves/releases)


Pobierz oprogramowanie walidatora:
```
wget https://github.com/wavesplatform/Waves/releases/download/v1.3.15/waves_1.3.15_all.deb
```
Zainstaluj oprogramowanie walidatora:
```
sudo apt install ./waves_1.3.15_all.deb
```

Sprawdź status serwisu:
```
sudo systemctl status waves
```

Wyedytuj plik konfiguracyjny:
```
sudo nano  /etc/waves/waves.conf
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
    # Node name to send during handshake. Comment this string out to set random node name.
    node-name = "your-waves-node"
    declared-address = "123.456.789.101:6868"
    bind-address = "192.168.3.234"
    port = 6868
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
tar -xvf blockchain_last.tar -C /var/lib/waves/data
```

Uruchom proces walidatora:
```
sudo systemctl start waves
```

Node łańcucha Waves został zainstalowany, skonfigurowany oraz zaktualizowany. Gratulacje!

## Aplikowanie o udział w decentralizacji Neutrino

[Adres Smart Kontraktu do obsługi node'ów Neutrino](https://wavesexplorer.com/address/3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE/tx)

[Smart Contract dapp interface](https://waves-dapp.com/3P9vKqQKjUdmpXAfiWau8krREYAY1Xr69pE)



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
