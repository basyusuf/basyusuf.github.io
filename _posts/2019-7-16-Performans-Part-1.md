# Network Performance
### 1-Minimize File
Sayfalardaki yazdığımız kodlarda derlenmeden önce bir eklentiyle bunların boşluklarını silmeliyiz. Buna örnek olarak javascript dosyasında yazdığımız kodun derlenmeden boyutunu düşürmek için yaptığımız [Uglify JS](https://skalman.github.io/UglifyJS-online/) uygulaması.
### 2-Minimize IMG
IMG,GIF,SVG VE PNG olarak aralarında performansına göre doğru imaj secmek sayfada hız kazandıracaktır.
* Bu resim dosyalarının avantaj dezavatanjları : [Avantaj Dezavantaj](https://99designs.com/blog/tips/image-file-types/)
* Karşılaştırması : [Karşılaştırma](https://www.sitepoint.com/gif-png-jpg-which-one-to-use/)
* Sitenin resim boyutu düşürecek test :[Page Weight](https://pageweight.imgix.com/)
### Testin [Sefamerve](http://www.sefamerve.com) için çıktısı
![Optimize Web Site Screen Example](https://raw.githubusercontent.com/basyusuf/basyusuf.github.io/master/_posts/OptimizeScreen.png)


## Özet:
* Transparent bir görüntü istiyorsan : **PNG**  formatını kullanmalısın.
* Animasyon görüntüsü istiyorsan : **GIF** formatını kullanmalısın.
* Renkli detay istiyorsan : **JPG** formatını kullanmalısın.
* Basit ikon ve logo kullanacaksanuz : **SVG** formatını kullanmalısın.
* PNG Küçültmek için => [Tinypng](https://tinypng.com/) Pnglerin boyutunda düşüş sağlamaya yardımcı olacaktır.
* JPG Küçültmek için => [Jpeg Optimizer](http://jpeg-optimizer.com/) Jpglerin boyutunda düşüş sağlamaya yardımcı olacaktır.
* Resim yerine ikon kullanabileceğin kısımları belirleyin ve gereksiz resim kullanımı yapmayın.
* Jpeg img kalitesini **%30 - %60** arasına indirmen hafızada farkedilecektir.
* Kullanacağımız nesnenin **max size**’ı **img size** ile aynı olsun. Örneğin bir div oluşturduk 500x500 resimin maximum size 500x500 yapmalıyız.
* Kullanacağımız img dosyasını ekran boyutlarına göre ayarlayıp her ekran boyutu için ayrı resize edip yazabiliriz. Örnek olarak background-img yüksek boyutta ise **media taglerine** göre **resize** hallerini yazabiliriz.
* Resimlerin içindeki **meta tag**larını silin. Resimin nerede çekildiği hangi aygıttan çekildiği gibi detayları silmek için kullanacağınız eklenti => [Verexif](https://www.verexif.com/en/)

Maxiumum tarayıcı başına **http isteklerinin** detaylı kaynağı: [Stackoverflow Parallel http](https://stackoverflow.com/questions/985431/max-parallel-http-connections-in-a-browser)
