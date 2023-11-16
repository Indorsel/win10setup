Краткое содержание:
- [Хочу "оптимизировать" мою систему](#хочу-оптимизировать-мою-систему)
- [Хочу выставить на минимум телеметрию через групповые политики](#хочу-выставить-на-минимум-телеметрию-через-групповые-политики)
- [Хочу удалить 'Onedrive'](#хочу-удалить-onedrive) 
- [Хочу поставить/обновить драйвера системы](#хочу-поставитьобновить-драйвера-системы)
- [Хочу перед установкой виндовс очистить диск от всего и ещё поменять структуру раздела](#хочу-перед-установкой-виндовс-очистить-диск-от-всего-и-ещё-поменять-структуру-раздела)
- [Хочу иметь журнал буфера обмена](#хочу-иметь-журнал-буфера-обмена)
---
- [ОФИС ОФИС ОФИС ХАЧУ ЫЫЫЫЫЫ СРЕНЬК ПУУУУУУК](#microsoft-office)
---
- [Активация](#активация)
- [Скачать](#скачать)
- [Дампы хешей](#дампы-хешей)
- [Как создать загрузочный образ?](#как-создать-загрузочный-образ)
---
- [Полезное](#полезное)
- [ПО по вкусу](#по-по-вкусу)
---
- [Установка Windows 10](#установка-windows-10)

## FAQ

### Хочу "оптимизировать" мою систему
Развлекайся, шизик:

Это на уже установленную систему:
- [privatezilla](https://github.com/builtbybel/privatezilla)
- [privacy.sexy](https://privacy.sexy)

### Хочу выставить на минимум телеметрию через групповые политики
> [!WARNING]  
>  Это работает на всех редакциях кроме домашней. 

1. Нажми клавиши Win+R на клавиатуре и введи gpedit.msc

В открывшемся редакторе локальной групповой политики переходи к разделу:
- "Конфигурация компьютера" - "Административные шаблоны" - "Компоненты Windows" - "Сборки для сбора данных и предварительные сборки"

- [x] Включаем пункт "Разрешить телеметрию" и выставляем параметр на 0.

### Хочу удалить 'Onedrive'
1. Открываем командную строку от имени администратора и вставляем:
- [x] [Onedrive.bat](https://gist.githubusercontent.com/shapkodebil/3e36aeba6d87b919d51e55c00b7a535d/raw/395734b8169f7ddd338aacc788764d259a0e7e19/Onedrive.bat)

### Хочу поставить/обновить драйвера системы
- Центр обновлений
- Сайт производителя материнки/ноутбука
- [SDI Origin](https://www.glenn.delahoy.com/snappy-driver-installer-origin/)
> [!NOTE]
>  Для `SDI Origin` **нет необходимости скачивать весь пакет драйверов**, скачиваем только "Установщик драйверов Snappy, исходная версия x.xx.xx" и при запуске появится возможность скачать только те драйвера которые необходимы для вашей системе.

> [!NOTE]  
> Не путать [SDI Origin](https://sourceforge.net/projects/snappy-driver-installer-origin/) с sdi-tool.

### Хочу перед установкой виндовс очистить диск от всего и ещё поменять структуру раздела
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

### Хочу иметь журнал буфера обмена
- [x] Комбинация `"Win+V"`

![](img/cvbuffer.png)

---


## Microsoft Office
1. [tb.rg-adguard.net](https://tb.rg-adguard.net/public.php)
	- Новый домен как актуальная альтернатива -> [files.rg-adguard.net](https://files.rg-adguard.net/version/5f2ad9c6-e111-76e8-06d1-56d44c136bae) - (Ищем `"Office"`), так как `tb.rg-adguard.net` в будущем не будет больше поддерживатся.

3. Выбираешь:
- Microsoft Office
- Microsoft Office 2021
- Office 2021 Professional Plus
- %язык_который_нужен%
- %единственное_имя_файла.img%
3. Двойной клик по файлу и потом setup.exe
4. Пусть закончит установку
5. Активация `только` с [**KMS_VL_ALL**](#kms_vl_all-by-abbodi1406) нажимаем `2`

![](img/adguardoffice.png)

---


## Активация

### KMS_VL_ALL (by abbodi1406)
Активирует все версии (volume) виндовс с 7 до 10:

  -  Windows 8 / 8.1 / 10 (Все официальные издания , кроме Windows 10 S)
  - Windows 7 (Корпоративная /N/E, Профессиональная /N/E, Embedded Standard/POSReady/ThinPC)
  - Windows Server 2008 R2 / 2012 / 2012 R2 / 2016 / 2019
  - Office Volume 2010 / 2013 / 2016 / 2019

Не используется интернет, планировщик задач, сервисы, серверы или драйвера. Код полностью открытый, ссылки находятся в readme.html в архиве полной версии. Работает на всех редакциях, которые можно активировать с помощью KMS. Вы можете активировать только Office с помощью KMS. Можно интегрировать и то, и другое, если требуется HWID для Windows и активация для Office, или использовать KMS для всего.  
:warning:  `Обязательно добавьте архив в исключения антивируса или временно отключите его`. 

![](img/kmsvlall.png)

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

---

Чуть ниже находится Media creation tool (средство установки).
Если с Media Creation Tool на Windows 7 выдаёт ошибку `0x80072f8f-0x20000` то это значит что [протоколы TLS 1.1/TLS 1.2 не поддерживаются](https://support.microsoft.com/en-us/topic/update-to-enable-tls-1-1-and-tls-1-2-as-default-secure-protocols-in-winhttp-in-windows-c4bd73d2-31d7-761e-0178-11268bb10392#bkmk_easy) их можно включить с помощью официальной [утилитой от майкрософт](https://download.microsoft.com/download/0/6/5/0658B1A7-6D2E-474F-BC2C-D69E5B9E9A68/MicrosoftEasyFix51044.msi).

---

- [Оригинальные образы Windows MSDN *NNM-Club*](https://nnmclub.to/forum/viewforum.php?f=504/).
 **ОБРАЗЫ ЛТСЦ СРАЗУ СНИЗУ**
- [Оригинальные образы Windows MSDN *Rutracker*](https://rutracker.org/forum/tracker.php?f=2489&nm=Windows+10).
- Оригинальные образы Windows MSDN *Rustorka*:
	- [22H2](https://rustorka.com/forum/viewtopic.php?t=284231)
	- [21H2 LTSC](https://rustorka.com/forum/viewtopic.php?t=272933)

---

- [Rg-adguard](https://files.rg-adguard.net/version/f0bd8307-d897-ef77-dbd6-216fefbe94c5). Прямые ссылки с сайта Microsoft.com. Любая виндовс и офис.
	- [Windows 10, version 22H2 (Updated Jan 2023)](https://files.rg-adguard.net/language/2035a908-5306-b748-0b90-cf987ca2dbae)
Ждём пока вся платформа пропердится да и собственно сиды были.


> [!WARNING]  
> `Всегда сверяй с дампами хешей`




## Дампы хешей

- [MVS dump](https://awuctl.github.io/mvs/)
	- **Нажимаем на "Select products" и вводим, к примеру, "Windows 10 22H2". Затем нажимаем клавишу Enter, чтобы выбрать нужную версию. Переходим к разделу "Generate summary files" и просто нажимаем "Generate". Теперь мы можем скачать файл со всеми хэшами.**

- [sha1.rg-adguard](https://sha1.rg-adguard.net/)

- [myvsdump](https://heidoc.net/php/myvsdump.php)




## Как создать загрузочный образ?

- [Rufus](https://rufus.ie/): (свободное ПО) самый простой и удобный способ.
	- Выбираешь схему раздела MBR для старых компьютеров без UEFI и GPT для новых. Можно нажать Alt+E, и флешка подойдет для обоих случаев, что удобно при установке на разные компьютеры. Однако будь осторожен и не устанавливай Windows в режиме Legacy на современном компьютере. Убедись, что в BIOS установлен режим UEFI Only.

- [Ventoy](https://github.com/ventoy/Ventoy): Тебе не нужно повторно форматировать диск, просто скопируй образы на USB-накопитель и загрузись с него.




## Полезное
>Всё на ваше усмотрение. Я добавляю ссылки, которые касаются операционной системы Windows. Если захотите, можете почитать и узнать об этом. Если нет, вы смело можете пройти мимо - ваша система будет работать как и прежде.
Основные компоненты при новой установки виндовс:

- [Visual C++](https://github.com/abbodi1406/vcredist)
- [.NET Framework 4.8.1](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net481-offline-installer)
- [DirectX End-User Runtimes (June 2010)](https://www.microsoft.com/en-us/download/confirmation.aspx?id=8109)

---

- [GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI) - Для разблокировки сайтов без VPN и прокси, можно установить как службу.
- [Deployment Tools](https://docs.microsoft.com/en-us/windows/deployment/windows-deployment-scenarios-and-tools)
- [Старый гайд для optimize-offline](https://rentry.co/mdl-optimize-guide)
- [Групповые политики для домашний версий](https://github.com/Fleex255/PolicyPlus)
- [Возможность скачивания приложений стора без стора, устанавливать через повершелл](https://store.rg-adguard.net/)
- [Powertoys](https://github.com/microsoft/PowerToys/releases)
- [Windows Terminal](https://github.com/microsoft/terminal/releases)
- [Icaros](https://shark007.net/forum/Thread-New-Release-3-3-0-RC-1?pid=689#pid689), [2](https://github.com/Xanashi/Icaros/releases)
Для эскизов `.webm` файлов
- [Office Retail-to-Volume](https://github.com/abbodi1406/C2R-R2V-AIO/blob/master/C2R-R2V-AIO.cmd)
- [Мануал с GHacks по переносу лицензии с до-десяток на десятку](https://www-ghacks-net.translate.goog/2015/08/30/how-to-clean-install-windows-10-directly-without-upgrade/?_x_tr_sl=auto&_x_tr_tl=ru&_x_tr_hl=ru)
- [AMD Chipset](https://www.amd.com/en/support)
- [Недооптимизатор WinAero Tweaker](https://winaero.com/downloads/winaerotweaker.zip)

Образы, ключи и скрипты:
- [Дамп разных ключей(возможно не работают)](https://jike.info/topic/2631/win-10-rtm-professional-retail-oem-mak?lang=en-US&page=1)
- [Много очень полезных скриптов от abbodi1406](https://github.com/abbodi1406/BatUtil)
- [BloatRemover(твикер) на свой страх и риск особо не рекомендую](https://github.com/Fs00/Win10BloatRemover)
- [Разная информация об образов и т.к](https://massgrave.dev/readme-genuine-installation-media.html)

Старый стиль win7:
- [Старый калькулятор](https://winaero.com/get-calculator-from-windows-8-and-windows-7-in-windows-10/)
- [Open-Shell(Старый Пуск)](https://github.com/Open-Shell/Open-Shell-Menu)
- [Старый микшер](https://vynesimozg.com/kak-vernut-staryj-regulyator-gromkosti-v-windows-10/)
- [Старое средство просмотра фотографий](https://remontka.pro/photo-viewer-windows-10/)
- [OldNewExplorer Разные допольнительные настройки для проводника](https://www.majorgeeks.com/files/details/oldnewexplorer.html)

Обновления:
- [Пакеты обновлений](https://support.microsoft.com/en-us/topic/windows-10-update-history-857b8ccb-71e4-49e5-b3f6-7073197d98fb)
- [Пакеты безопасности для корректного установление пакетов обновления ](https://msrc.microsoft.com/en-us/security-guidance/advisory/ADV990001)
- [WHDownloader](https://forums.mydigitallife.net/threads/whdownloader-download.66243/), [2](https://www.mediafire.com/file/ootxxrbhw73wt4h/WHDownloader_0.0.2.4.zip/file), [3](https://drive.google.com/file/d/1hIZbPDjK4sTADQ0oFdEsAa7MRC-hQbAC/view?usp=sharing)
- [Утилита для загрузки обновлений вручную "WSUS offline"](https://gitlab.com/wsusoffline/wsusoffline)

Разное для лтсц:
- [Стор на лтсц нужен аккаунт](https://forums.mydigitallife.net/threads/guide-add-store-to-windows-10-enterprises-sku-ltsb-ltsc.70741/)
- [Стор на лтсц не обновлённый](https://github.com/kkkgo/LTSC-Add-MicrosoftStore)
- [Конвертация LTSC Evaluation на LTSC](https://github.com/victorlish/Convert_to_Windows_10_LTSC)

Office 2010 и прочее:
- [Office 2010](https://archive.org/details/MSO2010), [2](https://forums.mydigitallife.net/threads/office-2010-professional-plus-sp1-iso-volume-37-languages.56883/), [3](https://opendirectory.luzea.de/Enthousiast/Office/Office%20Pro%20Plus%202010%20SP1%20VL/), [4](https://cloud.mail.ru/public/9KV2/mu3iZVBgb/2010)
- [Разное для офиса](https://github.com/YerongAI/Office-Tool)
- [Старые ссылки на офис](https://pastebin.com/raw/PLhB7UnK)
- [Исправление ошибки "копия офиса не легитимна"](https://massgrave.dev/office-license-is-not-genuine)
- [Ohook активация](https://github.com/asdcorp/ohook)

Всё для нвидий и амд драйверов видеокарты:
- [Утилита для полного удаление через безопасный режим старых драйверов видеокарты](https://www.guru3d.com/files-details/display-driver-uninstaller-download.html)
- [Утилита для установки только необходимых компонентов драйверов нвидий](https://www.techpowerup.com/nvcleanstall/)
- [Утилита для отключения Ansel Nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/4932)
- [Утилита для установки только необходимых компонентов драйверов амд](https://github.com/GSDragoon/RadeonSoftwareSlimmer)

## ПО по вкусу
>[Пикча](https://s1.desu-usergeneratedcontent.xyz/g/image/1562/46/1562467997749.png) от *друзей* с форча

**Браузер:**
[Firefox](https://ftp.mozilla.org/pub/firefox/releases/) `10x.x.x\` - [Firefox ESR](https://ftp.mozilla.org/pub/firefox/releases/) `Ищем с приставкой "esr\"` - [Ungoogled Chromium 1](https://ungoogled-software.github.io/ungoogled-chromium-binaries/releases/windows/64bit/) - [Ungoogled Chromium 2](https://github.com/macchrome/winchrome/releases)

**Текстовый редактор:**
[Notepad ++](https://notepad-plus-plus.org/downloads/) - [Vscodium](https://github.com/VSCodium/vscodium) - [Sublime Text](https://www.sublimetext.com/download) ([Делаем себе сами через hex бесконечную лицензию для sublime](https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47))

**Торрент-клиент:**
[qBittorent](https://www.qbittorrent.org/download.php) - [Transmission](https://transmissionbt.com/download/) - [Deluge](https://ftp.osuosl.org/pub/deluge/windows/?C=M;O=D) - [PicoTorrent](https://picotorrent.org/download)

**Просмотр изображений:**
[nomacs](https://github.com/nomacs/nomacs) - [jpegview](https://github.com/sylikc/jpegview) - [pictus](https://github.com/poppeman/Pictus/releases)

**Видео-Конвертер:**
[FFmpeg](https://ffmpeg.org/download.html#build-windows) - [Handbrake](https://handbrake.fr/downloads.php) - [StaxRip](https://github.com/staxrip/staxrip/releases)

**Видеоплееры:**
[MPC-HC](https://github.com/clsid2/mpc-hc/releases) - [mpv](https://sourceforge.net/projects/mpv-player-windows/files/) - [mpv.net](https://github.com/stax76/mpv.net/releases) - [VLC](https://www.videolan.org)

**Музыкальный Проигрыватель:**
[Clementine](https://www.clementine-player.org/ru/downloads) - [foobar2000](https://www.foobar2000.org/download) - [Audacious](https://audacious-media-player.org/download) - [Aimp](https://www.aimp.ru/?do=download)

**Запись Экрана:**
[OBS](https://obsproject.com/ru/download)

**Шифровка данных:**
[Veracrypt](https://www.veracrypt.fr/en/Downloads.html)

**Управление файлами**
[7zip](https://www.7-zip.org/download.html) - [fman](https://fman.io/download) - [Everything](https://www.voidtools.com/ru-ru/downloads/)

**Просмотр PDF:**
Твой браузер - [SumatraPDF](https://www.sumatrapdfreader.org/download-free-pdf-viewer)

**Офис:**
[Google Документы](https://docs.google.com/) - [Libre Office](https://www.libreoffice.org/download/download/?lang=ru)

**Общение:**
[Pidgin](https://www.pidgin.im) - [Thunderbird](https://www.thunderbird.net/ru/) - [Mumble](https://www.mumble.info/downloads/)

**Клинер:**
[Bleachbit](https://www.bleachbit.org/download/windows)




## Установка Windows 10

> [!NOTE]  
> [windows_for_retards](https://rentry.co/windows_for_retards)
### Что будет нужно
- Интернет
- Система хотя бы на семёрке для создания образа
- Флешка на хотя бы 8 гигов
- [Торрент клиент](https://www.qbittorrent.org/download.php)
- Комп с поддержкой UEFI
### Что получишь в конце
- Десятка Образовательная

Если захочешь:
- Полунапердолленая система без поломок
### Скачиваем виндовс
1. Открываешь [ru-ru_windows_10](https://nnmclub.to/forum/viewtopic.php?t=1662987)
2. Жмёшь на магнит
3. Скачиваешь только  `ru-ru_windows_10_business_editions_version_22h2_updated_sep_2023_x64_dvd_3e14a3b2.iso` 

![](img/nnmclubwiniso.png)

### Скачиваешь Ventoy
1. Открываешь [Ventoy](https://github.com/ventoy/Ventoy/releases)
2. Скачиваешь `"ventoy-1.0.XX-windows.zip"`
3. Распаковываешь в любое удобное для тебя место (Распаковать можно например с [7zip](https://www.7-zip.org/download.html))

![](img/ventoy.png)

### Запись образа на флешку
1. Вставляешь флешку
2. Открываешь `"Ventoy2Disk.exe"`
3. `"Устройство"` выбираешь свою флешку
4. Нажимаешь "Установить"
5. Когда установка закончится просто перетягиваем наш образ `.iso` на нашу флешку с названием `"Ventoy"` (Например `(E:) Ventoy`)

![](img/ventoycopy.png)

### Загрузка с флешки для дальнейший установки
- [x] Берёшь гуглишь как на твоей **марки ноутбука/материнки** запустится с флешки и так далее в основном ищешь какую **кнопку** жать при запуске компа

![](img/biosbutton.png)

> [!NOTE]  
> Может быть что угодно `"Del" - "F2" - "F8"` и т.к.

---

### Сама установка
1. `"Устанавливаемый язык"`

2. `"Формат времени и денежных единиц"`

3. `"Метод ввода"`

![](img/1windows.png)

4. **"Ключ продукта":**
- [x] **`"У меня нет ключа продукта" `**

![](img/2windows.png)

5. **"Выберите ос, которую вы хотите установить"**
- [x] **`Windows 10 для образовательных учреждений`**

![](img/3windows.png)

6. **"Условия лицензии"**
- [x] **`Я принимаю условия лицензии`**

![](img/4windows.png)

7. **"Выберите тип установки"**
- [x] **`Выборочная`**
 > [!IMPORTANT]  
> Обязательно сделайте бэкап всех данных перед очисткой диска или раздела.

![](img/5windows.png)

8. **"Где вы хотите установить Windows?":**
Выбираем `Незанятое пространство`, или `удаляем старый раздел`. Если выбрать раздел со старой виндовс, она переместится в папку **Windows.old** со всеми файлами. Хочешь удалить [всё](https://github.com/shapkodebil/win10thread#хочу-перед-установкой-виндовс-очистить-диск-от-всего-и-ещё-поменять-структуру-раздела) то бы наверняка?

![](img/6windows.png)

> [!NOTE]  
> **Ждёшь окончание установки.**

---

### Конфигурация (OOBE)
> [!IMPORTANT]  
> **Очень рекомендую отключить нахуй интернет (кабель и т.п.) во время всего процесса установки что бы избежать проблем с доёбыванием майкрософта с аккаунтом и разными обновлениями (особенно драйверами видеокарты) и собственно *телеметрий*(если это вас ебёт), включайте обратно когда уверенны что система сконфигурирована правильно и по вашему вкусу или надо активировать через HWID.**
1. Выбери - Регион и раскладку

![](img/oobe1.png)

![](img/oobe2.png)

2. "Давайте подключим вас к сети":

- [x] **`"У меня нет Интернета"`**

![](img/oobe3.png)

- [x] **`"Продолжить ограниченную установку"`**

![](img/oobe4.png)

3. Выбери - имя пользователя

![](img/oobe5.png)

4. "Выберите параметры конфиденциальности для этого устройства":
-  Отключить нахуй "Диагностические данные" - "Реклама" всё остальное на своё усмотрение 

![](img/oobe6.png)

---

### Активация самой виндовс
1. Скачиваешь любой из активаторов
2. Скачиваешь архиватор [7zip](https://www.7-zip.org/download.html)
3. Отключаешь на время и разрешаешь архив/exe активатора в **антивирусе** (Microsoft Defender)

[**KMS_VL_ALL**](#kms_vl_all-by-abbodi1406):
1. "Запустить от имени администратора"
2. Нажимаешь 2

---

### Хочу как следует попердолить сломать мою систему
1. Скачиваешь [Privatezilla](https://github.com/builtbybel/privatezilla)
2. Распаковываешь
3. Оставляешь по дефолту все настройки да бы не разьебать всё нахуй.
	- `"Disable Windows Hello Biometrics" не даст камере или отпечатку работать нормально как и пароли, для ноутбука лучше не отключать.`
5. "Применить" - "Apply selected"

![](img/privatezilla.png)
