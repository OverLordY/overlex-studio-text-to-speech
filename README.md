# OverLeX Studio — Text-to-Speech & Pack Builder

**Інструмент автора для створення, озвучування та публікації навчальних пакетів OverLeX**

[Українська](#українська) · [English](#english) · [Deutsch](#deutsch)

[OverLeX.eu](https://overlex.eu/) · [Пакети слів](https://overlex.eu/uk/packs.html) · [OverLeX Desktop](https://github.com/OverLordY/overlex-pc) · [OverLeX Mobile](https://github.com/OverLordY/overlex-mobile) · [Повідомити про проблему](https://github.com/OverLordY/overlex-studio-text-to-speech/issues/new)

## Українська

### Що таке OverLeX Studio?

OverLeX Studio — авторська настільна програма для підготовки мультимовних навчальних пакетів: від таблиці зі словами або фразами та прикладами до озвучених і зашифрованих пакетів для OverLeX Desktop та OverLeX Mobile.

Це не просто озвучування окремого тексту: Studio об'єднує підготовку даних, вибір голосів, пакетну генерацію, перевірку аудіо, складання релізу та інструменти публікації й ліцензування в одному робочому процесі.

### Масштаб і швидкість

За досвідом автора, озвучування пакета на **500 слів або фраз із п’ятьма прикладами на кожну одиницю — загалом 2 500 прикладів речень — може займати орієнтовно 3–5 годин** за відповідної конфігурації та обраних сервісів.

Це орієнтир, а не гарантія: час залежить від провайдерів і тарифних лімітів, кількості голосів, довжини текстів, налаштувань, мережі та необхідності повторної генерації. Він не означає, що підготовка текстів, перевірка якості й публікація завжди входять у цей час.

### Сервіси та моделі синтезу мовлення

Studio підтримує кілька способів озвучування з різними можливостями та вимогами:

| Провайдер / інструмент | Роль у Studio |
| --- | --- |
| **ElevenLabs** | Хмарний TTS через API; налаштування моделі та голосів, зокрема для українських перекладів. |
| **Fish Audio** | Хмарний TTS через API; підтримка вибору голосів і генерації іноземного озвучення. |
| **OpenAI TTS** | Експериментальний хмарний провайдер із вибором доступних голосів. |
| **Kokoro** | Експериментальний варіант синтезу з інструментами перевірки голосів. |
| **XTTS** | Експериментальний синтез із використанням референсних аудіозаписів; потрібна перевірка якості. |
| **Piper** | Експериментальний локальний синтез із голосовими моделями, зокрема німецькою моделлю Thorsten. |

У поточному робочому процесі **ElevenLabs і Fish Audio позначені як основні**, інші провайдери — експериментальні. Для хмарних сервісів потрібні власні доступи та інтернет; для локальних моделей — відповідне встановлення, моделі та ресурси комп’ютера. Доступність мов, голосів і фактична якість залежать від конкретного провайдера та конфігурації.

Один із виробничих сценаріїв розподіляє три іноземні голоси на Fish Audio та український голос перекладу на ElevenLabs. Можливі й інші профілі та ролі, зокрема озвучування всіх ролей через ElevenLabs. Для референсних голосів необхідно мати відповідні права та згоду.

### Підготовка навчальних матеріалів

- Імпорт і перевірка **CSV** зі словами або фразами, формами, перекладами та прикладами речень.
- CSV-шаблон, очищення даних, додавання й об’єднання матеріалів.
- Створення або оновлення пакета зі збереженням вихідних матеріалів.
- Налаштування назви, опису, обкладинки, мов, напрямку перекладу, рівня, категорії, версії та нотаток релізу.
- Розподіл пакетів на безкоштовні демонстраційні й ліцензійні; ідентифікатори пакета та продукту.

### Озвучування та контроль

- Голосові профілі й призначення голосів різним ролям: до трьох іноземних голосів і окремий голос перекладу.
- Генерація аудіо для всього набору, вибраного діапазону або окремих слів.
- Повторна генерація окремих фрагментів: слова, перекладу, форми чи прикладу — коли результат потребує виправлення.
- Покрокова робота з невеликими партіями, зупинка процесу, перегляд стану та журналів.
- Тестування голосів і налаштувань, перевірка доступності TTS-провайдерів та, де підтримується, інформації про використання.
- Перелік наявних аудіофайлів, звіти якості, попередня перевірка генерації та інструменти повторного використання наявного аудіо.
- Інструменти оцінки витрат на TTS для планування роботи.

Синтезоване аудіо потребує прослуховування й перевірки природності, вимови та відповідності перекладів.

### Складання пакета та публікація

- Формування зашифрованого пакета **.langpackx** для екосистеми OverLeX. Відкритий формат .langpack використовується як окремий інструмент розробки.
- Release Checklist для перевірки метаданих, файлу релізу, каталогу, R2 та пов’язаних ліцензійних параметрів.
- Інтеграція з **Cloudflare R2, Pages, Workers і D1** у налаштованому авторському середовищі.
- Завантаження та оновлення каталогу, зокрема multipart-завантаження великих файлів за наявності потрібних R2 S3 credentials.
- Реєстр продуктів, перевірка Product ID, синхронізація ключів і реєстрація продуктів у production.
- Ручна видача та керування ліцензіями, додавання продуктів до ліцензії та окреме надсилання/повторне надсилання листа користувачу.

Ці адміністративні функції потребують налаштованих сервісів і відповідних прав доступу. Секретні ключі, токени та особисті дані не належать до публічного репозиторію.

### Як виглядає робочий процес

1. Підготувати CSV зі словами або фразами, перекладами та прикладами.
2. Перевірити дані, створити пакет і задати його метадані.
3. Обрати TTS-провайдерів, голоси, ролі та параметри генерації.
4. Згенерувати аудіо, перевірити результати й за потреби переозвучити окремі фрагменти.
5. Зібрати .langpackx, пройти Release Checklist і опублікувати пакет.
6. Для ліцензійних пакетів налаштувати продукт та за потреби видати доступ користувачу.

### Приклади результатів

Навчальні пакети, створені для екосистеми OverLeX, можна переглянути в [каталозі на OverLeX.eu](https://overlex.eu/uk/packs.html). Для їх використання доступні [OverLeX Desktop](https://github.com/OverLordY/overlex-pc) та [OverLeX Mobile](https://github.com/OverLordY/overlex-mobile).

### Повідомлення про помилки

[Створити Issue](https://github.com/OverLordY/overlex-studio-text-to-speech/issues/new) або зв’язатися з автором через [контакти OverLeX](https://overlex.eu/uk/contact.html). Опишіть проблему, кроки відтворення та очікуваний результат. **Не публікуйте API-ключі, токени, License ID, ліцензійні e-mail або приватні файли.**

## English

OverLeX Studio is an author's desktop toolkit for creating multilingual audio learning packs for OverLeX. It combines CSV preparation, text-to-speech generation, audio checks, encrypted .langpackx packaging, release verification, publication and license administration.

The current workflow designates **ElevenLabs and Fish Audio** as production TTS providers, with **OpenAI, Kokoro, XTTS and Piper** available as experimental options. Provider accounts, installation, language coverage and quality depend on the selected setup. One workflow assigns three foreign-language voices to Fish Audio and a Ukrainian translation voice to ElevenLabs.

Based on the author's experience, voicing a 500-entry pack with five examples per entry (2,500 sentences) can take approximately **3–5 hours** under suitable conditions. Actual time varies with providers, limits, voice roles, text length, network, settings and regeneration; text preparation and quality review are not necessarily included.

[OverLeX website](https://overlex.eu/en/) · [Word packs](https://overlex.eu/en/packs.html) · [Report an issue](https://github.com/OverLordY/overlex-studio-text-to-speech/issues/new)

## Deutsch

OverLeX Studio ist ein Desktop-Werkzeug des Autors zur Erstellung mehrsprachiger Audio-Lernpakete für OverLeX. Es verbindet CSV-Vorbereitung, Sprachsynthese, Audioprüfung, verschlüsselte .langpackx-Pakete, Release-Prüfung, Veröffentlichung und Lizenzverwaltung.

Im aktuellen Arbeitsablauf sind **ElevenLabs und Fish Audio** als produktive TTS-Anbieter vorgesehen; **OpenAI, Kokoro, XTTS und Piper** sind experimentelle Optionen. Konten, Installation, Sprachabdeckung und Qualität hängen von der jeweiligen Konfiguration ab. Ein Arbeitsablauf verwendet drei fremdsprachige Stimmen von Fish Audio und eine ukrainische Übersetzungsstimme von ElevenLabs.

Nach Erfahrung des Autors kann die Vertonung eines Pakets mit 500 Einträgen und fünf Beispielen je Eintrag (2.500 Sätze) unter passenden Bedingungen ungefähr **3–5 Stunden** dauern. Die tatsächliche Zeit hängt unter anderem von Anbietern, Limits, Stimmen, Textlänge, Netzwerk, Einstellungen und erneuter Generierung ab; Textvorbereitung und Qualitätskontrolle sind nicht zwangsläufig enthalten.

[OverLeX-Website](https://overlex.eu/de/) · [Wortpakete](https://overlex.eu/de/packs.html) · [Fehler melden](https://github.com/OverLordY/overlex-studio-text-to-speech/issues/new)

## Source code and availability

This repository is a public project overview and support page. **The Studio source code, executable, API credentials, private keys and customer data are not published here.** Studio is an author's tool; this page does not imply a public download or grant a software license.
