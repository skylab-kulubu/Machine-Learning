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

  -**Yapay Sinir Ağları:** Daha karmaşık ve doğrusal olmayan sınıflandırma problemleri için güçlüdür.

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


