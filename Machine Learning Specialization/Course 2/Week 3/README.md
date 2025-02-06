# Machine Learning Specialization

# Makine Öğrenimini Uygulamaya Yönelik Tavsiyeler
Bir makine öğrenimi sistemini ne kadar hızlı ve başarılı bir şekilde çalıştırabileceğimiz, büyük ölçüde, bir makine öğrenimi projesi boyunca ne yapmamız gerektiğine dair iyi kararlar verebilme yeteneğimize bağlıdır.
Diyelim ki, konut fiyatlarını tahmin etmek için düzenlileştirilmiş doğrusal regresyonu uyguladık. Yani, öğrenme algoritmamız için klasik maliyet fonksiyonuna sahibiz. Ancak modeli eğittiğimizde, tahminlerinin kabul edilemeyecek kadar büyük hatalar yaptığını fark ettik.
![image](https://github.com/user-attachments/assets/37e36d3b-471d-4021-9b06-cc4260504f30)
 
Bir makine öğrenimi algoritması oluştururken deneyebileceğiniz birçok farklı şey vardır. Örneğin, daha fazla eğitim verisi almayı düşünebilirsiniz. Ya da belki çok fazla özelliğe sahipsiniz ve daha küçük bir özellik kümesiyle deneme yapmak isteyebilirsiniz. Veya belki de ek özellikler eklemek istiyorsunuz.
Ayrıca mevcut özellikleri, örneğin x1, x2 gibi girdileri, polinom özelliklere dönüştürmeyi düşünebilirsiniz: x1^2, x2^2, x1⋅x2 vb. gibi. Ya da belki düzenlileştirme parametresi olan λ'nın iyi seçilip seçilmediğini merak ediyorsunuz. Belki çok büyük olduğunu düşünüp azaltmak isteyebilirsiniz veya çok küçük olduğunu düşünüp artırmak isteyebilirsiniz.
Herhangi bir makine öğrenimi uygulamasında, bu yaklaşımlardan bazıları faydalı olabilirken, bazıları faydalı olmayabilir.
Şimdi, bir dizi tanı testi (diagnostic) yapmayı öğreneceksiniz. Burada tanı testi derken, öğrenme algoritmanızın neyin işe yarayıp neyin yaramadığını anlamanıza yardımcı olan ve performansını nasıl iyileştirebileceğinize dair yol gösteren testleri kastediyorum.

Bir makine öğrenimi modeli eğittik. Peki, bu modelin performansını nasıl değerlendiririz?
Konut fiyatlarını büyüklüğe bağlı olarak tahmin etmeyi öğrenme örneğini ele alalım. Diyelim ki, konut fiyatlarını tahmin etmek için x değişkenine bağlı bir model eğittiniz. Modeliniz dördüncü dereceden bir polinom; yani özellikleriniz x, x^2, x^3, x^4. Beş veri noktasına sahip bir eğitim kümesine dördüncü dereceden bir polinom uyarladığımız için, bu model eğitim verilerine oldukça iyi uyum sağlar.

![image](https://github.com/user-attachments/assets/05a854a6-fcf9-4c39-8a32-0609d61c2b8f)

Ancak, bu modeli pek sevmiyoruz. Çünkü model eğitim verilerine iyi uyum sağlasa da, eğitim kümesine dahil olmayan yeni örneklere genelleme yapamayacağını düşünüyoruz.
Konut fiyatlarını yalnızca evin büyüklüğü gibi tek bir özellik kullanarak tahmin ettiğinizde, modeli görselleştirebilir ve elde edilen eğrinin çok dalgalı olduğunu görebilirsiniz. Bu da muhtemelen iyi bir model olmadığını gösterir.
Ancak, modele daha fazla özellik eklediğinizi düşünelim. Örneğin, x evin büyüklüğü, x2 yatak odası sayısı, x3 kat sayısı, x4 evin yaşı olsun. Bu durumda f(x) fonksiyonunu görselleştirmek çok zorlaşır, çünkü artık dört boyutlu bir fonksiyona sahipsiniz.
# Modelinizin Başarılı Olup Olmadığını Nasıl Anlarsınız?
Özellikle bir veya iki özellikten fazla olan uygulamalarda, modelin nasıl performans gösterdiğini anlamak için daha sistematik bir değerlendirme yöntemine ihtiyacımız var. 
![image](https://github.com/user-attachments/assets/dd6aca49-42c2-4818-987c-fc8b753999b0)
 
Eğitim kümesine sahipseniz ve bu küçük eğitim kümesi sadece 10 örnek içeriyorsa, modelin parametrelerini w ve b ile eğitmek için tüm verileri kullanmak yerine, eğitim kümesini iki alt kümeye bölebilirsiniz. Veri kümenizi bölmek için yaygın kullanılan oranlar %70-30 veya %80-20’dir. Genellikle, verinin büyük bir kısmı eğitim için, küçük bir kısmı ise test için ayrılır.
•	Eğitim kümesi (%70): Verinin %70’ini eğitim kümesine koyabilirsiniz.
•	Test kümesi (%30): Geri kalan %30’u test kümesi olarak ayırabilirsiniz.
Bu yaklaşımda, modelin parametrelerini ilk %70'lik kısımda eğitiriz ve ardından modelin performansını test kümesi üzerinde değerlendiririz.
Bu noktada, bazı yeni notasyonlar tanıtabiliriz:
•	m_train: Eğitim kümesindeki örneklerin sayısıdır. Bu küçük veri setinde m_train=7 olur.
•	m_test: Test kümesindeki örneklerin sayısıdır. Bu örnekte m_test=3 olur.
Regresyon Modellerinde Model Performansını Değerlendirme
Doğrusal regresyon modelini kare hata maliyet fonksiyonu (squared error cost function) ile eğittiğinizi düşünelim. Modelin parametrelerini fit etmek için aşağıdaki maliyet fonksiyonunu minimize ederiz.
![image](https://github.com/user-attachments/assets/3b0e0bbc-be99-4366-9fb3-8aab2aabf6af)
 
Burada, λ düzenlileştirme terimidir.
Modelin ne kadar iyi çalıştığını görmek için test hatasını (test error) hesaplarız. Test hatası şu formüle sahiptir.

![image](https://github.com/user-attachments/assets/d58005dd-5b09-41dc-93ae-a66f2c52b0fd)
 
Dikkat ederseniz, test hatası formülünde düzenlileştirme terimi yoktur. Bu, öğrenme algoritmanızın yeni verilere nasıl genelleme yaptığını anlamanıza yardımcı olur.
Bir diğer önemli metrik ise eğitim hatası (training error) olup, şu formülle hesaplanır:
![image](https://github.com/user-attachments/assets/30aa5ffe-62f9-490f-9571-675738c3e8d0)
 
Bu, modelin eğitim verisinde ne kadar iyi çalıştığını gösterir.
Eğer modeliniz eğitim kümesinde çok düşük bir hataya sahipse (J_train çok küçükse) ancak test kümesinde yüksek bir hataya sahipse (J_test büyükse), model aşırı öğrenme (overfitting) yapıyor olabilir. Bu, modelin eğitim verisine çok iyi uyum sağladığını ancak yeni verilere genelleme yapamadığını gösterir.

![image](https://github.com/user-attachments/assets/917aa990-573c-400d-931b-ada55a870fbc)

Şimdiye kadar gördüğümüz şeylerden biri, bir modelin parametreleri w ve b eğitim setine göre belirlendikten sonra, eğitim hatasının algoritmanın ne kadar iyi çalışacağına veya yeni örnekler üzerinde ne kadar iyi genelleyeceğine dair iyi bir gösterge olmayabileceğidir. Özellikle, bu örnekte, eğitim hatası neredeyse sıfır olacaktır. Bu da, muhtemelen gerçek genelleme hatasından çok daha düşük bir değerdir. Gerçek genelleme hatası derken, modelin eğitim setinde yer almayan yeni örnekler üzerindeki ortalama hatasını kastediyorum.

# Model Seçimi ve Test Seti Kullanımı
Örneğin, konut fiyatlarını tahmin eden bir model oluşturduğunuzu düşünelim. Bu bir regresyon problemidir ve bir model olarak doğrusal (linear) bir fonksiyon kullanabilirsiniz.
Bu durumda, birinci dereceden (d = 1) bir polinom ile modelleme yapabiliriz. Birinci dereceden polinomun eğitimi tamamlandıktan sonra, elde ettiğimiz w^1 ve b^1 parametreleri ile test seti üzerinde bir hata hesaplayabiliriz. Bu hataya J_test(w^1, b^1) diyelim.
Aynı şekilde, ikinci dereceden (d = 2) bir polinom kullanarak modeli eğitebilir ve test hatasını hesaplayabiliriz. Bunu d = 10’a kadar sürdürebiliriz ve her bir model için test hatalarını elde edebiliriz.
Bu noktada şu yöntemi düşünebiliriz:
•	Farklı d derecelerine sahip modellerin test hatalarını karşılaştırarak en düşük test hatasına sahip olan modeli seçmek.
•	Örneğin, test hatasının en düşük olduğu model beşinci dereceden bir polinom (d = 5) ise, bu modeli seçmek.
Ancak bu prosedür yanlıştır, çünkü test hatası J_test(w^5, b^5) genellikle gerçek genelleme hatasından daha iyimser bir tahmin olur. Bunun nedeni, test setini model seçiminde kullanmamızdır.
Eğitim sırasında parametreleri belirlemek için eğitim setini kullanıyoruz. Ancak, modelin derecesi d gibi bir hiperparametreyi belirlemek için test setini kullanırsak, test seti artık tarafsız bir değerlendirme aracı olmaktan çıkar. Bu, test hatasının gerçekte olduğundan daha düşük görünmesine neden olur ve genelleme hatasını doğru bir şekilde tahmin etmemizi engeller.

# Daha Doğru Bir Model Seçim Yöntemi
Daha iyi bir yöntem kullanarak, model seçim sürecini iyileştirebiliriz. Bunun için, verimizi sadece ikiye (eğitim seti ve test seti) bölmek yerine, üçe ayıracağız:
1.	Eğitim Seti (Training Set)
2.	Çapraz Doğrulama Seti (Cross-Validation Set - CV)
3.	Test Seti (Test Set)
Örneğin, 10 verilik bir datasetimiz olduğunu düşünelim. Bu verileri şu şekilde bölebiliriz:
•	Eğitim Seti: Verinin %60’ı (örneğin, 6 veri noktası)
•	Çapraz Doğrulama Seti (CV Seti): Verinin %20’si (2 veri noktası)
•	Test Seti: Verinin kalan %20’si (2 veri noktası)
Burada çapraz doğrulama setini, farklı modellerin doğruluğunu karşılaştırmak ve en iyi modeli seçmek için kullanacağız.
Model seçim süreci şu şekilde işler:
1.	Eğitim Seti ile Model Eğitimi
o	w^1, b^1, w^2, b^2, …, w^{10}, b^{10} parametrelerini hesapla.
2.	Çapraz Doğrulama Seti ile Model Değerlendirme
o	Her model için çapraz doğrulama hatası J_{cv}(w, b) hesaplanır.
o	En düşük hata veren model seçilir.
3.	Test Seti ile Nihai Performans Değerlendirmesi
o	En iyi çapraz doğrulama hatasına sahip model seçildikten sonra, bu modelin test seti üzerindeki hatası J_test hesaplanır.
Böylece, test seti model seçim sürecinde kullanılmaz, yalnızca en iyi modeli değerlendirmek için saklanır. Bu, test hatasının gerçekte modelin yeni verilere ne kadar iyi genelleme yapabileceğini daha doğru bir şekilde tahmin etmesini sağlar.
Örneğin, yapay sinir ağları kullanıyorsak:
•	Küçük bir sinir ağı (az katmanlı, az nöronlu)
•	Orta büyüklükte bir sinir ağı
•	Büyük bir sinir ağı (çok katmanlı, çok nöronlu)
Bu üç model eğitildikten sonra, çapraz doğrulama seti kullanılarak en iyi performans gösteren model seçilir. Daha sonra, bu modelin gerçek performansını ölçmek için test seti kullanılır.

# Makine Öğrenimi Sisteminin Geliştirilme Süreci ve Bias-Variance (Önyargı-Varyans) Dengesi
Eğer bu verimize doğrusal bir model (bir doğru) uydurmaya çalışırsanız, modelin veriye iyi uyum sağlamadığını görürsünüz. Bu durumda, algoritmanın yüksek bias içerdiğini ya da veriye düşük uyum sağladığını (underfitting – eksik öğrenme) söyleyebiliriz.

![image](https://github.com/user-attachments/assets/b6b407f0-c260-4fc2-abe8-59d709d71e74)
 
Öte yandan, eğer dördüncü dereceden bir polinom kullanarak aynı veriye bir model oluşturursak, model aşırı karmaşık hale gelir ve yüksek varyanslı (overfitting – aşırı öğrenme) olur. Yani eğitim verisine çok iyi uyum sağlar ancak yeni verilere genelleme yapamaz.

![image](https://github.com/user-attachments/assets/85071bad-0bdc-42e4-a0fa-030a1fe518ad)

Bu iki uç nokta arasında, eğer ikinci dereceden bir polinom modeli kullanırsak, model hem eğitim hem de test verileri üzerinde iyi performans gösterir. Bu nedenle bu model uygun (just right) olarak değerlendirilebilir.

![image](https://github.com/user-attachments/assets/08c97e8b-b9ad-4a88-af37-c17023d6f107)
 

# Model Performansını Ölçmek: Eğitim Hatası ve Doğrulama Hatası
Bir makine öğrenimi modelinin bias veya varyans seviyesini anlamak için, modelin eğitim kümesindeki (training set) performansına (J_train) ve doğrulama kümesindeki (cross-validation set) performansına (J_cv) bakabiliriz.

![image](https://github.com/user-attachments/assets/c9c94b8f-8c63-4215-aa08-9a032cc5e6ba)
 
1.	Yüksek Bias Durumu (Eksik Öğrenme – Underfitting)
o	Eğitim setindeki hata (J_train) yüksek olur, çünkü model veriye iyi uyum sağlayamaz.
o	Doğrulama setindeki hata (J_cv) da yüksek olur, çünkü model yeni verileri de iyi genelleştiremez.
o	Bu durum, modelin yetersiz öğrenmesine işaret eder.
2.	Yüksek Varyans Durumu (Aşırı Öğrenme – Overfitting)
o	Eğitim setindeki hata (J_train) düşük olur, çünkü model eğitime çok iyi uyum sağlar.
o	Ancak doğrulama setindeki hata (J_cv) yüksek olur, çünkü model yeni veriler üzerinde iyi performans gösteremez.
o	Bu durum, modelin eğitim verisine aşırı uyum sağladığını ve genelleme yapamadığını gösterir.
3.	Denge Durumu (Optimum Öğrenme)
o	Eğitim setindeki hata (J_train) düşük olur.
o	Doğrulama setindeki hata (J_cv) de eğitim hatasına yakın bir seviyede düşük olur.
o	Bu durumda model, hem eğitim verisine hem de yeni verilere uyum sağlayarak iyi bir denge kurmuştur.


# Bias-Variance Dengesi ile Model Geliştirme Stratejisi
Makine öğrenimi modelinizi geliştirirken her zaman yüksek bias mı yoksa yüksek varyans mı olduğunu belirlemeye çalışmalısınız. Bu analiz, modelinizi nasıl iyileştireceğiniz konusunda çok önemli ipuçları sağlar.
•	Eğer modeliniz yüksek bias içeriyorsa (J_train ve J_cv ikisi de yüksek):
o	Daha karmaşık bir model seçebilirsiniz.
o	Daha fazla özellik ekleyebilirsiniz.
o	Daha fazla eğitim verisi kullanabilirsiniz.
•	Eğer modeliniz yüksek varyans içeriyorsa (J_train düşük, ancak J_cv yüksek):
o	Regularizasyon (düzenleme) yöntemlerini kullanabilirsiniz.
o	Daha fazla eğitim verisi ekleyebilirsiniz.
o	Daha basit bir model seçebilirsiniz.
Şimdi ise düzenlileştirme (regularization) ve özellikle düzenlileştirme parametresi olan λ seçimlerinin bias, varyans ve algoritmanın genel performansı üzerindeki etkilerini inceleyeceğiz. Bu, algoritmanız için iyi bir λ değeri seçmek istediğinizde size yardımcı olacaktır. 

![image](https://github.com/user-attachments/assets/bd359e21-60a0-4e0e-a5e7-b781a4a4f19e)
 
Bu örnekte dördüncü dereceden bir polinom kullanacağım, ancak bu modeli düzenlileştirme uygulayarak eğiteceğiz. Burada λ, düzenlileştirme parametresidir ve ağırlık parametrelerini küçük tutmak ile eğitim verisini iyi şekilde uydurmak arasındaki dengeyi kontrol eder. Öncelikle, λ değerini çok büyük bir değer olarak ayarladığımız bir örneğe bakalım. Örneğin, λ=10.000 olsun. Eğer böyle yaparsanız, aşağı yukarı şu şekilde bir model elde edersiniz. Çünkü λ çok büyük olduğunda, algoritma parametreleri w'yu oldukça küçük tutmaya zorlanır ve bu nedenle w1, w2, hatta tüm parametreler sıfıra çok yakın olur. Sonuç olarak, modeliniz yaklaşık olarak sabit bir değer olan f(x)≈ b olur. Bu model açıkça yüksek bias’a sahiptir ve eğitim verisine aşırı uydurmamakta (underfitting) yani eğitimi başarısızdır, çünkü eğitim setinde bile iyi performans gösteremez ve J_train (eğitim hatası) büyük olur.

![image](https://github.com/user-attachments/assets/4e1bdfb2-9fcb-47ea-86d7-9347b15b5353)

 
Şimdi ise diğer aşırı durumu ele alalım. Diyelim ki λ değerini çok küçük bir seviyeye çekiyoruz. Hatta en uç noktayı seçerek λ=0 olduğunu düşünelim. Bu seçimle, düzenlileştirme (regularization) tamamen kaldırılmış olur ve sadece dördüncü dereceden bir polinom eğitilmiş olur. Sonuç olarak, daha önce gördüğümüz gibi veriye aşırı uyum sağlayan (overfitting) bir eğri elde edilir. Daha önce gözlemlediğimiz üzere, böyle bir modelde J_train küçük olur, ancak çapraz doğrulama hatası J_cv, J_train'den çok daha büyük olur veya genel olarak yüksek olur. Bu durum, yüksek varyansa sahip olduğumuzu ve modelin aşırı öğrenme yaptığını gösterir.

![image](https://github.com/user-attachments/assets/424ffbb8-41cc-4515-a34c-acd3b84e2fbd)
 
Ancak, eğer λ için ne çok büyük (10.000 gibi) ne de çok küçük (0 gibi) olmayan orta bir değer seçilirse, umarım aşağıdaki gibi iyi bir model elde edersiniz. Bu model, hem eğitim hatası J_train hem de çapraz doğrulama hatası J_cv açısından düşük değerlere sahip olur ve veriye en uygun şekilde uyum sağlar.

![image](https://github.com/user-attachments/assets/a8307810-85d0-480b-ae2d-f50be4e58a73)
 
# λ seçimi
Hatırlatmak gerekirse, burada ele aldığımız problem şu: dördüncü dereceden bir polinom kullanarak model oluşturuyoruz ve düzenlileştirme uyguluyoruz. Peki, iyi bir λ değeri nasıl seçilir? Bu süreç, çapraz doğrulama ile polinom derecesi D seçimine benzer bir prosedür izler.
Özellikle, diyelim ki modeli λ=0 ile eğitmek istiyoruz. Bu durumda, maliyet fonksiyonunu λ=0 ile minimize ederiz ve bir takım parametreler (w1, b1) elde ederiz. Daha sonra, çapraz doğrulama hatasını, yani J_cv(w1, b1) değerini hesaplarız.
Şimdi farklı bir λ değeri deneyelim. Örneğin, λ=0.01 seçelim. Yine, maliyet fonksiyonunu minimize ederek (w2, b2) parametrelerini buluruz ve bu durumda çapraz doğrulama hatasını hesaplarız: J_cv(w2, b2).
Bu yöntemle, çok çeşitli λ değerlerini deneyerek, elde edilen parametrelerle çapraz doğrulama seti üzerinde performansı değerlendirerek, en iyi düzenlileştirme parametresini seçebiliriz.

# Öğrenme Eğrileri: Bias ve Varyansın Anlaşılması
Öğrenme eğrileri, öğrenme algoritmanızın ne kadar deneyime sahip olduğuna bağlı olarak nasıl performans gösterdiğini anlamanıza yardımcı olan bir yöntemdir. Buradaki deneyimden kastımız, örneğin, modelin sahip olduğu eğitim örneklerinin sayısıdır.
![image](https://github.com/user-attachments/assets/1d31a095-ce2f-42c4-afeb-e195f70d59cd)
 
Bu grafikte:
•	Yatay eksen: Eğitim veri setinin boyutu (m_train) yani algoritmanın öğrenmek için kullanabileceği örnek sayısıdır.
•	Dikey eksen: Hata değeridir (J_cv veya J_train).
Çapraz Doğrulama Hatasının Grafiği
İlk olarak, çapraz doğrulama hatasını çizelim. Grafik aşağıdaki gibi olacaktır:
•	Eğitim veri setinin boyutu arttıkça model daha iyi öğrenir ve J_cv azalır.
•	Bu beklenen bir durumdur çünkü daha fazla veri, modelin genelleme yeteneğini artırır.
Eğitim Hatasının Grafiği
Şimdi, eğitim hatasının nasıl değiştiğine bakalım:
•	Eğitim veri seti küçükken eğitim hatası düşük olur çünkü model eğitim örneklerine mükemmel şekilde uyum sağlayabilir.
•	Eğitim veri seti büyüdükçe eğitim hatası artar. Bunun sebebi, modelin artık tüm verileri mükemmel bir şekilde ezberleyememesidir.
Özetle:
•	Küçük eğitim setlerinde modelin eğitime uyumu mükemmel olabilir, ancak daha fazla veri ekledikçe tüm noktaları mükemmel şekilde uydurmak zorlaşır ve J_train artar.
•	Çapraz doğrulama hatası (J_cv) genellikle eğitim hatasından (J_train) daha büyük olur, çünkü modelin parametreleri eğitim setine uydurulmuştur ve model eğitim verisi üzerinde daha iyi performans gösterir.

# Yüksek Bias (Underfitting) Durumu
Şimdi, yüksek bias (düşük model karmaşıklığı) durumunda öğrenme eğrilerinin nasıl göründüğüne bakalım.
![image](https://github.com/user-attachments/assets/e1dce69a-d499-4bb5-b785-99eeb2c33255)
 
Örneğin, veriye sadece doğrusal bir model uyduruyorsanız (linear regression), aşağıdaki grafik oluşur:
•	Eğitim hatası (J_train) artar ve belirli bir noktadan sonra düzleşir (plato yapar).
•	Çapraz doğrulama hatası (J_cv) da azalır ama yine belirli bir noktadan sonra plato yapar.
Bu plato yapma durumu şunu gösterir:
•	Daha fazla eğitim verisi eklemek modelin performansını artırmaz çünkü model zaten çok basit olduğu için öğrenebileceğinden fazlasını öğrenememektedir.
•	İnsan seviyesinde performans ile modelin performansı arasında büyük bir fark vardır.
•	Eğer modeliniz yüksek bias’a sahipse, daha fazla veri eklemek öğrenme başarısını artırmaz. Bunun yerine:
o	Daha karmaşık bir model kullanabilirsiniz (örneğin, polinomal regresyon veya derin sinir ağları gibi).
o	Daha fazla özellik (feature) ekleyebilirsiniz.
o	Daha güçlü bir model mimarisi kullanabilirsiniz.
Bu nedenle, yüksek bias durumunda yalnızca veri setini büyütmek yerine modelin kapasitesini artırmak gerekir.
# Yüksek Varyans (Overfitting) Durumu
Şimdi, yüksek varyans (çok karmaşık model) durumunu inceleyelim.

![image](https://github.com/user-attachments/assets/b276e89f-fd5f-4e25-9aed-05c0266b11f4)
 
Örneğin, dördüncü dereceden bir polinom (çok esnek bir model) eğitiyorsanız, aşağıdaki öğrenme eğrileri oluşur:
•	Eğitim hatası (J_train) başlangıçta çok düşük olur çünkü model veriyi çok iyi ezberler.
•	Çapraz doğrulama hatası (J_cv) oldukça yüksektir çünkü model aşırı uyum sağladığı için genelleme yapamaz.
Bu grafikte J_train ve J_cv arasındaki büyük fark, yüksek varyansın bir göstergesidir.


# Bias-Varyans Dengesi ve Derin Öğrenme ile Yeni Yaklaşım
Geleneksel yaklaşımlarda, çok basit bir model yüksek yanlılığa, çok karmaşık bir model ise yüksek varyansa sahip olur. Bu nedenle, en iyi sonucu elde edebilmek için bu iki olumsuzluk arasında bir denge kurulması gerekir.
Ancak, derin öğrenme (neural networks), bu yanlılık-varyans dengesi zorunluluğundan bizi büyük ölçüde kurtaran yeni bir yaklaşım sunmaktadır. Bazı sınırlamalar olmakla birlikte, büyük yapay sinir ağları genellikle düşük yanlılık makineleri olarak işlev görür. Bunun anlamı, eğer bir sinir ağını yeterince büyük hale getirirseniz, genellikle eğitim verisine çok iyi uyum sağlayabilir. Yani, eğitim veri kümeniz aşırı büyük olmadığı sürece, büyük bir sinir ağı eğitim kümesi üzerinde çok düşük hata oranına ulaşabilir.
Bu durum, makine öğrenimi modellerini iyileştirme sürecinde yeni bir strateji sunmaktadır:
1.	Algoritmayı eğitim kümesi üzerinde eğitin ve eğitim hatasını (J_train) ölçün.
o	Eğer hata çok yüksekse, bu bir yüksek yanlılık (bias) sorunudur.
o	Yanlılığı azaltmanın en etkili yollarından biri, daha büyük bir sinir ağı kullanmaktır (daha fazla gizli katman veya daha fazla düğüm eklemek).
o	Bunu yaparak eğitim hatasını düşürmeye devam edebilirsiniz.
2.	Eğitim setindeki hata düşük olduğunda çapraz doğrulama setindeki (J_cv) hataya bakın.
o	Eğer çapraz doğrulama hatası yüksekse, bu bir yüksek varyans (variance) sorunudur.
o	Varyans sorununu çözmenin en etkili yollarından biri daha fazla veri toplamaktır.
o	Daha fazla veri ekleyerek modeli tekrar eğitmek, varyansın azalmasına yardımcı olur.
Bu döngü, modelin hem eğitim kümesi hem de çapraz doğrulama kümesi üzerinde iyi performans gösterene kadar tekrarlanabilir.
# Büyük Sinir Ağlarının Sınırlamaları
Her ne kadar büyük sinir ağları teorik olarak düşük yanlılık makineleri olsa da, pratikte bazı kısıtlamalar vardır:
•	Hesaplama maliyetleri: Büyük sinir ağlarının eğitimi zaman alır ve yüksek hesaplama gücü gerektirir. Bu nedenle, GPU’lar gibi özel donanımların yükselişi, derin öğrenmenin gelişiminde büyük rol oynamıştır.
•	Veri sınırlamaları: Daha fazla veri toplamak her zaman mümkün değildir. Bazı durumlarda veri toplamak çok maliyetli veya etik olarak sakıncalı olabilir.


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
