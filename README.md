# Fizmo

İnteraktif fizik simülasyonları. Her deney tek bir HTML dosyası; tarayıcıda açılır, kurulum gerekmez.

## Deneyler

| # | Deney | Dosya | Ne öğretiyor |
|---|-------|-------|--------------|
| 01 | Basit Sarkaç | `index.html` | Periyot ip boyuna ve g'ye bağlı, kütleye bağlı değil; büyük açıda küçük açı formülü sapıyor |

## Nasıl çalışıyor

- **3B sahne:** [Three.js](https://threejs.org) (WebGL). Sehpa, ip, top, açıölçer ve kuvvet okları tarayıcıda çiziliyor.
- **Fizik:** Hareket denklemi θ'' = −(g/L)·sin θ − γ·θ', küçük açı yaklaşımı yapılmadan RK4 yöntemiyle 2 ms'lik adımlarla çözülüyor. Ekrandaki "ölçülen periyot" gerçekten simülasyondan ölçülüyor (sıfırdan geçişler arası süre), formülden kopyalanmıyor.
- **Etkileşim:** Topu sürükleyerek açı ayarlanıyor, boş alanı sürükleyerek kamera döndürülüyor. Deneyler listesi, ziyaretçi ilgili ayarı değiştirince işaretlenip açıklamayı gösteriyor.
- **Grafik ve enerji:** Açı–zaman grafiği 2D canvas'ta, enerji çubukları kinetik ve potansiyel enerjinin birbirine dönüşmesini gösteriyor.

## Yerelde açmak

Dosyayı doğrudan tarayıcıda açabilirsin. Three.js ve yazı tipleri internetten (jsDelivr, Google Fonts) yüklendiği için bağlantı gerekir.

```bash
npx serve .   # ya da: python3 -m http.server
```

## Yayınlamak

GitHub Pages ile ücretsiz: depo ayarları → Pages → "Deploy from a branch" → `main` / root. Site `https://<kullanıcı-adı>.github.io/Fizmo/` adresinde açılır.

## Yeni deney eklemek

Claude'a verilebilecek örnek istek:

> Fizmo için yeni bir deney yap: **eğik atış**. `index.html`'deki sarkaç deneyiyle aynı yapıyı ve görsel dili kullan (sol ders kartı, sağ ayar paneli, alt ölçüm şeridi, Three.js sahnesi). Ayarlar: ilk hız, atış açısı, yerçekimi, hava direnci. Ölçümler: menzil, uçuş süresi, maksimum yükseklik (simülasyondan ölçülen ve formülden hesaplanan yan yana). Deneyler: "45° neden en uzağa gider?", "Hava direnci açınca en iyi açı değişiyor mu?". Fiziği gerçek denklemlerle çöz, telefonda da çalışsın.

İyi sonuç için: konuyu, ayarlanacak değişkenleri, gösterilecek ölçümleri ve ziyaretçinin kendisinin keşfetmesini istediğin 3–4 "aha" anını yaz.
