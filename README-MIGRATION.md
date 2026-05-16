# krersn Studio — Yeni Site Yapısı

Yeni studio yapısının dosyaları. GitHub deposuna (`krersn/krersn.github.io`) yükleneceklerdir.

## Yeni dizin yapısı

```
/
├── index.html                       ← TR studio ana sayfası (YENİ)
├── CNAME                            ← krersnstudio.com (kalır)
├── .nojekyll                        ← (kalır)
├── robots.txt                       ← YENİ
├── sitemap.xml                      ← YENİ
├── account-deletion.html            ← Yeni temaya güncellendi (TR + EN)
├── privacy-policy.html              ← Eski URL → yönlendirme
├── terms-of-service.html            ← Eski URL → yönlendirme
│
├── assets/
│   └── style.css                    ← Tüm sayfaların ortak stili
│
├── en/
│   └── index.html                   ← EN studio ana sayfası
│
└── games/
    └── yanik/
        ├── index.html               ← TR Yanık tanıtım sayfası
        ├── privacy.html             ← TR Yanık gizlilik
        ├── terms.html               ← TR Yanık kullanım şartları
        └── en/
            ├── index.html           ← EN Yanık tanıtım
            ├── privacy.html         ← EN Yanık gizlilik
            └── terms.html           ← EN Yanık kullanım şartları
```

## Depoda KORUNACAK dosyalar

Bu dosyalar mevcut depodaki halleriyle bırakılır:

- `app-ads.txt`
- `google824eec0f5ec91964.html` (Google site doğrulaması)
- `README.md`

## Depodan KALDIRILACAK dosyalar — YOK

Hiçbir mevcut dosya silinmiyor:
- `privacy-policy.html` → yeni içerikle **değiştirildi** (artık yönlendirme yapıyor)
- `terms-of-service.html` → yeni içerikle **değiştirildi** (artık yönlendirme yapıyor)
- `account-deletion.html` → yeni içerikle **değiştirildi**
- `index.html` → tamamen yeni içerikle **değiştirildi**

## Yükleme adımları

1. Bu zip'i aç, içindeki tüm dosyaları (klasörler dahil) GitHub deposuna yükle (`krersn/krersn.github.io` reposunun kök dizinine).
2. Aynı isimde olan dosyalar üzerine yazılacak — endişe etme, yenisi daha iyi.
3. Commit + push.
4. 1-2 dakika içinde site `krersnstudio.com` adresinde yayında.

## Migration sonrası yapılacaklar

### 1. Search Console'da Yeniden Doğrulama

- Search Console → "URL Inceleme" → her bir yeni URL'i tek tek ekle ve "Dizine eklenmeyi iste"
- Önemli URL'ler:
  - `https://krersnstudio.com/`
  - `https://krersnstudio.com/en/`
  - `https://krersnstudio.com/games/yanik/`
  - `https://krersnstudio.com/games/yanik/en/`
  - `https://krersnstudio.com/games/yanik/privacy.html`
  - `https://krersnstudio.com/games/yanik/terms.html`

### 2. Sitemap'i Search Console'a tanıt

- Search Console → Sitemaps → "Yeni site haritası ekle" → `sitemap.xml` yaz → Gönder

### 3. (İsteğe bağlı) Google Play Console linkleri

Eğer Play Console'da uygulamanın gizlilik linki olarak `privacy-policy.html` verdiysen, BÖYLE BIRAK — yönlendirme çalışır.
Yine de istersen daha temiz olması için Play Console'daki URL'leri güncelle:
- Privacy URL → `https://krersnstudio.com/games/yanik/privacy.html`
- (Play Console terms URL alanı varsa) → `https://krersnstudio.com/games/yanik/terms.html`

### 4. Yanık oyununun gerçek web sürümü (eski index.html)

Yüklediğin React tabanlı Yanık oyununu (büyük HTML dosyası) web'de oynanır halde sunmak istersen, onu `games/yanik/play/index.html` yoluna koyabilirsin. Tanıtım sayfasından buton ile bağlanır. İstersen bir sonraki adımda bunu da kurabiliriz.

## Gelecek: Yeni oyun eklemek

"Yanık Online" veya yeni bir oyun eklediğinde:

1. `games/yanik-online/` klasörü oluştur
2. İçine `index.html`, `privacy.html`, `terms.html` ve `en/` alt klasörünü kopyala
3. İçeriği o oyuna uyarla
4. Studio ana sayfasındaki `coming` kartını `game-card` link yap
5. `sitemap.xml`'e yeni URL'leri ekle

Yapı tamamen kopyalanabilir; her oyun aynı şablonu takip eder.
