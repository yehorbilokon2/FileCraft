# [cite_start]SOFTWARE REQUIREMENTS SPECIFICATION (SRS) [cite: 2]

## [cite_start]Назва проєкту: FileCraft-обробник файлів [cite: 3]

### Інформація про документ:
* [cite_start]**Версія:** v0.1 (draft) [cite: 3]
* [cite_start]**Дата:** 19.03.2026 [cite: 3]
* [cite_start]**Команда:** Панасенко, Білоконь, Окол [cite: 3]
* [cite_start]**Замовник:** Стартап YoungAnalytics ABB [cite: 3]

---

### [cite_start]1. ВСТУП (INTRODUCTION) [cite: 4]
* [cite_start]**Опис:** FileCraft — веб-сервіс для швидкого збереження та обробки файлів за допомогою ШІ. [cite: 4]
* [cite_start]**Замовник:** Стартап YoungAnalytics ABB. [cite: 4]
* [cite_start]**Проблема:** Користувачі витрачають багато часу на пошук основної інформації у файлі. [cite: 4]
* [cite_start]**Цільова аудиторія:** Студенти та бізнес-аналітики (вік 17–48, технічно грамотні користувачі). [cite: 4]

### [cite_start]2. ЗАГАЛЬНИЙ ОПИС (OVERALL DESCRIPTION) [cite: 5]
[cite_start]**Актори:** [cite: 5]
* [cite_start]**Гість (незареєстрований):** перегляд файлів до 500 МБ на день без ШІ. [cite: 5]
* [cite_start]**Зареєстрований користувач:** обробка файлів до 1 ГБ на день та базові можливості ШІ. [cite: 5]
* [cite_start]**Premium:** обробка файлів до 10 ГБ на день та розширені можливості ШІ. [cite: 5]
* [cite_start]**Залежності:** SMTP-сервер (email-підтвердження), PostgreSQL (зберігання даних). [cite: 5]

### [cite_start]3. ФУНКЦІОНАЛЬНІ ВИМОГИ (FUNCTIONAL REQUIREMENTS) [cite: 6]
* [cite_start]**FR-01 [Must]:** Система дозволяє реєстрацію через email. [cite: 6]
* [cite_start]**FR-02 [Must]:** Зареєстрований користувач може завантажити файл та отримати оброблений звіт. [cite: 6]
* [cite_start]**FR-03 [Must]:** ШІ оброблює файли. [cite: 6]
* [cite_start]**FR-04 [Should]:** Підтримується пошук файлів за ключовими тегами. [cite: 6]
* [cite_start]**FR-05 [Should]:** Файли можна позначати тегами. [cite: 6]
* [cite_start]**FR-06 [Could]:** Файл можна зробити публічним та поділитися посиланням. [cite: 6]
* [cite_start]**FR-07 [Must]:** Користувач може видалити та коригувати файл. [cite: 6]
* [cite_start]**FR-08 [Should]:** Адмін може деактивувати обліковий запис. [cite: 6]
* [cite_start]**FR-09 [Must]:** Користувач може купити Premium та використовувати всі його можливості. [cite: 6]

### [cite_start]4. НЕФУНКЦІОНАЛЬНІ ВИМОГИ (NON-FUNCTIONAL REQUIREMENTS) [cite: 7]
* [cite_start]**NFR-P-01:** Час відповіді для 95% операцій < 1,5 с при 500 одночасних користувачів. [cite: 7]
* [cite_start]**NFR-S-01:** Паролі зберігаються у вигляді argon2-хешів (cost factor ≥ 12). [cite: 7]
* [cite_start]**NFR-S-02:** HTTPS обов'язковий (TLS 1.2+). [cite: 7]
* [cite_start]**NFR-U-01:** Інтерфейс адаптивний: підтримка екранів 320px–2560px. [cite: 7]
* [cite_start]**NFR-R-01:** Uptime ≥ 99.5% (не більше 22 год/місяць недоступності). [cite: 7]
* [cite_start]**NFR-R-02:** Автоматичний backup БД раз на 12 год. [cite: 7]

### [cite_start]5. ОБМЕЖЕННЯ (CONSTRAINTS) [cite: 8]
* [cite_start]**C-01:** Back-end реалізується на Node.js (Express.js або NestJS). [cite: 8]
* [cite_start]**C-02:** Розгортання — Docker-контейнери на VPS. [cite: 8]
* [cite_start]**C-03:** Бюджет: 10 000€ на створення веб-сервісу, до 1000€/рік на інфраструктуру. [cite: 8]
* [cite_start]**C-04:** Дедлайн MVP: 3 місяці від дати підписання контракту. [cite: 8]
* [cite_start]**C-05:** Відповідність GDPR (права користувача на видалення даних). [cite: 8]

### [cite_start]6. ГЛОСАРІЙ (GLOSSARY) [cite: 9]
* [cite_start]**Файл (File):** текстовий документ з заголовком, тілом. [cite: 9]
* [cite_start]**Тег (Tag):** коротке ключове слово для знаходження потрібного файлу. [cite: 9]
* [cite_start]**MVP (Minimum Viable Product):** мінімальна версія продукту з базовою функціональністю. [cite: 9]
* [cite_start]**GDPR:** регуляторний акт ЄС щодо захисту персональних даних. [cite: 9]
* [cite_start]**CRUD:** Create, Read, Update, Delete (базові операції над даними). [cite: 9]

### [cite_start]7. МАТРИЦЯ ВІДСТЕЖУВАНОСТІ (TRACEABILITY MATRIX) [cite: 10]
| ID Вимоги | Зв'язок / Джерело | Метод перевірки (Тест) |
| :--- | :--- | :--- |
| **FR-01** | Питання 2.3 (ролі) | [cite_start]Тест: реєстрація нового email. [cite: 10] |
| **FR-02** | Питання 2.1 (основні дії) | [cite_start]Тест: завантаження файлів та іх обробка. [cite: 10] |
| **FR-04** | Питання 2.2 (бажані функції) | [cite_start]Тест: відстежувати кількість входів на день. [cite: 10] |
| **NFR-P-01** | Питання 3.2 (time-to-response) | [cite_start]JMeter тест 500 users. [cite: 10] |
