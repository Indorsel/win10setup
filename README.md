Краткое содержание:
- ["Оптимизация" системы](#оптимизация-системы)
- [Выставление на минимум телеметрии через групповые политики](#выставление-на-минимум-телеметрии-через-групповые-политики)
- [Удаление Onedrive](#удаление-onedrive) 
- [Установка/обновление драйверов](#установкаобновление-драйверов)
- [Полная очистка диска перед установкой системы](#полная-очистка-диска-перед-установкой-системы)
---
- [Активация](#активация)
- [Скачать](#скачать)
- [Создание загрузочного образа](#создание-загрузочного-образа)
---
- [Полезное](#полезное)
- [ПО по вкусу](#по-по-вкусу)
- [Microsoft Office](#microsoft-office)
---
- [Установка Windows 10](#установка-windows-10)

## FAQ

### "Оптимизация" системы
Развлекайся, шизик:

Это на уже установленную систему:
- [privatezilla](https://github.com/builtbybel/privatezilla)
- [privacy.sexy](https://privacy.sexy)

### Выставление на минимум телеметрии через групповые политики
> [!WARNING]  
>  Это работает на всех редакциях кроме домашней. 

1. Нажми клавиши Win+R на клавиатуре и введи gpedit.msc

В открывшемся редакторе локальной групповой политики переходи к разделу:
- "Конфигурация компьютера" - "Административные шаблоны" - "Компоненты Windows" - "Сборки для сбора данных и предварительные сборки"

- [x] Включаем пункт "Разрешить телеметрию" и выставляем параметр на 0.

### Удаление Onedrive
1. Открываем командную строку от имени администратора и вставляем:
- [x] [Onedrive.bat](https://gist.githubusercontent.com/shapkodebil/3e36aeba6d87b919d51e55c00b7a535d/raw/395734b8169f7ddd338aacc788764d259a0e7e19/Onedrive.bat)

### Установка/обновление драйверов
- Центр обновлений
- Сайт производителя материнки/ноутбука
- [SDI Origin](https://www.glenn.delahoy.com/snappy-driver-installer-origin/)
> [!NOTE]
>  Для `SDI Origin` **нет необходимости скачивать весь пакет драйверов**, скачиваем только "Установщик драйверов Snappy, исходная версия x.xx.xx" и при запуске появится возможность скачать только те драйвера которые необходимы для вашей системе.

> [!NOTE]  
> Не путать [SDI Origin](https://sourceforge.net/projects/snappy-driver-installer-origin/) с sdi-tool.

### Полная очистка диска перед установкой системы
На экране начальной установки сразу после загрузки с флешки нажимаешь "Восстановление системы", ищи "Командная строка".
Вводим:
```winbatch
diskpart
list disk
select disk %номер_диска_где_хотим_всё_удалить%
clean
convert gpt/mbr
```

Если нужно удалить только раздел:

`1 - 2 - 3` сверху
```winbatch
list partition
delete partition %номер_раздела_который_хотим_удалить%
```
Перезапуск с флэшки и устанавливаешь всё как обычно.

---

## Активация

### KMS_VL_ALL (by abbodi1406)
Активирует все версии (volume) виндовс с 7 до 10:
	- Windows 8 / 8.1 / 10 (Все официальные издания , кроме Windows 10 S)
	- Windows 7 (Корпоративная /N/E, Профессиональная /N/E, Embedded Standard/POSReady/ThinPC)
	- Windows Server 2008 R2 / 2012 / 2012 R2 / 2016 / 2019
	- Office Volume 2010 / 2013 / 2016 / 2019

Не используется интернет, планировщик задач, сервисы, серверы или драйвера. Код полностью открытый, ссылки находятся в readme.html в архиве полной версии. Работает на всех редакциях, которые можно активировать с помощью KMS. Вы можете активировать только Office с помощью KMS. Можно интегрировать и то, и другое, если требуется HWID для Windows и активация для Office, или использовать KMS для всего.  
:warning:  `Обязательно добавьте архив в исключения антивируса или временно отключите его`. 

**`Нажимаешь 2, и скрипт создаст задачу, которая будет обновлять активацию каждые 180 дней. После этого дополнительных действий с твоей стороны больше не потребуется.`**

> [!NOTE]  
> **[KMS_VL_ALL_AIO](https://github.com/abbodi1406/KMS_VL_ALL_AIO) - ПАРОЛЬ: "`2023`"**

> [!NOTE]  
> **Бэкап ссылки: [1](https://yzyveojj6tqzqwe5muzglg.on.drv.tw/KVA/ReadMe36.html),[2](https://forums.mydigitallife.net/posts/838808/),[3](https://pastebin.com/cpdmr6HZ),[4](https://textuploader.com/1dav8?__cf_chl_f_tk=xv7P1o994cZm7_6NCeyYTJ5MzaenzWHwTZZGjRKbj3c-1658049006-0-gaNycGzNB-U) - [Сурцы](https://yzyveojj6tqzqwe5muzglg.on.drv.tw/KVA/ReadMe36.html#Source)**

---

## Ссылки

### Скачать
- [Официальный сайт](https://www.microsoft.com/ru-ru/software-download/windows10/). Для скачивания ISO прямо с сайта нужно указать любой UA, кроме Windows:
	- Запускаем любой хром по вкусу
	- F12
	- CTRL+ SHIFT + M (Toggle device toolbar)
	- Смотришь вверх "Dimensions:" выбираешь любой
	- Перезагрузить вкладку
	- На самой страничке "выбрать выпуск"
	- "Windows 10 (multi-edition ISO)" и подтвердить

Чуть ниже находится Media creation tool (средство установки).
Если с Media Creation Tool на Windows 7 выдаёт ошибку `0x80072f8f-0x20000` то это значит что [протоколы TLS 1.1/TLS 1.2 не поддерживаются](https://support.microsoft.com/en-us/topic/update-to-enable-tls-1-1-and-tls-1-2-as-default-secure-protocols-in-winhttp-in-windows-c4bd73d2-31d7-761e-0178-11268bb10392#bkmk_easy) их можно включить с помощью официальной [утилитой от майкрософт](https://download.microsoft.com/download/0/6/5/0658B1A7-6D2E-474F-BC2C-D69E5B9E9A68/MicrosoftEasyFix51044.msi).

- [Оригинальные образы Windows MSDN *NNM-Club*](https://nnmclub.to/forum/viewforum.php?f=504/). **ОБРАЗЫ ЛТСЦ СРАЗУ СНИЗУ**
- [Оригинальные образы Windows MSDN *Rutracker*](https://rutracker.org/forum/tracker.php?f=2489&nm=Windows+10).
- Оригинальные образы Windows MSDN *Rustorka*:
	- [22H2](https://rustorka.com/forum/viewtopic.php?t=284231)
	- [21H2 LTSC](https://rustorka.com/forum/viewtopic.php?t=272933)
- [Rg-adguard](https://files.rg-adguard.net/version/f0bd8307-d897-ef77-dbd6-216fefbe94c5). Прямые ссылки с сайта Microsoft.com. Любая виндовс и офис.
	- [Windows 10, version 22H2 (Updated Jan 2023)](https://files.rg-adguard.net/language/2035a908-5306-b748-0b90-cf987ca2dbae)
Ждём пока вся платформа пропердится да и собственно сиды были.

### Создание загрузочного образа
- [Rufus](https://rufus.ie/): (свободное ПО) самый простой и удобный способ.
	- Выбираешь схему раздела MBR для старых компьютеров без UEFI и GPT для новых. Можно нажать Alt+E, и флешка подойдет для обоих случаев, что удобно при установке на разные компьютеры. Однако будь осторожен и не устанавливай Windows в режиме Legacy на современном компьютере. Убедись, что в BIOS установлен режим UEFI Only.
- [Ventoy](https://github.com/ventoy/Ventoy): Тебе не нужно повторно форматировать диск, просто скопируй образы на USB-накопитель и загрузись с него.

### Полезное
>Всё на ваше усмотрение. Я добавляю ссылки, которые касаются операционной системы Windows. Если захотите, можете почитать и узнать об этом. Если нет, вы смело можете пройти мимо - ваша система будет работать как и прежде.

Основные компоненты при новой установки виндовс:
- [Visual C++](https://github.com/abbodi1406/vcredist)
- [.NET Framework 4.8.1](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net481-offline-installer)
- [DirectX End-User Runtimes (June 2010)](https://www.microsoft.com/en-us/download/confirmation.aspx?id=8109)
---
- [Windows Terminal](https://github.com/microsoft/terminal/releases)
- [EarTrumpet](https://apps.microsoft.com/detail/eartrumpet/9NBLGGH516XP?cid=eartrumpet.landing&hl=ru-ru&gl=US)

---

### ПО по вкусу
>[Пик с софтом](https://s1.desu-usergeneratedcontent.xyz/g/image/1562/46/1562467997749.png)

**Браузер:**
[Firefox](https://ftp.mozilla.org/pub/firefox/releases/) `10x.x.x\` - [Ungoogled Chromium](https://ungoogled-software.github.io/ungoogled-chromium-binaries/releases/windows/64bit/)

**Текстовый редактор:**
[Notepad++](https://notepad-plus-plus.org/downloads/)

**Торрент-клиент:**
[qBittorent](https://www.qbittorrent.org/download.php)

**Просмотр изображений:**
[nomacs](https://github.com/nomacs/nomacs) - [jpegview](https://github.com/sylikc/jpegview)

**Графический редактор:**
[Paint.NET](https://paintnet.ru/download/)

**Видео-Конвертер:**
[FFmpeg](https://ffmpeg.org/download.html#build-windows) - [Handbrake](https://handbrake.fr/downloads.php)

**Видеоплееры:**
[MPC-HC](https://github.com/clsid2/mpc-hc/releases)

**Музыкальный Проигрыватель:**
[Aimp](https://www.aimp.ru/?do=download)

**Запись Экрана:**
[OBS](https://obsproject.com/ru/download)

**Управление файлами**
[7zip](https://www.7-zip.org/download.html) - [fman](https://fman.io/download)

**Просмотр PDF:**
[SumatraPDF](https://www.sumatrapdfreader.org/download-free-pdf-viewer)

**Клинер:**
[Bleachbit](https://www.bleachbit.org/download/windows)

**Общение:**
[Discord](https://discord.com/download)


### Microsoft Office
1. [tb.rg-adguard.net](https://tb.rg-adguard.net/public.php)
	- Новый домен как актуальная альтернатива -> [files.rg-adguard.net](https://files.rg-adguard.net/version/5f2ad9c6-e111-76e8-06d1-56d44c136bae) - (Ищем `"Office"`), так как `tb.rg-adguard.net` в будущем не будет больше поддерживатся.

2. Выбираешь:
	- Microsoft Office
	- Microsoft Office 2021
	- Office 2021 Professional Plus
	- %язык_который_нужен%
	- %единственное_имя_файла.img%
3. Двойной клик по файлу и потом setup.exe
4. Пусть закончит установку
5. Активация `только` с [**KMS_VL_ALL**](#kms_vl_all-by-abbodi1406) нажимаем `2`

---

## Установка Windows 10

> [!NOTE]  
> [windows_for_retards](https://rentry.co/windows_for_retards)
### Что будет нужно
- Интернет
- Система хотя бы на семёрке для создания образа
- Флешка на хотя бы 8 гигов
- [Торрент клиент](https://www.qbittorrent.org/download.php)
- Комп с поддержкой UEFI
### Скачиваем виндовс
1. Открываешь [ru-ru_windows_10](https://nnmclub.to/forum/viewtopic.php?t=1662987)
2. Жмёшь на магнит
3. Скачиваешь только  `ru-ru_windows_10_business_editions_version_22h2_updated_sep_2023_x64_dvd_3e14a3b2.iso` 
### Скачиваешь Ventoy
1. Открываешь [Ventoy](https://github.com/ventoy/Ventoy/releases)
2. Скачиваешь `"ventoy-1.0.XX-windows.zip"`
3. Распаковываешь в любое удобное для тебя место (Распаковать можно например с [7zip](https://www.7-zip.org/download.html))
### Запись образа на флешку
1. Вставляешь флешку
2. Открываешь `"Ventoy2Disk.exe"`
3. `"Устройство"` выбираешь свою флешку
4. Нажимаешь "Установить"
5. Когда установка закончится просто перетягиваем наш образ `.iso` на нашу флешку с названием `"Ventoy"` (Например `(E:) Ventoy`)
### Загрузка с флешки для дальнейший установки
- [x] Берёшь гуглишь как на твоей **марке ноутбука/материнки** запуститься с флешки(в основном ищешь какую **кнопку** жать при запуске компа)
> [!NOTE]  
> Может быть что угодно `"Del" - "F2" - "F8"` и т.д.

---

### Сама установка
1. `"Устанавливаемый язык"`
2. `"Формат времени и денежных единиц"`
3. `"Метод ввода"`
4. **"Ключ продукта":**
	- [x] **`"У меня нет ключа продукта" `**
5. **"Выберите ос, которую вы хотите установить"**
	- [x] **`Windows 10 для образовательных учреждений`**
6. **"Условия лицензии"**
	- [x] **`Я принимаю условия лицензии`**
7. **"Выберите тип установки"**
	- [x] **`Выборочная`**
8. **"Где вы хотите установить Windows?":**
	- [x] Выбираем `Незанятое пространство`, или `удаляем старый раздел`. Если выбрать раздел со старой виндовс, она переместится в папку **Windows.old** со всеми файлами. Хочешь удалить [всё](https://github.com/shapkodebil/win10thread#хочу-перед-установкой-виндовс-очистить-диск-от-всего-и-ещё-поменять-структуру-раздела) то бы наверняка?
> [!NOTE]  
> **Ждёшь окончание установки.**

---

### Конфигурация (OOBE)
> [!IMPORTANT]  
> **Очень рекомендую отключить нахуй интернет (кабель и т.п.) во время всего процесса установки что бы избежать проблем с доёбыванием майкрософта с аккаунтом и разными обновлениями (особенно драйверами видеокарты) и собственно *телеметрий*(если это вас ебёт), включайте обратно когда уверенны что система сконфигурирована правильно и по вашему вкусу или надо активировать через HWID.**
1. Выбери - Регион и раскладку
2. "Давайте подключим вас к сети":
	- [x] **`"У меня нет Интернета"`**
	- [x] **`"Продолжить ограниченную установку"`**
3. Выбери - имя пользователя
4. "Выберите параметры конфиденциальности для этого устройства":
	- [x] Отключить нахуй "Диагностические данные" - "Реклама" всё остальное на своё усмотрение 

---

### Активация самой виндовс
1. Скачиваешь [**KMS_VL_ALL**](#kms_vl_all-by-abbodi1406)
2. Скачиваешь архиватор [7zip](https://www.7-zip.org/download.html)
3. Отключаешь на время и разрешаешь архив/exe активатора в **антивирусе** (Microsoft Defender)
4. "Запустить от имени администратора"
5. Нажимаешь 2
