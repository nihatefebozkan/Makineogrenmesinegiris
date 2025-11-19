# Üniversite Veri Analizi Projesi

Bu proje, üniversite performans veri seti üzerinde yapılan analizleri ve görselleştirmeleri içerir.  
Özellikle eğitim ve araştırma skorları arasındaki ilişki, sayısal metrikler arasındaki korelasyon ve ülke bazında Overall Score ortalamaları incelenmektedir.

---

## Proje Amacı
Bu projenin amacı:
- Üniversite performans verilerini analiz ederek eğitim ve araştırma skorları arasındaki ilişkileri anlamak.  
- Sayısal değişkenler arasındaki korelasyonları belirlemek.  
- Ülkeler bazında ortalama performans farklılıklarını görselleştirmek.  

Proje, veri analizi ve görselleştirme adımlarını birleştirerek üniversite performansına dair içgörüler üretmeyi hedefler.

---

## Veri Seti
- **Format:** CSV  
- **Özellikler:**
  - `Location` → Üniversitenin bulunduğu ülke  
  - `Teaching` → Öğretim kalitesi skoru  
  - `Research Score` → Araştırma performans skoru  
  - `Overall Score` → Genel performans  
  - Diğer sayısal skorlar: Industry Income, International Outlook vb.

---

## Veri İşleme Adımları
1. **Veri Yükleme:** CSV dosyası okunmuş ve ilk birkaç satır görüntülenmiştir.  
2. **Sütun Seçimi:** `Teaching` ve `Research Score` sütunları seçilmiş ve sayısala dönüştürülmüştür.  
3. **Eksik Veri Temizliği:** Analiz için gerekli sütunlarda eksik veriler çıkarılmıştır.  
4. **Korelasyon Analizi:** Sayısal tüm sütunlar arasındaki Pearson korelasyon katsayıları hesaplanmış ve ısı haritası ile görselleştirilmiştir.  
5. **Ülke Bazlı Ortalama:** `Overall Score` değerleri ülke bazında gruplanmış ve ortalama skorlar çizgi grafiği ile görselleştirilmiştir.

---

## Kullanılan Model
### Lineer Regresyon
- **Kullanım Alanı:** `Research Score` ile `Teaching` arasındaki ilişkiyi analiz etmek.  
- **Sebep:** İki sürekli değişken arasındaki doğrusal ilişkiyi anlamak ve genel trendi görselleştirmek için basit, açıklayıcı ve yorumlanabilir bir modeldir.

---

## Görselleştirmeler ve Yorumlar

### 1. Lineer Regresyon: Research → Teaching
<img src="images/lineerregresyon.png" alt="Lineer Regresyon Grafiği" width="700">

**Yorum:**  
- `Research Score` arttıkça `Teaching` skoru da artıyor; pozitif doğrusal ilişki gözlemleniyor.  
- Bu, yüksek araştırma performansına sahip üniversitelerin öğretim açısından da güçlü olabileceğini gösteriyor.  
- Veri noktalarının dağılımı, uç değerler ve genel trend regresyon çizgisi ile anlaşılabiliyor.

### 2. Sayısal Değişkenler Arasındaki Korelasyon
<img src="images/korelasyonisiharita.png" alt="Korelasyon Heatmap" width="700">

**Yorum:**  
- Heatmap, sayısal skorlar arasındaki ilişkileri renk ve sayı ile gösteriyor.  
- `Teaching` ve `Research Score` arasında güçlü bir pozitif korelasyon mevcut (r ≈ 0.85).  
- Bazı metrikler arasında daha zayıf veya negatif korelasyonlar var; bu da değişkenlerin bağımsız olabileceğini gösteriyor.  
- Analiz, hangi skorların birbirini etkilediğini ve hangi metriklerin bağımsız hareket ettiğini ortaya koyuyor.

### 3. Ülke Bazında Ortalama Overall Score
<img src="images/ortalamagrafik.png" alt="Ülke Bazında Overall Score Grafiği" width="700">

**Yorum:**  
- Çizgi grafikte her ülkenin ortalama `Overall Score` değeri gösteriliyor.  
- Üst sıralarda ABD ve İngiltere gibi ülkeler yer alıyor, bazı ülkeler ise ortalamanın altında.  
- Bu grafik, ülke bazında eğitim ve araştırma performans farklarını görselleştirmek için kullanışlıdır.  

---

## Sonuç
- `Research Score` ve `Teaching` arasında anlamlı bir pozitif ilişki var; araştırma performansı öğretim kalitesiyle paralel ilerliyor.  
- Korelasyon analizi, değişkenler arasındaki ilişkileri ortaya koyuyor.  
- Ülke bazlı Overall Score grafikleri, ülkeler arasındaki ortalama performans farklılıklarını net bir şekilde gösteriyor.  

> Bu proje, veri analizi ve görselleştirme tekniklerini birleştirerek üniversite performansına dair anlamlı içgörüler sunmayı amaçlamaktadır.

---

## Lisans
Bu proje MIT Lisansı altında paylaşılmıştır. Dilediğiniz gibi inceleyebilir, geliştirebilir ve paylaşabilirsiniz.
