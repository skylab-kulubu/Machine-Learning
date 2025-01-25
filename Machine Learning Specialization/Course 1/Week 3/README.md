# Week 3

## Sınıflandırma Nedir?

Makine öğrenmesinde sınıflandırma, veri kümeleri üzerinde, yeni bir girdi verisinin eğitim sonucu belirlenen sınıflardan hangisine ait olduğunu belirleme sorunudur. Sınıflandırma problemini çözen algoritmaya sınıflandırıcı (classifier), tahmin edilen örneklerden sınıflara doğru yönlendirmeye de sınıflandırma modeli (classification model) denir.

Bir model, eğitim veri kümesi (training dataset) kullanarak daha önce görmediği test verilerinin sınıf etiketleriyle (label) nasıl eşleşeceğini hesaplar. Örneğin bir varlığın köpek, kedi vs. olduğunu belirlemek birer sınıflandırma modelidir.

**Example:**

|Question|Answer|
|-----------|----------|
|Is this email spam?|Yes or no|
|Is the transaction fraudulent?|Yes or no|
|Is the tumor malignant?|Yes or no|

## İkili Sınıflandırma

İkili sınıflandırma, bir girdi verisi için iki çıktıdan birini üreten bir sınıflandırma yöntemidir. Örneğin; e-posta mesajlarını “spam” olup olmadığını değerlendiren makine öğrenme modeli, kalite kontrol standartlarına göre bir ürünün kaliteli veya kalitesiz olduğuna karar veren makine öğrenme modeli birer ikili sınıflandırıcıdır.

İkili sınıflandırma pozitif sınıf ve negatif sınıf olarak ikiye ayrılır. Test sonuçlarına göre bir hastanın bulaşıcı virüs taşıyıp taşımadığını belirleyen bir model düşünün. Test sonucu negatifse hastanın sağlıklı olduğu, test sonucu pozitifse hastanın virüs taşıdığı kabul edilir. Burada pozitif sınıf pozitif testtir (virüs taşıyan hasta)  . Negatif sınıf ise negatif testtir (sağlıklı birey). Modelin her zaman mükemmel çalışacağını ve doğru tahminler yapacağını varsayamayız. Sağlıklı bir bireyin test sonucu pozitif olarak (virüs taşıyan bir hasta olarak) sınıflandırılabilir. Bu tür hataya yanlış ya da pozitif [false-  positive(FP)] denir. Aynı zamanda virüs taşıyan bir hastanın test sonucu negatif (sağlıklı bir birey) olarak sınıflandırılabilir. Bu tür hataya da yanlış-negatif [false-negative(FN)] denir. Bu hatalar çok ciddi sorunlara yol açabilir.

![Binary Classification](https://www.sharpsightlabs.com/wp-content/uploads/2023/12/binary-classification_simple-example.png)

+ ## İkili Sınıflandırmanın Kullanım Alanları
  İkili sınıflandırma, çeşitli alanlarda geniş bir uygulama yelpazesine sahiptir:

  -**Tıp:** Bir hastalığın teşhisi (örneğin, "kanser var mı, yok mu?").

  -**Finans:** Müşterilerin kredi riskini değerlendirme (örneğin, "bu müşteri kredi ödeyebilir mi?").

  -**Doğal Dil İşleme:** E-postaların spam olup olmadığını belirleme.

  -**Biyoinformatik:** Genetik dizilimlerin bir hastalıkla ilişkili olup olmadığını sınıflandırma.

  -**Görüntü İşleme:** Görüntüde belirli bir nesnenin bulunup bulunmadığını algılama.

+ ## İkili Sınıflandırma Algoritmaları

  İkili sınıflandırma için kullanılan bazı yaygın algoritmalar:

  -**Lojistik Regresyon:** İkili sınıflandırma problemlerinde en yaygın kullanılan algoritmalardan biridir. Tahmin edilen olasılık, sigmoid fonksiyonu ile hesaplanır.

  -**Destek Vektör Makineleri** (SVM): Doğrusal veya doğrusal olmayan bir karar sınırı kullanarak sınıflandırma yapar.

  -**Karar Ağaçları:** Veriyi bir dizi kurala göre bölerek sınıflandırır.
,0
  -**K-En Yakın Komşu (K-NN):** Yeni bir örneği, en yakın komşularının sınıfına göre sınıflandırır.

+ ## İkili Sınıflandırmada Performans Ölçütleri

  Bir ikili sınıflandırma modelinin başarısını değerlendirmek için çeşitli metrikler kullanılır:

  -**Doğruluk (Accuracy):** Doğru tahminlerin tüm tahminlere oranı.

  -**Hassasiyet (Precision):** Doğru pozitif tahminlerin, toplam pozitif tahminlere oranı.

  -**Duyarlılık (Recall):** Gerçek pozitif sınıfların, toplam gerçek pozitif sınıflara oranı.

  -**F1 Skoru:** Hassasiyet ve duyarlılığın harmonik ortalaması.

  -**ROC Eğrisi ve AUC:** Modelin farklı eşik değerlerinde nasıl performans gösterdiğini analiz eder.

+ ## İkili Sınıflandırmada Zorluklar

  -**Dengesiz Veri:** Pozitif ve negatif sınıfların dağılımı dengesiz olduğunda, model doğru performans gösteremeyebilir. Bu durumda veri dengeleme teknikleri (örneğin, oversampling veya undersampling) kullanılır.

  -**Overfitting:** Model, eğitildiği veriyle çok iyi uyum sağlarken yeni verilerde kötü performans gösterebilir. Bu sorun regularization veya daha fazla veri toplama ile çözülebilir.

## Lojistik Regresyon

  Lojistik regresyon, bir sınıflandırma yöntemidir. Adındaki "regresyon" kelimesi kafa karıştırıcı olabilir, çünkü lojistik regresyon bir şeyin miktarını tahmin etmekle değil, hangi sınıfa ait olduğunu belirlemekle ilgilidir. Örneğin, bir e-postanın spam olup olmadığını veya bir müşterinin kredi ödemesini yapıp yapmayacağını anlamak için kullanılır.

![Logistic Regression](https://images.spiceworks.com/wp-content/uploads/2022/04/11040521/46-4-e1715636469361.png)

+ ## Lojistik Regresyon Neden Kullanılır?

  Lojistik regresyon, elimizdeki veriyi iki sınıfa ayırmamız gerektiğinde işe yarar. Örneğin, bir grup hasta hakkında bilgileriniz varsa ve bu hastaların belirli bir hastalığa sahip olup olmadığını tahmin etmek istiyorsanız, lojistik regresyon size bu sorunun cevabını verebilir. Bu yöntem, belirli bir durumun gerçekleşme olasılığını hesaplar ve bu olasılığa göre sınıflandırma yapar.
  
+ ## Lojistik Regresyon Nasıl Çalışır?

  Lojistik regresyon, tahmin edilen bir sayıyı (örneğin hastalık olasılığı) 0 ile 1 arasında bir değere çevirmek için sigmoid fonksiyonu kullanır. Veriler (örneğin yaş, kilo, kan test sonuçları) matematiksel bir denklemde işlenir ve çıkan değer sigmoid fonksiyonundan geçirilir. Bu işlem, bize olayın (örneğin hastalık) olma olasılığını verir. Çıktı %50’nin üzerindeyse pozitif sınıf (örneğin "hastalık var"), altında ise negatif sınıf (örneğin "hastalık yok") olarak sınıflandırılır.

+ ## Lojistik Regresyonun Avantajları Nelerdir?

  Lojistik regresyon, özellikle basit ama etkili bir çözüm arandığında tercih edilir.

  -	Veriler arasında çok karmaşık bir ilişki olmadığında ve iki sınıf net bir şekilde ayrılabiliyorsa, hızlı ve doğru sonuçlar verir.

  - Az veriyle çalışabilir ve fazla hesaplama gücü gerektirmez.

  -	Modelin sonuçlarını anlamak kolaydır, çünkü bir olayın olasılığını açık bir şekilde sunar.

+ ## Lojistik Regresyonun Sınırlamaları Nelerdir?

  -	Her durumda lojistik regresyon ideal bir yöntem olmayabilir. Eğer:
  -	Veriler çok karmaşıksa,
  -	İki sınıf arasındaki sınır net değilse;
      *  Daha karmaşık algoritmalar daha iyi sonuçlar verebilir. Ancak basitlik,      açıklık ve hız isteniyorsa, lojistik regresyon genellikle iyi bir başlangıç noktasıdır.

+ ## Lojistik Regresyon Çıktısının Yorumlanması

  Lojistik regresyonun çıktısı, bir bağımlı değişkenin belirli bir sınıfa ait olma olasılığını ifade eder. Bu çıktı, 0 ile 1 arasında bir değer alır ve bir olayın gerçekleşme olasılığı olarak yorumlanır. Lojistik regresyonun temel amacı, verileri kullanarak iki sınıf arasındaki farkı belirlemek ve bu farkı matematiksel olarak açıklamaktır.

![Interpretation of Logistic Regression Output](https://velog.velcdn.com/images/brandonnam/post/bb233eca-83e5-4ea8-b5fa-125e09fef358/image.png)

  Modelin temel formülü, bir sınıfın (örneğin, kötü huylu tümör) olma olasılığını hesaplayan sigmoid fonksiyonudur. Çıktı fw,b(x⃗)f_{w,b}(\vec{x})fw,b (x), 000 ile 111 arasında bir olasılık değeri verir. Örneğin, fw,b(x⃗)=0.7f_{w,b}(\vec{x}) = 0.7fw,b (x)=0.7 ise, bu, y=1y=1y=1 (kötü huylu tümör) olma olasılığının %70 olduğunu gösterir. Ayrıca, iki sınıfın olasılıklarının toplamı her zaman 1’dir: 

`` P(y=0)+P(y=1)=1 P(y=0)+P(y=1)=1 P(y=0)+P(y=1)=1 ``

## Karar Sınırı

Karar sınırı, makine öğreniminde bir özellik alanındaki farklı sınıfları ayıran bir hiper yüzeydir. Modelin tahmininin bir sınıftan diğerine geçtiği alanı temsil eder. Örneğin, iki boyutlu bir öznitelik uzayında, karar sınırı, bir ikili sınıflandırma probleminde iki sınıfı ayıran bir çizgi veya eğri olabilir. Modelin farklı sınıflar arasında ayrım yapmasına yardımcı olur, böylece görünmeyen veriler üzerinde doğru tahminler yapılmasını sağlar.

Karar sınırı, bir makine öğrenmesi modelinin eğitim aşaması sırasında öğrenilir ve daha sonra görünmeyen veri noktalarının sınıfını tahmin etmek için kullanılır. Karar sınırının doğası ve karmaşıklığı, eldeki soruna, mevcut verilere, seçilen modele ve öğrenme sürecine bağlı olarak değişebilir.

Doğrusal ve doğrusal olmayan dahil olmak üzere farklı karar sınırları vardır. Doğrusal karar sınırı, verileri iki sınıfa ayıran düz bir çizgidir ve sınıflandırma problemi doğrusal olarak ayrılabilir olduğunda kullanılır. Öte yandan, doğrusal olmayan bir karar sınırı, verileri iki veya daha fazla sınıfa ayıran eğri bir çizgidir.

Karar sınırının doğruluğu ve genelleştirme yetenekleri çok önemlidir. Sınır iyi tanımlanmışsa ve sınıfları temiz bir şekilde ayırıyorsa, modelin tahminlerinin doğruluğu artar. Bununla birlikte, karar sınırı çok kesinse veya eğitim verilerine 'gereğinden fazla uyuyorsa', yeni verilere iyi bir şekilde genellenmeyebilir. Buna karşılık, bir karar sınırı çok esnekse veya verilere iyi uymuyorsa yeterince doğru olmayabilir.

Görselleştirme açısından, modelin sınıflandırma davranışını daha iyi anlamak için karar sınırları çizilebilir. Örneğin, Python'da bir modelin karar sınırını çizmek için matplotlib veya seaborn gibi kitaplıkları kullanabilirsiniz.

+ ## Makine öğreniminde karar sınırları nasıl kullanılır?
Karar sınırları, makine öğreniminde, özellikle sınıflandırma görevlerinde temel bir kavramdır. Bunlar, özellik alanındaki farklı veri noktası gruplarını ayıran yüzeyi veya çizgiyi temsil eder. Eğitim sırasında, bir makine öğrenimi algoritması bu karar sınırını öğrenir ve daha sonra görünmeyen veri noktalarının sınıfını tahmin etmek için kullanır.

  Karar sınırı, eğitim verilerinin bir özelliği değil, sınıflandırıcının bir özelliğidir. Farklı sınıflandırıcılar farklı karar sınırlarına yol açabilir. Örneğin, lojistik regresyonda karar sınırı düz bir çizgi iken, sinir ağları gibi doğrusal olmayan sınıflandırma yöntemlerinde karar sınırı bir eğri olabilir.

  Karar sınırının karmaşıklığı, model ve kullanılan özellikler tarafından belirlenir. Lojistik regresyon veya doğrusal destek vektör makineleri (SVM'ler) gibi basit modeller genellikle doğrusal karar sınırları üretirken, sinir ağları veya k-en yakın komşular (KNN) gibi daha karmaşık modeller doğrusal olmayan karar sınırları üretebilir.

  Karar sınırının kalitesi, bir makine öğrenimi modelinin etkinliğini önemli ölçüde etkiler. Kesin ve iyi tanımlanmış karar sınırları, gelişmiş sınıflandırma doğruluğuna katkıda bulunur ve böylece yapay zeka modellerinin genel tahmin yeteneklerini etkiler. Bununla birlikte, özellikle bir sınıfa veya diğerine üyeliğin belirsiz olduğu bulanık mantık tabanlı sınıflandırma algoritmalarında, karar sınırlarının her zaman kesin olmadığını belirtmek önemlidir.

  Dengesiz veriler bağlamında, karar sınırı çoğunluk sınıfına karşı önyargılı olabilir ve bu da azınlık sınıfının tahmininde bir miktar önyargıya neden olabilir. Karar eşiğindeki ayarlamalar, sınıf dengesizliği aşırı olmadıkça bu önyargıyı hafifletebilir.

  Sinir ağları söz konusu olduğunda, ağın öğrenebileceği karar sınırının türü, gizli katmanların sayısına göre belirlenir. Gizli katmanları yoksa, o zaman sadece doğrusal problemleri öğrenebilir. Gizli bir katmanı varsa, herhangi bir sürekli işlevi öğrenebilir.
  
+ ## Karar sınırlarını bulmak için bazı yaygın yöntemler nelerdir?

Karar sınırlarını bulmak için birkaç yaygın yöntem vardır:

1.	Doğrusal Sınıflandırma — Doğrusal karar sınırları, giriş özelliklerinin doğrusal fonksiyonlarıdır. Bunlar, D boyutlu bir giriş uzayındaki (D-1) boyutlu hiperdüzlemlerdir. Örneğin, bir 3 boyutlu özellikler kümesi 2B karar sınırlarına (düzlemler) sahip olacaktır ve bir dizi 2 boyutlu özellik 1B karar sınırlarına (çizgiler) sahip olacaktır.

2.	Doğrusal Olmayan Sınıflandırma — Doğrusal olmayan karar sınırları, özellik alanını dönüştürerek veya sinir ağları gibi belirli modeller kullanılarak elde edilebilir. Örneğin, gizli katmanlara sahip bir sinir ağı, doğrusal olmayan karar sınırlarını öğrenebilir.

3.	Kernel Trick — Çekirdek hilesi, Destek Vektör Makinelerinde (SVM'ler) doğrusal olmayan karar sınırları oluşturmak için kullanılan bir yöntemdir. Verilerin, karar sınırının doğrusal olabileceği daha yüksek boyutlu bir alana eşlenmesini içerir. Bu süreç, sinir ağlarındaki gizli katmanların doğrusal olmayan karar sınırı problemini nasıl çözdüğüne benzer.

4.	Karar Ağaçları ve Sinir Ağları — Karar sınırları, karar ağaçları ve sinir ağları kullanılarak da oluşturulabilir. Bu yöntemler, doğrusal olarak ayrılamayan verileri işleyebilen karmaşık karar sınırları oluşturabilir.

5.	Lojistik Regresyon — Lojistik regresyon, girdi özelliklerini polinom lojistik regresyon kullanmak gibi belirli bir şekilde işleyerek doğrusal olmayan karar sınırları oluşturabilir.

Yöntem seçimi, modelin karmaşıklığına, özellik kümesine ve eldeki sorunun doğasına bağlıdır. Model karmaşıklığı ile verilerin fazla veya yetersiz sığdırılması riski arasındaki dengeyi göz önünde bulundurmak da önemlidir.

+ ## Daha iyi performans için karar sınırları nasıl optimize edilebilir?

Karar sınırlarının optimize edilmesi, makine öğrenimi modellerinin performansını önemli ölçüde artırabilir. Bunu başarmak için bazı stratejiler şunlardır:

1.	Sınır Kalınlığı — Kalın karar sınırları daha iyi performans ve sağlamlığa yol açabilirken, ince karar sınırları aşırı uyuma neden olabilir. Bu nedenle, sınır kalınlığını açıkça artıran öğrenme algoritmaları tasarlamak faydalı olabilir.

2.	Esneklik ve Kesinlik — Karar sınırı, aykırı değerler de dahil olmak üzere verilerin karmaşıklığına uyum sağlayacak kadar esnek olmalıdır. Bununla birlikte, farklı sınıfları doğru bir şekilde ayırmak için yeterince kesin olmalıdır. Aşırı esnek sınırlar verilere tam olarak uymayabilirken, aşırı kesin sınırlar eğitim verilerine gereğinden fazla sığabilir ve yeni verilere iyi bir şekilde genellenmeyebilir.

3.	Sınıf Sınırı Etiketi Belirsizliğinin Azaltılması — Karar sınırı, daha fazla sınır eğitimi örneğini barındıracak şekilde uyarlanabilir ve bu da eğitim doğruluğunu artırabilir. Ancak, bu daha karmaşık bir sınıflandırma modeliyle sonuçlanabilir.

4.	Sınır Yumuşatma — Karar sınırlarının yumuşatılması, aşırı uyumun önlenmesine yardımcı olabilir. Bu, sınır örneklerini ortadan kaldırarak başarılabilir.

5.	En Yakın Komşular — Karar sınırları, bir numunenin ve en yakın komşularının tahmininin ağırlıklı ortalaması yapılarak iyileştirilebilir. Bu yaklaşım, ağ mimarisinde, eğitim prosedüründe veya veri kümesinde herhangi bir değişiklik gerektirmez.

6.	Yanlılık-Varyans Ödünleşimi — Karar sınırının karmaşıklığı, yanlılık-varyans ödünleşimini etkileyebilir. Örneğin, k-en yakın komşularda (kNN) daha küçük k değerleriyle, karar sınırları pürüzlü ve karmaşıktır (yüksek varyans), ancak daha büyük k değerleri için basit ve düzdür (yüksek yanlılık). Bu nedenle, daha iyi performans için yanlılık ve varyans arasında optimal bir denge sağlanmalıdır.

7.	Reddetme Seçeneğine Dayalı Sınıflandırma (ROC) — Bu teknik, çoğu ayrımcılığın, bir modelin tahminden en az emin olduğu zaman, yani karar sınırı çevresinde meydana geldiğini varsayar. Ayrımcılığın azaltılması için bir sınıflandırıcının düşük güven bölgesinden yararlanarak, model tahminlerindeki yanlılık azaltılabilir.

Strateji seçimi, belirli bir soruna ve verilerin doğasına bağlıdır. Nasıl geliştiklerini anlamak ve olası kusurları bulmak için hem eğitim hem de test sırasında karar sınırlarını görselleştirmek ve analiz etmek de önemlidir.

+ ## Karar sınırları ile sınıf sınırı etiketi belirsizliği arasındaki ilişki nedir?
Karar sınırları ve sınıf sınırı etiketi belirsizliği arasındaki ilişki, model karmaşıklığı ile görünmeyen verilere genelleştirme yeteneği arasındaki değiş tokuş etrafında toplanmıştır. Bir sınıflandırma modelinin karar sınırı, daha fazla sınır eğitim örneğini barındıracak şekilde ince ayarlandığında, daha düşük yanlılık nedeniyle eğitim doğruluğunu artırabilir, ancak potansiyel olarak daha yüksek varyans pahasına genellemeye zarar verebilir. Bu ince ayar, model karmaşıklığını artırır ve modelin eğitim verilerinde iyi performans gösterdiği ancak yeni, görünmeyen verilerde kötü performans gösterdiği aşırı öğrenmeye yol açabilir.

Sınıf sınırı etiketi belirsizliği, eğitim verilerinin etiketlerinde belirsizlik veya gürültü olduğunda ortaya çıkar, bu da öznel etiketleme süreçleri veya sınıflar arasındaki doğal örtüşmeler gibi çeşitli faktörlerden kaynaklanabilir. Bir karar sınırı, yanlış etiketlenmiş bir noktayı içerecek şekilde genişletilirse, modeldeki hem yanlılığı hem de varyansı artırabilir.

Sınıf sınırı etiketi belirsizliğinin etkilerini azaltmak için bir yaklaşım, eğitim setinin noktasal etiket belirsizliğini tahmin etmek ve öğrenme sürecini buna göre ayarlamaktır. Bu, belirsiz etiketlere sahip örneklerin, modelin öğrenme sürecinin nesnel işlevi üzerinde daha küçük bir etkiye sahip olduğu anlamına gelir ve bu da hem yanlılığı hem de varyansı azaltmaya yardımcı olabilir. Bu yaklaşım, özellikle bazı etiketlerin diğerlerinden daha az güvenilir olduğunu gösteren kanıtlar olduğunda, tüm eğitim örneklerinin eşit şekilde ele alınmaması gerektiğini kabul eder.

Karar sınırları ve sınıf sınırı etiket belirsizliği arasındaki ilişki, amacın aşırı karmaşık veya etiket gürültüsüne duyarlı olmadan doğru ve genelleştirilebilir bir karar sınırı elde etmek olduğu bir dengeleme eylemidir. Etiket belirsizliğini hesaba katan yöntemler, belirsiz etiketlerin modelin öğrenme süreci üzerindeki etkisini azaltarak karar sınırının sağlamlığını artırmayı amaçlar.

+ ##Doğrusal ve doğrusal olmayan karar sınırları arasındaki fark nedir?
Doğrusal ve doğrusal olmayan karar sınırları arasındaki fark, karmaşıklıklarında ve ayırabilecekleri veri türünde yatmaktadır.

Doğrusal karar sınırı, bir özellik uzayında farklı sınıfları ayıran düz bir çizgi (iki boyutta), bir düzlem (üç boyutta) veya bir hiper düzlemdir (üçten fazla boyutta). Doğrusal karar sınırları, veriler doğrusal olarak ayrılabilir olduğunda kullanılır, yani düz bir çizgi veya düzlem, sınıfları herhangi bir yanlış sınıflandırma olmadan ayırabilir. Doğrusal karar sınırları daha basit ve yorumlanması daha kolaydır, ancak veriler doğrusal olarak ayrılabilir olmadığında iyi performans göstermeyebilir.

Öte yandan, doğrusal olmayan bir karar sınırı, bir özellik uzayındaki farklı sınıfları ayıran bir eğri veya daha karmaşık bir şekil olabilir. Doğrusal olmayan karar sınırları, veriler doğrusal olarak ayrılamadığında, yani düz bir çizgi veya düzlemin yanlış sınıflandırma olmadan sınıfları ayıramayacağı durumlarda kullanılır. Doğrusal olmayan karar sınırları, daha karmaşık veri dağıtımlarını işleyebilir ve veriler doğrusal olarak ayrılabilir olmadığında daha doğru sınıflandırmalara yol açabilir. Ancak, daha karmaşıktırlar ve yorumlanmaları daha zordur.

Sınıflandırıcılar açısından, lojistik regresyon veya doğrusal destek vektör makineleri (SVM'ler) gibi doğrusal sınıflandırıcılar genellikle doğrusal karar sınırları üretirken, sinir ağları veya k-en yakın komşular (KNN) gibi doğrusal olmayan sınıflandırıcılar doğrusal olmayan karar sınırları üretebilir. Örneğin, SVM'lerde, orijinal özellik uzayında doğrusal olmayan görünse bile, verileri karar sınırının doğrusal olabileceği daha yüksek boyutlu bir alana dönüştürmek için çekirdek hilesi adı verilen bir teknik kullanılır.

![Decision Boundry 1](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*8_qfUgM7ASaleuM47FkzcA.png)
![Decision Boundry 2](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi-zJVRtYF9cFHvOxZhUaYTtVlUM1vXXoPPj0Fmj6ssI03FOpTSEZcBhUJ-dB7TluclAxaawyRXipeyGi_4pgRqVDIbfd_mYjGgBl0hyphenhyphenxkfBuPM7krBJB-dzFK-8zZB665Rj6PCT9gGh_6f/s1600/nonlinearDB.JPG)

## Lojistik Regression Lineer Regression Farkı
Aşağıda  şekildeki görsel, lineer ve lojistik regresyonun matematiksel farklarını ve neden farklı davrandıklarını açıklıyor. Temelde, her iki yöntem de bir modelin yaptığı tahminlerle gerçek değerler arasındaki hatayı ölçmeye çalışır. Ancak bu ölçüm ve optimizasyon süreçleri farklıdır.

Lineer regresyonda amaç, verilen veriler üzerinden düz bir çizgi çizerek tahmin yapmak. Burada hata, tahmin edilen değerle gerçek değer arasındaki farkın karesiyle hesaplanır. Bu yöntemde hata fonksiyonunun şekli düzgün bir çanak gibidir, yani sadece bir tane en düşük nokta (global minimum) vardır. Bu, "konveks" yapı olarak adlandırılır ve doğru yöntemlerle bu en düşük noktayı bulmak oldukça kolaydır.

Lojistik regresyon ise genelde sınıflandırma problemleri için kullanılır (örneğin, evet/hayır gibi iki seçenek). Tahminler, 0 ile 1 arasında bir olasılık olarak ifade edilir. Bu yöntemde hata fonksiyonu daha karmaşıktır ve birden fazla düşük nokta olabilir (bunlara "lokal minimum" denir). Bu da optimizasyonu, yani hatayı en aza indirmeyi daha zor hale getirebilir.

Görselde ayrıca "loss" ve "cost" kavramlarına değinilmiş. Basitçe, "loss" tek bir veri noktası için yapılan hatayı gösterirken, "cost" tüm veri kümesindeki hataların ortalamasıdır. Yani "loss", bireysel bir sorun, "cost" ise genel tabloyu gösterir.

Sonuç olarak, lineer regresyon hataları azaltmada daha basit ve doğrudan bir yola sahipken, lojistik regresyon daha karmaşık bir yapıda çalışır ve optimizasyonu daha dikkatli bir yaklaşım gerektirir.

![Logistic1](https://github.com/user-attachments/assets/77fd2b9f-bb5a-4822-a5b0-acadd866051a)
![Logistic2](https://global.discourse-cdn.com/dlai/original/3X/c/2/c22ec781fe0d6baf52100555824f82d9537b5e0f.jpeg)


## Logistic Loss Function

Lojistik regresyonun bu kayıp fonksiyonu, modelin tahminlerini doğru yöne itmek için tasarlanmıştır. Doğru tahminlerde düşük bir ceza verirken, yanlış tahminlerde ağır bir ceza uygular. Bu yapı, modelin sınıflandırma görevlerinde daha iyi performans göstermesini sağlar. Özellikle yanlış sınıflandırmaların yüksek maliyeti olan durumlarda (örneğin, tıbbi teşhis), bu fonksiyon çok kullanışlıdır.

![image](https://github.com/user-attachments/assets/4a89e805-5877-4819-a495-39c68594960c)

Eğer gerçek etiket y=1y = 1y=1 ise, modelin tahmini ne kadar 1'e yakınsa (yani doğru tahmin yapıyorsa), kayıp o kadar düşük olur. Tahmin tamamen 1 olduğunda kayıp sıfıra yaklaşır. Ancak modelin tahmini 0'a yaklaştıkça kayıp hızla artar.

Eğer gerçek etiket y=0y = 0y=0 ise, modelin tahmini ne kadar 0'a yakınsa, kayıp o kadar düşük olur. Ancak tahmin 1'e yaklaştıkça kayıp artar.
Logaritmik yapı, bu kayıpları daha hassas bir şekilde ölçmemizi sağlar ve yanlış tahminlerde daha ağır bir ceza uygular. Bu, modelin doğru tahmin yapmaya daha fazla odaklanmasını sağlar.

![image](https://github.com/user-attachments/assets/ac3e1284-d113-42bb-bb2f-bf34aed55cc3)

Bu görselde benzer bilgiler biraz daha detaylı ele alınıyor:

Eğer gerçek değer y=0y = 0y=0 ise ve modelin tahmini fff 0'a yakınsa, kayıp düşüktür. Ancak tahmin 1'e yaklaştığında kayıp hızla artar ve teorik olarak sonsuza gidebilir. Örneğin, model bir veriyi yanlışlıkla "1" (örneğin, kanser var) olarak tahmin ederse, bu ciddi bir hata olur ve kayıp çok büyük olur.
Eğer gerçek değer y=1y = 1y=1 ise ve modelin tahmini 1'e yaklaştıkça kayıp azalır. Ancak tahmin 0'a yaklaştıkça, kayıp yine hızla artar. 

Örneğin, model bir veriyi yanlışlıkla "0" (örneğin, kanser yok) olarak tahmin ederse, bu da ciddi bir hata olarak değerlendirilir.

Görseldeki grafikler, tahminin doğru olduğu durumda kaybın nasıl sıfıra yaklaştığını ve yanlış tahminlerde kaybın nasıl hızla arttığını görselleştiriyor.

## Lojistik Fonksiyon için maliyet fonsiyonu 
Lojistik regresyonda cost (maliyet) fonksiyonu, modelin tüm veri kümesi üzerindeki performansını ölçmek için kullanılan bir yöntemdir. Her bir veri noktasındaki loss (kayıp) fonksiyonunun ortalaması alınarak hesaplanır. Bu, modelin genel hatasını değerlendirmemize olanak tanır.

![image](https://github.com/user-attachments/assets/5980f9a9-ebff-4a17-b32b-92aacad82eba)

+ ## Cost Fonksiyonunun Amacı
Cost fonksiyonu, bir modelin yaptığı tahminlerin doğruluğunu ölçen bir araçtır. Modelin tüm veri setindeki performansını özetleyerek, hataları sayısal olarak ifade eder. Amaç, bu fonksiyonu minimize ederek modeli daha doğru hale getirmektir. Bu, modelin parametrelerini (örneğin, ağırlıklar ve bias) ayarlamak için kullanılır.

Cost fonksiyonu üç temel amaca hizmet eder:

1.	Tüm Veriyi Kapsar: Birkaç tahminin doğru olması yeterli değildir; modelin tüm veri setindeki genel başarısı önemlidir.
2.	Modeli Yönlendirir: Hataları belirler ve bu hataları azaltacak şekilde modelin öğrenmesine rehberlik eder.
3.	Doğruyu Ödüllendirir, Yanlışı Cezalandırır: Doğru tahminlere küçük, yanlış tahminlere büyük bir maliyet (hata) değeri verir.

+ ## Lojistik Regresyonda Cost Fonksiyonu Nasıl Çalışır?
Lojistik regresyonda tahminler, modelin bir örneğin y=1y = 1y=1 ya da y=0y = 0y=0 olma olasılığını tahmin etmesine dayanır. Cost fonksiyonu, bu olasılıklar ile gerçek değerler arasındaki farkı değerlendirir:

Gerçek etiket y=1y = 1y=1: Modelin tahmini f(x)f(x)f(x) değeri 1’e yaklaştıkça cost düşer. Eğer tahmin 0’a yaklaşırsa, cost hızla artar.

Gerçek etiket y=0y = 0y=0: Modelin tahmini f(x)f(x)f(x) değeri 0’a yaklaştıkça cost düşer. Eğer tahmin 1’e yaklaşırsa, cost hızla artar.

Bu yapı, modeli yanlış tahminlere karşı daha hassas hale getirir. Yanlış tahminler yapıldığında cost değeri çok yükselir, bu da modelin o tür hataları düzeltmesi için daha fazla öğrenmesini sağlar.

## Cost Fonksiyonunun Özellikleri 

1.	Tüm Veri Üzerinde Ortalama Performans: Her bir veri noktası için hesaplanan hataları birleştirir ve tüm veri seti üzerindeki ortalama hatayı ölçer.
2.	Hataları Minimize Etme: Modeli daha iyi hale getirmek için öğrenme sürecinde hataları azaltmaya çalışır.
3.	Dengeli Hesaplama: Doğru tahminlere düşük maliyet, yanlış tahminlere yüksek maliyet vererek modelin genel başarısını optimize eder.

 Bir örnekle açıklamak gerekirse;
 
Bir öğretmen, öğrencilerinin sınav sonuçlarını değerlendirmek için bir sistem kuruyor. Eğer bir öğrenci doğru cevabı verdiyse, düşük bir hata puanı alıyor. Yanlış cevaplar verdiğinde ise hata puanı hızla artıyor. Ardından, tüm öğrencilerin hata puanlarının ortalamasını hesaplayarak sınıfın genel başarısını ölçüyor. Öğrencilerin kendini geliştirmesi için de bu hata puanlarını düşürmelerini hedefliyor.

Cost fonksiyonu, aynen bu öğretmen gibi çalışıyor: Her bir veri noktasındaki hatayı ölçüyor, ortalamasını alıyor ve modeli geliştirmek için bu hataları minimize etmeye çalışıyor.

## Gradyan inişi
![image](https://github.com/user-attachments/assets/41f818a9-a703-41d1-9bde-aed06c22a84f)

+ ## Gradient descent implementation
En iyi w ve b’yi bulmak için gradyan iniş algoritmasını kullanıyoruz. Gradyan iniş ve türevleri makine öğrenmesinde yaygın olarak kullanılır.
![image](https://github.com/user-attachments/assets/e1569a2d-b562-4430-a6e9-3470ee8ef33f)

Gradient Descent algoritması, maliyet fonksiyonundaki minimum değeri bulmak için kullanılan birinci dereceden yinelemeli bir optimizasyondur. Bu yaklaşımda, w (ağırlıkları) rastgele bir değerle başlatır ve gradyanı buluruz. Sonra w’yi gradyanın ters yönünde güncelleriz. Ve bu süreç minimum maliyet bulunana kadar devam eder. Gradyan her zaman en büyük artışın olduğu yönü gösterir, bu yüzden minimum veya iniş noktasını bulmak için ağırlıkları gradyanın ters yönünde güncelleriz. Aynı yaklaşımı b’nin minimumunu bulmak için de uygularız.

Çoklu doğrusal regresyon algoritmasına dayanarak, aşağıda gösterildiği gibi gradyan iniş algoritmasını uygulayabileceğimizi biliyoruz.
![image](https://github.com/user-attachments/assets/b9ae8443-370b-4d9a-a6db-9ef3add35ac8)

Algoritmanın türevini daha da genişleterek uygulamaya hazır hale getirebiliriz. Bu kavram doğrusal regresyondan alınmıştır.
![image](https://github.com/user-attachments/assets/db250d73-2ca2-4c0b-9026-c55b52893506)
![image](https://github.com/user-attachments/assets/81b1166f-f6e6-45e8-aff9-b9295ee60c07)

Gradyan inişine hazır algoritmayı tamamlamak için f terimini sigmoid fonksiyonuyla yeniden yazabiliriz.
![image](https://github.com/user-attachments/assets/d1ec6d02-706c-4859-9c9e-d2ca1aef1d2c)


## Uyumun İyiliği
İstatistikte uyum iyiliği , bir modelin tahmin edilen değerlerinin gözlenen (gerçek) değerlerle ne kadar yakın eşleştiğini ifade eder.

Sinyal yerine gürültüyü öğrenen bir model, eğitim veri setine uyduğu ancak yeni veri setleriyle zayıf uyum sağladığı için "aşırı uyum" olarak kabul edilir.
![image](https://github.com/user-attachments/assets/eb881f71-8d57-4d3c-a7d4-9c6cd587af1f)


+ ## Aşırı Uyum ve Yetersiz Uyum
Aşırı uyumu, tam tersi sorun olan yetersiz uyuma bakarak daha iyi anlayabiliriz.

Yetersiz uyum, bir modelin çok basit olması durumunda ortaya çıkar; çok az özellik ile bilgilendirilmiş veya çok fazla düzenlenmişse, bu da veri kümesinden öğrenmede esnek olmamasına neden olur.

Basit öğrenenler, tahminlerinde daha az varyansa sahip olma eğilimindedirler ancak yanlış sonuçlara doğru daha fazla önyargıya sahiptirler (bkz: Önyargı-Varyans Dengesi ).Öte yandan karmaşık öğrenenler tahminlerinde daha fazla varyansa sahip olma eğilimindedir.


+ ## Makine öğrenmesinde hem önyargı hem de varyans birer tahmin hatasıdır.
 Tipik olarak, önyargıdan kaynaklanan hatayı azaltabiliriz ancak bunun sonucunda varyanstan kaynaklanan hatayı artırabiliriz veya tam tersi.
  
 Çok basit (yüksek önyargı) ile çok karmaşık (yüksek varyans) arasındaki bu denge, istatistik ve makine öğrenmesinde temel bir kavramdır ve tüm denetlenen öğrenme algoritmalarını etkiler
 ![image](https://github.com/user-attachments/assets/c693c409-8f8b-44ec-8b11-62e64e200781)

+ ## Makine Öğrenmesinde Aşırı Uyum Nasıl Tespit Edilir
+ Aşırı uyumun ve genel olarak makine öğrenmesinin temel zorluklarından biri, modelimizin yeni verilerde ne kadar iyi performans göstereceğini, onu gerçekten test edene kadar bilemememizdir
+ Bunu ele almak için, başlangıç veri setimizi ayrı eğitim ve test alt kümelerine ayırabiliriz .
  
![image](https://github.com/user-attachments/assets/86e687b9-086e-4332-868a-bf9ef38ea1c7)

Bu yöntem, modelimizin yeni veriler üzerinde ne kadar iyi performans göstereceğini yaklaşık olarak tahmin etmemizi sağlayabilir.
 
Eğer modelimiz eğitim setinde test setinden çok daha iyi performans gösteriyorsa, o zaman büyük ihtimalle aşırı uyum sağlıyoruz demektir.
 
Örneğin, modelimiz eğitim setinde %99 doğruluk elde ederken test setinde yalnızca %55 doğruluk elde ederse bu büyük bir kırmızı bayrak olur.

## Makine Öğrenmesinde Aşırı Uyum Nasıl Önlenir
Aşırı uyumu tespit etmek yararlıdır, ancak sorunu çözmez. Neyse ki deneyebileceğiniz birkaç seçeneğiniz var.

Aşırı uyum sorununa yönelik en popüler çözümlerden birkaçı şunlardır:

+ ## Çapraz doğrulama
 Çapraz doğrulama, aşırı uyuma karşı güçlü bir önleyici tedbirdir.
 
Fikir akıllıca: İlk eğitim verilerinizi kullanarak birden fazla mini eğitim-test bölümü oluşturun. Bu bölümleri modelinizi ayarlamak için kullanın.

Standart k katlı çapraz doğrulamada, verileri katlama adı verilen k alt kümeye böleriz. Sonra, kalan katı test kümesi olarak kullanırken (buna "bekleme katı" denir) algoritmayı k-1 kat üzerinde yinelemeli olarak eğitiriz.

![image](https://github.com/user-attachments/assets/a92b4e68-4e89-4599-8425-209ab4a33b7f)

Çapraz doğrulama, hiperparametreleri yalnızca orijinal eğitim setinizle ayarlamanıza olanak tanır. Bu, test setinizi nihai modelinizi seçmek için gerçekten görülmemiş bir veri seti olarak tutmanıza olanak tanır.

+ ## Daha fazla veriyle eğitin
Her zaman işe yaramayacaktır, ancak daha fazla veriyle eğitim, algoritmaların sinyali daha iyi algılamasına yardımcı olabilir. Çocuklarda boy ve yaş modellemesinin daha önceki örneğinde, daha fazla okul örneklemesinin modelinize nasıl yardımcı olacağı açıktır.

Elbette, durum her zaman böyle değildir. Sadece daha gürültülü veriler eklersek, bu teknik işe yaramayacaktır. Bu yüzden verilerinizin her zaman temiz ve alakalı olduğundan emin olmalısınız.

+ ## Özellikleri kaldır
Bazı algoritmaların dahili özellik seçimi vardır.

Bunu yapmayanlar için, alakasız giriş özelliklerini kaldırarak genelleştirilebilirliklerini manuel olarak iyileştirebilirsiniz.

Bunu yapmanın ilginç bir yolu, her bir özelliğin modele nasıl uyduğuna dair bir hikaye anlatmaktır. Bu, veri bilimcisinin yazılım mühendisinin lastik ördek hata ayıklama tekniğine yaptığı yorum gibidir; burada kodlarını satır satır bir lastik ördeğe açıklayarak hata ayıklarlar.
Herhangi bir şey mantıklı gelmiyorsa veya belirli özellikleri haklı çıkarmak zorsa, bunları tanımlamanın iyi bir yolu budur.
Ayrıca, iyi bir başlangıç noktası için kullanabileceğiniz birkaç özellik seçimi buluşsal yöntemi vardır.


+ ## Erken durdurma
Bir öğrenme algoritmasını yinelemeli olarak eğittiğinizde , modelin her yinelemesinin ne kadar iyi performans gösterdiğini ölçebilirsiniz.
Belirli bir yineleme sayısına kadar, yeni yinelemeler modeli iyileştirir. Ancak bu noktadan sonra, eğitim verilerine aşırı uyum sağlamaya başladığından modelin genelleme yeteneği zayıflayabilir.

Erken durdurma, öğrencinin o noktayı geçmesinden önce eğitim sürecini durdurmak anlamına gelir.

![image](https://github.com/user-attachments/assets/e38a9b8a-778a-4210-8140-366f7e373df9)

Günümüzde bu teknik daha çok derin öğrenmede kullanılmakta olup klasik makine öğrenmesinde ise diğer teknikler (örneğin düzenleme) tercih edilmektedir.

+ ## Düzenleme

Düzenleme, modelinizi yapay olarak daha basit hale getirmek için kullanılan çok çeşitli teknikleri ifade eder.

Yöntem, kullandığınız öğrenen türüne bağlı olacaktır. Örneğin, bir karar ağacını budayabilir, bir sinir ağında bırakmayı kullanabilir veya regresyondaki maliyet fonksiyonuna bir ceza parametresi ekleyebilirsiniz.

Çoğu zaman, düzenleme yöntemi aynı zamanda bir hiperparametredir, yani çapraz doğrulama yoluyla ayarlanabilir.

+ ## Bir araya getirme
Topluluklar, birden fazla ayrı modelden gelen tahminleri birleştirmek için kullanılan makine öğrenme yöntemleridir. Topluluk oluşturma için birkaç farklı yöntem vardır, ancak en yaygın ikisi şunlardır:

Bagging, karmaşık modellerin aşırı uyum sağlama olasılığını azaltmayı amaçlar.
-Çok sayıda “güçlü” öğrenciyi paralel olarak eğitir.
-Güçlü öğrenen, nispeten kısıtlanmamış bir modeldir.
-Bagging daha sonra tahminlerini "düzeltmek" için tüm güçlü öğrencileri bir araya getirir.
Basit modellerin öngörü esnekliğini artırmaya yönelik girişimleri artırmak;
-Çok sayıda “zayıf” öğrenciyi sırayla eğitir.
-Zayıf öğrenen, kısıtlanmış bir modeldir (yani her karar ağacının maksimum derinliğini sınırlayabilirsiniz).
-Dizideki her bir bölüm, kendinden öncekinin hatalarından ders çıkarmaya odaklanıyor.
-Daha sonra güçlendirme, tüm zayıf öğrencileri tek bir güçlü öğrencide birleştirir.

Torbalama ve güçlendirme her ikisi de topluluk yöntemleri olmasına rağmen, soruna zıt yönlerden yaklaşırlar.

Bagging karmaşık temel modeller kullanır ve tahminlerini "düzeltmeye" çalışırken, artırma basit temel modeller kullanır ve toplam karmaşıklıklarını "artırmaya" çalışır.


## Düzenlileştirme Nedir?
Düzenlileştirme, makine öğrenmesi ve derin öğrenme modellerinde aşırı öğrenmeyi önlemek için kullanılan bir tekniktir. Modelin karmaşıklığını kontrol altında tutarak, modelin eğitim verisine aşırı uyum sağlamasını ve genelleme yeteneğinin düşmesini engeller. Düzenlileştirme, modelin parametrelerine ceza ekleyerek gerçekleşir ve bu cezalar modelin daha basit ve genelleyici olmasını sağlar.

## L1 Düzenlileştirme (Lasso)
L1 düzenlileştirme, modelin bazı parametrelerinin sıfıra yakın olmasını teşvik eder. Bu, parametrelerin mutlak değerlerinin toplamını ceza terimi olarak ekleyerek yapılır. L1 düzenlileştirme, aşağıdaki maliyet fonksiyonuna eklenen bir terimle ifade edilir:

![image](https://github.com/user-attachments/assets/abc4cc43-5097-442d-8ef0-aff33c2d2c87)

Burada:
- λ, düzenlileştirme parametresidir ve modelin ne kadar cezalandırılacağını belirler.
- θi, modelin parametreleridir.
L1 düzenlileştirme, bazı parametrelerin tamamen sıfıra inmesini sağladığı için modelde seçicilik sağlar ve gereksiz parametreleri elimine eder. Bu, özellikle yüksek boyutlu veri setlerinde etkili olabilir.

## L2 Düzenlileştirme (Ridge)
L2 düzenlileştirme, modelin parametrelerinin büyük olmasını cezalandırır ve tüm parametrelerin küçük olmasını teşvik eder. Bu, parametrelerin karelerinin toplamını ceza terimi olarak ekleyerek yapılır. L2 düzenlileştirme, aşağıdaki maliyet fonksiyonuna eklenen bir terimle ifade edilir:

![image](https://github.com/user-attachments/assets/6fff8a17-1cc9-4453-82ee-00e35c0a445f)

L2 düzenlileştirme, parametrelerin büyüklüğünü sınırlar ve modelin daha düzgün ve genelleyici olmasını sağlar. Bu, özellikle aşırı öğrenmenin önlenmesinde etkili bir yöntemdir.

## L1 ve L2'nin Birleşimi: Elastic Net
Elastic Net, L1 ve L2 düzenlileştirmenin birleşimidir ve her iki yöntemin avantajlarını bir araya getirir. Elastic Net, aşağıdaki maliyet fonksiyonuna eklenen bir terimle ifade edilir:

![image](https://github.com/user-attachments/assets/4b603395-a6ca-4185-94b4-eebcdddb6a0f)

Elastic Net, hem parametrelerin sıfıra yakın olmasını teşvik eder hem de büyük parametreleri cezalandırır. Bu sayede, model hem daha seçici olur hem de genelleyici yeteneği artırılır.

Düzenlileştirme, derin öğrenme modellerinde aşırı öğrenmeyi önlemek için kritik bir rol oynar. L1, L2, Elastic Net, Dropout ve Batch Normalization gibi teknikler, modelin daha sade, genelleyici ve güvenilir olmasını sağlar. Bu yöntemler, deep learning modellerinin performansını artırarak gerçek dünya uygulamalarında daha başarılı olmalarına katkı sağlar.

Kaynakça
https://medium.com/@oran.yasemin/d%C3%BCzenlile%C5%9Ftirme-regularization-teknikleri-ile-a%C5%9F%C4%B1r%C4%B1-%C3%B6%C4%9Frenmeyi-%C3%B6nleme-l1-ve-l2-d%C3%BCzenlile%C5%9Ftirme-9afc04e624e3
https://elitedatascience.com/overfitting-in-machine-learning)
https://klu.ai
https://bulutistan.com/blog/
https://www.veribilimiokulu.com/






















