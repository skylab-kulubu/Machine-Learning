# Makine Öğrenmesi Nedir?

Makine öğrenmesi, bilgisayarların açıkça programlanmadan, verilerden öğrenerek belirli görevleri yerine getirebilmesini sağlayan yapay zekâ alt dalıdır. Bu alan, bilgisayarların geçmiş deneyimlerden veya büyük veri setlerinden öğrenmesini mümkün kılar. Temel amacı, sistemlerin otomatik olarak öğrenmesini sağlamak ve zamanla performanslarını geliştirmelerine olanak tanımaktır.

Makine öğrenmesi; algoritmaların tasarımı, geliştirilmesi ve gerçek dünyadaki problemlere uygulanmasını içerir. Bu algoritmalar, verideki örüntüleri ve ilişkileri analiz ederek tahminlerde bulunabilir veya kararlar alabilir. 

## 🎯 Gerçek Hayattan Bir Örnek

Bir banka, müşterilerinin gelecekte banka hesabını kapatıp kapatmayacağını önceden tahmin etmek isteyebilir. Bankanın veri tabanında, mevcut ve daha önce hesap kapatmış olan müşterilere ait yaş, gelir durumu, hesap bakiyesi, ürün sayısı, kredi kartı sahipliği gibi özellikler mevcuttur.

Bu veriler kullanılarak bir makine öğrenmesi modeli eğitilebilir. Model, geçmiş verilerdeki örüntülere dayanarak gelecekte benzer davranışlar sergileyebilecek müşterileri tespit edebilir. Böylece banka, potansiyel müşteri kayıplarını önlemek için erken müdahalede bulunabilir.

---

## ⚙️ Makine Öğrenmesi Algoritma Türleri

Makine öğrenmesi algoritmaları, öğrenme şekline göre üç ana kategoriye ayrılır:

### 1. Denetimli Öğrenme (Supervised Learning)

Model etiketlenmiş veriyle eğitilir. Yani, her veri örneği için hem giriş (özellikler) hem de çıkış (etiket) bilgisi mevcuttur. Model bu örneklerden öğrenerek yeni veriler üzerinde tahmin yapabilir.

#### 🔹 Alt Türleri:
- **Regresyon:** Sürekli (sayısal) değerlerin tahmini.  
  *Örnek: Ev fiyatı tahmini.*
- **Sınıflandırma:** Verileri kategorilere ayırma.  
  *Örnek: E-postaların spam olup olmadığını tespit etme.*

---

### 2. Denetimsiz Öğrenme (Unsupervised Learning)

Etiketlenmemiş veri kullanılır. Model, veri içindeki gizli yapıları ve örüntüleri keşfetmeye çalışır.

#### 🔹 Alt Türleri:
- **Kümeleme (Clustering):** Benzer özelliklere sahip verileri gruplama.  
  *Örnek: Müşteri segmentasyonu.*
- **Boyut Azaltma (Dimensionality Reduction):** Verideki öznitelik sayısını azaltma.  
  *Örnek: Görsel veride öznitelik seçimi (PCA, t-SNE).*
- **Birliktelik Kuralları (Association Rules):** Verideki öğeler arasındaki ilişkiyi bulma.  
  *Örnek: Market sepeti analizi.*

---

### 3. Pekiştirmeli Öğrenme (Reinforcement Learning)

Bir ajan (yapay zekâ), çevresiyle etkileşime girerek ödül veya ceza alır. Amaç, en yüksek ödülü getiren eylemleri öğrenmektir.

#### 🔹 Örnekler:
- Oyun oynayan yapay zekâlar (örneğin AlphaGo)
- Robotların yön bulma öğrenimi
- Otonom araçların sürüş kararları

---

Bu bölüm, makine öğrenmesine temel bir giriş sunmakta ve algoritma türleri hakkında genel bir bakış sağlamaktadır. Daha derinlemesine bilgi için `Machine Learning Specialization/` klasörüne göz atabilirsiniz.
