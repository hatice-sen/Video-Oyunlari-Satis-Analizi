#  Video Oyunları Satış Analizi

Bu proje, **vgsales** veri seti kullanılarak popüler video oyunlarının satış verilerini analiz etmek, görselleştirmek ve makine öğrenmesi modelleriyle küresel satış performanslarını tahmin etmek amacıyla geliştirilmiştir.

---

##  Proje Özet Bilgileri
* **Veri Seti:** Video Game Sales (vgsales.csv)
* **Kullanılan Diller/Kütüphaneler:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn
* **Geliştirme Ortamı:** PyCharm / Jupyter Notebook

---

##  Uygulanan Aşamalar

### 1. Keşifsel Veri Analizi (EDA) & Temizlik
* Veri setinin yapısal özellikleri, veri tipleri ve eksik değerleri incelendi.
* `Global_Sales` sütunundaki aykırı değerler **IQR (Interquartile Range)** yöntemiyle tespit edilerek temizlendi.
* Eksik çıkış yılları veri setinin **Mod** değeriyle dolduruldu, yayıncı ismi eksik olan satırlar elendi.

### 2. Veri Görselleştirme (Seaborn & Matplotlib)
* Global satış dağılımları histogramlar yardımıyla analiz edildi.
* Oyun türlerinin pazar payları ve satış aralıkları kutu grafiği (**Boxplot**) ve keman grafiği (**Violinplot**) ile gösterildi.
* Bölgeler arası (Kuzey Amerika, Avrupa, Japonya) korelasyon ilişkileri **Heatmap** ve **Scatterplot** ile görselleştirildi.
* En popüler 10 platformun ortalama satış performansları hata çubuklarıyla (**Barplot**) incelendi.

### 3. Gruplama ve Koşullu Sorgular (Pandas)
* `groupby()` ve `agg()` fonksiyonları kullanılarak tür bazlı Japonya satış ortalamaları, yayıncıların toplam oyun sayıları ve yıllara göre min/max satış eğilimleri analiz edildi.
* Belirli satış eşiklerine ve yıllara (örneğin 2000-2010 arası) göre filtrelemeler yapıldı.
* `transform()` fonksiyonuyla grup bazlı ortalamalar ana veri setine yeni bir özellik olarak eklendi.

### 4. Makine Öğrenmesi Modeli (Satış Tahmini)
* `Platform`, `Genre` ve `Publisher` özellikleri **LabelEncoder** ve **StandardScaler** aşamalarından geçirilerek modele hazırlandı.
* Dünya genelindeki toplam satış miktarını (`Global_Sales`) tahmin etmek için iki farklı algoritma eğitildi ve karşılaştırıldı:

| Model | MAE (Ortalama Mutlak Hata) | $R^2$ Skoru (Açıklayıcılık Katsayısı) |
| :--- | :--- | :--- |
| **Linear Regression** | ~0.2014 | ~0.0068 |
| **Random Forest Regressor** | **~0.1596** | **~0.1878** |

> ** Model Yorumu:** Veri setindeki yapısal karmaşıklık ve doğrusal olmayan ilişkiler nedeniyle **Random Forest Regressor** modeli, Linear Regression'a kıyasla çok daha yüksek bir tahmin başarısı ($R^2 = \%18.78$) göstermiştir.

---

##  Kurulum ve Çalıştırma

Projeyi yerelde çalıştırmak isterseniz:
```bash
   git clone [https://github.com/KULLANICI_ADINIZ/video-game-sales-analysis.git](https://github.com/KULLANICI_ADINIZ/video-game-sales-analysis.git)

1. Depoyu bilgisayarınıza indirin:
   ```bash
   git clone [https://github.com/KULLANICI_ADINIZ/video-game-sales-analysis.git](https://github.com/KULLANICI_ADINIZ/video-game-sales-analysis.git)
