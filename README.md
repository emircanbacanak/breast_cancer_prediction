# Makine Öğrenmesi ile Meme Kanseri Tahmini

## Genel Bakış
Bu proje, meme kanseri tanısı için kullanılan verilerle **makine öğrenmesi modelleri** oluşturarak, tümörlerin iyi huylu (benign) veya kötü huylu (malign) olup olmadığını tahmin etmeyi amaçlamaktadır. Projede çeşitli veri analizleri, model seçimi ve değerlendirme işlemleri yer almaktadır.

Bu çalışmanın amacı, klinik veriler kullanarak hekimlere veya araştırmacılara yardımcı olabilecek bir sınıflandırıcı modeli oluşturmaktır. Çeşitli algoritmalar denenmiş ve en iyi sonuç veren model seçilmiştir.

## Proje İçeriği
### 1. Veri Seti Hakkında
Kullanılan veri seti **Breast Cancer Wisconsin (Diagnostic) Dataset** adlı ünlü veri setidir. Bu veri seti, meme kanseri teşhisi için alınan biyopsi örneklerinden elde edilen 30 farklı özellik içerir.

- **Toplam Örnek Sayısı**: 569
- **Özellik Sayısı**: 30
- **Sınıflar**: İyi Huylu (Benign) ve Kötü Huylu (Malign)

### 2. Keşifsel Veri Analizi (Exploratory Data Analysis - EDA)
Bu aşamada, veri setine genel bir bakış atılır ve özelliklerin dağılımları görselleştirilir. Neden bunu yapıyoruz? Çünkü, verinin yapısını anlamak, modelleme adımlarında daha bilinçli kararlar almamıza yardımcı olur.

- Özellikler arasındaki ilişkiler incelenir.
- Sınıfların dağılımı görselleştirilir (örneğin, malign ve benign sınıflarının dengeli olup olmadığı kontrol edilir).
- Veri setindeki olası uç değerler veya eksik veriler tespit edilir.

### 3. Veri Ön İşleme (Data Preprocessing)
Modelleme aşamasına geçmeden önce veri setini hazırlamak gereklidir. Bu bölümde:
- Eksik veri olup olmadığı kontrol edilir ve gerekirse eksik veriler işlenir.
- Veriler normalize edilir. Bunun nedeni, bazı makine öğrenmesi algoritmalarının farklı ölçeklerdeki verilere karşı hassas olmasıdır. Özellikle K-Nearest Neighbors gibi algoritmalar, veri ölçeklerinden etkilenir.

Veri seti eğitim (train) ve test (test) verisi olarak bölünür. Bu sayede modelin performansı, daha önce görmediği veriler üzerinde test edilebilir.

### 4. Model Seçimi ve Eğitim
Bu projede, farklı makine öğrenmesi algoritmaları denenmiştir. Model seçiminde kullanılan algoritmalar:
- **Lojistik Regresyon (Logistic Regression)**: İkili sınıflandırma problemleri için yaygın olarak kullanılan basit ve etkili bir modeldir.
- **Karar Ağaçları (Decision Trees)**: Veriyi dallara ayırarak kararlar veren sezgisel bir modeldir.
- **Rastgele Orman (Random Forest)**: Birden fazla karar ağacı oluşturarak daha güçlü ve genellenebilir sonuçlar elde eder.
- **Destek Vektör Makineleri (Support Vector Machines - SVM)**: İki sınıfı birbirinden en iyi şekilde ayıran bir hiper düzlem bulmayı amaçlayan güçlü bir algoritmadır.

### Neden birden fazla model deniyoruz?
Her modelin avantajları ve dezavantajları vardır. Bu yüzden farklı modelleri deneyerek, hangisinin veri setimize daha uygun olduğunu anlamaya çalışırız. En iyi performans gösteren modeli seçerken doğruluk (accuracy), hassasiyet (precision), geri çağırma (recall) ve F1-skoru gibi metrikler kullanılır.

### 5. Model Değerlendirme
Modeller eğitildikten sonra test verisi üzerinde değerlendirilir. Bu aşamada:
- **Doğruluk (Accuracy)**: Modelin doğru tahminlerinin oranı.
- **Hassasiyet (Precision)**: Modelin kötü huylu tümörleri ne kadar doğru tespit ettiği.
- **Geri Çağırma (Recall)**: Gerçekten kötü huylu olan tümörlerin ne kadarını doğru tahmin ettiği.
- **F1-Skoru**: Hassasiyet ve geri çağırmanın dengeli bir kombinasyonu.

Bu metrikler, modelin klinik kullanımda ne kadar başarılı olacağını anlamak için önemlidir. Örneğin, geri çağırma oranı yüksek bir model, kanserli hastaları kaçırma olasılığı düşük olan bir modeldir, bu da sağlık alanında kritik bir metriktir.

### 6. Sonuçlar
Bu projede denenen çeşitli modeller arasında en iyi performansı gösteren model **X modeli** olmuştur. Bu model, test veri seti üzerinde %X doğruluk ile meme kanseri tümörlerini sınıflandırabilmiştir.

### 7. Görselleştirme
Modelin performansını ve veriyi daha iyi anlamak için çeşitli grafikler ve görseller sunulmuştur:
- Confusion Matrix (Karmaşıklık Matrisi)
- ROC Eğrisi ve AUC Skoru
- Özelliklerin model üzerindeki etkisini gösteren Feature Importance grafikleri

## Kurulum ve Kullanım
Projenin kendi bilgisayarınızda çalıştırılabilmesi için aşağıdaki adımları izleyin.

1. Bu projeyi klonlayın:
    ```bash
    git clone https://github.com/emircanbacanak/breast-cancer-prediction.git
    ```
2. Gerekli kütüphaneleri yükleyin:
    ```bash
    pip install -r requirements.txt
    ```
3. Jupyter Notebook'u başlatın:
    ```bash
    jupyter notebook breast-cancer-prediction.ipynb
    ```

### Gereksinimler
- Python 3.x
- Aşağıdaki Python kütüphaneleri:
    - `numpy`
    - `pandas`
    - `scikit-learn`
    - `matplotlib`
    - `seaborn`

Bu kütüphaneleri kurmak için şu komutu çalıştırabilirsiniz:
```bash
pip install -r requirements.txt
```
