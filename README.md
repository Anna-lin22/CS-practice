# CS-practice

Практичні лабораторні роботи з курсу з кібербезпеки. Кожна лаба виконана у власному навчальному середовищі (Docker-контейнери), а хід виконання задокументовано у вигляді markdown-звітів зі скріншотами.

## Структура репозиторію

```
CS-practice/
├── webgoat/       # Лабораторні роботи на основі OWASP WebGoat
├── juice_shop/    # Лабораторні роботи на основі OWASP Juice Shop
├── DeathNote/     # Проходження CTF-машини Deathnote
├── ColddBox/      # Проходження CTF-машини ColddBox: Easy
└── suricata/      # Встановлення та налаштування Suricata IDS
```

## WebGoat

Навчальний застосунок із покроковими уроками за категоріями **OWASP Top 10**.

| Звіт | Категорія | Опис |
| :--- | :--- | :--- |
| [A01 — Hijack Session](webgoat/A01BrokenAccessControl_HijackSession.md) | Broken Access Control | Передбачення значення `hijack_cookie` для перехоплення чужої сесії |
| [A01 — IDOR](webgoat/A01BrokenAccessControl_IDOR.md) | Broken Access Control | Перегляд і редагування чужого профілю через прямі об'єктні посилання |
| [A03 — SQL Injection](webgoat/A03InjectionSQL(intro).md) | Injection | Порушення конфіденційності, цілісності та доступності через SQL-ін'єкції (String, Numeric, DML/DDL/DCL, query chaining) |
| [A07 —  Identity & Auth Failure](webgoat/A07IdentityAuthFailures.md) | Authentication Failures | Помилки автентифікації (обхід 2FA, небезпечний логін), вразливості JWT (JSON Web Token) |

## Juice Shop

Гейміфікований навчальний застосунок у форматі окремих "challenges" без покрокових підказок.

| Звіт | Опис |
| :--- | :--- |
| [OWASP Juice Shop — звіт](juice_shop/OWASP_JuiceShop_report.md) | Score Board, Missing Encoding, Error Handling, вхід під адміном (SQLi), Poison Null Byte, Easter Egg, DOM XSS, Confidential Document, View Basket (IDOR через Burp Suite) |

## DeathNote: 1

Навчальна CTF-машина з VulnHub, стилізована під аніме *Death Note*. Завдання передбачає проведення розвідки цільової системи, отримання початкового доступу та підвищення привілеїв до `root`.

| Звіт | Опис |
| :--- | :--- |
| [DeathNote: 1 — CTF write-up](DeathNote/Deathnote_CTF_report.md) | Розвідка та сканування цільової системи, пошук інформації на вебсервері, отримання облікових даних, SSH-доступ до користувача `l`, підвищення привілеїв та отримання `root` |

## ColddBox: Easy

Навчальна CTF-машина з VulnHub на базі WordPress. Мета — отримати початковий доступ через веб-застосунок та підвищити привілеї до root. Демонструє типовий ланцюжок експлуатації реального WordPress-сайту.

| Звіт | Опис |
| :--- | :--- |
| [ColddBox: Easy — CTF write-up](ColddBox/ColddBox_CTF_report.md) | Сканування мережі, знаходження логіна через приховану сторінку, брутфорс пароля Hydra, заливка веб-шелла через плагін, отримання reverse shell, SSH-доступ через пароль бази даних, підвищення привілеїв через sudo/chmod (GTFOBins) |

## Suricata IDS

Розгортання та налаштування системи виявлення вторгнень **Suricata** на сервері Ubuntu: встановлення з офіційного PPA, конфігурація захоплення трафіку (af-packet), написання власних сигнатур та перевірка роботи на реальному й тестовому трафіку.

| Звіт | Опис |
| :--- | :--- |
| [Suricata IDS — звіт](Suricata/Suricata_IDS_report.md) | Встановлення Suricata через PPA, налаштування af-packet та HOME_NET, оновлення правил (suricata-update), перевірка на testmynids.org, написання власних правил (local.rules), аналіз помилок синтаксису сигнатур, перевірка алертів у fast.log/eve.json |

## Інструменти

* **Kali Linux** — робоче середовище для виконання лабораторних робіт і CTF
* **Docker** — запуск вразливих навчальних застосунків (WebGoat, Juice Shop)
* **Nmap** — сканування портів і визначення запущених мережевих сервісів
* **Burp Suite** — перехоплення та модифікація HTTP-запитів (Proxy, Repeater, Intruder)
* **SSH** — віддалене підключення до цільової системи
* **CyberChef** — декодування та аналіз даних (Base64, ROT13 тощо)
* **Netdiscover** — виявлення активних хостів у локальній мережі
* **Hydra** — автоматизований перебір облікових даних для мережевих сервісів
* **Wget** — завантаження файлів із вебресурсів
* **Dirb** — брутфорс директорій та файлів на веб-сервері
* **Netcat** — створення reverse shell з'єднань
* **Suricata** — система виявлення вторгнень (IDS/IPS/NSM), аналіз мережевого трафіку та сигнатурне виявлення атак
* **jq** — обробка та фільтрація JSON-логів (зокрема `eve.json` від Suricata)
