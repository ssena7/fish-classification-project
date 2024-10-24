# fish-classification-project

Bu proje, balık türlerini sınıflandırmak amacıyla derin öğrenme tekniklerini kullanarak bir model geliştirmeyi hedeflemektedir. Proje, Kaggle üzerinde bulunan "A Large Scale Fish Dataset" adlı veri setini kullanmakta olup, bu veri seti farklı balık türlerine ait görüntüleri içermektedir. Projenin temelinde görüntü işleme, model eğitimi ve sonuçların görselleştirilmesi yer almaktadır.

Gerekli kütüphaneler arasında os, cv2, numpy, pandas, sklearn, tensorflow, keras_tuner ve matplotlib bulunmaktadır. Kod, öncelikle veri setini yükleyip, görüntüleri boyutlandırarak bir pandas DataFrame oluşturur. Ardından, bu görüntüler numpy dizisine dönüştürülerek normalleştirilir ve etiketler one-hot encoding yöntemiyle dönüştürülür. Eğitim ve test setleri, eğitim verilerinin %80’i ve test verilerinin %20’si olacak şekilde ayrılır.
Model, Keras Tuner kullanılarak hiperparametre optimizasyonu ile oluşturulmakta ve eğitim sürecinde modelin en iyi versiyonu bulunmaktadır. Model eğitilirken toplam 5 epoch kullanılmıştır; bu, veri setinin büyüklüğü nedeniyle eğitim süresinin uzamasına neden olmuştur. Modelin performansı test verileri üzerinde değerlendirilirken kayıp ve doğruluk metrikleri ölçülmektedir. Eğitim sürecinin görselleştirilmesi için kayıp ve doğruluk grafiklerine yer verilmiştir. Proje, çalıştırıldığında modelin eğitim sürecini başlatmakta ve sonuçları grafikler ile göstermektedir.

Kod yapay sinir ağı (ANN) mimarisini kullanıyor. Özellikle, sequential bir model oluşturulmuş ve bu model aşağıdaki katmanları içermektedir:

1)Flatten Katmanı: Görüntü verisini 1D diziye dönüştürerek, girişlerin dense katmanlarına uygun hale getirilmesini sağlar. Burada, görüntülerin boyutları (128, 128, 3) olduğu için toplam 49,152 (128 × 128 × 3) özelliğe sahiptir.

2)Dense Katmanı: Bu, tam bağlı bir katmandır ve burada ilk dense katmanında 96 nöron bulunmaktadır. Bu katman, modelin öğrenme yeteneğini artırmak için ağırlıklar ve biaslar içeren bağlantılarla donatılmıştır.

3)Dropout Katmanı: Overfitting (aşırı öğrenme) sorununu önlemek için belirli bir oranla nöronları devre dışı bırakarak modelin genelleme yeteneğini artırır.

4)İkinci Dense Katmanı: Bu katman, modelin çıktısını oluşturmak için kullanılır. Burada, balık türlerinin sayısına göre 18 nöron bulunmaktadır, bu da sınıflandırılacak farklı balık türlerini temsil eder. Bu katmanın çıkışı softmax aktivasyon fonksiyonu ile işlenir, böylece her balık türü için olasılık değerleri elde edilir.

## Proje testi hakkkında
Projeyi CNN kullanarak rahatça yapabildim ve sonuçları elde edebildim fakat ANN kullanımında zorlandım.
(Projede epoch sayısı artırılarak optimizasyon sağlanarak daha doğru sonuçlar elde edilebilir fakat ben test etme aşamasında veri setinin büyüklüğünden dolayı yüklenme sorunuyla karşılaştım ve hızlı test edebilmek için epoch sayılarını küçük tuttum.)

## Kaggle Notebook

Projeye ait Kaggle Notebook'a ([KAGGLE_NOTEBOOK_LINKI](https://www.kaggle.com/code/senasmer/notebook8437a20cc5)) buradan ulaşabilirsiniz.
https://www.kaggle.com/code/senasmer/bal-k-s-n-fland-rma-globalai/notebook

