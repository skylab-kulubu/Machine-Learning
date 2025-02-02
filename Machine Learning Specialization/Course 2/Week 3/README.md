# Machine Learning Specialization



# Makine Öğrenimi Geliştirme Süreci ve Önyargılı Veriler

Makine Öğrenimi Gelişiminin Yinelenen Döngüsü
Makine öğrenimi geliştirme süreci, temel bir hedef doğrultusunda başlayıp sürekli olarak geliştirilmesi gereken bir döngü şeklinde ilerler. Model eğitildikçe, yapılan tahminlerin doğruluğu ve performansı sürekli analiz edilir. Bu analizler doğrultusunda modelin daha verimli çalışması sağlanır ve sonuçlar iyileştirilir. Modelin doğruluğu, genellikle hata analizi ve yeni verilerle desteklenerek artırılır.

Bu süreç şu adımlardan oluşur:
1. Veri toplama ve ön işleme: Veri, makine öğrenimi modelinin temelini oluşturur. Çeşitli veri kaynaklarından veriler toplanarak, analize uygun hale getirilir. Bu aşama, veri temizliği, eksik verilerin tamamlanması, anormal değerlerin tespiti gibi önemli işlemleri içerir.
2. Model seçimi ve eğitimi: Bu aşamada, veri kümesine en uygun model seçilir ve eğitim verileri kullanılarak eğitilir. Modelin başarısı, doğru seçim ve uygun parametrelerin kullanımıyla doğrudan ilişkilidir.
3. Modelin performansının değerlendirilmesi: Eğitim süreci tamamlandıktan sonra, modelin doğruluğu ve genel performansı test edilir. Performans değerlendirilmesi, modelin ne kadar başarılı olduğuna dair net bilgiler sağlar.
4. Hata analizi: Yanlış tahminlerin, hatalı sınıflandırmaların veya düşük performanslı sonuçların nedenleri incelenir. Hataların kökeni tespit edilerek gerekli iyileştirmeler yapılır.
5. Modeli geliştirmek için veri ekleme veya artırma: Hata analizinden sonra, modelin daha geniş bir veri setiyle eğitilmesi sağlanarak, modelin hatalarını daha iyi öğrenmesi ve genel doğruluğunun artırılması hedeflenir.
6. Modelin yeniden eğitilmesi: Yeni eklenen veri ile model yeniden eğitilir. Bu işlem, modelin önceki verilerden öğrendiklerinin yanı sıra yeni bilgileri de içermesini sağlar.
7. Modelin dağıtıma alınması: Son olarak, eğitilen ve test edilen model gerçek dünya verileriyle çalışmaya başlamak için dağıtıma alınır.

Bu döngü, modelin doğruluğunu artırmak için sürekli olarak tekrar edilir ve gelişen teknolojiler ile model her geçen gün daha iyi hale gelir.

Spam Sınıflandırıcı Oluşturma
Spam sınıflandırıcı, e-postaları spam (istenmeyen) ve spam olmayan olarak ayıran bir makine öğrenimi modelidir. Spam sınıflandırıcıları, e-posta filtreleme sistemlerinde kullanılır ve kullanıcıların gereksiz e-postaları görmesini engeller. Bir spam sınıflandırıcı oluştururken aşağıdaki yöntemler kullanılır:
- Özellik mühendisliği: Kelime frekansları, konu satırları, gönderen bilgileri, metin uzunluğu gibi çeşitli verilerden anlamlı özellikler çıkarılır. Bu özellikler, spam veya normal e-posta arasındaki farkları anlamaya yardımcı olur.
- Model eğitimi: Lojistik regresyon, destek vektör makineleri (SVM), karar ağaçları gibi makine öğrenimi algoritmalarını kullanarak model eğitilir. Bu modeller, veriyi analiz ederek e-posta içeriğinin spam olup olmadığına karar verir.
- Hata analizi: Yanlış sınıflandırılan spam ve spam olmayan e-postalar incelenerek, modelin neden yanlış kararlar verdiği anlaşılır ve düzeltilir. Hata analizi ile modelin sınıflandırma hataları daha iyi anlaşılır ve iyileştirme yapılabilir.

Spam sınıflandırıcısının doğruluğunu artırmak için daha fazla veri toplanabilir, modelin önyargıları analiz edilebilir ve modelin sonuçları daha hassas hale getirilebilir.

Spam Sınıflandırıcısının Hatasını Nasıl Azaltabilirsiniz?
Bir modelin hatasını azaltmak için çeşitli stratejiler uygulanabilir:
- Veri artırma (Data Augmentation): Eğitim verisini çeşitlendirmek için yeni veri türleri eklenebilir. Bu teknik, modelin daha geniş bir veri yelpazesinde çalışmasını sağlar ve doğruluğu artırır.
- Daha fazla veri ekleme: Eğitim verisi arttıkça, modelin genelleme kapasitesi artar. Daha fazla örnekle eğitilen model, daha iyi sonuçlar verebilir.
- Özellik mühendisliği: Verinin içeriği hakkında daha derinlemesine bilgi edinmek için, modelin analiz yapabilmesi adına daha anlamlı ve özelleştirilmiş özellikler kullanılabilir.
- Daha karmaşık modeller kullanma: Derin öğrenme gibi gelişmiş teknikler kullanarak, daha güçlü ve kapasitesi yüksek modeller oluşturulabilir.

Bu yöntemler, spam sınıflandırıcısının genel başarısını artırır ve modelin doğruluğunu iyileştirir.

Hata Analizi
Hata analizi, modelin yaptığı yanlış tahminleri inceleyerek, modelin eksikliklerini ve zayıf yönlerini tespit etmeye yardımcı olur. Hata analizi süreci şu şekilde işler:
1. Yanlış sınıflandırılan örneklerin incelenmesi: Modelin yanlış tahmin yaptığı veriler analiz edilir. Bu yanlış sınıflandırmaların modelin nasıl hatalı kararlar verdiğini anlamak için önemli ipuçları verir.
2. Hataların nedenlerinin belirlenmesi: Hataların kaynağı incelenir. Bu hatalar veriyle mi, modelin parametreleriyle mi, yoksa algoritmanın yanlış uygulanmasıyla mı ilgili?
3. Modelin hangi tür hataları yaptığını anlamak: Modelin hatalı pozitif (false positive) ya da hatalı negatif (false negative) yaptığı belirlenir. Hangi hataların daha fazla yapıldığını anlamak, modelin geliştirilmesine yardımcı olur.
4. Gereken iyileştirmeleri uygulamak: Hata analizinden elde edilen verilerle, modelin eksikliklerini giderecek iyileştirmeler yapılır. Bu iyileştirmeler, modelin doğruluğunu artırmak için uygulanır.

Bu süreç, modelin eksikliklerini belirlemek ve daha iyi performans elde etmek için kritik öneme sahiptir.

Veri Eklemek ve Veri Artırma (Data Augmentation)
Veri artırma, modelin daha iyi öğrenmesini sağlamak amacıyla mevcut veriyi çeşitlendirerek yeni eğitim verileri oluşturma sürecidir. Veri artırma, modelin daha fazla örnek görmesine olanak tanır, böylece daha güçlü bir genelleme yeteneği elde edilir.

Veri Artırma Teknikleri:
- Görüntü işleme için: Görüntüleri döndürmek, ölçeklemek veya parlaklık gibi özelliklerde değişiklikler yapmak veri setini çeşitlendirir ve modelin görsel veriye karşı daha dayanıklı olmasını sağlar.
- Ses işleme için: Gürültü eklemek, sesin hızını değiştirmek veya sesin tonunu değiştirmek gibi yöntemler, sesli veri ile çalışan modeller için faydalıdır.
- OCR (Optik Karakter Tanıma) için: Yapay veri sentezi ile yeni ve çeşitli yazı tipleri, el yazısı karakterleri eklenerek modelin daha fazla örnek görmesi sağlanır.

Veri artırma, modelin daha geniş veri türlerine karşı dayanıklılığını artırır ve gerçek dünya senaryolarına daha iyi adapte olmasını sağlar.

Sisteminizde Kullanılan Verinin Mühendislik Süreci
Veri mühendisliği, model geliştirme sürecinde veriyi etkili bir şekilde yönetmek için kullanılan teknikleri içerir. Bu süreç, modelin doğru çalışması için veriyi hazırlamak ve işlemek adına çok önemlidir.

İki ana yaklaşım bulunmaktadır:
- Model-merkezli yaklaşım: Modelin mimarisini değiştirerek performansı artırmak. Bu yaklaşım, daha güçlü modeller kullanmak ve parametre ayarlamaları yapmak üzerine yoğunlaşır.
- Veri-merkezli yaklaşım: Modelin eğitildiği veri setini temizleyerek ve genişleterek iyileştirme yapmak. Bu yaklaşımda, veri setindeki eksiklikleri, hataları ve dengesizlikleri düzeltmek amaçlanır.

Veri mühendisliği süreçleri, modelin doğruluğunu ve güvenilirliğini artırmada büyük rol oynar.

Transfer Öğrenme
Transfer öğrenme, önceden eğitilmiş bir modelin, farklı bir problem için yeniden kullanılmasıdır. Bu yöntem, sınırlı veri setlerine sahip projelerde oldukça yararlıdır.

Transfer öğrenme yöntemleri:
1. Yalnızca çıktı katmanlarının parametrelerini eğitmek: Mevcut modelin üzerine, belirli bir problem için çıktı katmanları eklenerek eğitim yapılır.
2. Tüm model parametrelerini eğitmek: Modelin tüm katmanları yeniden eğitilerek, daha spesifik bir probleme uyum sağlanır.

Transfer öğrenme, veri setinin sınırlı olduğu durumlarda çok faydalıdır ve eğitim sürecini hızlandırır.

Makine Öğrenimi Projesinin Tam Döngüsü
Makine öğrenimi projeleri, aşağıdaki temel aşamalardan oluşur:
1. Veri toplama ve ön işleme
2. Model eğitimi
3. Model değerlendirme
4. Hata analizi ve iyileştirme
5. Model dağıtımı
6. Modelin izlenmesi ve güncellenmesi

Bu süreç, modelin sürdürülebilir şekilde geliştirilmesini sağlar.

Deployment (Dağıtım)
Makine öğrenimi modeli, geliştirildikten sonra üretim ortamına alınarak gerçek dünyada kullanılabilir hale getirilmelidir. Dağıtım aşamasında aşağıdaki süreçler uygulanır:
- Güvenilir ve verimli tahminler sağlama
- Ölçeklenebilirlik ve sistem optimizasyonu
- Günlükleme ve sistem izleme
- Model güncellemeleri ve yeniden eğitim

Bu süreçler, modelin uzun vadeli performansını sağlamak için gereklidir.

Bias (Önyargı) ve Modelin Adaletli Olması
Makine öğrenimi modelleri, eğitim verilerindeki dengesizliklerden dolayı önyargılı olabilir. Bu durumun önüne geçmek için:
- Veri setini dengeli hale getirmek
- Farklı gruplar arasında adil sonuçlar sağlamak
- Önyargıyı tespit eden metrikler kullanmak gereklidir.

Precision, Recall ve F1 Skoru
Bir modelin başarısını ölçmek için kullanılan metrikler:
- Precision (Kesinlik): Doğru pozitiflerin, toplam pozitif tahminlere oranı. Yani modelin doğru bir şekilde pozitif tahmin ettiği sonuçların, tüm pozitif tahminlere oranıdır. Bu metrik, modelin pozitif sınıfı ne kadar doğru tahmin ettiğini gösterir. Precision, özellikle yanlış pozitiflerin (False Positive) önemli olduğu durumlarda, yani gereksiz yere olumlu tahminler yapmanın maliyetli olduğu durumlarda çok önemlidir. Formül olarak, 
    Precision = Doğru Pozitif / (Doğru Pozitif + Yanlış Pozitif)

- Recall (Duyarlılık): Gerçek pozitiflerin, toplam gerçek pozitiflere oranı. Recall, modelin tüm gerçek pozitifleri ne kadar doğru bir şekilde yakaladığını ölçer. Bu metrik, özellikle yanlış negatiflerin (False Negative) kritik olduğu durumlarda, yani gerçek pozitifleri kaçırmanın maliyetli olduğu durumlarda daha fazla önem kazanır. Örneğin, bir hastalık teşhisinde hastalığı yanlış bir şekilde negatif olarak sınıflandırmak, daha kötü sonuçlara yol açabilir. Formül olarak,
    Recall = Doğru Pozitif / (Doğru Pozitif + Yanlış Negatif)

- F1 Skoru: Precision ve Recall’un harmonik ortalaması olarak tanımlanır. Bu metrik, iki metrik arasında bir denge kurar ve her iki metriği de dikkate alır. F1 skoru, özellikle veri setinde sınıfların dengesiz olduğu durumlarda (örneğin, çok daha fazla negatif örnek varsa) daha anlamlıdır. Çünkü hem yanlış pozitifleri hem de yanlış negatifleri dengeleyerek modelin genel başarısını gösterir. F1 skoru, genellikle bu iki metriğin arasında bir denge gerektiren senaryolarda tercih edilir. Formül olarak,
    F1 Skoru = 2 * (Precision * Recall) / (Precision + Recall)

Precision ve Recall arasında bir denge bulunmalıdır. Uygulama senaryosuna bağlı olarak biri diğerine tercih edilebilir. Örneğin, sağlık alanında bir model geliştirirken, hastalıkları tespit etmek için Recall'ı yüksek tutmak önemli olabilir, çünkü yanlış negatif (hastalığı kaçırma) çok daha ciddi sonuçlara yol açabilir. Ancak, reklam hedefleme gibi bazı uygulamalarda ise Precision’ı yüksek tutmak, yanlış pozitiflerin (gereksiz reklam gösterimleri) sayısını azaltmak açısından önemli olabilir. Bu nedenle, hangi metriklerin ön planda olacağı, uygulama alanına ve verinin doğasına göre değişir. Ayrıca, bu metriklerin optimum seviyeleri genellikle modelin türü ve uygulama gereksinimlerine göre ayarlanır. Bu tür kararlar, modelin başarısını artırmak için kritik öneme sahiptir.
