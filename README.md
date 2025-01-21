# README

## Çoklu Özellikler için Lineer Regresyon

### Tanım ve Kullanım
Regresyon modelleri, değişkenler arasındaki ilişkileri açıklamak için gözlemlenen verilere bir çizgi uydurur. *Çoklu Lineer Regresyon (MLR)*, bir bağımlı değişken ile iki veya daha fazla bağımsız değişken arasındaki ilişkiyi tahmin eder.

### Amaçlar
İlişkileri değerlendirme: Birden fazla bağımsız değişkenin bir bağımlı değişken üzerindeki etkisini değerlendirir (örneğin, yağış, sıcaklık ve gübrenin bitki büyümesi üzerindeki etkisi).

Tahminler yapma: Bağımsız değişkenlerin belirli değerlerine dayanarak bağımlı değişkenin değerini tahmin eder (örneğin, belirli seviyelerde yağış, sıcaklık ve gübre için beklenen mahsul verimi).

### Uygulama Örneği
Bir halk sağlığı araştırmacısı, sosyal faktörlerin kalp hastalığı üzerindeki etkisini inceler. 500 kasabadan toplanan veriler:
Sigara içenlerin yüzdesi (bağımsız değişken 1).
İşe bisikletle gidenlerin yüzdesi (bağımsız değişken 2).
Kalp hastalığı olanların yüzdesi (bağımlı değişken).
Bu iki bağımsız değişken ve bir bağımlı değişkenle, MLR ilişkileri analiz etmek için kullanılabilir.

### Ana Noktalar

MLR, bir yanıt değişkenini tahmin etmek için birden fazla açıklayıcı değişken kullanan istatistiksel bir tekniktir.

Basit doğrusal regresyonu (tek değişken) birden fazla değişkeni kapsayacak şekilde genişletir.

Uygulamalar: Ekonometrik analizler, finansal tahminler, değişkenler arasındaki ilişkileri açıklama ve teorileri test etme.

### Vektörizasyon

Öğrenme süreçlerindeki verimliliği artırmak için büyük veri gereklidir. Ancak, bu büyük veriyi hızlı bir şekilde işlemek gerekir. Hızlı sonuç elde etmek için vektörizasyon kullanılır.

Vektörizasyon işlemi, aynı veri seti ile yapılan işlemleri hızlandırarak derleme süresini önemli ölçüde kısaltır. Bu teknik, yüksek performans gerektiren bilimsel uygulamalar için işlemcinin bellekteki veri bloklarını tek seferde alıp işleyebilmesini sağlar.

### SIMD Nedir?

SIMD (Single Instruction Multiple Data), tek bir çekirdeğin aynı anda birden fazla işlemi gerçekleştirmesini sağlar. GPU'lar ve CPU'lar, vektör işlemleri için SIMD birimlerini kullanır.



