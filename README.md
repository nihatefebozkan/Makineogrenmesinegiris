# Üniversite Veri Analizi Projesi

Bu proje, üniversite veri seti üzerinde yapılan analizleri ve görselleştirmeleri içerir.  
Analizler, **Teaching** skoru ile **Research Score** arasındaki ilişki, sayısal değişkenler arasındaki korelasyonlar, ve ülkeler bazında **Overall Score** ortalamalarının değerlendirilmesi üzerine odaklanmaktadır.  

---

## 1. Teaching ve Research Score Arasındaki İlişki

<img src="images/lineerregresyon.png" alt="Lineer Regresyon Grafiği" width="700">

**Analiz Yorumları:**
- Scatter plot ve regresyon çizgisi, `Research Score` ile `Teaching` arasında **pozitif doğrusal bir ilişki** olduğunu gösteriyor.  
- Eğim pozitif; yani araştırma skoru arttıkça öğretim skoru da artıyor.  
- Bu, yüksek araştırma performansına sahip üniversitelerin genellikle öğretim kalitesi açısından da güçlü olduğunu işaret ediyor.  
- Veri noktalarındaki dağılım, bazı üniversitelerin ortalamanın üzerinde performans gösterdiğini, bazılarının ise daha düşük seviyelerde olduğunu gösteriyor.  
- Regresyon çizgisi ile birlikte, genel trend ve uç değerler kolayca gözlemlenebilir.  

---

## 2. Sayısal Değişkenler Arasındaki Korelasyon

<img src="images/korelasyonisiharita.png" alt="Korelasyon Heatmap" width="700">

**Analiz Yorumları:**
- Heatmap, veri setindeki tüm sayısal skorlar arasındaki Pearson korelasyon katsayılarını renk ve sayılarla gösteriyor.  
- `Teaching` ve `Research Score` arasında yüksek pozitif korelasyon (r ≈ 0.85) var; bu iki metrik genellikle birlikte artıyor.  
- `Industry Income` ve `International Outlook` gibi bazı sütunlar ile diğer metrikler arasında daha zayıf ilişkiler mevcut.  
- Korelasyon sayıları ve renkler, hangi metriklerin birbirini güçlü etkilediğini anlamak için oldukça faydalı.  
- Bu analiz, veri setindeki değişkenler arasındaki bağımlılıkları ve ilişkisel yapıyı ortaya koyar.  

---

## 3. Ülke Bazında Ortalama Overall Score

<img src="images/ortalamagrafik.png" alt="Ülke Bazında Overall Score Grafiği" width="700">

**Analiz Yorumları:**
- Çizgi grafikte ülkeler X ekseninde, ortalama `Overall Score` değerleri Y ekseninde gösteriliyor.  
- Grafiğe bakarak hangi ülkelerin üniversite performansının yüksek olduğu rahatça görülebiliyor.  
- Üst sıralarda genellikle ABD ve İngiltere gibi ülkeler yer alıyor; bazı ülkeler ise ortalamanın altında kalıyor.  
- Bu sonuçlar, eğitim ve araştırma kalitesinin ülkesel farklılıklarını görselleştiriyor ve uluslararası karşılaştırmalar için fikir veriyor.  
- Grafikteki noktaların dağılımı ve trend çizgisi, genel performans seviyelerini hızlıca özetlemeye yarıyor.  

---

## Sonuç

- **Teaching** ve **Research Score** arasında anlamlı bir pozitif ilişki var; araştırma performansı öğretim kalitesiyle ilişkili.  
- Korelasyon analizi, veri setindeki metriklerin birbirini nasıl etkilediğini ve hangi metriklerin bağımsız hareket ettiğini gösteriyor.  
- Ülke bazında Overall Score grafikleri, ülkeler arasındaki ortalama performans farklarını görselleştirerek uluslararası eğitim kalite karşılaştırması yapmayı kolaylaştırıyor.  
- Bu proje, veri analizi ve görselleştirme tekniklerini bir arada sunarak, üniversite performansına dair içgörüler üretmeyi amaçlıyor.  

---

## Lisans

Bu proje MIT Lisansı altında paylaşılmıştır; dilediğiniz gibi inceleyebilir, geliştirebilir ve paylaşabilirsiniz.
