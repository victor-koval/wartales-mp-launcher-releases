# Wartales-MP Launcher

**Українською** · [English](#english)

Лаунчер і інсталятор кооперативного мода [wartales-mp](https://github.com/UberMorgott/Wartales-Mod-wartales-mp) для Wartales.

> Неофіційний проєкт. Не пов'язаний із Shiro Games чи автором мода.

## Завантажити

Остання версія — на сторінці [Releases](https://github.com/victor-koval/wartales-mp-launcher-releases/releases/latest): файл `WartalesMP-Launcher.exe`.
Запускайте з будь-якої теки, встановлення не потрібне. Далі лаунчер оновлюється сам.

Потрібен .NET Framework 4.5+ — він уже є у Windows 10 і 11.

## Що вміє

- Запуск гри через Steam, показує, з якою версією мода вона стартує.
- Встановлення, оновлення, відкат і видалення мода з перевіркою SHA256; нову версію мода ставить сам.
- Резервна копія збережень перед кожним встановленням мода; вікно «Копии сохранений» для відновлення.
- «Остаться на этой версии» — якщо компанія домовилась грати на одній версії мода.
- Попереджає про версії, які автор мода просить не використовувати, і про оновлення гри після встановлення мода.

Інтерфейс лаунчера — російською, англійська — на вибір у «Настройках» («Язык · Language»).

## Попередження Windows SmartScreen

Файл не має цифрового підпису, тому під час першого запуску Windows може показати «ОС Windows захистила цей ПК».
Натисніть «Докладніше» → «Виконати все одно».

Перевірити, що файл не змінено: у PowerShell виконайте

```powershell
Get-FileHash .\WartalesMP-Launcher.exe
```

і порівняйте результат із SHA256 в описі релізу.

## Steam Deck і Linux

Лаунчер працює лише у Windows. На Steam Deck, SteamOS і Linux (Proton) мод ставиться вручну —
за інструкцією автора в [README мода](https://github.com/UberMorgott/Wartales-Mod-wartales-mp#readme). Коротко:

1. Завантажте `winmm.dll` потрібної версії зі сторінки [релізів мода](https://github.com/UberMorgott/Wartales-Mod-wartales-mp/releases).
   Версія має бути **однаковою в усіх гравців** — і тих, хто на Windows з лаунчером, теж.
2. Перевірте файл: `sha256sum winmm.dll` у терміналі має збігтися з SHA256 у релізі мода.
3. Покладіть `winmm.dll` у теку гри поруч із `Wartales.exe` (Steam → Wartales → «Керування» → «Переглянути локальні файли»).
4. У Proton гра за замовчуванням бере вбудовану `winmm.dll`, і мод не запускається. Тому в Steam: правою кнопкою по Wartales →
   «Властивості» → «Загальні» → «Параметри запуску» — і введіть:

   ```
   WINEDLLOVERRIDES="winmm=n,b" %command%
   ```

5. Перед кожним оновленням мода скопіюйте теку `save` з теки гри — у Windows цю копію робить лаунчер.

Оновлюється мод так само: закрийте гру й покладіть новий `winmm.dll` на місце старого. Щоб вимкнути мод, приберіть параметр запуску
або видаліть `winmm.dll`. Гравці на Proton можуть грати разом із гравцями на Windows.

---

<a id="english"></a>

## English

Launcher and installer for the [wartales-mp](https://github.com/UberMorgott/Wartales-Mod-wartales-mp) co-op mod for Wartales.

> Unofficial project. Not affiliated with Shiro Games or the mod author.

### Download

The latest version is on the [Releases](https://github.com/victor-koval/wartales-mp-launcher-releases/releases/latest) page: `WartalesMP-Launcher.exe`.
Run it from any folder, no installation needed. After that the launcher updates itself.

Requires .NET Framework 4.5+ — it is already included in Windows 10 and 11.

### Features

- Launches the game through Steam and shows which mod version it starts with.
- Installs, updates, rolls back and removes the mod with SHA256 verification; installs new mod versions by itself.
- Backs up your saves before every mod install; the “Save backups” window restores them.
- “Stay on this version” — when your group agreed to play on one mod version.
- Warns about versions the mod author asks not to use, and about game updates after the mod was installed.

The interface is in Russian by default; English can be chosen in Settings (“Язык · Language”).

### Windows SmartScreen warning

The file has no digital signature, so on first launch Windows may show “Windows protected your PC”.
Click “More info” → “Run anyway”.

To check that the file is unchanged, run in PowerShell

```powershell
Get-FileHash .\WartalesMP-Launcher.exe
```

and compare the result with the SHA256 in the release notes.

### Steam Deck and Linux

The launcher only works on Windows. On Steam Deck, SteamOS and Linux (Proton) the mod is installed manually —
following the author's instructions in the [mod README](https://github.com/UberMorgott/Wartales-Mod-wartales-mp#readme). In short:

1. Download `winmm.dll` of the right version from the [mod releases](https://github.com/UberMorgott/Wartales-Mod-wartales-mp/releases).
   The version must be **the same for all players** — including those on Windows with the launcher.
2. Check the file: `sha256sum winmm.dll` in a terminal must match the SHA256 in the mod release.
3. Put `winmm.dll` into the game folder next to `Wartales.exe` (Steam → Wartales → “Manage” → “Browse local files”).
4. Under Proton the game uses its built-in `winmm.dll` by default, and the mod does not start. So in Steam: right-click Wartales →
   “Properties” → “General” → “Launch options” — and enter:

   ```
   WINEDLLOVERRIDES="winmm=n,b" %command%
   ```

5. Before every mod update, copy the `save` folder from the game folder — on Windows the launcher makes this backup.

Updating works the same way: close the game and put the new `winmm.dll` in place of the old one. To disable the mod, remove the launch option
or delete `winmm.dll`. Proton players can play together with Windows players.
