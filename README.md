# Overboard! — русский перевод (Nintendo Switch)

Неофициальный фанатский перевод игры [Overboard!](https://www.inklestudios.com/overboard/) от inkle на русский язык для Nintendo Switch.

- Переведён весь текст игры: сюжет, все концовки, меню и настройки, газеты, записная книжка, стихи, титры.
- В шрифты игры добавлена кириллица (включая «», —, №, …).
- Перевод занимает место **испанского** языка — английский остаётся доступен.

> ⚠️ Перевод выполнен с помощью ИИ (Claude) и проверен на целостность логики игры, но **не вычитан носителем языка полностью**. Опечатки и неловкие фразы возможны — пожалуйста, сообщайте о них в [Issues](../../issues).

## Требования

- Nintendo Switch с кастомной прошивкой **Atmosphère** (используется LayeredFS).
- Своя легальная копия Overboard! **с обновлением v262144** (Title ID `01000CA014CA0000`).
- Файл `Data/sharedassets2.assets` из RomFS вашей копии игры (с применённым обновлением).

Патч содержит только изменения — сами файлы игры в репозитории не распространяются.

## Установка

### 1. Достаньте оригинальный файл

Нужен файл `Data/sharedassets2.assets` из RomFS игры **с установленным обновлением v262144**. Способы:

- **nxdumptool** (на самой консоли): выберите Overboard!, откройте просмотр RomFS с применённым обновлением и сохраните `Data/sharedassets2.assets` на SD-карту.
- **Ryujinx** (на ПК, с установленным обновлением): правый клик по игре → *Extract Data* → *RomFS*, файл будет в `Data/`.
- **hactool / hactoolnet** со своими ключами — для опытных пользователей.

Проверьте контрольную сумму исходного файла:

```
SHA-256 (оригинал): de6da9ec8e9f406b95e7ec332dd2a7f1071c218d0128b6566c5f52a231a6d3c3
```

Если сумма не совпадает — скорее всего, у вас другая версия игры, и патч не подойдёт.

### 2. Примените патч

Скачайте `overboard_ru.xdelta` со страницы [Releases](../../releases) и примените любым способом:

- **В браузере:** [Rom Patcher JS](https://www.marcrobledo.com/RomPatcher.js/) — выберите оригинальный файл и патч, нажмите *Apply patch*.
- **Windows:** [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher).
- **Командная строка:**
  ```
  xdelta3 -d -s sharedassets2.assets overboard_ru.xdelta sharedassets2_ru.assets
  ```

Контрольная сумма результата:

```
SHA-256 (после патча): 2c774caeb904aaf50257a1d0cf057fa2f3f71089ef23a00bb9a98552bb798eb1
```

### 3. Скопируйте на SD-карту

Переименуйте результат обратно в `sharedassets2.assets` и положите сюда:

```
SD:/atmosphere/contents/01000CA014CA0000/romfs/Data/sharedassets2.assets
```

### 4. Включите русский

Запустите игру, откройте меню паузы → *Language* и выберите **испанский** (Spanish). Игра переключится на русский.

**Удаление:** удалите папку `SD:/atmosphere/contents/01000CA014CA0000`.

## Технические детали

- Русский текст заменяет испанский сценарий ink (`sp_core`). Логика сюжета не менялась: русская и английская версии прогонялись параллельно в движке ink (80 случайных прохождений, ~4900 выборов) с идентичным результатом.
- Фразы, которые игра собирает из кусочков во время работы (названия локаций, ругательства, время суток и т. п.), переработаны под русскую грамматику. Время показывается в 24-часовом формате, суммы — цифрами.
- Атласы шрифтов TextMeshPro расширены до 1024×1024; оригинальные латинские глифы не тронуты. Шрифты-источники кириллицы — см. [FONTS.md](FONTS.md).

## Отказ от ответственности

Это фанатский проект, не связанный с inkle Ltd. Overboard! © inkle Ltd. Все права на игру принадлежат её авторам. Для использования перевода нужна собственная легально приобретённая копия игры.

---

## English

Unofficial Russian fan translation of inkle's **Overboard!** for Nintendo Switch (Atmosphère LayeredFS). It replaces the **Spanish** language slot, so English stays available, and adds Cyrillic glyphs to the game's fonts. Requires your own copy of the game with **update v262144**.

1. Extract `Data/sharedassets2.assets` from the game's RomFS with the update applied (nxdumptool, Ryujinx *Extract Data → RomFS*, or hactool). SHA-256 must be `de6da9ec…a6d3c3`.
2. Apply `overboard_ru.xdelta` from [Releases](../../releases) (Rom Patcher JS, Delta Patcher, or `xdelta3 -d -s original patch output`). Result SHA-256: `2c774cae…798eb1`.
3. Copy the result to `SD:/atmosphere/contents/01000CA014CA0000/romfs/Data/sharedassets2.assets`.
4. In game, set the language to **Spanish**.

The translation was produced with AI assistance and has not been fully proofread by a native speaker. Corrections are welcome via Issues. Not affiliated with inkle Ltd.
