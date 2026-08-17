### 🌓 OTOMATİK TEMA SİSTEMİ (CSS YALNIZCA)

Siteye sıfır JavaScript bağımlılığı ile, kullanıcının işletim sistemi veya tarayıcı ayarlarına göre otomatik değişen Light/Dark Mode ekle. 

Tüm renk hiyerarşisini `:root` ve `@media (prefers-color-scheme: light)` kullanarak CSS değişkenleri (CSS Custom Properties) üzerinden yönet:

```css
/* Varsayılan Tema: Dark Mode */
:root {
  --bg-main: #0f0f12;
  --bg-card: #1a1a20;
  --bg-card-hover: #22222b;
  --border-color: #2a2a35;
  --text-main: #ededed;
  --text-muted: #9e9ea8;
  --accent: #e53935;
  --accent-hover: #ff5252;
  --badge-bg: rgba(229, 57, 53, 0.15);
  --shadow-color: rgba(0, 0, 0, 0.5);
}

/* Kullanıcı Sistemi/Tarayıcısı Açık Tema İse: Light Mode */
@media (prefers-color-scheme: light) {
  :root {
    --bg-main: #f8f9fa;
    --bg-card: #ffffff;
    --bg-card-hover: #f1f3f5;
    --border-color: #e5e7eb;
    --text-main: #18181b;
    --text-muted: #6b7280;
    --accent: #d32f2f;
    --accent-hover: #b71c1c;
    --badge-bg: rgba(211, 47, 47, 0.1);
    --shadow-color: rgba(0, 0, 0, 0.08);
  }
}
```

**Uygulama Kuralları:**
1. Kodda hiçbir elemente statik renk verme (`background: #000` veya `color: white` gibi).
2. Tüm arka plan, metin, border, hover ve buton renklerini `var(--degisken-adi)` şeklinde ata.
3. Light modda kartlara hafif bir `box-shadow: 0 4px 12px var(--shadow-color)` vererek beyaz zeminde öne çıkmasını sağla.
4. Buton veya JS ile tema değiştirme kodu ekleme; geçiş tamamen `prefers-color-scheme` medya sorgusu üzerinden otomatik çalışsın.