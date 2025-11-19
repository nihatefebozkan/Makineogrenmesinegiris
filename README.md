# Üniversite Veri Analizi

Bu proje, üniversite veri seti üzerinde temel veri analizi ve görselleştirme işlemlerini içerir.  
Analizler, öğretim ve araştırma skorları, korelasyon yapısı ve ülke bazlı ortalama skorlar üzerine odaklanmaktadır.

---

## Lineer Regresyon: Research → Teaching

<img src="images/lineerregresyon.png" alt="Lineer Regresyon Grafik" width="700">

  
- Grafikte `Research Score` ile `Teaching` arasında **pozitif doğrusal ilişki** görülüyor.  
- Eğim pozitif olduğu için araştırma skoru arttıkça öğretim skoru da artıyor.  
- Bu durum, yüksek araştırma performansına sahip üniversitelerin genellikle öğretim kalitesinin de yüksek olduğunu gösteriyor.

---

## Korelasyon Isı Haritası (Correlation Heatmap)

<img src="images/korelasyonisiharita.png" alt="Korelasyon Isı Harita" width="700">


- Heatmap, sayısal sütunlar arasındaki korelasyonu gösteriyor.  
- `Teaching` ve `Research` arasında yüksek pozitif korelasyon gözlemleniyor, yani bu iki metrik birlikte yükseliyor.  
- Bazı sütunlar (ör. `International Outlook`) daha düşük veya zayıf korelasyon gösteriyor.  
- Bu, hangi skorların birbirini güçlü etkilediğini anlamak için faydalıdır.

---

## Ülke Bazında Ortalama Overall Score

<img src="images/ortalamagrafik.png" alt="Ülke Bazında Ortalama Skor" width="700">

  
- Çizgi grafikte ülkeler X ekseninde, ortalama Overall Score Y ekseninde gösteriliyor.  
- Grafiğe bakarak hangi ülkelerin genel performansının yüksek olduğunu görebiliyoruz.  
- Örneğin, üst sıralarda genellikle ABD ve İngiltere gibi ülkeler bulunuyor.  
- Bu analiz, ülkeler arası eğitim kalitesi ve genel skor farklarını görselleştirmeye yarıyor.

---

## Özet

- `Research Score` ve `Teaching` arasında anlamlı bir pozitif ilişki var.  
- Korelasyon analizi, hangi skor metriklerinin birbirini etkilediğini gösteriyor.  
- Ülke bazlı skor grafikleri, ülkeler arasındaki ortalama performans farklarını ortaya koyuyor.  

> Bu README, tüm grafiklerin anlamını ve analiz sonuçlarını özetleyerek projeyi daha anlaşılır hale getirir.
