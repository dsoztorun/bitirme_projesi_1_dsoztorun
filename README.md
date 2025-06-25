## Müşteri Deneyimi Analizi – Bitirme Projesi
Bu proje, Kız Başına Veri Analizi Bootcamp kapsamında hazırlanan birinci bitirme çalışmasıdır. Projede, bir müşteri deneyimi veri seti kullanılarak müşteri sadakati ve memnuniyetini etkileyen faktörler analiz edilmiştir.

### Proje Amacı
Veri setinde yer alan demografik ve davranışsal veriler kullanılarak:
- Müşteri sadakati (`Retention_Status`) ile ilişkili olabilecek faktörlerin (ör. yaş, cinsiyet, konum, satın alınan ürün sayısı, geri bildirim puanı) görselleştirilmesi
- Sayısal ve kategorik değişkenler arasında istatistiksel ilişki olup olmadığının grafiklerle analiz edilmesi
- Anlamlı örüntülerin yorumlanarak iş içgörülerine dönüştürülmesi amaçlanmıştır.

### Ekli Dosyalar
| Dosya Adı | Açıklama |
|-----------|----------|
| `Bitirme_Projesi_1.ipynb` | Veri analizi sürecini ve grafiklerle yapılan yorumları içeren Jupyter Notebook |
| `customer_experience_data.csv` | Analizde kullanılan veri seti |
| `Müşteri Deneyimi İncelemesi.pptx` | Projenin özet sunumu |
| `README.md` | Proje tanımı ve içeriği |

### Kullanılan Araçlar
- Python
- Google Colab
- Pandas
- Matplotlib
- Seaborn

### Not:
1. Bu repoyu klonlayın veya `.ipynb` dosyasını Google Colab'de açın.
2. Gerekli kütüphaneleri yükleyin.
3. Notebook'ta bulunan hücreleri sırasıyla çalıştırarak analiz sürecini izleyin.
4. CSV dosyası otomatik olarak GitHub'dan okunur (Drive bağlantısı gerekmez).

```python
url = "https://raw.githubusercontent.com/dsoztorun/bitirme_projesi_1_dsoztorun/main/customer_experience_data.csv"
c_exp1 = pd.read_csv(url)
```

## Özet

Raporda ilk olarak hangi veri setinin seçildiği ve  raporun hedefi belirtilmiştir. Ardından rapora konu olan verilerin istatistiksel özeti yapılmış, verilerde eksik ve aykırı değerler olup olmadığı incelenmiştir. Daha sonra veriler incelenerek, aralarında anlamlı ilişki bulunabilecek veri kümeleri belirlenmiş ve bu ilişkileri en anlamlı ve okunaklı şekilde ortaya koyabilecek grafik türleri tespit edilmiştir. Grafiklerin kodlaması ve her grafiğin ardından yapılan analizlerle birlikte rapora konu olan verilerin değerlendirilmesi yapılmıştır. Son olarak raporlama kısmında bu değerlendirmeler özetlenmiş ve raporun hedefi doğrultusunda ortaya çıkan sonuçlar ele alınmışlardır.

## Sonuç

Bu analiz çalışmasında, müşteri davranışlarını etkileyen temel metrikler olan **etkileşim sayısı**, **görüntüleme**, **sitede geçirilen süre**, **geri bildirim puanı**, **memnuniyet düzeyi**, **müşteri durumu** ve **satın alınan ürün sayısı** arasındaki ilişkiler ayrı ayrı ve segment bazında detaylı şekilde incelenmiştir.

### Genel Çıkarımlar:

- **Etkileşim, Görüntüleme ve Satın Alma Arasındaki İlişki**:
  - Daha fazla etkileşimde bulunan kullanıcıların daha fazla ürün görüntülediği ve genellikle daha fazla satın alma eğilimi gösterdiği gözlemlenmiştir.

- **Sitede Geçirilen Süre**:
  - Özellikle **15 dakika ve üzeri** sitede kalan kullanıcıların daha fazla ürün satın aldığı tespit edilmiştir. Bu etki tutulan müşterilerde daha da belirgindir. Dolayısıyla sitede kalma süresinin artırılması, satışlara doğrudan katkı sağlayabilir.

- **Memnuniyet ve Sadakat**:
  - Yüksek memnuniyet puanları tutulan müşteri grubunda daha sık görülmektedir. Aynı memnuniyet düzeyine sahip olsalar bile tutulan müşterilerin daha fazla ürün satın alma eğiliminde olduğu gözlemlenmiştir.
  - Geri bildirim puanı ve memnuniyet puanı arasında pozitif yönlü bir ilişki mevcuttur. Bu da geri bildirimlerin doğru şekilde izlenmesinin memnuniyet yönetimi açısından önemini ortaya koymaktadır.

- **Geri Bildirim ve Memnuniyetin Dağılımı**:
  - Tutulan müşterilerde memnuniyet puanları genellikle daha geniş bir aralıkta ve yüksek seviyelerde toplanırken, kaybedilen müşterilerde memnuniyet puanları daha düşüktür. Bu durum, müşteri memnuniyetinin kayıp riskini azaltmada belirleyici bir faktör olduğunu göstermektedir.

- **Segment Bazlı Yaklaşımların Önemi**:
  - Heatmap gibi görselleştirmelerde; **site süresi** ve **görüntüleme sayısı** gibi metriklerin memnuniyet puanı üzerindeki etkisinin, müşteri segmentlerine göre değiştiği görülmüştür. Bu da tekil metrik analizlerinin yetersiz kalabileceğini ve **çok boyutlu segment analizlerine** ihtiyaç duyulduğunu ortaya koymaktadır.
  - **Kategorik segmentlerde** müşteri davranışları açısından küçük farklar bulunduğu gözlemlenmiş olup, dönemsel olarak **cinsiyet** ve **konum** bazlı çalışma ve kampanyaların, satılan ürün ve tutulan müşteri sayısını arttırmayı sağlayabileceği görülmektedir.  

### Öneriler:

- **Sadakat stratejileri** geliştirirken yalnızca memnuniyet puanı değil, sitede geçirilen süre, geri bildirim puanı ve etkileşim gibi diğer davranışsal veriler de birlikte değerlendirilmelidir.
- **Kritik eşikler** (örneğin 15 dakika üzeri sitede kalma, 20’den fazla ürün görüntüleme gibi) müşteri kaybetme riskinin düştüğü segmentleri tanımlamada kullanılabilir.
- **Geri bildirim ve memnuniyet sistemleri**, sadece içsel ölçümlemeler değil, aynı zamanda satış ve sadakat tahminleme aracı olarak da etkin biçimde yapılandırılmalıdır.
- **Tutulan müşteriler**, hemen her boyutta daha istikrarlı ve olumlu davranışlar göstermektedir. Bu gruba özel kampanyalar ve teşvik sistemleri ile müşteri değeri artırılabilir.

Sonuç olarak, analiz hedeflerine ulaşılmış, veri görselleştirmeleri yoluyla kullanıcı davranışlarının satın alma kararları üzerindeki etkileri kapsamlı biçimde ortaya konmuştur. Elde edilen bulgular, müşteri deneyimi optimizasyonunda stratejik adımlar için sağlam bir temel sunmaktadır.
