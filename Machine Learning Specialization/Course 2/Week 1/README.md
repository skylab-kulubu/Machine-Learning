# Derin Öğrenme: Sinir Ağları ve Karar Ağaçları

## Giriş
Bu doküman, yapay zeka ve makine öğrenmesinin en güçlü araçlarından olan yapay sinir ağları ve karar ağaçlarını detaylı bir şekilde açıklamaktadır. Özellikle derin öğrenme yaklaşımı ile sinir ağlarının nasıl çalıştığı, gelişimi, mimarisi ve öğrenme süreci ele alınırken, karar ağaçlarının yapısı ve kullanım alanlarına da odaklanılacaktır.

---

## Yapay Sinir Ağları

### Biyolojik İlham: Sinir Ağlarının Kökenleri
**Biyolojik Sinirler:** İnsan beyninin temel birimi olan nöronlar, elektrik sinyalleri aracılığıyla bilgi işler. Yapay sinir ağları, bu biyolojik sistemin işleyişinden esinlenerek geliştirilmiştir.

![Biyolojik Sinir Hücresi](https://github.com/user-attachments/assets/21359a6b-df51-4fa7-a92b-b30887bee087)

**Yapay Sinirler:** Yapay sinir ağları, biyolojik sinirlerin basitleştirilmiş matematiksel modelleri olarak, girdi verilerini işler ve çıktı üretir.

![Yapay Sinir](https://github.com/user-attachments/assets/b2c4cb10-be14-4573-b23b-e7b070223590)

### Sinir Ağlarının Çalışma Prensibi
**Katmanlar:** Sinir ağları, girdi, gizli ve çıktı katmanlarından oluşur. Girdi katmanı, veriyi alırken; gizli katmanlar bu veriyi işler ve çıktı katmanı sonucu üretir.

**Aktivasyon Fonksiyonları:** Her nöron, aldığı girdileri bir aktivasyon fonksiyonu ile işler ve diğer nöronlara aktarır. Bu süreç, ağın nihai çıktısını oluşturur.

**Öğrenme Süreci:** Sinir ağları, ağırlıkları güncelleyerek girdiler ile hedef çıktılar arasındaki hatayı minimize eder ve performanslarını iyileştirir.

### Uygulama Alanları
- **Konuşma Tanıma:** Sesli asistanlar, otomatik çeviri ve arama motorlarında kullanılır.
- **Görüntü İşleme:** Görüntü sınıflandırma, nesne algılama ve yüz tanıma gibi işlemlerde rol oynar.
- **Doğal Dil İşleme:** Metin özetleme, dil çeviri ve sohbet robotlarında kullanılmaktadır.

### Derin Öğrenmenin Tarihsel Gelişimi
1. **1950'ler:** İlk sinir ağı modelleri ortaya çıktı, ancak sınırlı işlem gücü nedeniyle ilerleme kısıtlıydı.
2. **1980'ler:** Geri yayılım algoritmasının geliştirilmesiyle sinir ağlarının eğitimi kolaylaştı.
3. **2000'ler:** Güçlü işlemciler ve büyük veri kümeleri sayesinde önemli atılımlar gerçekleşti.
4. **Günümüz:** Derin öğrenme, günlük hayatın birçok alanında yaygınlaşmıştır.

### Sinir Ağlarının Mimari Seçimi
- **Katman Sayısı:** Derinlik, ağın karmaşıklığını ve öğrenme kapasitesini artırır.
- **Nöron Sayısı:** Her katmandaki nöron sayısı, ağın bilgiyi işleme yeteneğini belirler.
- **Bağlantı Türleri:** Nöronlar arasındaki bağlantılar, bilgi akışını ve öğrenme biçimini etkiler.

### Sinir Ağlarının Öğrenme Süreci
1. **Eğitim Verisi:** Girdi ve hedef çıktıları içeren veri setleri kullanılır.
2. **Ağırlık Güncelleme:** Hata hesaplanır ve bağlantı ağırlıkları optimize edilir.
3. **Optimizasyon:** Hataların minimize edilmesi için algoritmalar kullanılır.

---

## Karar Ağaçları

### Genel Bakış
Karar ağaçları, veriyi hiyerarşik olarak bölen ve kolay anlaşılabilir kararlar veren bir makine öğrenme algoritmasıdır.

### Avantajları
1. **Kolay Anlaşılabilir:** Karar ağacı modelleri, insan tarafından kolayca yorumlanabilir.
2. **Hiyerarşik Yapı:** Veriyi sistematik bir şekilde böler.
3. **Geniş Uygulama Alanı:** Sınıflandırma, regresyon ve veri madenciliğinde yaygın olarak kullanılır.

---




# Sinir Ağı Katmanları ve Kompleks Ağlar
Yapay sinir ağları belirli sayıda nöron içeren katmanlardan oluşurlar. Her bir nöron kendine ait w ve b parametreleri ile lojistik regresyon hesabı yapar ve bu işlemin sonucunda değeri 0 ile 1 arasında değişen bir sayı üretir. Dolayısıyla bir katmanın çıkış değeri, içerdiği nöron sayısına eşit sayıda değer içeren bir vektördür.
![Basit Bir Sinir Ağı](https://github.com/user-attachments/assets/31a09b2a-e6ca-4648-9f1e-69d3776f0580)
Yukarıda verilen resimde 2 katmandan oluşan basit bir sinir ağı görülmektedir. Katmanlar sırasıyla 3 ve 1 adet nöron içermektedirler. Dolayısıyla giriş vektörünün boyutundan bağımsız olarak 1.katmanın çıkışı 3, 2.katmanın çıkışı da 1 adet değerden oluşur. 
