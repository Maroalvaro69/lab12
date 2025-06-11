# lab12
zadanie obowiązkowe z laboratorium nr 12 z dockera 
# 🐳 Projekt Docker LEMP + phpMyAdmin

## 📌 Opis

Projekt realizowany w ramach Laboratorium 12 z przedmiotu *Programowanie Aplikacji w Chmurze Obliczeniowej (PAwChO)*.  
Celem było zbudowanie i uruchomienie stacka **LEMP** (Linux, Nginx, MySQL, PHP) z phpMyAdminem przy użyciu Docker Compose.

---

## 🧱 🔧 Zawartość stacka

- **🔹 Nginx** – serwer WWW (port `4001`)
- **🔹 PHP-FPM** – obsługa plików `.php` przez FastCGI
- **🔹 MySQL** – serwer bazy danych (zainicjalizowana baza `testdb`)
- **🔹 phpMyAdmin** – interfejs WWW do zarządzania MySQL (port `6001`)

---

## 📦 Obrazy użyte z DockerHub

- `mysql:8.0`
- `php:8.2-fpm`
- `nginx:latest`
- `phpmyadmin/phpmyadmin:latest`

Każdy obraz został zdefiniowany z konkretnym tagiem zgodnie z wymaganiami zadania.

---

## 🔗 Konfiguracja sieci

- `backend`:
  - `mysql`
  - `php`
  - `nginx`
  - `phpmyadmin`

- `frontend`:
  - `nginx`
  - `phpmyadmin`

---

## 🗂️ Struktura projektu

lemp-compose/
├── app/
│ └── index.php
├── app/nginx/
│ └── default.conf
├── docker-compose.yml
├── README.md


---

## ▶️ Uruchomienie

1. Upewnij się, że **Docker Desktop jest uruchomiony**
2. Otwórz terminal w katalogu z plikiem `docker-compose.yml`
3. Uruchom polecenie:

```bash
docker compose up --build

4. Aby zatrzymać kontery 
docker compose down

🌐 Dostęp przez przeglądarkę
http://localhost:4001 → strona index.php (PHP 8.2 – phpinfo)

http://localhost:6001 → phpMyAdmin

login: root

hasło: rootpass

widoczna baza danych: testdb

📋 Użyte polecenia
bash
Kopiuj
Edytuj
docker compose up --build      # uruchomienie i budowanie kontenerów
docker compose ps              # sprawdzenie działania usług
docker compose down            # zatrzymanie i usunięcie usług

✅ Dowody działania
✔️ Strona index.php wyświetla poprawnie phpinfo() pod localhost:4001

✔️ phpMyAdmin dostępny pod localhost:6001

✔️ Baza danych testdb została utworzona automatycznie przez kontener MySQL

✔️ Możliwość tworzenia tabel i manipulacji danymi w phpMyAdmin

