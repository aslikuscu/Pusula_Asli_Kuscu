# Veri İşleme Süreci Özeti
### 1. Gerekli Kütüphanelerin İçe Aktarılması
Pandas, sklearn kütüphaneleri ve ilgili sınıflar veri işleme için içe aktarılmıştır:

pandas: Veri analizi için.
SimpleImputer: Eksik verileri doldurmak için.
OneHotEncoder: Kategorik verilerin kodlanması için.
StandardScaler: Sayısal verilerin ölçeklendirilmesi için.
ColumnTransformer ve Pipeline: Veri dönüşüm adımlarını düzenlemek için.
### 2. Veri Setinin Yüklenmesi ve İncelenmesi
Veri seti side_effect_data.csv dosyasından pandas ile yüklenmiştir. Veri seti hakkında genel bilgi almak için df.info() kullanılarak sütun isimleri, veri tipleri ve eksik veriler kontrol edilmiştir.

Veri Setinin Genel Özellikleri:
Toplam 2357 kayıt ve 19 sütun bulunmaktadır.
Cinsiyet, il, alerjiler, kronik hastalıklar gibi bazı kategorik sütunlarda eksik veriler bulunmaktadır.
### 3. Tarih Verilerinin İşlenmesi
Tarih formatındaki sütunlar (Dogum_Tarihi, Ilac_Baslangic_Tarihi, Ilac_Bitis_Tarihi) datetime formatına dönüştürülmüştür.

### 4. Eksik Verilerin Kontrolü
Eksik verilerin sayısı her sütun için df.isnull().sum() ile kontrol edilmiştir.

### 5. Aykırı Değerlerin Kontrolü
Kilo ve boy sütunlarının istatistikleri describe() metodu ile incelenmiştir. Aykırı değerler tanımlanmış ve analize hazır hale getirilmiştir.

### 6. Yeni Özelliklerin Oluşturulması
İlaç kullanım süresi, başlangıç ve bitiş tarihleri arasındaki gün sayısı ile hesaplanarak yeni bir sütun (Ilac_Kullanim_Suresi) oluşturulmuştur.

### 7. Veri Dönüşümü İçin Hazırlık
Kategorik sütunlar categorical_cols listesinde ve sayısal sütunlar numerical_cols listesinde toplanmıştır.
Kategorik verilerde eksik olan değerler için SimpleImputer kullanılarak en sık görülen değer ile doldurma yapılacaktır.
Sayısal verilerde eksik olan değerler için ortalama ile doldurma yapılacaktır.
### 8. Veri İşleme Pipeline'ı
Bir Pipeline oluşturularak veri dönüşüm adımları sıralı bir şekilde tanımlanmıştır:

Eksik Veri Doldurma: Kategorik ve sayısal sütunlar için uygun stratejiler uygulanmıştır.
Kategorik Verilerin Kodlanması: OneHotEncoder ile kodlama yapılmıştır.
Sayısal Verilerin Ölçeklendirilmesi: StandardScaler ile standartlaştırma gerçekleştirilmiştir.
### 9. Pipeline'ın Uygulanması
Tanımlanan pipeline, veri setine uygulanmış ve işlenmiş veri X_processed değişkenine atanmıştır. İşlenmiş veri, sayısal ve kategorik verilerin uygun şekilde dönüştürülmesini sağlamıştır.

# Bu projeyi çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

### Gereksinimler
Projenin düzgün çalışması için aşağıdaki Python kütüphanelerinin yüklü olduğundan emin olun:

pandas
scikit-learn
### Kurulum
Python'u İndirin: Eğer sisteminizde Python yüklü değilse, Python'un resmi web sitesinden en son sürümü indirin ve kurun.

Gerekli Kütüphaneleri Yükleyin: Projeyi çalıştırmak için gerekli kütüphaneleri yüklemek için terminal veya komut istemcisine aşağıdaki komutu yazın:

```bash
pip install pandas scikit-learn
```

### Projeyi Çalıştırma
Veri Setini İndirin: Projeye ait side_effect_data.csv dosyasını indirip proje dizinine yerleştirin.

Python Dosyasını Çalıştırın: Terminal veya komut istemcisinde proje dizinine gidin ve aşağıdaki komutu çalıştırın:

```bash
python dosya_adi.py
```

(dosya_adi.py kısmını kendi Python dosyanızın adıyla değiştirin.)

### Sonuçları İnceleme
Kod çalıştırıldıktan sonra, işlenmiş veriyi incelemek için X_processed değişkenini kontrol edebilirsiniz. Çıktıyı görmek için kodun sonuna şu satırı ekleyebilirsiniz:

```bash
print(X_processed) 
```

##### Aslı Kuşçu
##### aslii.ksc@gmail.com
