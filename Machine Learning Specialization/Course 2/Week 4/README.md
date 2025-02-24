# Course 2 Week 4 
## Karar Ağaçları 
Karar ağaçları, verileri belirli bir kurala göre  dallara ayırarak sınıflandırma veya regresyon yapabilen bir makine öğrenimi modelidir. Bu model, ağaç yapısında düğümlerden ve dallardan oluşur. Bir karar ağacı, veriye ardışık bir şekilde sorular sorarak onu alt gruplara ayırır ve en uygun sonucu bulmaya çalışır.

Bu süreç, insan zihninin birtakım problemleri çözme şekline benzer. Örneğin, bir hayvanın kedi mi yoksa köpek mi olduğunu belirlemek için önce kulak şekline, sonra kuyruğun uzunluğuna bakması gibi, karar ağaçları da veride belirli özelliklere odaklanarak ilerler. 

Karar ağaçları genellikle aşağıdaki sebeplerden dolayı tercih edilir: <br/> 
**Yorumlanabilirlik**: Çıktıların açıklanması ve görselleştirilmesi kolaydır. <br/>
**Özellik Seçimi**: Hangi özelliklerin daha önemli olduğu belirlenebilir. <br/>
**Önişleme Gerektirmez**: Eksik veri veya normalizasyon gerektirmez. <br/>
**Karmaşık Olmayan Yapı**: Basit kurallara göre tahmin yapar. <br/>

Ancak karar ağaçlarının dezavantajları da vardır: <br/>
**Aşırı Öğrenme (Overfitting)**: Derin ağaçlar, eğitildikleri veriye çok iyi uyum sağlayabilir ancak yeni verilere karşı genelleme yapmakta zorlanabilir. <br/>
**Kararsızlık**: Küçük veri değişiklikleri, tamamen farklı ağaç yapılarının ortaya çıkmasına neden olabilir. <br/>
![Image](https://github.com/user-attachments/assets/7a009048-0ccf-4bc4-9f67-ef23dec7e458) <br/>
### Karar Ağacı Yapısı 
**Kök Düğüm (Root Node)**: En üstteki düğümdür ve verinin ilk bölümlendiği noktadır. Burada verinin hangi özelliğe göre ilk bölümleneceği belirlenir. Seçilen ilk bölüm ağacın geri kalanını şekillendireceğinden büyük bir önem taşır. <br/>
**Karar Düğümleri (Decision Nodes)**: Her düğüm, belirli bir özelliğe göre veriyi böler. Bu düğümler, veriyi farklı alt kümelere ayırarak sınıflandırma sürecini devam ettirir. <br/>
**Yaprak Düğümler (Leaf Nodes)**: Son karar noktalarıdır ve bir sınıf veya sayısal bir değer içerir. Yaprak düğümleri, artık daha fazla bölme yapılamayan noktalardır. Buradaki değerler, modelin tahmin ettiği sonuçları temsil eder. <br/>
![Image](https://github.com/user-attachments/assets/0ce377f1-1421-43cc-b1c5-76e846abb65e) <br/>

### Karar Ağacında Bölme (Splitting)
Karar ağaçları verileri bölmek için belirli kurallar kullanır. Bir düğümün nasıl bölüneceği kritik bir karardır çünkü ağacın doğruluk oranını direkt olarak etkiler. İyi bir bölme işlemi her bir alt grubu mümkün olduğunca tek bir sınıf haline getirmeye çalışır, yani mümkün olduğunca saf bir hale getirir.

Bölme işleminin nasıl devam ettirildiğini anlatmak için önce entropi kavramını açıklayalım. Entropi, bir veri kümesindeki safsızlığı ölçen metriktir. Veri ne kadar düzensizse entropi o kadar yüksektir. Eğer bir veri kümesi %100 tek bir sınıfa aitse, bu kümenin entropi değeri 0 olur yani belirsizlik yoktur. Amacımız entropiyi düşürerek veriyi daha saf hale getirmektir.
![Image](https://github.com/user-attachments/assets/8465cad7-67e2-4870-b4b8-e096bda7e658) <br/>
Peki, bir düğümün bölünmesi sonucunda entropinin nasıl değiştiğini nasıl ölçebiliriz? İşte burada bilgi kazanımı (Information Gain) devreye girer. Bilgi kazanımı, bir düğümün bölünmesi sonucunda entropinin ne kadar azaldığını ölçer. Eğer bölme işlemi sonucu alt kümelerin entropisi önemli ölçüde azalmışsa, bu bölmenin faydalı olduğu anlamına gelir. <br/>
![Image](https://github.com/user-attachments/assets/8650f20e-905a-44ef-8aa5-cc7cd628d29d) <br/>

![Image](https://github.com/user-attachments/assets/525c07bc-17da-4f14-b313-1cf31e0a9a66) <br/>

### One Hot Encoding 
Karar ağaçları, sayısal özelliklerle daha iyi çalışır. Ancak, birçok veri setinde kategorik değişkenler bulunur (örneğin, "renk: kırmızı, mavi, yeşil"). Kategorik değişkenleri makine öğrenimi modellerine uygun hale getirmek için One-Hot Encoding (Tekil Kodlama) yöntemi kullanılır.

One-Hot Encoding, her kategorik değişken için ayrı bir sütun oluşturarak ve yalnızca ilgili kategoriye 1, diğerlerine 0 değerini atayarak çalışır. Örneğin kulak şekli değişkeni oval, sivri ve sarkık değerlerini gibi üç kategori içeriyorsa, one hot encoding şu şekilde olur:
![Image](https://github.com/user-attachments/assets/a4b51a34-d1e5-497f-8946-0dc90bae9cd1) <br/>

Bu yöntem, karar ağaçları gibi algoritmaların kategorik değişkenlerle çalışmasını kolaylaştırır, çünkü model artık her özelliği bağımsız olarak değerlendirebilir.

One-Hot Encoding'in avantajları: <br/>
Kategorik veriyi sayısal hale getirerek makine öğrenimi modellerine uygun hale getirir. <br/>
Karar ağaçlarında özellikleri daha iyi ayırt edebilme imkanı sağlar. <br/>
### Sürekli Değerlenen Özellikler (Continuous Features)
Karar ağaçları sadece kategorik değil, sürekli değişkenler (ağırlık, yaş) ile de çalışabilir. <br/>
Sürekli değişkenler için bölme yapmak, belirli bir eşik değerine göre karar vermeyi gerektirir. Örneğin, "Ağırlığı 9 lbs'den büyük mü?" gibi bir soru oluşturulabilir. <br/>
Bir veri setinde birçok sürekli değişken olabilir ve her birinin bölme noktası en iyi bilgi kazancı sağlayacak şekilde belirlenmelidir.<br/>

![Image](https://github.com/user-attachments/assets/a4b51a34-d1e5-497f-8946-0dc90bae9cd1)

![Image](https://github.com/user-attachments/assets/35dfeaa9-78e8-4b23-ae7f-859f6c09ef44) <br/>

### Regresyon Karar Ağaçları (Regression with Decision Trees)
Eğer hedef değişken sayısal bir değer içeriyorsa, karar ağaçları regresyon modeli olarak kullanılabilir.<br/>
Yaprak düğümlerde tahmin, o düğüme gelen örneklerin ortalaması alınarak yapılır.<br/>
Bölme kriteri olarak entropi yerine varyans, bilgi kazanımı yerine varyans azalımı (variance reduction) kullanılır.<br/>

![Image](https://github.com/user-attachments/assets/e1aae02f-ae43-4f08-ba53-4f6b641e8d36) <br/>

![Image](https://github.com/user-attachments/assets/c36e1bd6-3c7e-406d-94f1-06a8a8496ba9)  <br/>


Tree Ensembles

Tek bir karar ağacı kullanmanın iyi olduğu kadar olumsuz yönleri de vardır. Zayıf yönlerinden biri, bu karar ağacının verilerdeki küçük değişikliklere karşı oldukça hassas olmasıdır.
Eğitim örneğini değiştirirseniz sonuçta değişir. Mesela bu kedi ilk karar ağacına göre kedi kategorisine girememişti çünkü kriterlerden biri olan keskin kulak yapısına uymuyordu ve ilk karar ağacına göre kedi değildi. Ancak eğitim örneğini değiştirip kriterimizi bıyık yaptığımızda kedi kategorisine girdi bu yüzden bahsettiğim gibi birden fazla karar ağacı yani decision tree ensembles ile hata oranını minimize etmeye çalışırız.
Tek bir eğitim örneğinin değişmesi bile o karar ağacının kökten itibaren bölünmesini değiştireceğinden o ağacı tamamen değiştirir. Böylece biz de ağaç topluluğu ile daha doğru tahminler elde ederiz.


![alt text](image.png)

