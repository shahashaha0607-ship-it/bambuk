# Bambuk: Android loyihasi (Capacitor 8)

## 1. GitHub'ga yuklash
1. github.com'da yangi repo oching (masalan `bambuk`).
2. Shu papkadagi hamma fayllarni (`.github` papkasi bilan) repoga yuklang.

## 2. Ikonka
Canva'da Bambuk ikonkasini 1024×1024 PNG qilib yuklab oling va repoda `assets/icon-only.png` nomi bilan saqlang.

## 3. Imzo kaliti (bir marta, kompyuterda)
```
keytool -genkey -v -keystore bambuk-upload.jks -keyalg RSA -keysize 2048 -validity 10000 -alias bambuk
base64 -w0 bambuk-upload.jks
```
`.jks` faylni **yo'qotmang**, zaxira nusxasini saqlang. Repo > Settings > Secrets and variables > Actions'ga qo'shing:
`KEYSTORE_BASE64`, `KEY_ALIAS` (bambuk), `KEYSTORE_PASSWORD`, `KEY_PASSWORD`.

## 4. Yig'ish
Repo > Actions > "Android build" > Run workflow. Tugagach, Artifacts bo'limidan:
- `bambuk-debug-apk`: telefonga o'rnatib sinash uchun
- `bambuk-release-aab`: Play Console'ga yuklash uchun

## 5. Play Console
1. play.google.com/console'da dasturchi akkaunti oching (bir martalik to'lov).
2. Yangi ilova yarating, `store/listing-uz.md` matnlarini kiriting.
3. `store/privacy-policy.html` ni GitHub Pages orqali joylab, havolasini bering.
4. AAB'ni Testing > Closed testing'ga yuklang.

**Muhim:** shaxsiy akkaunt bo'lsa, ishlab chiqarishga chiqishdan oldin kamida 12 testchi bilan 14 kun uzluksiz yopiq test kerak. Tashkilot (kompaniya) akkaunti bu talabdan ozod.

## Eslatmalar
- `appId` (`uz.yorqintalim.bambuk`) Play'ga yuklangach o'zgarmaydi. Kerak bo'lsa, `capacitor.config.json`'da hozir o'zgartiring.
- Gapirishni avtomatik tekshirish (mikrofon) Android WebView'da ishlamaydi, ilovada "Qiyin / Aytdim" o'z-o'zini baholash ishlaydi. Keyingi versiyada speech-recognition plagini qo'shiladi.
- Kod har yili Google'ning yangi target API talabiga mos Capacitor versiyasiga yangilanishi kerak.
