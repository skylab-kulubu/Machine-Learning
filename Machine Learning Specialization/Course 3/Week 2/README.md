# Çoklu Dogrusal Regresyon

## Tanım ve Kullanım

- Regresyon modelleri, değişkenler arasındaki ilişkileri gözlemlenen verilere uyan bir doğru çizerek açıklar. Çoklu doğrusal regresyon (MLR), bir bağımlı değişken ile iki veya daha fazla bağımsız değişken arasındaki ilişkiyi tahmin eder.

## Amaçlar

- İlişkileri değerlendirme: Birden fazla bağımsız değişkenin bir bağımlı değişken üzerindeki etkisini değerlendirir (örneğin, yağış, sıcaklık ve gübrenin bitki büyümesi üzerindeki etkisi).

- Tahminler yapma: Bağımsız değişkenlerin belirli değerlerine dayanarak bağımlı değişkenin değerini tahmin eder (örneğin, belirli seviyelerde yağış, sıcaklık ve gübre için beklenen mahsul verimi).

## Uygulama Örneği

Bir halk sağlığı araştırmacısı, sosyal faktörlerin kalp hastalığı üzerindeki etkisini inceler. 500 kasabadan toplanan veriler:

- Sigara içenlerin yüzdesi (bağımsız değişken 1).

- İşe bisikletle gidenlerin yüzdesi (bağımsız değişken 2).

- Kalp hastalığı olanların yüzdesi (bağımlı değişken).

Bu iki bağımsız değişken ve bir bağımlı değişkenle, MLR ilişkileri analiz etmek için kullanılabilir.

## Ana Noktalar

- MLR, bir yanıt değişkenini tahmin etmek için birden fazla açıklayıcı değişken kullanan istatistiksel bir tekniktir.

- Basit doğrusal regresyonu (tek değişken) birden fazla değişkeni kapsayacak şekilde genişletir.

Uygulamalar: Ekonometrik analizler, finansal tahminler, değişkenler arasındaki ilişkileri açıklama ve teorileri test etme.

## Vektörizasyon

Öğrenme süreçlerindeki verimliliği artırmak için büyük veri gereklidir. Ancak, bu büyük veriyi hızlı bir şekilde işlemek gerekir. Hızlı sonuç elde etmek için vektörizasyon kullanılır.

Vektörizasyon işlemi, aynı veri seti ile yapılan işlemleri hızlandırarak derleme süresini önemli ölçüde kısaltır. Bu teknik, yüksek performans gerektiren bilimsel uygulamalar için işlemcinin bellekteki veri bloklarını tek seferde alıp işleyebilmesini sağlar.

## SIMD Nedir?

SIMD (Single Instruction Multiple Data), tek bir çekirdeğin aynı anda birden fazla işlemi gerçekleştirmesini sağlar. GPU'lar ve CPU'lar, vektör işlemleri için SIMD birimlerini kullanır.

## Gradient Descent ve Vektörizasyon

Gradient Descent (eğim azalma algoritması), büyük veri kümeleri üzerinde model eğitirken önemli bir kavramdır. Çoklu doğrusal regresyon ile birleştirildiğinde daha verimli ve hızlı hesaplamalar sağlar.

Çoklu doğrusal regresyonda, bağımlı değişken (y), birden fazla bağımsız değişken (x) ile doğrusal bir ilişki içinde modellenir.

## Özellik Ölçeklendirme

Özellik ölçeklendirme (Feature Scaling), değişkenler arasındaki ölçüm farklılıklarını ortadan kaldırmayı amaçlar. Amaç, modellerin değişkenlere eşit koşullar altında yaklaşmasını sağlamaktır.

Özellik ölçeklendirme, özellikle Gradient Descent gibi algoritmaların eğitim süresini kısaltır. Ayrıca, KNN, K-Means ve PCA gibi mesafe tabanlı yöntemlerde oluşabilecek yanlılığı önler.

## Ölçeklendirme Yöntemleri

- Normalize Etme (Min-Max Ölçeklendirme): Verileri genellikle 0 ile 1 arasına çeker.

- Standartlaştırma (Z-Score Ölçeklendirme): Verileri ortalama sıfır ve standart sapma bir olacak şekilde ayarlar.

## Özellik Mühendisliği

Özellik mühendisliği, ham veriyi denetimli öğrenmeye uygun özelliklere dönüştürme sürecidir. Beş ana süreç içerir:

- Özellik oluşturma

- Dönüştürme

- Özellik çıkarımı

- Keşifsel veri analizi

- Karşılaştırmalı analiz

## Yaygın Teknikler

- Eksik verilerin tamamlanması (Imputation): Eksik veriler ortalama veya medyan gibi değerlerle doldurulur.

- Ayıklamalarla başa çıkma: Aykırı değerlerin kaldırılması veya değiştirilmesi.

- Log Dönüşümü: Eğik dağılımları düzeltmek için log fonksiyonu uygulanır.

- Tek-Sıcak Kodlama (One-Hot Encoding): Kategorik değişkenler, ikili vektörlere dönüştürülür.


## En İyi Araçlar

FeatureTools: Zaman serileri ve ilişkisel veriler için özellik matrisleri oluşturur.

AutoFeat: Otomatik özellik mühendisliği ve seçimi yapar.

TsFresh: Zaman serisi verilerini otomatik olarak işler.

Polinom Regresyonu ve Özellik Mühendisliği

Polinom regresyonu, doğrusal regresyonun üzerine inşa edilerek veri içindeki doğrusal olmayan ilişkileri modellemek için kullanılır.

## Önemli Noktalar

Ölçeklendirme: Büyük veri aralıkları algoritmaları olumsuz etkileyebilir.

Alternatif Özellikler: Karekök, log gibi dönüşümler kullanılabilir.

Scikit-learn Kullanımı: Basit ve verimli model oluşturmayı sağlar.


