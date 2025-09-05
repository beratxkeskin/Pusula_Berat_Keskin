# EDA Summary – Physical Medicine & Rehabilitation Dataset  

**Name:** Berat Keskin  
**Email:** bbbekeskin61@gmail.com 



##  Dataset Overview  
Bu veri seti, fiziksel tıp ve rehabilitasyon alanında kaydedilmiş **2235 gözlem** ve **13 özellikten** oluşmaktadır.  
Amacım bu veri setini keşifsel veri analizi (EDA) ve veri temizleme adımları ile düzenleyip, tahmine dayalı modellemeye hazır hale getirmektir.  


##  EDA Findings  

### 1. General Structure  
- Veri setinde hem sayısal (örn. TedaviSuresi, UygulamaSuresi) hem de kategorik (örn. Tanılar, Bölüm, Alerji) değişkenler bulunmaktaydı.  
- Bazı sütunlarda eksik değerler (NaN) vardı.  

### 2. Patient-Level Data  
- Aynı hasta numarasına sahip birden fazla satır olduğu görüldü.  
- Veri tedavi bazlı olduğu için, hasta numaraları (Hastano) analiz dışı bırakıldı.  

### 3. Categorical Features  
- Cinsiyet: Eksik değerler, aynı hastanın önceki kayıtları incelenerek dolduruldu.  
- Kan Grubu: Eksikler benzer şekilde dolduruldu, kalanlar "Unknown" etiketiyle işaretlendi.  
- Alerji: Veriler standardize edildi (örn. “POLEN” → “Polen”, “TOZ” → “Toz”). Çoklu alerjiler ayrılarak her birine ayrı sütun oluşturuldu.  
- Tanilar: Çoklu tanılar ayrıldı, kısaltmalar düzeltildi ve en sık görülen tanılar için binary sütunlar açıldı.  
- Bolum: Frekans analizi yapıldı, olduğu gibi bırakıldı.  
- Tedavi Adı : Standardizasyon yapıldı. Çok düşük frekanslı tedaviler toplulaştırıldı.  
- Uygulama Yerleri : Çoklu girişler ayrılarak one-hot encoding ile binary sütunlara dönüştürüldü.  

### 4. Numerical Features  
- Tedavi Süresi : “Seans” kelimesi kaldırılarak sayısal hale getirildi.  
- **Uygulama Süresi : Dakika değerleri sayısal hale getirildi.  

### 5. Missing Data  
- Eksik verilerin hangi sütunlarda kaç adet olduğu analiz edildi.  
- Henüz imputasyon yapılmadı, sadece işaretlendi.  

### 6. Outlier Analysis  
- Boxplot kullanılarak aykırı değerler incelendi.  
- Ciddi bir aykırı değer bulunmadı.  

### 7. Correlation & Relationships  
- Sayısal değişkenler arasındaki korelasyon incelendi.  
- Korelasyonlar heatmap ile görselleştirildi.  
- Sayısal-kategorik ilişkiler (örn. Tedavi Süresi farklı tanılara göre değişiyor mu) analiz edildi.  

---

##  Preprocessing Steps  
- Eksik değerler belirlendi.  
- Categorical veriler temizlenip yeniden kodlandı.  
- Çoklu kategorik alanlar (Tanılar, Alerjiler, Uygulama Yerleri) binary sütunlara dönüştürüldü.  
- Sayısal değişkenler dönüştürülerek modellemeye hazır hale getirildi.  

---

##  Conclusion  
- Veri seti temizlendi, tutarsızlıklar giderildi ve sayısal hale getirildi.  
- Kategorik veriler düzenlenerek analiz edilebilir hale geldi.  
- Eksik değerler belirlendi, imputasyon opsiyonel olarak sonraki aşamalarda yapılabilir.  
- Bu noktada veri seti, potansiyel tahmine dayalı modelleme için hazır hale gelmiştir.  

---
