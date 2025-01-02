# Week 1
Makine Öğrenmesi Nedir?
Makine öğrenmesi, bilgisayarların, verilerden öğrenmesini ve bu öğrenilen bilgiyi kullanarak belirli görevleri otomatik olarak yerine getirmesini sağlayan bir bilgisayar bilimleri alanıdır.

Makine öğrenmesi Denetimli Öğrenme(Supervised Machine Learning), Denetimsiz Öğrenme (Unsupervised Machine Learning) ve Pekiştirmeli Öğrenme (Reinforcement Learning) olarak üçe ayrılır.
Makine Öğrenmesinin Uygulama Alanları Nerelerdir?
Makine öğrenimi yaklaşımları, doğal dil işleme, bilgisayar görüşü, konuşma tanıma, e-posta filtreleme, otonom araçlar, tıbbi görüntüleme ve tanı, finansal uygulamalar, tarım ve tıp dahil olmak üzere birçok alana uygulanmıştır. Bu teknikler, genellikle tahmine dayalı analitik olarak tanımlanan iş sorunlarına yönelik uygulamalarda önemli bir rol oynamaktadır.

Denetimli Makine Öğrenmesi Nedir?
Sınıflandırma ve regresyon metotlarını kullanır. Kullanıcıdan alınan veriler doğrultusunda giriş-çıkış sistemi kullanılarak makine öğrenmesi şekillendirilir. 

Sınıflandırma: Alınan veriler kullanıcının beyanı doğrultusunda sınıflandırılmıştır, sistem önce girilen verinin hangi sınıfa ait olduğunu öğrenir, ardından gelecek olan verinin hangi sınıfa ait olduğunu beyan eder.

Regresyon: Amacı elimizdeki veriye en uygun olan fonksiyonu üretmektir. Ardından bu fonksiyonu baz alarak yeni gelecek olan veri hakkında tahminler yapabilir. Lineer regresyon, çoklu-lineer regresyon ve non-lineer regresyon olarak üç alt dala ayrılır.
Kullanım alanları sağlık, finans, otonom araçlar, spam tespiti ve doğal dil işlemedir.

Denetimsiz Makine Öğrenmesi Nedir?
Clustering ve Association metotlarını kullanır. Sınıflandırılmamış verileri kullanarak onların arasında bir örüntü kurabilir.

Clustering: Benzer verileri gruplandırılması.
Anomaly detection:Aykırı veri noktalarını tespit etme.
Boyut düşürme:Verinin boyutunu anlam kaybı olmayacak şekilde düşürmeye yarar.
Association:Veriler arasındaki gizli ilişkileri veya örüntüleri keşfetmeye yönelik bir tekniktir.
Kullanım alanları habercilik ve mikrobiyoloji alanında mevcuttur.

Lineer Regresyon Nedir?
İki veya daha fazla verinin bir doğru ile ifade edilmesine lineer regresyon denir. Verilere göre en optimize doğrunun çizilmesidir.
Basit doğrusal regresyon modeli hatırlarsak iki boyutlu uzayda yer alan veri modelleri için uygun olan y = ax + b doğrusunu çizmeye çalışan bir prediction (tahmin) algoritmasıdır. Bu doğrunun çizilmesindeki amaç ise tahmin edilmesi istenen değere (bağımlı değişken) en yakın sonuçları üretebilmektir.

Regresyon çeşitleri: Basit Lineer Regresyon, Çoklu Lineer Regresyon, Ridge Regresyon, Lasso Regresyon, Elastic Net Regresyon, 

Robust (Dayanıklı) Lineer Regresyon.
Çoklu Lineer Regresyon: Çoklu doğrusal regresyon modeli ise sistemde birden fazla bağımsız değişkenin sonucu etkilediği durumlarda kullanılmaktadır. Aslında kullanımı ve mantığı basit doğrusal regresyon ile benzerdir. Sadece birden fazla değişken işin içinde olduğundan dolayı doğru denklemimiz şu şekilde temsil edilir:
y= b0 + ax1 + bx2 + cx3 + d

Ridge Regresyon(L2 regularization): Çok değişkenli regresyon verilerini analiz etmede kullanılır. Amaç hata kareler toplamını minimize eden katsayıları, bu katsayılara bir ceza uygulayarak bulmaktır. Over-fittinge karşı dirençlidir. Çok boyutluluğa çözüm sunar. Tüm değişkenler ile model kurar, ilgisiz değişkenleri çıkarmaz sadece katsayılarını sıfıra yaklaştırır. Modeli kurarken alpha (ceza) için iyi bir değer bulmak gerekir.
 
Lasso Regresyon(L1 regularization): Ürettiği modelin tahmin doğruluğunu ve yorumlanabilirliğini arttırmak için hem değişken seçimi hem de regularization yapar. Aynı ridge regresyonda olduğu gibi amaç hata kareler toplamını minimize eden katsayıları, katsayılara ceza uygularayarak bulmaktır. Fakat ridge regresyondan farklı olarak ilgisiz değişkenlerin katsayılarını sıfıra eşitler.
 
Elastic Net Regresyon: Amaç ridge ve lasso regresyon ile aynıdır ama elastic net, ridge ve lasso regresyonu birleştirir. Ridge regresyon tarzı cezalandırma ve lasso regresyon tarzında değişken seçimi yapar.
 
Robust (Dayanıklı) Lineer Regresyon: Uzaktaki(outliers) faktörlerin etkilerini (ağırlıklarını) azaltmak için sağlam tahminciler kullanılır.

Minimum Kareler Metotu
Doğrunun ne kadar isabetli olduğunu tespit edebilmek için bir takım yöntemler kullanılır. Bunlardan biri de min-squared error (MSE)’dir. Amacımız bu hatanın olabilecek en düşük değere ulaşmasıdır. Bu fonksiyona aynı zamanda cost function(loss function) denir.
 
Gradient Descent Algoritması Nedir?
Kayıp fonksiyonun değerini düşürmek için sistemimizi backward progress denen bir süreçten geçiririz. Bu süreçte amacımız ortaya attığımız lineer regresyon fonksiyonun optimizasyonunu gerçekleştirmektir.
Buradaki a değişkenimiz öğrenme oranını sembolize etmektedir. Ağırlık fonksiyonun local minimum değerine yaklaşması açısından önem arz eder çünkü local minumum değeri hata fonksiyonun en az olduğu değerdir.
Gradient descent türleri: Batch, Stochastic, Mini-Batch

Batch Gradient Descent
Gradient tüm veri seti üzerinden hesaplanır. Güncellemeler daha kesin ve kararlıdır.

Stochastic Gradient Descent (SGD)
Gradient her bir veri örneği için ayrı ayrı hesaplanır. Daha hızlıdır, ancak güncellemeler gürültülü olabilir.

Mini-Batch Gradient Descent
Gradient, veri setinden rastgele seçilen küçük bir alt küme (mini-batch) üzerinde hesaplanır. Batch ve SGD arasında bir denge sağlar.
