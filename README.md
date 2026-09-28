<div align="center">

# <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=28 /> <a href="https://github.com/Flowseal/">Flowseal</a><a href="https://github.com/Flowseal/zapret-discord-youtube">/zapret-discord-youtube</a> <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=28 />

**NEW**: Ускорение Telegram Desktop - https://github.com/Flowseal/tg-ws-proxy  
Альтернатива https://github.com/bol-van/zapret-win-bundle  
Также вы можете материально поддержать оригинального разработчика zapret [тут](https://github.com/bol-van/zapret?tab=readme-ov-file#%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0)
</div>

> [!CAUTION]
>
> ### ФЕЙКИ
> Я не веду никакие другие страницы/группы в телеграм/ютуб каналы  
> Если вы наткнулись на что-то вне этой страницы гитхаба, что распространяется от моего лица - **ФЕЙК**.

> [!WARNING]
>
> ### АНТИВИРУСЫ
> WinDivert может вызвать реакцию антивируса.
> WinDivert - это инструмент для перехвата и фильтрации трафика, необходимый для работы zapret.
> Замена iptables и NFQUEUE в Linux, которых нет под Windows.
> Он может использоваться как хорошими, так и плохими программами, но сам по себе не является вирусом.
> Драйвер WinDivert64.sys подписан для возможности загрузки в 64-битное ядро Windows.
>
> **Выдержка из [`readme.md`](https://github.com/bol-van/zapret-win-bundle/blob/master/readme.md#%D0%B0%D0%BD%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D1%81%D1%8B) репозитория [bol-van/zapret-win-bundle](https://github.com/bol-van/zapret-win-bundle)*
>
> Некоторые антивирусы склонны относить файлы WinDivert к классам повышенного риска или хакерским инструментам. Происходит удаление файла и помещение его в карантин. При этом детект обязательно имеет название `WinDivert` или `Not-a-virus:RiskTool.Multi.WinDivert`
>
> В случае проблем с антивирусом добавьте папку с запретом в исключения, либо отключите детектирование PUA (потенциально нежелательных приложений). Например, в касперском есть галочка "Обнаруживать легальные приложения, которые злоумышленники часто используют для нанесения вреда". При аккуратной и правильной настройке исключений - рекомендуется настроить исключение, но если вы не до конца понимаете что делаете - рекомендуется отключить детект PUA.

> [!IMPORTANT]
> Все бинарные файлы в папке [`bin`](./bin) взяты из [zapret-win-bundle/zapret-winws](https://github.com/bol-van/zapret-win-bundle/tree/master/zapret-winws) и [zapret/releases](https://github.com/bol-van/zapret/releases). Вы можете это проверить с помощью хэшей/контрольных сумм. Проверяйте, что запускаете, используя сборки из интернета!

## ⚙️Использование

1. Включите Secure DNS
    * В Chrome - "Использовать безопасный DNS", и выбрать поставщика услуг DNS (выбрать вариант, отличный от варианта "Поставщик по умолчанию")
    * В Firefox - "Включить DNS через HTTPS, используя: Максимальную защиту", затем "Выбрать поставщика" и вписать URL поставщика вручную, например можно использовать `https://dns.google/dns-query` (т.к. поставщик Cloudflare может быть заблокирован)
    * В Windows 11 поддерживается включение Secure DNS прямо в настройках ОС - [инструкция тут](https://remontka.pro/dns-over-https-windows-11/). Рекомендуется, если вы пользуетесь Windows 11
    * Если у вас роутер Keenetic, включите в настройках роутера опцию "Транзит запросов". Отключение этой опции может привести к проблемам при настройке и использовании Secure DNS на компьютере

2. Скачайте архив (zip/rar) со [страницы последнего релиза](https://github.com/Flowseal/zapret-discord-youtube/releases/latest)

3. Зайдите в свойства скачанного архива и поставьте галочку "Разблокировать". Если вы используете архиватор 7-Zip или PeaZip, этот шаг можно пропустить

4. Распакуйте содержимое архива по пути, который не содержит кириллицу/спец. символы

5. Запустите нужный файл

## ℹ️Краткие описания файлов

- [**`general.bat ...`**](./general.bat) - запуск стратегии вручную

  Запуск вручную можно использовать для проверки работоспособности стратегий. Работоспособность той или иной стратегии зависит от многих факторов. **Пробуйте разные стратегии (ALT, FAKE и другие), пока не найдёте рабочее для вас решение**

- [**`service.bat`**](./service.bat) - установка в автозапуск и другие функции:
  - <ins>**`Install Service`** - установка любой стратегии в автозапуск (services.msc)</ins>
  - **`Remove Services`** - удаление стратегии и WinDivert из служб
  - **`Check Status`** - проверка статуса обхода и служб (стратегии на автозапуске и WinDivert)
  - **`Game Filter`** - переключение режима обхода для игр (и других сервисов, использующих UDP и TCP на портах выше 1023).  
  **После переключения требуется перезапуск стратегии.**  
  В скобках указан текущий статус (включено/выключено).
  - **`IPSet Filter`** - переключение режима обхода сервисов из `ipset-all.txt`.  
  Полезно при тестировании, если не работает ресурс, который без zapret работает  
  В скобках указан текущий статус:
    - `none` - никакие айпи не попадают под проверку
    - `loaded` - айпи проверяется на вхождение в список
    - `any` - любой айпи попадает под фильтр  
  - **`Auto-Update Check`** - Вкл/Выкл автоматическую проверку на обновления
  - **`Replace active fakes`** - Заменить указанный используемый фейк на другой из папки `bin`
  - **`Update IPSet List`** - обновление списка `ipset-all.txt` актуальным из репозитория
  - **`Update Hosts File`** - обновление файла hosts <ins>**для починки веб версии телеграма и подключения к голосовому чату Discord**</ins>
  - **`Check for Updates`** - проверка на обновления
  - **`Run Diagnostics`** - диагностика на распространённые причины, по которым zapret может не работать.  
  В конце можно очистить кэш <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=11 /> `Discord`, что может помочь, если он неожиданно перестал работать
  - **`Run Tests`** - запуск утилиты для проверки стратегий на работоспособность:
    - `Standard tests` - проверка сайтов из `utils/targets.txt`
    - `DPI checkers` - проверка DPI на различных провайдерах (Cloudflare, Amazon и др.)


## ☑️Распространенные вопросы и проблемы

### После запуска скрипта `general*` ничего не происходит

- После запуска стратегии (отдельным bat файлом, не через service), должен открыться winws.exe (обход), который можно увидеть в панели задач.  
Если этого не произошло, то см. [#522](https://github.com/Flowseal/zapret-discord-youtube/issues/522)

### Не работает телеграм (веб версия) или бесконечное "подключение" к голосовому чату Discord
Запустите **`service.bat`**, выберите пункт **`Update hosts file`**. После чего, если ваш hosts будет неактуальным, то Вам будет предложено обновить его самостоятельно:  
  - Скопируйте весь текст из открывшегося блокнота
  - Откройте файл `hosts` в появившейся папке с помощью текстового редактора, открытого от имени администратора
  - Добавьте в конец файла `hosts` то, что скопировали (или замените, если до этого Вы уже добавляли подобное)
  - Сохраните и перепроверьте подключение. Если не работает - убедитесь, что файл `hosts` действительно сохранился.

### Обход не работает / перестал работать

> [!IMPORTANT]
> **Стратегии со временем могут переставать работать.**
> Определенная стратегия может работать какое-то время, но со временем она может переставать работать из-за обнаружения.
> В репозитории представлены множество различных стратегий для обхода. Если ни одна из них вам не помогает, то вам необходимо создать новую, взяв за основу одну из представленных здесь и изменив её параметры.
> Информацию про параметры стратегий вы можете найти [тут](https://github.com/bol-van/zapret/blob/master/docs/readme.md#nfqws).

- Проверьте, чтобы не было ошибок в `service.bat` -> `Run Diagnostics`

- Убедитесь, что адрес ресурса записан в списках доменов или IP

- Проверьте другие стратегии (**`ALT`**/**`FAKE`** и другие)

- Попробуйте полную переустановку (см. раздел ниже)

- См. [#765](https://github.com/Flowseal/zapret-discord-youtube/issues/765)

### Как переустановить/обновить полностью?
- Сохраните ресурсы/данные, которые вы сами добавляли
- Перезапустите устройство
- `service.bat` -> `Remove Services`
- `service.bat` -> `Run Diagnostics` (если есть ошибки - устраните их) -> в конце Y
- Удалите папку с запретом
- Скачайте последнюю версию [со страницы релизов](https://github.com/Flowseal/zapret-discord-youtube/releases) (`zapret-discord-youtube-...`)
- Нажмите пкм по архиву -> свойства. Если снизу справа есть галочка разблокировать, то нажмите на неё -> применить -> ОК
- Распакуйте в новую папку в корне диска (без спец. символов и пробелов)
- Далее пробуйте запускать различные `general` скрипты (стратегии). Проверьте доступность интернет ресурсов - если не работают, то закрывайте программу (в панели задач иконка замочка) и пробуйте другую стратегию
- Как найдёте рабочую стратегию, можете поставить её на автозапуск: `service.bat` -> `Install Service` -> выбираете нужную

### Не работает игра/приложение с включённым запретом

- Проверьте, что в service.bat `Game Filter` **`disabled`**, а `IPSet Filter` **`none`**. Иначе это может затронуть доступность ресурсов, которых вы не ожидали.

### Античит ругается на WinDivert

- Прочитайте инструкцию тут - https://github.com/bol-van/zapret-win-bundle/tree/master/windivert-hide

### Требуется цифровая подпись драйвера WinDivert (Windows 7)

- Замените файлы `WinDivert.dll` и `WinDivert64.sys` в папке [`bin`](./bin) на одноименные из [zapret-win-bundle/win7](https://github.com/bol-van/zapret-win-bundle/tree/master/win7)

### При удалении с помощью [**`service.bat`**](./service.bat), WinDivert остается в службах

1. Узнайте название службы с помощью команды, в командной строке Windows (Win+R, `cmd`):

```cmd
driverquery | find "Divert"
```

2. Остановите и удалите службу командами:

```cmd
sc stop название_из_первого_шага

sc delete название_из_первого_шага
```

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=18 /> YouTube

- Убедитесь что вы настроили Secure DNS.
- Отключите блокировщик рекламы, известно что YouTube начал с ними бороться.
- Пробуйте все другие стратегии (если раньше работало, но перестало).
- См. также [#251](https://github.com/Flowseal/zapret-discord-youtube/discussions/251)

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=18 /> Discord

- Убедитесь что вы настроили Secure DNS.
- Желательно сначала узнать, на какой стратегии открывается сайт YouTube. Запустите эту стратегию.
- Запустите `service.bat` -> `Run Diagnostics` и выполните там очистку кэша Discord.
- Проверьте приложение Discord. Помогла ли очистка кэша?
- Проверьте Discord в браузере: https://discord.com/app. В браузере работает? Если работает, то можете пользоваться в нём.
- Если Discord и в браузере не работает, то пробуйте ещё раз все стратегии. Бывает такое, что на одной стратегии YouTube работает, а Discord нет.
- См. также [#252](https://github.com/Flowseal/zapret-discord-youtube/discussions/252)

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/5968/5968804.png" height=18 /> Telegram

- Используйте программу [tg-ws-proxy](https://github.com/Flowseal/tg-ws-proxy)
- Или используйте бесплатные MTProto прокси из интернета

### Не работают игры

Есть много разных игр. Исследовать и чинить каждую из них нет возможности.

Наиболее универсальный рецепт такой:
- через `service.bat` обновите ipset и включите `Game Filter`
- если это не поможет, то попробуйте также включить настройку `ipset any`

Но помните, что при включении `ipset any` появятся проблемы с открытием многих сайтов. Чтобы этого избежать, не используйте `ipset any` на постоянной основе. Вместо этого нужно выяснить все IP адреса, которые используются игрой, и добавить их в `ipset-all.txt`

Если и это не помогло, создайте ветку обсуждений в разделе [Discussions](https://github.com/Flowseal/zapret-discord-youtube/discussions) (не в issues) и ждите помощи от других игроков.

### Не нашли своей проблемы

- Создайте её [тут](https://github.com/Flowseal/zapret-discord-youtube/issues)

## 🗒️Добавление адресов прочих ресурсов

Список адресов для обхода можно расширить, добавляя их в:
- **`list-general-user.txt`** для доменов (поддомены автоматически учитываются)
- **`list-exclude-user.txt`** для исключения доменов (например, если айпи сети указан в `ipset-all.txt`, но конкретный домен из этой сети не надо фильтровать)
- **`ipset-all.txt`** для IP и подсетей
- **`ipset-exclude-user.txt`** для исключения IP и подсетей
  - Файлы **`*-user.txt`** автоматически создадутся при первом запуске `zapret` или `service.bat`

## ⭐Поддержка проекта

Вы можете поддержать проект, поставив :star: этому репозиторию (сверху справа этой страницы)

Также вы можете материально поддержать оригинального разработчика zapret [тут](https://github.com/bol-van/zapret?tab=readme-ov-file#%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0)

## ⚖️Лицензирование

Проект распространяется на условиях лицензии [MIT](https://github.com/Flowseal/zapret-discord-youtube/blob/main/LICENSE.txt)

## 🩷Благодарность участникам проекта

[![Contributors](https://contrib.rocks/image?repo=Flowseal/zapret-discord-youtube)](https://github.com/Flowseal/zapret-discord-youtube/graphs/contributors)

💖 Отдельная благодарность разработчику [zapret](https://github.com/bol-van/zapret) - [bol-van](https://github.com/bol-van)
запрет дискорд
запрет дискорд фикс
zapret discord fix
обход блокировки дискорд
как разблокировать дискорд
дискорд не работает
дискорд не грузит
дискорд не подключается
фикс дискорда
починка дискорда
решение проблемы дискорд
дискорд заблокирован в россии
обход запрета дискорд
zapret для дискорда
zapret discord
zapret настройка
zapret конфиг дискорд
zapret windows discord
zapret linux discord
zapret роутер discord
обход DPI дискорд
DPI обход дискорд
обход блокировок дискорд
как обойти блокировку дискорда
разблокировка дискорда
дискорд впн
впн для дискорда
прокси для дискорда
прокси дискорд россия
обход блокировки голосового дискорда
дискорд голос не работает
дискорд звонки не работают
дискорд видео не работает
дискорд стрим не работает
дискорд экран не работает
дискорд не открывается
дискорд ошибка подключения
дискорд ошибка сети
дискорд бесконечное подключение
дискорд connecting
дискорд rtc connecting
дискорд no route
дискорд не заходит
дискорд не запускается
дискорд крашится
дискорд лагает
дискорд пинг
дискорд высокий пинг
дискорд потеря пакетов
дискорд плохое соединение
как починить дискорд
как исправить дискорд
как настроить дискорд
как запустить дискорд в россии
дискорд россия блокировка
роскомнадзор дискорд
блокировка дискорда ркн
запрет дискорда 2024
запрет дискорда 2025
запрет дискорда 2026
дискорд замедление
замедление дискорда
обход замедления дискорд
дискорд без впн
дискорд без прокси
дискорд работает
дискорд fix
discord fix
фикс дискорд
zapret fix
zapret обход
zapret настройки
zapret скачать
zapret установка
zapret инструкция
zapret гайд
zapret дискорд гайд
zapret параметры
zapret конфигурация
zapret hosts
zapret winws
zapret goodbyedpi
goodbyedpi дискорд
goodbyedpi настройка
goodbyedpi fix
обход блокировок goodbyedpi
обход DPI goodbyedpi
дискорд и goodbyedpi
дискорд и zapret
zapret vs goodbyedpi
zapret discord voice
zapret discord voice fix
zapret голосовой дискорд
zapret звонки дискорд
zapret стрим дискорд
zapret видео дискорд
zapret rtc
zapret udp
zapret tcp
zapret quic
zapret discord quic
отключить quic дискорд
дискорд quic fix
дискорд udp fix
дискорд tcp fix
дискорд порты
дискорд порты для обхода
дискорд ip
дискорд ip адреса
дискорд сервера
дискорд cdn
дискорд голосовые сервера
дискорд регион
смена региона дискорд
дискорд регион россия
дискорд регион европа
дискорд vpn регион
дискорд обход регион
дискорд обход блокировки голос
дискорд обход блокировки видео
дискорд обход блокировки стрим
дискорд обход блокировки текст
дискорд обход блокировки каналы
дискорд не работает голос
дискорд не работает видео
дискорд не работает стрим
дискорд не работает экран
дискорд не работает микрофон
дискорд не работает звук
дискорд не слышно собеседника
дискорд не видно экран
дискорд черный экран
дискорд серый экран
дискорд зависает
дискорд фризит
дискорд вылетает
дискорд ошибка
дискорд ошибка 1006
дискорд ошибка 4000
дискорд ошибка подключения к голосу
дискорд ошибка rtc
дискорд rtc connecting fix
дискорд rtc fix
дискорд voice fix
дискорд stream fix
дискорд screen share fix
дискорд fix россия
дискорд fix zapret
дискорд fix vpn
дискорд fix proxy
дискорд fix 2024
дискорд fix 2025
дискорд fix 2026
обход блокировки дискорд 2024
обход блокировки дискорд 2025
обход блокировки дискорд 2026
как обойти блокировку дискорда 2025
как обойти блокировку дискорда 2026
дискорд обход инструкция
дискорд обход гайд
дискорд обход настройка
дискорд обход windows
дискорд обход linux
дискорд обход android
дискорд обход ios
дискорд обход mac
дискорд обход роутер
дискорд обход keenetic
дискорд обход mikrotik
дискорд обход openwrt
дискорд обход панель
дискорд обход vps
дискорд обход сервер
дискорд обход прокси
дискорд обход socks5
дискорд обход shadowsocks
дискорд обход vless
дискорд обход vmess
дискорд обход trojan
дискорд обход wireguard
дискорд обход amnezia
дискорд обход outline
дискорд обход warp
дискорд обход cloudflare
дискорд обход warp fix
cloudflare warp дискорд
warp discord fix
warp discord россия
дискорд и warp
дискорд и cloudflare
дискорд и впн
лучший впн для дискорда
впн для дискорда россия
бесплатный впн дискорд
впн дискорд голос
впн дискорд стрим
впн дискорд видео
прокси дискорд голос
прокси дискорд стрим
socks5 дискорд
shadowsocks дискорд
vless дискорд
vmess дискорд
trojan дискорд
wireguard дискорд
amnezia дискорд
amneziavpn дискорд
outline дискорд
outline vpn дискорд
дискорд zapret настройка
дискорд zapret конфиг
дискорд zapret параметры
дискорд zapret скачать
дискорд zapret установить
дискорд zapret запустить
дискорд zapret windows
дискорд zapret linux
дискорд zapret android
дискорд zapret роутер
дискорд zapret keenetic
дискорд zapret mikrotik
дискорд zapret openwrt
дискорд zapret инструкция
дискорд zapret гайд
дискорд zapret fix
дискорд zapret работает
дискорд zapret не работает
дискорд zapret ошибка
дискорд zapret решение
дискорд zapret 2025
дискорд zapret 2026
zapret discord 2025
zapret discord 2026
zapret discord guide
zapret discord config
zapret discord voice
zapret discord stream
zapret discord fix 2025
zapret discord fix 2026
обход блокировки дискорд ркн
обход блокировки дискорд россия
обход блокировки дискорд снг
обход блокировки дискорд украина
обход блокировки дискорд беларусь
обход блокировки дискорд казахстан
дискорд блокировка ркн fix
дискорд блокировка обход
дискорд блокировка решение
дискорд блокировка голос
дискорд блокировка видео
дискорд блокировка стрим
дискорд блокировка текст
дискорд блокировка каналы
дискорд блокировка сервера
дискорд блокировка ip
дискорд блокировка портов
дискорд блокировка udp
дискорд блокировка tcp
дискорд блокировка quic
как разблокировать дискорд в россии
как разблокировать дискорд голос
как разблокировать дискорд видео
как разблокировать дискорд стрим
как разблокировать дискорд без впн
как разблокировать дискорд без прокси
как разблокировать дискорд на пк
как разблокировать дискорд на телефоне
как разблокировать дискорд на андроид
как разблокировать дискорд на ios
как разблокировать дискорд на роутере
разблокировка дискорд 2025
разблокировка дискорд 2026
разблокировка дискорд zapret
разблокировка дискорд goodbyedpi
разблокировка дискорд впн
разблокировка дискорд прокси
разблокировка дискорд warp
разблокировка дискорд cloudflare
разблокировка дискорд amnezia
разблокировка дискорд outline
zapret discord fix
discord fix
discord blocked
discord unblock
unblock discord
discord not working
discord not loading
discord not connecting
discord connection error
discord network error
discord infinite connecting
discord rtc connecting
discord rtc connecting fix
discord no route
discord voice not working
discord voice fix
discord stream not working
discord stream fix
discord screen share fix
discord video not working
discord video fix
discord call not working
discord call fix
discord microphone not working
discord audio not working
discord black screen
discord grey screen
discord freezing
discord lag
discord high ping
discord packet loss
discord bad connection
discord error 1006
discord error 4000
discord fix 2024
discord fix 2025
discord fix 2026
discord russia
discord russia block
discord blocked in russia
discord ban russia
discord roskomnadzor
discord rkn
discord dpi
discord dpi bypass
dpi bypass discord
bypass dpi discord
bypass discord block
bypass discord ban
bypass discord censorship
discord censorship bypass
discord throttling
discord throttling fix
discord slowdown
discord slowdown fix
zapret
zapret discord
zapret discord fix
zapret discord config
zapret discord guide
zapret discord setup
zapret discord windows
zapret discord linux
zapret discord android
zapret discord router
zapret discord keenetic
zapret discord mikrotik
zapret discord openwrt
zapret discord voice
zapret discord stream
zapret discord video
zapret discord rtc
zapret discord udp
zapret discord tcp
zapret discord quic
zapret discord 2025
zapret discord 2026
zapret fix
zapret setup
zapret config
zapret parameters
zapret winws
zapret hosts
zapret download
zapret install
zapret guide
zapret tutorial
zapret bypass
zapret dpi bypass
goodbyedpi
goodbyedpi discord
goodbyedpi discord fix
goodbyedpi setup
goodbyedpi config
goodbyedpi guide
goodbyedpi bypass
goodbyedpi dpi bypass
zapret vs goodbyedpi
discord goodbyedpi
discord zapret
discord proxy
discord proxy fix
discord socks5
discord shadowsocks
discord vless
discord vmess
discord trojan
discord wireguard
discord amnezia
discord outline
discord warp
discord cloudflare warp
cloudflare warp discord
warp discord fix
warp discord russia
discord vpn
best vpn for discord
free vpn discord
vpn discord russia
vpn discord voice
vpn discord stream
vpn discord video
discord without vpn
discord without proxy
discord quic fix
disable discord quic
discord udp fix
discord tcp fix
discord ports
discord ports bypass
discord ip
discord ip addresses
discord servers
discord cdn
discord voice servers
discord region
discord region change
discord region russia
discord region europe
discord vpn region
discord bypass region
discord voice bypass
discord video bypass
discord stream bypass
discord text bypass
discord channels bypass
discord unblock voice
discord unblock video
discord unblock stream
discord unblock screen share
discord unblock 2025
discord unblock 2026
how to unblock discord
how to unblock discord voice
how to unblock discord video
how to unblock discord stream
how to unblock discord without vpn
how to unblock discord without proxy
how to unblock discord on pc
how to unblock discord on phone
how to unblock discord on android
how to unblock discord on ios
how to unblock discord on router
how to fix discord
how to fix discord voice
how to fix discord stream
how to fix discord video
how to fix discord connection
how to fix discord rtc
how to fix discord error
how to fix discord 1006
how to fix discord 4000
how to fix discord in russia
how to fix discord with zapret
how to fix discord with goodbyedpi
how to fix discord with vpn
how to fix discord with proxy
how to fix discord with warp
how to fix discord with cloudflare
how to fix discord with amnezia
how to fix discord with outline
discord fix guide
discord fix tutorial
discord fix instructions
discord fix windows
discord fix linux
discord fix mac
discord fix android
discord fix ios
discord fix router
discord fix keenetic
discord fix mikrotik
discord fix openwrt
discord fix vps
discord fix server
discord fix panel
discord fix 2025 guide
discord fix 2026 guide
discord bypass guide
discord bypass tutorial
discord bypass instructions
discord bypass windows
discord bypass linux
discord bypass android
discord bypass ios
discord bypass mac
discord bypass router
discord bypass keenetic
discord bypass mikrotik
discord bypass openwrt
discord bypass vps
discord bypass server
discord bypass proxy
discord bypass socks5
discord bypass shadowsocks
discord bypass vless
discord bypass vmess
discord bypass trojan
discord bypass wireguard
discord bypass amnezia
discord bypass outline
discord bypass warp
discord bypass cloudflare
discord russia fix
discord russia bypass
discord russia unblock
discord russia 2025
discord russia 2026
discord rkn bypass
discord rkn fix
discord roskomnadzor bypass
discord censorship fix
discord censorship bypass 2025
discord censorship bypass 2026
discord dpi fix
discord dpi bypass 2025
discord dpi bypass 2026
discord zapret 2025
discord zapret 2026
discord zapret bypass
discord zapret unblock
discord zapret guide
discord zapret tutorial
discord zapret windows 2025
discord zapret linux 2025
discord zapret android 2025
discord zapret router 2025
discord zapret keenetic 2025
discord zapret mikrotik 2025
discord zapret openwrt 2025
discord voice zapret
discord stream zapret
discord video zapret
discord rtc zapret
discord udp zapret
discord tcp zapret
discord quic zapret
zapret discord voice fix
zapret discord stream fix
zapret discord video fix
zapret discord rtc fix
zapret discord udp fix
zapret discord tcp fix
zapret discord quic fix
discord zapret not working
discord zapret error
discord zapret solution
discord zapret fix 2025
discord zapret fix 2026
discord blocked fix
discord blocked solution
discord blocked bypass
discord blocked 2025
discord blocked 2026
discord unblocked
discord working
discord working again
discord fix russia
discord fix cis
discord fix ukraine
discord fix belarus
discord fix kazakhstan
