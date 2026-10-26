# RefresherVPN

Приватный VPN-клиент для узкого круга друзей: Android и iOS, одна кнопка «Подключить».
Основной канал — VLESS + Reality, запасной — AmneziaWG. Доступ выдаётся Telegram-ботом: он присылает
персональную ссылку подписки, приложение её импортирует и обновляет само.

Это не публичный сервис: в приложении нет серверов, ключей или ссылок — только то, что пришло от бота.

## Статус

Ранняя стадия. Сейчас репозиторий — форк [Hiddify](https://github.com/hiddify/hiddify-app) с
изменённой сборкой; брендинг, онбординг и упрощённый интерфейс в работе.

- Android: сборка в GitHub Actions (`CI` → `Build`), APK публикуется в релиз с тегом `draft`.
- iOS: собирается в симуляторе; распространение через TestFlight после регистрации в Apple
  Developer Program.

## Сборка

```bash
make android-apk-install-deps
make android-prepare          # pub get, codegen, translations, скачивание ядра
flutter build apk --release --target lib/main_prod.dart
```

Ядро (`hiddify-core`, форк sing-box) скачивается готовым, Go не нужен.

## Происхождение и лицензия

RefresherVPN основан на исходном коде [Hiddify](https://github.com/hiddify/hiddify-app) и
[hiddify-core](https://github.com/hiddify/hiddify-core). Распространяется на условиях
**Hiddify Extended GPLv3** — см. [LICENSE.md](LICENSE.md). Код форка публичен, сборки выполняются в
GitHub Actions, проект некоммерческий. RefresherVPN не связан с проектом Hiddify и не поддерживается им.
