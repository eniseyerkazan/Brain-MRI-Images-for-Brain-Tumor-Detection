# Brain-MRI-Images-for-Brain-Tumor-Detection
# 🧠 Beyin MR Görüntüleri ile Tümör Sınıflandırması

## Proje Amacı
Bu proje, beyin MR görüntülerinden tümör var/yok sınıflandırması yapmak için bir **Convolutional Neural Network (CNN)** modeli geliştirmeyi amaçlamaktadır. Model, farklı optimizasyon algoritmalarının performansını karşılaştırarak en iyi doğruluk sağlayanı belirlemeyi hedefler.

## Veri Seti
- **Kaynak:** [Brain MRI Images for Brain Tumor Detection - Kaggle](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)
- **İçerik:** İki sınıf bulunur: `no` (tümör yok), `yes` (tümör var)
- **Toplam Görüntü:** 253 MR görüntüsü
- **Önişleme:** 
  - Görüntüler `150x150` boyutuna yeniden boyutlandırıldı
  - Piksel değerleri normalize edildi (`0-1` aralığı)
  - Etiketler one-hot encoding veya 0/1 formatına dönüştürüldü
  - Eğitim/test seti %80/%20 olarak ayrıldı

## Kullanılan Yöntemler
- **CNN Modeli Yapısı:**
  - Conv2D + MaxPooling katmanları ile özellik çıkarımı
  - Flatten + Dense katmanları ile sınıflandırma
  - Dropout ile overfitting önleme
  - Son katman: Sigmoid (binary) veya Softmax (2 sınıf)
- **Veri Artırma:** `ImageDataGenerator` ile
  - Rotasyon, zoom, yatay/dikey kaydırma, flip
- **Optimizasyon Algoritmaları:**
  - Adam
  - RMSprop
  - SGD
- **Değerlendirme:**
  - Test doğruluğu
  - Confusion matrix ve classification report
  - Doğru/yanlış tahmin örneklerinin görselleştirilmesi

## Elde Edilen Sonuçlar
- Temel CNN Model Doğruluğu: **`%{test_accuracy:.2f}`**  
- En iyi optimizer: **Adam / RMSprop / SGD** (hangisi daha yüksekse)  
- Confusion matrix ve classification report ile model performansı detaylı şekilde incelendi.
- Eğitim/doğrulama kayıp ve doğruluk grafikleri ile overfitting/underfitting durumu gözlendi.

## Görselleştirmeler
- Eğitim/Doğrulama Accuracy & Loss grafikleri
- Confusion Matrix heatmap
- Doğru ve yanlış tahminlerin örnek görüntüleri
- Optimizasyon algoritmalarının doğruluk karşılaştırması

## Kaggle Notebook Linki
Projenin Kaggle notebook sürümü için [tıklayın](https://www.kaggle.com/code/eniseyerkazan/akbank)

## Kullanım
1. Kaggle ortamında notebook’u çalıştırabilirsiniz.
2. Model eğitimi ve değerlendirmesi otomatik olarak yapılacaktır.
3. Gerektiğinde optimizer, epoch sayısı ve veri artırma parametreleri değiştirilebilir.
