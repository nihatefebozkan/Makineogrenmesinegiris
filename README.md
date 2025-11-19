# Üniversite Veri Seti: Veri Yükleme ve İlk İnceleme

Bu proje, üniversite veri seti üzerinde temel veri analizi yapmak için hazırlanmıştır. Bu bölüm, **CSV dosyasının Python ortamına yüklenmesi** ve verinin **ilk birkaç satırının incelenmesini** göstermektedir.  

---

## 1. Projenin Amacı

Bu kodun temel amacı:

- Üniversite veri setini Python ortamına aktarmak.  
- Verinin yapısını ve ilk birkaç satırını gözlemlemek.  
- İlerleyen analizler (temizlik, görselleştirme, modelleme) için hazırlık yapmak.  

Bu adım, veri analizi sürecinin **ilk ve en önemli adımı**dır.

---

## 2. Kullanılan Kütüphaneler

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import re
from sklearn.linear_model import LinearRegression
```
-------
## Teaching ve Research Score Sütunlarının Seçimi ve Kontrolü

Bu bölümde, veri çerçevesinde `Teaching` ve `Research Score` sütunlarını otomatik olarak bulma ve bu sütunların varlığını kontrol etme işlemleri yapılmaktadır.

---

## 1. Sütunların Otomatik Seçimi

```python
teaching_col = next((c for c in df.columns if "teaching" in c.lower()), None)
research_col = next((c for c in df.columns if "research score" in c.lower()), None)
```


# Teaching ve Research Score Sütunlarının Sayısal Hale Getirilmesi ve Eksik Değerlerin Temizlenmesi

Bu bölümde, veri çerçevesindeki `Teaching` ve `Research Score` sütunları **sayısal değere** dönüştürülmekte ve eksik veriler temizlenmektedir.

---

## 1. Sütunların Sayısal Hale Getirilmesi

```python
df[teaching_col] = pd.to_numeric(df[teaching_col], errors="coerce")
df[research_col] = pd.to_numeric(df[research_col], errors="coerce")
```

# Lineer Regresyon: Teaching ~ Research Score

Bu bölümde, üniversite veri setindeki `Research Score` değişkeni kullanılarak `Teaching` değerlerini tahmin eden **lineer regresyon modeli** oluşturulmaktadır. Modelin eğimi ve kesişimi hesaplanır ve scatter plot ile görselleştirilir.

---

## Kod Açıklaması

```python
# Bağımsız ve bağımlı değişkenlerin belirlenmesi
X = df[[research_col]]  # Research Score (bağımsız değişken)
Y = df[teaching_col]    # Teaching (bağımlı değişken)
```
# Lineer regresyon modelinin oluşturulması ve eğitilmesi
```python
model = LinearRegression()
model.fit(X, Y)
```
# Regresyon çizgisi için X değerleri oluşturma
```python
x_line = pd.DataFrame(np.linspace(X.min(), X.max(), 200), columns=[research_col])
y_line = model.predict(x_line)
```
# Grafiğin oluşturulması
```python
plt.figure(figsize=(9,6))
plt.scatter(X, Y, s=60, edgecolor="black", label="Veri Noktaları")  # Veri noktaları
plt.plot(x_line, y_line, linewidth=2, label="Lineer Regresyon")      # Regresyon çizgisi
plt.xlabel(research_col)
plt.ylabel(teaching_col)
plt.title("Lineer Regresyon: Research → Teaching")
plt.legend()
plt.tight_layout()
plt.show()
```
# Model parametrelerinin ekrana yazdırılması
```python
print("Eğim:", model.coef_[0])
print("Kesişim:", model.intercept_)
```
<img src="images/lineerregresyon.png" alt="lineer regresyon grafiği" width="600">


# Korelasyon Isı Haritası (Correlation Heatmap)



Bu bölümde, veri setindeki tüm sayısal sütunlar arasındaki korelasyonları görselleştirmek için **ısı haritası** oluşturulmaktadır. Bu sayede hangi skor metriklerinin birbirine ne kadar bağlı olduğu hızlıca anlaşılır.

---

## Kod Açıklaması


# Sayısal sütunları seçme
```python
num_df = df.select_dtypes(include=["float", "int"])
```
# En az iki sayısal sütun varsa korelasyon hesapla
```python
if len(num_df.columns) > 1:
    corr = num_df.corr()
```
# Korelasyon ısı haritasının çizimi
```python
plt.figure(figsize=(10, 8))
plt.imshow(corr, cmap="coolwarm", interpolation="nearest")
plt.colorbar()
plt.xticks(range(len(corr.columns)), corr.columns, rotation=45, ha="right")
plt.yticks(range(len(corr.columns)), corr.columns)
```
# Korelasyon sayılarını her hücreye yazdırma
```python
for i in range(len(corr.columns)):
  for j in range(len(corr.columns)):
    plt.text(j, i, f"{corr.iloc[i, j]:.2f}",
      ha='center', va='center', color="black")

    plt.title("Correlation Heatmap (All Score Metrics)")
    plt.tight_layout()
    plt.show()
```
<img src="images/korelasyonisiharita.png" alt="korelasyon ısı haritası" width="600">

# Ülke Bazında Ortalama Overall Score

Bu bölümde, her ülke için `Overall Score` değerlerinin ortalaması hesaplanır ve bir **çizgi grafiği** ile görselleştirilir. Böylece hangi ülkelerin ortalama skorlarının yüksek olduğu kolayca görülebilir.

---

## Kod Açıklaması


# Sütun isimlerinin belirlenmesi
```python
country_col = "Location"
overall_col = "Overall Score"
```
# Overall Score sütununu sayısal hale getirme ve eksik verileri temizleme
```python
df[overall_col] = pd.to_numeric(df[overall_col].astype(str).str.replace(",", "."), errors="coerce")
df = df.dropna(subset=[country_col, overall_col])
```
# Ülke bazında ortalama Overall Score hesaplama
```python
country_avg = df.groupby(country_col)[overall_col].mean().sort_values(ascending=False)
```
# Grafiğin oluşturulması
```python
plt.figure(figsize=(12,6))
plt.plot(country_avg.index, country_avg.values, marker='o', linewidth=2)
plt.xticks(rotation=90)
plt.ylabel(overall_col)
plt.title("Ülke Bazında Ortalama Overall Score")
plt.grid(True, linestyle='--', alpha=0.5)
plt.tight_layout()
plt.show()
```
<img src="images/ortalamagrafik.png" alt="ortalama overall score grafiği" width="600">
