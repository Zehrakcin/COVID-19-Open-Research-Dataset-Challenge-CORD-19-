# COVID-19-Open-Research-Dataset-Challenge-CORD-19-
# Veri Analizi ve Konu Modelleme

Bu proje, Allen Institute for AI tarafından sağlanan [CORD-19](https://www.kaggle.com/datasets/allen-institute-for-ai/CORD-19-research-challenge) veri seti üzerinde yapılan bir metin madenciliği çalışmasını içermektedir. Amaç, COVID-19 ile ilgili bilimsel yayınların özetlerini (abstract) analiz ederek konu dağılımlarını ortaya çıkarmaktır.

---

## 🔍 Kullanılan Dosya

- `metadata.csv`: Makalelere ait başlık, özet, tarih, yazar ve dergi bilgilerini içerir.

---

## Uygulanan Adımlar

### 1. Veri Temizleme
- `title`, `abstract`, `publish_time` sütunlarında eksik veri olan satırlar çıkarıldı.
- `publish_time` tarih formatına dönüştürüldü ve `year` sütunu oluşturuldu.

### 2. Keşifsel Veri Analizi (EDA)
- Yıllara göre yayın dağılımı görselleştirildi.
- En çok yayın yapan 15 dergi tespit edilip bar grafikle gösterildi.
- Özetlerde en sık geçen kelimeler WordCloud ile sunuldu.

### 3. TF-IDF Analizi
- İlk 10.000 abstract kullanılarak `TfidfVectorizer` ile en anlamlı kelimeler çıkarıldı.
- En yüksek ortalama TF-IDF skoruna sahip 20 kelime görselleştirildi.

### 4. LDA (Latent Dirichlet Allocation) ile Konu Modelleme
- İlk 5.000 abstract üzerinde `CountVectorizer` ile Bag-of-Words matrisi oluşturuldu.
- 5 konudan oluşan LDA modeli eğitildi.
- Her konunun en anlamlı 10 kelimesi grafikle sunuldu.
- Abstract'ların baskın olduğu konu dağılımı çıkarıldı.

---

## 📌 Kullanılan Kütüphaneler
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `sklearn.feature_extraction.text`
- `sklearn.decomposition`


