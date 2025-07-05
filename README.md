# Heart Risk ML Model

Bu proje, bireylerde kalp hastalığı riski olup olmadığını tahmin eden bir **makine öğrenmesi sınıflandırma modelidir**.  
Kullanılan veri seti, [Heart Disease UCI Dataset](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data) adlı açık bir veri setidir.

---

## 🎯 Amaç

Bu projenin amacı, bireyin sağlık verilerine göre **kalp hastalığı riski taşıyıp taşımadığını (0 = yok, 1 = var)** tahmin etmektir.

---

## 📊 Veri Seti Hakkında

- Toplam 14+ sütun içerir.
- Demografik, klinik ve efor testi verileri içerir.
- Orijinal `num` sütunu 0-4 arasında sınıflandırma içeriyordu. Bu proje kapsamında, ikili sınıfa dönüştürüldü:  
  `0 = Hastalık Yok`, `1 = Hastalık Var`

---

## 🧹 Veri Ön İşleme

- Eksik veriler analiz edildi, gerektiğinde çıkarıldı veya dönüştürüldü.
- Kategorik değişkenler One-Hot Encoding ile dönüştürüldü.
- Sayısal değişkenler `StandardScaler` ile ölçeklendirildi.
- Eğitim/test seti oranı: **%80 - %20**

---

## 🤖 Modelleme

İki farklı sınıflandırma algoritması kullanıldı:

1. **Logistic Regression**
2. **Random Forest Classifier**

Ayrıca Random Forest için **GridSearchCV ile hiperparametre optimizasyonu** uygulandı.

---

## 📈 Başarı Metrikleri

| Metrik         | Logistic Regression | Random Forest (Opt.) |
|----------------|---------------------|-----------------------|
| Eğitim Doğruluğu | 0.8315              | **1.0000**            |
| Test Doğruluğu   | 0.8261              | **0.8370**            |
| F1-score         | 0.83                | **0.84**              |
| ROC-AUC Skoru    | 0.89                | **0.91**              |

Random Forest, her metrikte daha başarılı sonuç vermiştir.

---

## ✅ Sonuçlar ve Yorumlar

- Hedef değişkenin ikili forma dönüştürülmesi performansı ciddi şekilde artırmıştır.
- **Random Forest**, özellikle hasta bireyleri tanımada daha başarılı olmuştur.
- Modelin genelleme başarısı ROC-AUC ve F1-score gibi metriklerle desteklenmiştir.
- GridSearch ile en iyi parametre kombinasyonu bulunarak doğruluk daha da artırılmıştır.

---

## 🧰 Kullanılan Kütüphaneler

- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn`

---
