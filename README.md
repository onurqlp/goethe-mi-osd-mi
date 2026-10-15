# AYDA V5 UI — Goethe A1 / ÖSD A1 — Son sürüm

Kullanıcının sağladığı AYDA ANA SAYFA V5 tasarımı uygulanmıştır: dosyadaki gerçek logo, lacivert #102541 / #0b1b31, altın #e8c37b, krem #fbf7ef ve açık mavi #edf5fb yüzeyler; duyuru şeridi, mobil kısa menü ve kurumsal alt bölüm. Tasarım uyarlaması `public/assets/ayda-v5.css` dosyasındadır. PHP dosyasındaki WordPress kurulum talimatları uygulanmamıştır; bu paket GitHub Pages için statik HTML sürümüdür.

Bu sürüm derlendi; 1440 px masaüstü ve 390 px mobil görünümü tarayıcıda incelendi. 390 px görünümde yatay taşma görülmedi. Ekran görüntüleri `preview/` klasöründedir. GitHub üzerinde yayın yapılmadı.

GitHub Pages için hazırlanmış, bağımlılıksız statik web sitesi. 11 görev karşılaştırması, 8 SSS, görsel büyütme ve 5 soruluk format seçici içerir.

## GitHub'a yükleme

1. GitHub'da yeni bir repository oluşturun.
2. ZIP'i çıkarın. **İçindeki dosya ve klasörleri doğrudan repository köküne yükleyin.** ZIP dosyasını veya dış klasörü yüklemeyin. `.github/workflows/pages.yml` dosyasının da yüklendiğinden emin olun.
3. **Settings → Pages → Build and deployment → Source: GitHub Actions** seçin.
4. **Actions → Publish GitHub Pages → Run workflow** ile yayını başlatın. Sonraki `main` veya `master` güncellemelerinde otomatik yayınlanır.
5. Yayın adresi başarılı workflow'un `github-pages` ortamında ve Settings → Pages ekranında görünür.

GitHub kullanıcı adı veya repo adı kodda elle yazılmaz. Workflow gerçek Pages adresini alır; canonical, paylaşım, sosyal görsel ve sitemap URL'lerini depo alt dizinine göre oluşturur. Özel alan adı Pages ayarlarında tanımlanmışsa o adres kullanılır. GitHub hesabına bu çalışma sırasında yükleme/yayın yapılmadı.

Resmî kurulum belgesi: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages

## Bilgisayarda açma

Hazır önizleme: `dist/index.html` dosyasını açın. GitHub Actions `dist/` klasörünü kaynaklardan yeniden üretir; Git ile gönderirken bu klasörün dışarıda bırakılması normaldir.

Node.js **24** ile:

```sh
npm run build
npm run dev
```

Yerel adres: http://127.0.0.1:4173/goethe-osd-a1-karsilastirma/

`npm install` gerekmez. Yerel derlemede `site.config.json` içindeki localhost adresi kullanılır; GitHub yayını sırasında gerçek adres otomatik uygulanır.

## Dosyalar

- `src/`: HTML şablonu ve karşılaştırma içerikleri.
- `public/assets/`: CSS, JS, WebP görselleri.
- `scripts/build.mjs`: statik üretim ve Pages URL uyarlaması.
- `site.config.json`: bağlantılar, SEO, analitik ve reklam ayarları.
- `.github/workflows/pages.yml`: otomatik yayın.
- `tests/`: mevcut format seçici testleri. İstenirse `npm test` ve `npm run lint` ile çalıştırılır.

## SEO ve servis ayarları

Arama motoru indekslemesi başlangıçta kapalıdır. Yayın indekslenebilecek duruma geldiğinde `site.config.json` içinde `indexable: true` yapıp commit edin. Meta robots ve robots.txt yeniden üretilir. GitHub proje sitelerinde repo altındaki robots.txt alan adının kökündeki robots.txt yerine geçmez; sayfanın meta robots ayarı ayrıca bulunur.

AYDA kurs, materyal, WhatsApp ve gerçek A1 seviye testi bağlantıları hazırdır. Ücretsiz tam deneme adresi doğrulanmadığı için `links.mockExam` boştur. GA4, AdSense ve Search Console kimlikleri verilmemiştir; analitik ve reklamlar kapalıdır. Bunları `site.config.json` üzerinden ayarlayın. Reklam yüklemesi ayrıca uygun CMP entegrasyonu ve onayı gerektirir. Hiçbir gizli anahtarı bu dosyaya koymayın; statik dosyalar ziyaretçilere açıktır.

Kaynak görseller kullanıcının verdiği sunumdaki resmî model kesitleridir. Kaynaklar sayfada belirtilmiştir; genel kullanıma açmadan önce yeniden yayınlama hakkını değerlendirin. Mevcut AYDA WordPress/React projesi değiştirilmemiştir.

GitHub Actions üzerinde canlı yayın testi yapılmadı; bu paket mevcut çalışan sitenin GitHub Pages'e uyarlanmış kaynak sürümüdür. Önceki tarayıcı kontrolleri ve birim testleri önceki sürüm içindir. Lighthouse puanı veya gerçek cihaz performans sonucu iddia edilmez.
