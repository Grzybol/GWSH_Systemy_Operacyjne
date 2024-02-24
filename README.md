# Dokumentacja serwera Palworld BetterPals Polska

## Opis plików konfiguracyjnych i skryptów

### PalServer.sh

Skrypt uruchamiający serwer gry Palworld na Linuxie. Ustawia uprawnienia wykonania dla pliku binarnego serwera i uruchamia go z przekazanymi argumentami.

- **Ścieżka**: `Pal/Binaries/Linux/PalServer-Linux-Test`
- **Zastosowanie**: Uruchamianie serwera Palworld.

### palworld.service

Plik usługi systemowej dla systemów używających systemd, zarządza serwerem Palworld jako usługą systemową.

- **Opis**: Serwer dedykowany Palworld BetterPals Polska.
- **Użytkownik/Grupa**: steam
- **Środowisko wykonawcze**: Ustawienia ścieżek bibliotek i ID aplikacji Steam.
- **Komendy**: Uruchamianie skryptu konserwacyjnego i start serwera z określonymi flagami.
- **Zachowanie**: Automatyczne restartowanie, maksymalny czas działania 4h.

### palworld-maintenance.sh

Skrypt konserwacyjny serwera, aktualizuje serwer gry przez SteamCMD i tworzy kopie zapasowe katalogu zapisów gry.

- **Operacje**: Aktualizacja aplikacji, tworzenie kopii zapasowych, usuwanie starych kopii.

### PalWorldSettings.ini

Plik konfiguracyjny gry Palworld, definiujący ustawienia serwera i gry.

- **Ustawienia**: Trudność, szybkość cyklu dnia/nocy, współczynniki expa, zdolności Pal i gracza, ustawienia gildii, maksymalna liczba graczy, nazwa i opis serwera, hasło administratora.

## Wskazówki

- Przed uruchomieniem serwera zaleca się sprawdzenie i dostosowanie ustawień w pliku `PalWorldSettings.ini` do preferencji.
- Regularne uruchamianie skryptu `palworld-maintenance.sh` pomoże utrzymać serwer w dobrym stanie oraz zabezpieczyć postępy gry poprzez tworzenie kopii zapasowych.
- Aby zarządzać serwerem jako usługą systemową, można użyć komend `systemctl start palworld.service`, `systemctl stop palworld.service` oraz `systemctl enable palworld.service` dla odpowiednio uruchamiania, zatrzymywania i dodawania serwera do autostartu systemu.
