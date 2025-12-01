# Google Play Store Apps – Exploratory Data Analysis (EDA)

Bu proje, **Google Play Store** üzerindeki uygulamalara ait verilerin temizlenmesi, düzenlenmesi ve keşifsel veri analizi (EDA) adımlarını içermektedir.  
Amaç; veri setindeki eksik değerleri işlemek, kategori bazında uygulama davranışlarını incelemek ve kullanıcı eğilimlerini ortaya çıkarmaktır.

---

## Veri Seti Hakkında

Kullanılan veri seti:

- **googleplaystore.csv**
- Google Play Store üzerindeki uygulamalara dair:
  - **App** — Uygulama adı  
  - **Rating** — Derecelendirme  
  - **Category** — Kategori  
  - **Reviews** — Kullanıcı yorum sayısı  
  - **Size** — Uygulama boyutu  
  - **Installs** — İndirme sayısı  
  - **Price** — Fiyat  
  - **Content Rating** — İçerik derecesi  
  - **Last Updated** — Son güncellenme tarihi  
  - **Android Ver** — Minimum Android sürümü  

---

## Veri Temizleme (Data Cleaning)

Projede yapılan veri temizleme adımları:

### Eksik verilerin tespiti ve işlenmesi
- Eksik `Size`, `Price`, `Reviews`, `Android Ver` değerleri ele alındı  
- Hatalı satırlar silindi (ör. index **10472**)  

### Veri tiplerinin dönüştürülmesi
- `Reviews` → int  
- `Installs` → int  
- `Price` → float  
- `Size` → float (M → KB dönüşümü)  
- `Last Updated` → datetime  

### Karakter temizliği
- `Installs`: `"+"`, `","` kaldırıldı  
- `Price`: `"$"` kaldırıldı  
- `Size`: `"M"` → `"000"`, `"k"` → `""`  
- `"Varies with device"` → NaN  
- `Android Ver` içindeki `"and up"` kaldırıldı, gereksiz karakterler temizlendi  

### Tekrar eden uygulamaların kaldırılması
- `App` alanına göre duplicate satırlar silindi  

---

## Keşifsel Veri Analizi (EDA)

Proje kapsamında yapılan analizler:

### Sayısal değişkenlerin dağılımları
- KDE (density) grafikler ile incelendi  

### Kategorik değişkenlerin dağılımları
- `Type`, `Category`, `Content Rating` için countplot çizildi  

### Kategorilere göre toplam indirme sayıları
- Kategorilerin toplam indirme miktarları hesaplandı  
- İlk 10 kategori barplot ile görselleştirildi  

### Popüler kategorilerde en çok indirilen uygulamalar
- `GAME`, `COMMUNICATION`, `TOOLS`, `PRODUCTIVITY`, `SOCIAL` için  
  en çok indirilen **top 5 uygulama** ayrı grafiklerde gösterildi  

### Rating değeri 5 olan uygulamalar
- Rating’i 5 olan uygulamalar filtrelendi ve analiz edildi  

---

## Kullanılan Teknolojiler
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Google Colab  

---

## Notebook

Bu repo içerisinde proje boyunca kullanılan Colab notebook'u bulunmaktadır:

**`GooglePlayApps.ipynb`**

---

## Sonuç

Bu çalışma, Google Play Store uygulamalarının:

- Kullanıcı davranışlarını  
- Kategori bazında trendlerini  
- Fiyat–indirme ilişkilerini  
- Güncellenme tarihinin etkisini  
- En popüler uygulamaları  

anlamaya yönelik kapsamlı bir veri analizi projesidir.

---

