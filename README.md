# DNS Hızlı

Tek dokunuşla hızlı ve şifreli DNS. Reklam ve izleyici engelleme. Android 8.0 (API 26) ve üzeri.

## Sürüm 1.10.0 — ne yeni?

- **DPI atlatma** (isteğe bağlı): bazı sitelerin engellenmesini aşmaya çalışır. Bağlantının ilk paketini
  parçalara böler (TLS kaydı bölme, TCP bölme, HTTP başlık oyunları, düşük TTL). Hangi yöntemin işe yaradığını
  siteye göre hatırlar.
- **Reklam+** (isteğe bağlı): DNS'ten bağımsız ikinci katman. Site adına bakıp reklam ve izleyici sunucularına
  giden bağlantıları keser, sistemin düz DNS sorgularını yerelde cevaplar, QUIC (UDP/443) trafiğini düşürür ve
  DNS atlatan şifreli DNS'leri (DoT/DoH) kapatır.
- **Üç bağımsız düğme:** ana ekrandaki küre (DNS), DPI atlatma ve Reklam+ birbirinden bağımsız çalışır. Üçü
  aynı anda, ikisi ya da yalnızca biri açık olabilir. Reklam+, başka bir DNS sağlayıcısına bağlıyken de çalışır.
- **Güvenlik vanası:** modüller bir bağlantı sorununa yol açarsa kendiliğinden kapanır ve bunu bildirir.
- **QUIC'i engelle** ayarı (varsayılan açık).
- Kartlarda engellenen ve bölünen bağlantı sayacı.
- İlk açılış bilgilendirmesi, 12 dilde, yeni modüllerin ne yaptığını ve trafiğin nereye gitmediğini anlatır.

Modüller **varsayılan kapalıdır**. Açmadan önce DNS Hızlı yalnızca DNS sorgularını yönlendirir, eskisi gibi.

## Bilinen sınırlar

- DPI atlatma, şifreli SNI (ECH) kullanan sitelerde işe yaramaz. IP engelini ve DNS zehirlemesini tek başına
  çözmez.
- Başka bir VPN uygulamasıyla aynı anda çalışmaz (Android'de aynı anda tek VPN olabilir).
- HTTPS içindeki sayfa ve video reklamlarını göremez; reklam engelleme alan adı düzeyindedir.
- Modüller yeni ve **henüz gerçek cihazda kapsamlı denenmedi**. Sorun yaşarsan bildir.

## Gizlilik

Hesap yok, kişisel veri toplanmaz, reklam ve analitik yok. Site adları kaydedilmez. Modüller açıkken trafik
yalnızca telefonun içindeki aktarıcıdan geçer; hiçbir sunucuya gönderilmez. Ayrıntı: GIZLILIK.md.

## Kurulum ve derleme

- Derleme GitHub Actions ile yapılır: **Actions → APK derle → Run workflow**. Bitince çalıştırma sayfasının
  altındaki *dns-hizli-apk* dosyasından APK'yı indir.
- Ayrıntılar: OKUBENI.md. Yol haritası: YOLHARITASI.md. Sürüm geçmişi: DNS_HIZLI_TARIHCE.txt.
