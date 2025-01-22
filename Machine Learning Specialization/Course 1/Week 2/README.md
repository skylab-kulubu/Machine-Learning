# Makine Öğrenimi Uzmanlaşma - Hafta 2

Bu doküman, "Machine Learning Specialization" kursunun ikinci haftasında ele alınan kavramları ve teknikleri kapsamaktadır. Amaç, çoklu özelliklerle çalışan lineer regresyon modellerini anlamak, vektörleştirme ile işlem süresini hızlandırmak ve özellik mühendisliği gibi kritik makine öğrenimi tekniklerini uygulamaya almaktır.

---

## İçerik

1. [Projenin Amacı](#projenin-amacı)
2. [Temel Kavramlar](#temel-kavramlar)
   - [1. Çoklu Özellikler İçin Lineer Regresyon](#1-çoklu-özellikler-için-lineer-regresyon)
   - [2. Vektörleştirme](#2-vektörleştirme)
   - [3. Gradient Descent ile Optimizasyon](#3-gradient-descent-ile-optimizasyon)
   - [4. Özellik Ölçekleme (Feature Scaling)](#4-özellik-ölçekleme-feature-scaling)
   - [5. Özellik Mühendisliği](#5-özellik-mühendisliği)
3. [Kullanım Alanları ve Avantajlar](#kullanım-alanları-ve-avantajlar)
4. [Gereksinimler ve Kurulum](#gereksinimler-ve-kurulum)
5. [Katkıda Bulunma](#katkıda-bulunma)

---

## Projenin Amacı

Bu projede, makine öğrenimi uygulamalarında kritik öneme sahip olan "çoklu lineer regresyon", "vektörleştirme", "özellik ölçekleme" ve "özellik mühendisliği" gibi temel kavramlar derinlemesine incelenmektedir. Amacımız:

- Karmaşık veri setlerindeki özelliklerin önemini anlamak,
- Modelleri optimize etmek için gradient descent gibi algoritmaları etkin kullanmak,
- Çözüm süreçlerini hızlandırmak için vektörleştirme tekniklerini uygulamak,
- Daha doğru tahminler yapmak için yeni özellikler yaratmak ve dönüştürmek.

---
## Coklu Dogrusal Regresyon

# Tanım ve Kullanım

- Regresyon modelleri, değişkenler arasındaki ilişkileri gözlemlenen verilere uyan bir doğru çizerek açıklar. Çoklu doğrusal regresyon (MLR), bir bağımlı değişken ile iki veya daha fazla bağımsız değişken arasındaki ilişkiyi tahmin eder.

# Amaçlar

- İlişkileri değerlendirme: Birden fazla bağımsız değişkenin bir bağımlı değişken üzerindeki etkisini değerlendirir (örneğin, yağış, sıcaklık ve gübrenin bitki büyümesi üzerindeki etkisi).

- Tahminler yapma: Bağımsız değişkenlerin belirli değerlerine dayanarak bağımlı değişkenin değerini tahmin eder (örneğin, belirli seviyelerde yağış, sıcaklık ve gübre için beklenen mahsul verimi).

# Uygulama Örneği

Bir halk sağlığı araştırmacısı, sosyal faktörlerin kalp hastalığı üzerindeki etkisini inceler. 500 kasabadan toplanan veriler:

- Sigara içenlerin yüzdesi (bağımsız değişken 1).

- İşe bisikletle gidenlerin yüzdesi (bağımsız değişken 2).

- Kalp hastalığı olanların yüzdesi (bağımlı değişken).

Bu iki bağımsız değişken ve bir bağımlı değişkenle, MLR ilişkileri analiz etmek için kullanılabilir.

# Ana Noktalar

- MLR, bir yanıt değişkenini tahmin etmek için birden fazla açıklayıcı değişken kullanan istatistiksel bir tekniktir.

- Basit doğrusal regresyonu (tek değişken) birden fazla değişkeni kapsayacak şekilde genişletir.

Uygulamalar: Ekonometrik analizler, finansal tahminler, değişkenler arasındaki ilişkileri açıklama ve teorileri test etme.

