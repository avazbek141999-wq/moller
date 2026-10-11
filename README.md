# Tg+Insta — Telegram va Instagram bitta ilovada

Pastdagi tugmalar orqali Telegram Web va Instagram o'rtasida almashadigan Android ilova.
Ikkala sayt ham rasmiy veb-versiya orqali ishlaydi, login ma'lumotlari qurilmada saqlanadi.

## APK yig'ish (Android Studio)

1. **Android Studio**ni oching (Koala yoki yangiroq tavsiya etiladi).
2. `File > Open` orqali `TgInstaApp` papkasini tanlang.
3. Gradle sinxronlanishini kuting (birinchi marta bir necha daqiqa ketadi).
4. Menyudan: `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
5. Tayyor fayl: `app/build/outputs/apk/debug/app-debug.apk`.
6. APK'ni telefonga ko'chiring va o'rnating (sozlamalarda "Noma'lum manbalardan o'rnatish"ga ruxsat bering).

## APK'ni GitHub'da avtomatik yig'ish (Android Studio'siz)

1. github.com'da bepul akkaunt oching va yangi repository yarating (masalan, `tginsta`).
2. Zip'ni oching va **papka ichidagi** hamma fayllarni repository'ga yuklang (`Add file > Upload files`). Papkaning o'zini emas, ichidagi `app`, `gradle`, `build.gradle` va boshqa fayllarni yuklang.
3. `.github/workflows/build.yml` fayli ham repository ildizida bo'lishi kerak. Agar yuklanmasa, `Add file > Create new file` bosib, nomiga `.github/workflows/build.yml` yozing va ichiga shu fayl mazmunini joylang.
4. Yuklagandan keyin `Actions` bo'limiga o'ting: "Build APK" ishga tushadi (3-6 daqiqa).
5. Tugagach, o'sha ishni oching va pastdagi `Artifacts` dan `TgInsta-debug-apk` ni yuklab oling. Ichida `app-debug.apk` bor.

## Imkoniyatlar

- Pastda Telegram / Instagram tablari (ikkalasi ham xotirada saqlanadi, almashganda qayta yuklanmaydi)
- Pastga tortib yangilash
- "Orqaga" tugmasi avval sahifa ichida orqaga qaytadi
- Rasm/fayl yuborish (fayl tanlash oynasi)
- Kamera va mikrofon ruxsati: ovozli xabar, video xabar, kameradan rasmga olish
- Joylashuvni (lokatsiya) yuborish
- Fayllarni "Yuklanmalar" papkasiga yuklab olish
- To'liq ekran video
- "Reels joylash" tugmasi: telefondan video tanlanadi va Instagram ilovasiga yuboriladi (u yerda Reels sifatida joylanadi). Buning uchun telefonda Instagram ilovasi o'rnatilgan bo'lishi kerak; bo'lmasa Instagram tabidagi + tugmasi orqali yuklash mumkin.
- Tashqi havolalar telefon brauzerida ochiladi

## Sozlash

- Havolalar: `MainActivity.kt` ichidagi `TELEGRAM_URL` va `INSTAGRAM_URL`
- Ilova nomi: `res/values/strings.xml`
- Ranglar: `res/values/themes.xml`
- Paket nomi: `app/build.gradle` ichidagi `applicationId`

## Cheklovlar

- Bu rasmiy Telegram/Instagram ilovasi emas, balki ularning veb-versiyalarini o'rab turuvchi ilova.
- Bildirishnomalar (push) veb-versiyada ishonchli ishlamasligi mumkin.
- Instagram veb-versiyasi ba'zi funksiyalarni (masalan, ba'zi Reels/DM imkoniyatlarini) cheklashi mumkin.
- Play Market'ga joylash uchun release kalit bilan imzolash kerak (`Build > Generate Signed Bundle / APK`).
