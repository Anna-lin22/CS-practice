# CS-practice

Практичні лабораторні роботи з курсу з кібербезпеки. Кожна лаба виконана у власному навчальному середовищі (Docker-контейнери), а хід виконання задокументовано у вигляді markdown-звітів зі скріншотами.

## Структура репозиторію

```
CS-practice/
├── webgoat/       # Лабораторні роботи на основі OWASP WebGoat
└── juice_shop/    # Лабораторні роботи на основі OWASP Juice Shop
```

## WebGoat

Навчальний застосунок із покроковими уроками за категоріями **OWASP Top 10**.

| Звіт | Категорія | Опис |
| :--- | :--- | :--- |
| [A01 — Hijack Session](webgoat/A01BrokenAccessControl_HijackSession.md) | Broken Access Control | Передбачення значення `hijack_cookie` для перехоплення чужої сесії |
| [A01 — IDOR](webgoat/A01BrokenAccessControl_IDOR.md) | Broken Access Control | Перегляд і редагування чужого профілю через прямі об'єктні посилання |
| [A03 — SQL Injection](webgoat/A03InjectionSQL.md) | Injection | Порушення конфіденційності, цілісності та доступності через SQL-ін'єкції (String, Numeric, DML/DDL/DCL, query chaining) |

## Juice Shop

Гейміфікований навчальний застосунок у форматі окремих "challenges" без покрокових підказок.

| Звіт | Опис |
| :--- | :--- |
| [OWASP Juice Shop — звіт](juice_shop/OWASP_JuiceShop_report.md) | Score Board, Missing Encoding, Error Handling, вхід під адміном (SQLi), Poison Null Byte, Easter Egg, DOM XSS, Confidential Document, View Basket (IDOR через Burp Suite) |

## Інструменти

* **Kali Linux** — робоче середовище
* **Docker** — запуск вразливих застосунків (WebGoat, Juice Shop)
* **Burp Suite** — перехоплення та модифікація HTTP-запитів (Proxy, Repeater, Intruder)
* **CyberChef** — декодування (Base64, ROT13 тощо)
