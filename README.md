# CineSync — bağlantıyla izleme arayüzü prototipi

Bu, `veysel1kerimli-max/cinesync` reposundan ayrı hazırlanmış bir arayüz prototipidir. İçerik kartları gerçek film kataloğu değildir; kullanıcı kendi video/site bağlantısını verir.

## Çalıştırma ve test

Bu klasörde `npm run start` komutunu çalıştırıp `http://localhost:4173` adresini aç. Ekran/sekme paylaşımı için localhost ya da HTTPS gerekir. `npm test`, JavaScript sözdizimini doğrular.

Ön izlemeler: [masaüstü ana ekran](preview-desktop.png), [masaüstü izleme odası](preview-room.png), [mobil ana ekran](preview-mobile.png), [mobil izleme odası](preview-room-mobile.png) ve [yayın platformu sınır kartı](preview-platform-limits.png).

## Gerçek URL ile izleme

Oda ekranının üstündeki alana YouTube, Vimeo, MP4/WebM/OGG veya başka bir HTTPS site bağlantısı yapıştırıp **Videoyu aç** seç. YouTube linkleri privacy-enhanced YouTube iframe oynatıcısına; Vimeo linkleri Vimeo player'a; doğrudan video dosyaları tarayıcının yerel video oynatıcısına yönlenir. YouTube video başlangıç zamanı da desteklenir. Diğer siteler mini iframe'de denenir; bilinen yayın platformları önce uyarı gösterir, ardından kullanıcı isterse gömülü görünümü deneyebilir veya resmi siteyi yeni sekmede açabilir.

Açık bağlantıyı **Sıraya ekle** ile aynı cihazdaki demo kuyruğuna alabilir, sıra panelinden tekrar oynatabilirsin. Ekran/sekme paylaşımı tarayıcı izniyle yerel ön izleme başlatır.

## Önemli sınırlar

YouTube/Vimeo/video URL'si gerçek içerik açabilir, ancak oynatma bu prototipte yalnızca kullanıcının cihazında gerçekleşir; gerçek odada senkronizasyon veya diğer katılımcılara aktarım yoktur. Mini tarayıcıdaki giriş ve video davranışı kaynak sitenin iframe, çerez, DRM ve tarayıcı kurallarına bağlıdır. Site gömmeyi engellerse yeni sekme seçeneği kullanılır; herhangi bir kısıtlama aşılmaz. Ekran paylaşımı da bu cihazda kalır ve DRM içeriği siyah görüntü verebilir.

Prototip hiçbir parola istemez veya saklamaz. Sohbet, katılımcılar, odalar, oylama ve video araması gerçek backend'e bağlı değildir. Gerçek ortak izleme için oda servisi, izinli platform entegrasyonu ve senkron/WebRTC katmanı gerekir. Kaynakların teknik sınırları [Platform notları](PLATFORM-LIMITATIONS.md) içinde resmi kaynaklarla açıklanmıştır.

## Orijinal repo ve yayınlama

Orijinal [`veysel1kerimli-max/cinesync`](https://github.com/veysel1kerimli-max/cinesync) deposu değiştirilmedi. Bu bağımsız prototip, yeni ve herkese açık [`veysel1kerimli-max/cinesync-redesign`](https://github.com/veysel1kerimli-max/cinesync-redesign) deposunda tutulur. Bu statik tasarım için production deploy yapılmamıştır.
