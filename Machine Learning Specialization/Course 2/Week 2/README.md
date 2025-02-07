# Course 2 Week 2

 ## Geriye Yayılım(Backpropagation) Nedir?
 Daha öncesinde verilen başlangıç ağırlıkları ve sapmalar ile çıkış katmanına 'ileri' doğru giderdik. Bu sürece ileri yayılım denirdi ve burada bir değer hesaplanır. Hesaplanan değer ile gerçek değer arasındaki fark bir hata veya maliyet oluşturur ve Geriye Yayılım burada devreye girer. Bu hatanın geriye doğru katmanlara yayılması ve minimize edilmesi için oluşan sürece Geriye Yayılım denir. 

 Hatayı minimize etmek için maliyetimizin daha doğrusu maliyet fonksiyonumuzun ağırlıklara göre negatif gradyanını alırız. Gradyan dediğimiz fonksiyonumuzun her parametreye göre türevilerinin bir matrisi veya vektörüdür. Yönlü türev alınırken eğer değerimizi maksimize etmek istiyorsak bu yön olarak gradyan vektörü yönü alınır. Tam tersi minimize etmek için gereken ise sadece negatifini almak.

 O zaman bu maliyet fonksiyonumuzun bağlı olduğu parametrelere yani ağırlık ve sapmalara göre türev almamız gerektiğini biliyoruz. Ağırlık fonksiyonuna göre türevini ele alalım. Direkt olarak türevini alamayız çünkü ağırlığımız doğrudan maliyet fonksiyonumuza bağlı değildir. Maliyet fonksiyonumuz, aktivasyon fonksiyonun ve gerçek değer arasındaki farka, aktivasyon fonksiyonumuz, aktivaston fonksiyonumuzun içindeki z değeri yani katmandaki nöronların aktivasyon öncesi toplam girdisi ağırlığa, sapmaya ve aktivasyona bağlıdır. Görüldüğü üzere doğrudan ağırılığa bağlı değildir bu yüzden türevi alınırken zincir kuralı uygulanır. Önce maliyet fonksiyonun aktivasyona göre, aktivasyon fonksiyonunun z değerine göre z'nin de ağırlığa göre türevi alınır.
 
 ![Backpropagation](https://miro.medium.com/v2/resize:fit:2000/format:webp/1*XJ7ioX3mFycK5FwsLqVJ8w.png)

 ## Aktivasyon Fonksiyonları
 
+ ## Lineer Aktivasyon Fonksiyonu
    Aktivasyon fonksiyonumuz g(z) = w.x + b olacak şekilde bir çıktı değeri üreten bu lineer aktivasyon fonksiyonu çıktı katmanımızda, çıktı [-∞,+∞] aralığında bir sürekli değer isteniyorsa ya da sayısal yuvarlama hataları kaldırılmak isteniyorsa kullanılabilir. Fakat Gizli katmanlarda yani girdi katmanlarıyla çıktı katmanları arasındaki katmanlarda tercih edilmez.
     - ### Neden Gizli Katmanlarda Lineer Aktivasyon Fonksiyonu Tercih Edilmez
        1. Doğrusal fonksiyonların doğrusal şekilde bir birleşimi yine bir doğrusal fonksiyondur. Bu sinir ağlarının kullanılma amacını yok eder çünkü ortada artık herhangi bir karmaşıklık kalmaz. Ara katmanlar artık işlevsiz kalıp, bunun bir lineer regresyon modelinden farkı kalmaz.
        2. Geriye yayılımın türev alan bir algoritmayla oluştuğunu söylemiştik. Lineer fonksiyonun türevi sabit bir sayı olduğundan, x'e bağlı olmadığından türevlerin küçülmesi ya da büyümesini engelleyerek öğrenmeyi etkisiz hale getirir.
+ ## Sigmoid Aktivasyon Fonksiyonu
    Aktivasyon fonksiyonu, e euler sayısını belirtecek şekilde, g(z) = 1 / (1 + e^(-z)) olan sigmoid fonksiyonumuz; z'nin +∞'a gittiği durumda 1, z'nin -∞'a gittiği durumda 0, z'nin 0 olduğu durumda 0.5'tir. Eğer ikili sınıflandırma problemimiz varsa (('0','1'),('Kansersiz Tümör Hücresi','Kanserli Tümör Hücresi')) çıktı katmanının aktivasyon fonksiyonu, sigmoid fonksiyonu olarak kullanılır. Sigmoid foksiyonu gizli katmanlarda aktivasyon fonksiyonu olarak kullanılmasının ise; 1980'ler ve 1990'larda popüler olarak kullanılan, 2000'lerde ise dezavantajları ortaya çıkmaya başlayan, 2010'da ReLU'nun çıkışıyla birlikte gizli katmanlarda kullanımı azalıp günümüzde ise neredeyse hiç kullanılmayan tarihi vardır.
    - ### Neden Gizli Katmanlarda Sigmoid Fonksiyonu Tercih Edilmez
        1. Fonksiyonun uçlarına gittikçe türevin değerleri oldukça küçülmeye başlar ve 0'a yakınsar. Bu gradyanların her katmanda daha da küçülmesine ve öğrenmenin durmasına yol açar. Bu duruma **gradyanların ölmesi(vanishing gradient)** denir.
        2. Yavaş bir öğrenme olayı gerçekleştiğinden optimizasyon algoritması yerel minimum değerlere takılır ve yapay sinir ağı modelinden alınabilecek maksimum performansı alamayız.
+ ## ReLU(Rectified Linear Unit) Aktivasyon Fonksiyonu
    ReLU aktivasyon fonksiyonu 2010 yılında tanıtıldıktan sonra kullanılmaya başlandı ve sigmoid fonksiyonunun yerini aldı. z = w.x + b olsun w burada ağırlık, b sapmadır. g(z) aktivasyon fonksiyonumuz z değeri eğer 0'dan büyükse z, 0'a küçük ya da eşitse 0 olarak çıkan bir parçalı fonksiyon olup; a aktivasyon fonksiyonu olacak şekilde da/dz türev fonksiyonumuz da eğer z 0'dan büyükse 1, 0'a küçük ya da eşit ise 0 olan bir parçalı fonksiyondur. O zaman g(z)'miz g(z) = max(0,z) olan bir fonksiyondur.
    - ### ReLU'nun Sigmoid Fonksiyonuna göre Avantajları
        1. Çok fazla nöronlu bir sinir ağımız olsun. Eğer aktivasyon fonksiyonu olarak sigmoid fonksiyonu kullansaydık tüm nöronlarımız aynı anda çalıştırıldığı için tüm nöronlar aktif olurdu, bu  aktivasyon çok işlem gerektirir ve hesaplama yükü ağır olurdu. Eğer aktivasyon fonksiyonu olarak ReLU kullanırsak, z değeri negatif çıkan nöronlar elimine olacak olup sadece bazı nöronlar aktif olacaktır. Böylece verimli bir hesaplama yükü elde etmiş olacağız.
        2. Tüm sinir ağlarında üstelin hesaplanması yerine maksimuun hesaplanması  biraz daha hızlı olması ReLU'yu avantajlı konuma sokar.
        3. Sigmoid'de gradyan inişi özellikle z değeri arttıkça oldukça yavaş olmasına rağmen ReLU'da bu durum yoktur. Belirtildiği üzere aktivasyon fonksiyonumuzun z'ye göre türevi 1 ya da 0 alır.
    - ### ReLU'nun dezavantajları
        1. Sıfır değer bölgesin de öğrenme gerçekleşmez çünkü o bölgede türev değeri sıfırdır. Bu durumu düzeltmek için **Leaky ReLU** kullanılır. Leaky ReLU'da sıfıra yakın değer verilirse sızıntı değer 0 değil de 0,01 gibi küçük sayılar verilir. Böylece 0'a yakın ama 0 olmayan değerlerde ReLU'da ölen gradyanları yaşatmış oluruz.
        2. ReLU'da pek çok nöron negatif değer üretirse, türev sıfır olur ve nöronlar güncellenemez aksine ReLU'nun çıktısı sınırsız da büyüyebilir; eğer ağırlıklar çok büyürse öğrenme süreci bozulabilir.

| ![Resim 1](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*sCasook3f4KX7J8cSeAXww.png) | ![Resim 2](https://miro.medium.com/v2/resize:fit:640/format:webp/1*kh22MSwUHPhuur1l6QyYoQ.png) | ![Resim 3](https://miro.medium.com/v2/resize:fit:828/format:webp/1*m_0v2nY5upLmCU-0SuGZXg.png) |
|:--:|:--:|:--:|
| **Doğrusal Fonksiyon ve Türevi** | **Sigmoid Fonksiyonu ve Türevi** | **ReLU fonksiyonu ve Türevi** |

## Çoklu  Sınıflandırma
   - Eğer çıktımızın olabileceği sınıf iki değil de ikiden fazla ise bu bir çoklu sınıflandırma görevidir yani ikiden fazla sınıfa sahip bir sınıflandırma görevidi. Bir nesnenin bir sınıflandırma alabileceği varsayımını yapar. Örnek olarak portakal,elma ve armut içeren meyve resimleri kümesini etiketlemek olacaktır. 
    ![Resim5](https://miro.medium.com/v2/resize:fit:828/format:webp/1*zC8tszLffnQNduZBI4O6CQ.png) 
+ ## Softmax Regresyonu 
    - Çoklu sınıf problemlerinde çıktı katmanı olarak kullandığımız aktivasyon fonksiyonu softmax regresyonudur. Lojistik regresyonun genelleştirilmiş halidir. Genel formülü:
        P(y = j|x) = aj = e^zj/(e^z1 + e^z2 + ..... + e^zN) burada j. sınıf için olasılığı görüyoruz. Olasılığı en yüksek olan değer bizim o örnek için tahmin edilen sınıfımız oluyor. 
    - Eğer tahminimiz 1'e yakın olursa bu bir iyi tahmin olur 0'a yaklaştıkça kötüleşir. 
    - Belirtilmesi gerektir ki aynı anda yalnızca bir sınıfı tahmin eder yani çok sınıflı bir modeldir, çok çıktılı değildir.
    - a1 + a2 + .... + aN = 1 olmak zorundadır.
+ ## Softmax Regresyonun Kayıp Fonksiyonu:
    - Maliyet fonksiyonu olarak **Çapraz Entropi** kullanılır. Eğer verilen eğitim setinde çıktıda j.sınıfta en yüksek olasılık değeri çıkmışsa bunun maliyetini hesaplamamız için yapmamız gereken çıkan aj'yi logaritmanın içine koyup negatifini hesaplamak. yani maliyetimiz loss(kayıp) = log(aj)'dir.Verilen tüm eğitim setin bu çapraz entropileri hesaplanır ve böylece toplam çapraz entropiyi bulmuş oluruz.
    - ### Çapraz Entropinin Avantajı
        Çapraz entropinin bir avantajı değerlerimiz sıfıra yaklaştıkça bunun kaybını katlanarak arttırmasıdır. Eğer en küçük kareler yöntemi kullansaydık 0'a çok yakın olsa bile bu kayıp katlanarak artmazdı fakat bizim istediğimiz 0'a yakın olan yani kötü bir tahminin iyi bir kayıp verip bunun gradyanıyla düzeltilmesidir. Çünkü çapraz entropide bulduğumuz değerin türevi yüksek olup bunu düzeltmesi çok daha kolay olacaktır. Kısaca doğru sınıfları güçlü ödüllendirir, yanlışları ağır cezalandırır.
    ![Resim6](https://ml-cheatsheet.readthedocs.io/en/latest/_images/cross_entropy.png)
    
+ ## Softmax Regresyonunun Kodlanması
    - ### 1.Yöntem
        - ilk olarak çıktı katmanının aktivasyonunu softmax yaparız --> model = Sequential([...., Dense(units = 10,activation = 'softmax')])
        - sonra compile'da maliyet fonksiyonumuzu SparseCategoricalCrossentropy olarak tanıtırız --> loss = model.compile(SparseCategoricalCrossentropy())
        - loss = - log(aj) olur.
    - ### 2. Yöntem
        - Diğer yöntemden farklı olarak çıktı katmanının aktivasyon fonksiyonunu sayısal yuvarlama hatalarını azaltmak için 'linear' yapar --> model = Sequential([...., Dense(units = 10,activation = 'linear')])  
        - Maliyet fonksiyonumuzda SparseCategoricalCrossentropy'nin içine from_logits parametresini yazıp True'ya eşitleriz -->  SparseCategoricalCrossentropy olarak tanıtırız --> loss = model.compile(SparseCategoricalCrossentropy(from_logits = True))
        - Bu yöntemde amaç küçük sayılar çıkınca sebep olduğu yuvarlama hatalarını azaltmak
     

Kaynakça
https://ayyucekizrak.medium.com/derin-%C3%B6%C4%9Frenme-i%C3%A7in-aktivasyon-fonksiyonlar%C4%B1n%C4%B1n-kar%C5%9F%C4%B1la%C5%9Ft%C4%B1r%C4%B1lmas%C4%B1-cee17fd1d9cd
https://www.youtube.com/watch?v=Ilg3gGewQ5U&t=123s&ab_channel=3Blue1Brown
https://www.youtube.com/watch?v=tIeHLnjs5U8&t=260s&ab_channel=3Blue1Brown
https://www.youtube.com/watch?v=KpKog-L9veg&t=735s&ab_channel=StatQuestwithJoshStarmer
https://www.youtube.com/watch?v=6ArSys5qHAU&t=456s&ab_channel=StatQuestwithJoshStarmer
 
