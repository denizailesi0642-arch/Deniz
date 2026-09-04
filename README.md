# Deniz Ailesi Derneği — Gelir/Gider Takip Uygulaması

Tek dosyalık (HTML/CSS/JS) bir dernek gelir-gider ve üye aidat takip uygulaması. Kurulum gerektirmez, doğrudan tarayıcıda çalışır.

## Canlı Demo
GitHub Pages etkinleştirildikten sonra şu adresten erişilebilir:
`https://KULLANICI_ADIN.github.io/REPO_ADIN/`

## Özellikler
- Gelir/gider hareketleri (döviz ve gram altın birimiyle, TL karşılığı otomatik hesaplanır)
- Üye kayıtları ve aidat takibi (üyeye özel ödeme ekranı, ödeme geçmişi)
- Raporlar (günlük/aylık/yıllık/tarih aralığı), yazdırma ve Excel'e aktarma
- Üye listesini yazdırma / Excel'e aktarma (baba adı dahil)
- TCMB güncel döviz kurları (otomatik veya manuel giriş)
- **Ana ekrana ekleme / uygulama olarak yükleme** (mobil ve masaüstü, çevrimdışı çalışma desteğiyle)

## Ana Ekrana Ekleme / Uygulama Olarak Yükleme
Uygulama bir PWA'dır (Progressive Web App) — normal bir web sitesi gibi tarayıcıda açılır ama telefonda/bilgisayarda gerçek bir uygulama gibi kurulabilir:

- **Android (Chrome/Edge):** Siteyi aç → Ayarlar sayfasında **"Yükle"** butonuna bas (veya tarayıcı menüsünden "Uygulamayı Yükle").
- **iPhone/iPad (Safari):** Siteyi aç → alttaki **Paylaş** simgesine dokun → **"Ana Ekrana Ekle"**.
- **Bilgisayar (Chrome/Edge):** Adres çubuğunun sağındaki kurulum simgesine tıkla, ya da Ayarlar sayfasındaki **"Yükle"** butonunu kullan.

Kurulduktan sonra uygulama kendi simgesiyle ana ekranda/masaüstünde görünür, tam ekran açılır ve **internet olmadan da** son yüklenen haliyle çalışabilir (veriler zaten cihazda saklandığı için).

> Not: GitHub Pages otomatik olarak HTTPS ile yayın yaptığı için PWA kurulumu (manifest + service worker) sorunsuz çalışır. Dosyayı sadece bilgisayarınızda `file://` ile açarsanız (GitHub Pages olmadan) "yükleme" özelliği çalışmayabilir; bunun için siteye HTTPS üzerinden (GitHub Pages linkinden) erişmeniz gerekir.

## Veri Saklama Hakkında ÖNEMLİ NOT
Bu uygulama verileri **tarayıcının localStorage'ında**, yalnızca kullanıldığı cihaz + tarayıcıya özel olarak saklar.
- Farklı bir cihaz veya tarayıcıdan açıldığında veriler **görünmez** (ortak/bulut senkronizasyonu yoktur).
- Tarayıcı geçmişi/verileri temizlenirse kayıtlar **kalıcı olarak silinir**.
- Bu nedenle **Ayarlar > Tüm Verileri Dışa Aktar** ile düzenli Excel yedeği almanız ve dernek üyeleriyle bu dosyayı paylaşmanız önerilir. Aynı Excel şablonuyla başka bir cihaza **İçe Aktar** yapılabilir.

## Yerel Olarak Çalıştırma
Sadece `index.html` dosyasını bir tarayıcıda açmanız yeterlidir. Sunucu veya kurulum gerekmez. (PWA kurulum/yükleme özelliği için HTTPS üzerinden — yani GitHub Pages linkinden — açmanız gerekir, bkz. yukarıdaki not.)

## Repo Dosya Yapısı
```
index.html            → Ana uygulama (tüm HTML/CSS/JS tek dosyada)
manifest.json         → PWA kurulum bilgileri (isim, ikon, renkler)
sw.js                 → Service worker (çevrimdışı çalışma / önbellekleme)
icons/                → Uygulama ikonları (farklı boyutlarda)
```

## Güncelleme
Kodu düzenledikten sonra değişiklikleri GitHub'a `git push` ile gönderin; GitHub Pages birkaç dakika içinde otomatik günceller. Service worker eski dosyaları önbelleğe aldığı için, güncelleme sonrası kullanıcıların bazen sayfayı **iki kez yenilemesi** (veya "Ana ekrana eklenmiş" uygulamayı kapatıp yeniden açması) gerekebilir.
