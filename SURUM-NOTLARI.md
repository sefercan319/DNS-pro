# DNS Hızlı 1.10.0 — Sürüm notları

**Yeni: DPI atlatma ve Reklam+ (isteğe bağlı modüller, varsayılan kapalı)**

- Ana ekranda küreden sonra iki yeni kart: DPI atlatma ve Reklam+. Her biri ayrı açılır/kapanır; DNS ile birlikte,
  tek başına ya da üçü birden çalışabilir.
- DPI atlatma: bağlantının ilk paketini parçalara bölerek bazı engellenen sitelere erişmeyi dener. Hangi yöntemin
  işe yaradığını siteye göre öğrenir.
- Reklam+: DNS'ten bağımsız reklam ve izleyici engelleme, düz DNS sorgularını yerelde cevaplama, QUIC'i ve
  DNS atlatan şifreli DNS'leri (DoT/DoH) engelleme.
- Bağlantı sorunu olursa modüller kendiliğinden kapanır ve bildirilir.
- Bağlantı ayarlarına "QUIC'i engelle" eklendi (varsayılan açık).

**İyileştirmeler**

- Modül kartlarında engellenen ve bölünen bağlantı sayacı.
- Yerel ağ yayın paketleri (mDNS, SSDP) tünele alınmıyor.
- Ayarları dışa aktarma kodu modül durumunu taşımaz (cihaza özgü).

**Bilinen sınırlar**

- Şifreli SNI (ECH) kullanan sitelerde DPI atlatma ve alan adı engeli çalışmaz.
- Başka bir VPN uygulamasıyla aynı anda çalışmaz.
- Modüller yeni; gerçek cihazda geniş kapsamlı denemesi henüz yapılmadı. Sorun olursa lütfen bildir.

**Gizlilik**

- Hesap, kişisel veri toplama, reklam ve analitik yok. Modüller açıkken trafik yalnızca cihaz içindeki
  aktarıcıdan geçer, hiçbir sunucuya gönderilmez. Site adları kaydedilmez.
