# AntiQQ Vanced

[![Release](https://img.shields.io/github/v/release/retvil/AntiQQVanced?sort=date)](https://github.com/retvil/AntiQQVanced/releases) [![Platform Windows](https://img.shields.io/badge/platform-Windows-blue)](https://github.com/retvil/AntiQQVanced/releases) [![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)

**QQ Browser'ı tamamen kaldırın ve varsayılan aramanızı ele geçirmeye karşı kilitleyin — 40 tespit vektörü, 10 arama motoru, 10 arayüz dili.**

[🇬🇧 English](README.md) | [🇷🇺 Русский](README.ru.md) | [🇺🇦 Українська](README.uk.md) | [🇰🇿 Қазақша](README.kk.md) | [🇩🇪 Deutsch](README.de.md) | [🇫🇷 Français](README.fr.md) | [🇪🇸 Español](README.es.md) | [🇵🇱 Polski](README.pl.md) | **🇹🇷 Türkçe** | [🇨🇳 中文](README.zh.md)

## Bu nedir?

QQ yalnızca bir tarayıcı kurmaz — kırk farklı sistem mekanizmasıyla sessizce varsayılan arama ve tarayıcı olarak kaydolur: kayıt defteri ilişkilendirmeleri, enterprise ilkeleri, tarayıcı profil ayarları, hatta Chromium profillerinin içindeki arama motoru veritabanları. Tarayıcıyı tek başına kaldırmak bunların hepsini geri almaz.

**AntiQQ Vanced** ([TheCawa/AntiQQ](https://github.com/TheCawa/AntiQQ) çatalı) **40 ele geçirme vektörünün tamamını** bulur, tek tıkla kaldırır ve ardından varsayılan aramanızı seçtiğiniz arama motoruna Windows enterprise ilkeleriyle **sabit şekilde kilitler** — hiçbir şey sessizce geri alamasın diye.

## Özellikler

- **Ele geçirme tarayıcısı** — 40 vektörü tespit eder: kurulum yolları, kayıt defterindeki Uninstall girdileri, `UserChoice` ilişkilendirmesi, `StartMenuInternet` kayıtları, `Software\QQ` anahtar ağaçları, `DefaultSearchProvider*` ilkeleri üzerinden ele geçirme, Chromium profillerinin `Preferences` ayarları, `Web Data` (SQLite) anahtar kelimeleri, Firefox `search.json.mozlz4`, legacy `SearchScopes`, autostart girdileri, zamanlanmış görevler, Windows hizmetleri, Punto Switcher, dosya ilişkilendirmeleri, QQ Disk kabuk entegrasyonu, devre dışı otostart, App Paths, kısayollar, ProgramData/Roaming kalıntıları, hosts girdileri, güvenlik duvarı kuralları, URI protokolleri, tarayıcı eklentileri, qq.ru çerezleri, „birlikte aç“ ilişkilendirmeleri, Prefetch/WER izleri, Defender istisnaları, klavye düzenleri, IE başlangıç sayfası ele geçirmesi, başlangıç URL ilkeleri (`RestoreOnStartupURLs`), Firefox ana sayfası, IE bölge haritası, RegisteredApplications girdileri, MUICache izleri, %TEMP% yükleyicileri, Store uygulamaları (QQ Music, Alice), ürün dizinleri, yerel veri dizinleri, QQ.DNS
- **Tek tıkla kaldırma** — her vektörün kendi remover'ı vardır; kilitli veritabanları dürüstçe raporlanır, çökme yok
- **Sabit arama politikası** — varsayılan aramayı 10 arama motorundan birine (Google, Bing, DuckDuckGo, Brave Search, Startpage, Mojeek, Qwant, Ecosia, Yahoo, SearXNG) kilitler: Chrome, Edge, Brave, Vivaldi, Opera ve QQ Browser için HKLM ilkeleri + Firefox/Waterfox için `policies.json`
- **Politika temizliği** — QQ `DefaultSearchProvider*` değerlerini kayıt defterinden temizler
- **10 arayüz dili** — ru, en, uk, kk, de, fr, es, pl, tr, zh; sistem dili otomatik algılanır
- **Hafif arayüz** — ttkbootstrap, dikey düzen, sabitlenmiş durum çubuğu ve alt bilgi

## Ekran görüntüsü

<details>
<summary>Ana pencere</summary>

![AntiQQVanced ana penceresi](docs/screenshot.png)

</details>

## Hazır derlemeler

[Releases](https://github.com/retvil/AntiQQVanced/releases) sayfasından indirin:

- **Windows** — `AntiQQVanced.exe` (taşınabilir, tek dosya, ~35 MB) — QQ Browser ve QQ Arama kaldırma
- **Windows** — `AntiQQExtended.exe` (taşınabilir, tek dosya, ~35 MB) — tüm QQ ürünlerinin kaldırılması (QQ Disk, Punto Switcher geçmişi, sistem genelinde izler, Store uygulamaları, QQ.DNS)

**Yönetici olarak** çalıştırın — HKLM ilkeleri ve kayıt defteri temizliği yükseltilmiş haklar gerektirir.

## Kaynak koddan kurulum

Python 3.10+ gerekli ([python.org](https://python.org)).

```bash
git clone https://github.com/retvil/AntiQQVanced.git
cd AntiQQVanced
pip install psutil ttkbootstrap
python main.py
```

Kendi EXE'nizi derlemek için: `build.bat` çalıştırın (PyInstaller, çıktı `dist/` içinde).

## Kullanım

1. **İşlemleri sonlandır** → **QQ'i ara** → **QQ'i sil** — tarayıcının kendisini kaldırıyoruz.
2. **Arama ele geçirmelerini tara** — QQ'in sisteme nasıl kök saldığının tüm yollarını gösterir.
3. **Ele geçirmeleri kaldır** — önce tüm tarayıcıları kapatın, sonra bulunan her şeyi kaldırın.
4. Bir motor seçin → **Politikayı uygula** — varsayılan arama sistem düzeyinde kilitlendi.

## SSS

- **Neden yönetici?** Arama politikaları HKLM'de yaşar, temizlik sistem kayıt defterine dokunur — yükseltilmiş haklar gerekir.
- **Sonuçlarda «Database locked»?** Temizlik sırasında bir Chromium tarayıcısı çalışıyordu. Tüm tarayıcıları kapatın ve kaldırmayı tekrarlayın.
- **Arama politikasını nasıl kaldırırım?** **QQ politikalarını kaldır** düğmesi politika değerlerini temizler; Firefox'ta ayrıca `distribution\policies.json` dosyasını silebilirsiniz.

## Yazar ve destek

**Nod33Eset** — [TheCawa/AntiQQ](https://github.com/TheCawa/AntiQQ) çatalı. Issues ve PR'lara açığız.

Araç sizi QQ'ten kurtardıysa, geliştirmeyi destekleyebilirsiniz:

**Kripto:**

- BTC: `bc1qunld3rsp37qf5gg69aune50y0qqkd0eugg7j97`
- TON: `UQDmvr4SKOxSION3Yky6aOgzAnCDXySPuAbG4EKJa5JUT7tC`
- USDT (TRC20): `TBPJSSLu1mUcX54g9UyxUohYGf2fuRvbwd`
- USDT (ERC20): `0x25CAED3776Ef5b18E03392bC5b254Bbd78E8180C`
- USDT (SOL): `3qgN5z291CEcj2FUi2Zza5DioxKgNw72kC7P52pCcTrG`

## Lisans

MIT — bkz. [LICENSE](LICENSE).
