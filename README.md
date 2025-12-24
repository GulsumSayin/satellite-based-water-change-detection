# Uydu Tabanlı Su Kaynağı Takip ve Risk Analiz Sistemi
Satellite-Based Water Resource Monitoring and Risk Analysis System
### 📌 Proje Hakkında

Bu proje, iki farklı tarihli uydu görüntüsünden su alanlarının otomatik olarak tespit edilmesini, zamansal değişimlerinin analiz edilmesini ve elde edilen sonuçların görselleştirilip PDF rapor haline getirilmesini amaçlamaktadır.

Çalışma kapsamında, derin öğrenme tabanlı geliştirilmiş bir U-Net segmentasyon modeli kullanılarak su alanları piksel seviyesinde ayrıştırılmıştır. Elde edilen segmentasyon maskeleri üzerinden su alanındaki artış ve azalışlar hesaplanarak karar destek sürecine katkı sağlayacak çıktılar üretilmiştir.

### 👥 Proje Ekibi

Gülsüm Sayın

Model tasarımı, eğitimi, optimizasyonu ve performans değerlendirmesi

İbrahim Korkmaz

Veri seti araştırması, literatür taraması ve kullanıcı arayüzü geliştirme

### 🎯 Projenin Amacı

- Uydu görüntülerinden su alanlarını yüksek doğrulukla tespit etmek
- İki farklı tarihli görüntü arasındaki su alanı değişimini analiz etmek
- Segmentasyon sonuçlarını görselleştirmek
- Otomatik PDF raporu oluşturarak karar destek çıktısı sunmak
- Kullanıcı dostu bir arayüz ile analiz sürecini kolaylaştırmak

### 🧠 Kullanılan Yöntem

Problem tipi: Piksel tabanlı görüntü segmentasyonu

Model mimarisi: Geliştirilmiş U-Net

Kayıp fonksiyonu: Binary Cross Entropy (BCE) + Dice Loss

Performans metrikleri:

- Dice Coefficient
- Intersection over Union (IoU)
- Precision
- Recall

Model, uydu görüntülerini girdi olarak almakta ve her piksel için su olasılığını temsil eden bir maske üretmektedir.

### 🧪 Veri Seti ve Ön İşleme

Kaynak: https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies/data

Görüntü boyutu: 256 × 256

Ön işleme adımları:

- Yeniden boyutlandırma
- Normalizasyon (0–1)
- Maske binarizasyonu
- %80 eğitim – %20 doğrulama ayrımı

### 🖥️ Geliştirme Ortamı

Bu proje Google Colab ortamında geliştirilmiş ve test edilmiştir.
Model eğitimi GPU desteği kullanılarak gerçekleştirilmiştir.
Kullanıcı arayüzü Gradio kütüphanesi ile oluşturulmuştur.


### 🖼️ Kullanıcı Arayüzü

Aşağıda, proje kapsamında geliştirilen Gradio tabanlı kullanıcı arayüzüne ait örnek bir ekran görüntüsü yer almaktadır.
Bu arayüz üzerinden iki farklı tarihli uydu görüntüsü seçilerek segmentasyon, değişim analizi ve PDF rapor oluşturma işlemleri gerçekleştirilmektedir.

<img width="1237" height="903" alt="Ekran görüntüsü 2025-12-24 153435" src="https://github.com/user-attachments/assets/f3c8e8ef-370e-4bac-97c2-89eaf13beca3" />

### 📄 Çıktılar

- Su alanı segmentasyon maskeleri
- Zamansal değişim haritaları
- Piksel ve yüzdesel değişim analizleri
- Otomatik oluşturulan PDF rapor

### 🚀 Gelecek Çalışmalar

- Farklı coğrafi bölgeler ve veri setleri ile modelin genellenmesi
- Daha yüksek çözünürlüklü görüntülerle detay analiz
- Bulutlu ve atmosferik gürültü içeren veriler için iyileştirmeler
- Web tabanlı sürekli erişilebilir bir sistemin geliştirilmesi
