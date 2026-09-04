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

## Veri Saklama Hakkında ÖNEMLİ NOT
Bu uygulama verileri **tarayıcının localStorage'ında**, yalnızca kullanıldığı cihaz + tarayıcıya özel olarak saklar.
- Farklı bir cihaz veya tarayıcıdan açıldığında veriler **görünmez** (ortak/bulut senkronizasyonu yoktur).
- Tarayıcı geçmişi/verileri temizlenirse kayıtlar **kalıcı olarak silinir**.
- Bu nedenle **Ayarlar > Tüm Verileri Dışa Aktar** ile düzenli Excel yedeği almanız ve dernek üyeleriyle bu dosyayı paylaşmanız önerilir. Aynı Excel şablonuyla başka bir cihaza **İçe Aktar** yapılabilir.

## Yerel Olarak Çalıştırma
Sadece `index.html` dosyasını bir tarayıcıda açmanız yeterlidir. Sunucu veya kurulum gerekmez.

## Güncelleme
Kodu düzenledikten sonra değişiklikleri GitHub'a `git push` ile gönderin; GitHub Pages birkaç dakika içinde otomatik günceller.
