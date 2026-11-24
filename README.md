# Deniz Ailesi Derneği – Gelir/Gider ve Aidat Takibi

Tek dosyalık (`index.html`), sunucusuz bir web uygulaması. Telefonda "Ana ekrana ekle" ile uygulama gibi kullanılabilir (PWA). GitHub Pages üzerinde yayınlanır.

## Özellikler
- Gelir / gider kaydı; kategori, ödeme yöntemi, açıklama ve belge (dekont/fotoğraf) ekleme
- TL, USD, EUR, GBP ve gram altın; kayıt anındaki kur saklanır
- Üye listesi (ad soyad, baba adı, telefon, üyelik/çıkış tarihi), aylık aidat takibi, borç hesabı, WhatsApp hatırlatma
- Günlük / aylık / yıllık / özel tarih raporları, yazdırma
- Excel (içe/dışa aktarma) ve JSON tam yedek
- Özel kategoriler (Üyelik Aidatı kategorisi silinemez)

## Veri nerede tutulur?
Veriler tarayıcının yerel deposunda (localStorage) durur. **Google Drive bağlanırsa** aynı veri Drive'daki "Deniz Ailesi Derneği Yedekleri" klasörüne `deniz-dernek-yedek.json` olarak yazılır (değişiklikten ~4 sn sonra otomatik).

- Drive'daki yedek daha yeniyse uygulama açılışta sorar: Tamam = bu cihazdaki veri Drive'dakiyle değişir, İptal = bu cihaz korunur ve Drive güncellenir.
- Her şey tek bir dosyada olduğu için aynı anda iki cihazda farklı değişiklik yapmayın; son yazan kazanır.
- Düzenli olarak **Ayarlar → JSON yedek** ile bilgisayarınıza da yedek alın. (Excel yedeği üyeleri ve belgeleri içermez.)
- Belgeler: resimler otomatik 1600 px'e küçültülür, PDF en fazla 2 MB. Tarayıcı deposu yaklaşık 5 MB olduğundan çok belge eklenirse "kaydedilemedi" uyarısı çıkabilir; belgeleri sık sık Drive'a yedekleyin.

## Google Drive kurulumu
1. Google Cloud Console'da proje açın, **Google Drive API**'yi etkinleştirin.
2. OAuth ekranını yapılandırın; kendinizi test kullanıcısı olarak ekleyin.
3. **OAuth istemci kimliği (Web uygulaması)** oluşturun; "Yetkili JavaScript kaynağı" olarak sitenizin adresini ekleyin (örn. `https://KULLANICI.github.io`).
4. Uygulamada Ayarlar → Google Drive bölümüne Client ID'yi yapıştırıp **Bağlan**'a basın. Yalnızca uygulamanın kendi oluşturduğu dosyalara erişir (`drive.file`).

Not: Drive girişi `file://` ile çalışmaz; siteyi GitHub Pages (https) üzerinden açın. Chrome veya Safari önerilir.

## Yayınlama (GitHub Pages)
1. Bu klasördeki tüm dosyaları depo köküne yükleyin.
2. Settings → Pages → Branch: `main` / `(root)`.
3. Güncelleme yayınlarken `sw.js` içindeki `CACHE_NAME` değerini artırın.

## Dosyalar
`index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon-32.png` — hepsi depo kökünde.

## Çevrimdışı
Uygulama kabuğu önbelleğe alınır; ancak yazı tipleri ve Excel kütüphanesi (CDN) internet gerektirir. Çevrimdışıyken kayıt ekleme çalışır, Excel işlemleri ve Drive/kur güncellemesi çalışmaz.
