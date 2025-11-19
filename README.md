# Üniversite Veri Analizi

Bu proje, üniversite veri seti üzerinde temel veri analizi ve görselleştirme işlemleri yapmaktadır. 

Özellikle:
- `Teaching` ve `Research Score` arasındaki ilişkiyi lineer regresyon ile analiz eder.
- Ülkeler bazında `Overall Score` ortalamalarını görselleştirir.
- Tüm sayısal skor sütunlarının korelasyonlarını ısı haritası ile gösterir.

---

## Kod Açıklaması

### 1. Veri Yükleme ve Temizlik
- `Teaching` ve `Research Score` sütunları seçilir ve sayısal hale dönüştürülür.
- Eksik veya hatalı veriler temizlenir.

### 2. Lineer Regresyon
- `Research Score` bağımsız değişken, `Teaching` bağımlı değişken.
- Scatter plot ile veri ve regresyon çizgisi görselleştirilir.
- Eğim ve kesişim hesaplanır.

### 3. Ülke Bazında Ortalama Overall Score
- Her ülke için ortalama `Overall Score` hesaplanır ve çizgi grafiği ile gösterilir.

### 4. Korelasyon Isı Haritası
- Tüm sayısal sütunların korelasyonu hesaplanır.
- Isı haritası ile görselleştirilir ve hücrelerde korelasyon değerleri gösterilir.

---

## Sonuç
- `Teaching` ve `Research Score` arasında doğrusal ilişki gözlemlenebilir.
- Ülkeler bazında ortalama `Overall Score` karşılaştırılabilir.
- Korelasyon ısı haritası, tüm skor metriklerinin birbirleriyle olan ilişkilerini görselleştirir.
