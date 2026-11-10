# Словари для LookTomato

Готовые словари для кнопки «Скачать словарь» в программе LookTomato (вкладка «Словари»).
Программа скачивает `catalog.json` из последнего релиза этого репозитория, показывает список и ставит
выбранный архив в один клик, проверяя SHA-256.

| Файл | Язык | Статьи | Источник | Лицензия |
|---|---|---|---|---|
| `wiktionary-XX-ru.zip` | DE, FR, ES, IT, PT, PL | определения на русском | русский Викисловарь (ru.wiktionary.org) | CC BY-SA 4.0 |
| `wiktionary-XX-en.zip` | DE, FR, ES, IT, PT, PL | толкования на английском | английский Викисловарь (en.wiktionary.org) | CC BY-SA 4.0 |
| `jmdict-ja-ru.zip` | японский | значения на русском, чтения | JMdict (EDRDG), формат Yomitan — yomidevs/jmdict-yomitan | CC BY-SA 4.0 |
| `jmdict-ja-en.zip` | японский | значения на английском, чтения | JMdict (EDRDG), формат Yomitan — yomidevs/jmdict-yomitan | CC BY-SA 4.0 |

`jmdict-ja-en.zip` (15 МБ) в этом релизе не лежит: `catalog.json` ссылает на тот же файл в релизе
yomidevs/jmdict-yomitan, закреплённый по дате, с проверкой SHA-256.

Словари Викисловаря — формат StarDict, словоформы (ging → gehen, yeux → œil) в `.syn` из обоих Викисловарей.

## Авторство и лицензии

- **Викисловарь** — авторы Викисловаря, https://www.wiktionary.org. Тексты доступны по лицензии
  [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Данные извлечены проектом
  [wiktextract](https://github.com/tatuylonen/wiktextract) (Tatu Ylonen, https://kaikki.org).
  Изменения: отобраны статьи нужного языка, оставлены значения и словоформы, переведено в формат StarDict.
- **JMdict** — Electronic Dictionary Research and Development Group (EDRDG),
  https://www.edrdg.org/jmdict/j_jmdict.html, лицензия [CC BY-SA 4.0](https://www.edrdg.org/edrdg/licence.html).
  Формат Yomitan — проект [yomidevs/jmdict-yomitan](https://github.com/yomidevs/jmdict-yomitan), без изменений.

Эти архивы распространяются на тех же условиях (CC BY-SA 4.0).

## Как обновить

1. В проекте LookTomato: `powershell -ExecutionPolicy Bypass -File tools\DictBuilder\build-wiktionary.ps1`
   (скачивает свежие выгрузки, собирает словари, пишет `catalog.json` и копирует всё в `Release\dictionaries`).
2. Создайте новый релиз в этом репозитории и прикрепите **все** файлы из `Release\dictionaries`
   (`catalog.json` и `*.zip`). Программа всегда берёт последний релиз.
