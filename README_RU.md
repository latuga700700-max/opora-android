# ОПОРА — Android APK через GitHub Actions

Этот проект упаковывает автономный HTML-интерфейс в Android-приложение WebView. HTML находится внутри APK и открывается без интернета. Внешний ИИ-чат в этой версии не подключён.

## Сборка через GitHub без установки инструментов на Astra Linux

1. Создайте на GitHub новый **публичный** репозиторий, например `opora-android`. Публичный репозиторий удобен для бесплатного GitHub Actions; не добавляйте в проект личные данные или секреты.
2. Загрузите в репозиторий содержимое этой папки, сохранив структуру папок и файлов, затем выполните Commit changes в ветку `main`.
3. Откройте вкладку **Actions** и выберите workflow **Build Opora APK**. Если GitHub запросит разрешение на Actions, включите их.
4. После завершения успешного запуска откройте запуск workflow, прокрутите до **Artifacts** и скачайте `Opora-debug-apk`.
5. Распакуйте ZIP-архив артефакта. Внутри будет `app-debug.apk`. Передайте APK на Android-телефон и установите его, разрешив установку из этого источника при необходимости.

## Локальная сборка

Требуются JDK 17, Android SDK Platform 35 и Gradle 8.9. Команда: `gradle assembleDebug`.

## Состав

- `app/src/main/assets/index.html` — HTML-приложение.
- `app/src/main/java/ru/opora/app/MainActivity.kt` — Android WebView-оболочка.
- `.github/workflows/build-apk.yml` — облачная сборка.

APK для установки на телефон — тестовая debug-сборка, не подписанная для публикации в Google Play.
