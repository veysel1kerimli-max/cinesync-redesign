# Platform bağlantı desteği ve sınırlar

## YouTube

- [YouTube IFrame Player API](https://developers.google.com/youtube/iframe_api_reference) web sayfasına YouTube oynatıcısı gömmeyi ve JavaScript ile video kuyruğa alma, oynat/duraklat, ses ayarı ve oynatıcı olaylarını yönetmeyi destekler.
- Google'ın dokümanında gömülü oynatıcı için en az 200×200 piksel görünüm şartı ve 16:9 için 480×270 piksel önerisi yer alır. Bazı videolar sahibinin ayarı, yaş/ülke veya YouTube koşulları nedeniyle gömülü oynatılmayabilir; bu durumda doğrudan YouTube bağlantısı alternatif olmalıdır.
- Bu prototip YouTube URL'sini resmi privacy-enhanced `youtube-nocookie.com` iframe oynatıcısına çözer. Oynatma bu cihazda yapılır; oda üyeleri arasında senkronizasyon bu prototipte kurulmaz.

## Vimeo, doğrudan video ve web sayfaları

- Vimeo bağlantıları `player.vimeo.com` oynatıcısına; MP4/WebM/OGG bağlantıları tarayıcının kendi `<video>` oynatıcısına dönüştürülür.
- Diğer HTTPS sayfaları mini iframe içinde denenebilir. Giriş, video oynatma, çerezler ve üçüncü taraf sayfa davranışları kaynak siteye ve tarayıcıya bağlıdır. Prototip sayfanın içeriğini okuyamaz veya site hesabı parolalarını saklamaz.

## Abonelikli yayın servisleri

- [MDN: X-Frame-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options) `DENY` ve `SAMEORIGIN` başlıklarının sayfaların başka bir sitede iframe içinde açılmasını engelleyebildiğini açıklar.
- [MDN: CSP `frame-ancestors`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Content-Security-Policy/frame-ancestors) sayfanın hangi üst kaynaklarda gömülebileceğini belirler; eşleşmeyen çerçeve isteği tarayıcı tarafından iptal edilir.
- [Netflix'in desteklenen tarayıcıları](https://help.netflix.com/en/node/30081) listesi, bir hizmetin kendi desteklediği üst düzey tarayıcı/cihaz gereksinimlerini ayrıca yönetebildiğini gösterir.
- Bu nedenle Netflix, Prime Video, Disney+, Max ve benzeri sitelerde uygulama içi giriş/oynatmayı garanti etmek veya bu sınırları aşmak mümkün değildir. Prototip, site linkini yeni sekmede açma ve tarayıcının ekran paylaşım izni varsa yerel ön izleme sunar. DRM korumalı içerik ekran paylaşımında siyah görüntü verebilir.

## Bağımsız ve güvenli davranış

Giriş bilgileri hiçbir zaman CineSync arayüzüne istenmez veya uygulama tarafından kaydedilmez; kullanıcı resmi hizmet alan adına yönlendirilir. Prototipte ekran paylaşımı yalnızca bu cihazda ön izlenir; diğer oda üyelerine aktarılmaz. Gerçek ortak izleme için özgün oda/RTCP/WebRTC servisi ve kaynak platformun izin verdiği entegrasyon gerekir.
