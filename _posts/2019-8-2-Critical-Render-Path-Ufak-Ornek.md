Bir web sayfamız var html ve css ile oluşturulmuş. Web sayfamızda css yüklemesi yapmak istiyoruz fakat css boyutlarımız devasa şekile ulaştı. Sayfamızda performansa ihtiyaç duyduk ne yapabiliriz diye düşündük. Javascript sayesinde bir şey yapabilir miyiz diye karar verdikten sonra işe koyulduk.
Yapmamız gereken şey önemli olan cssleri belirlemek.
### Örnek projemde sahip olduğum dosyalar;
* index.html
* style1.css
* style2.css

Benim amacım style1.css ana divlerimi oluşturan css olduğundan ilk yüklenmesini yapmak istiyorum. Bir değişiklik yapmadan sayfama baktığımda yüklenme şu şekilde olmakta
![Normal Html Css Load](https://raw.githubusercontent.com/basyusuf/basyusuf.github.io/master/_posts/NormalhalCropped.png)

Ayar.js Adında bir dosya oluşturuyorum ve içine şu satırları yazıyorum
```
const loadStyleSheet = (src) =>{
    if(document.createStylesheet){
        document.createStylesheet(src)
    }
    else{
        const stylesheet = document.createElement("link");
        stylesheet.href= src;
        stylesheet.type="text/css";
        stylesheet.rel="stylesheet";
        document.getElementsByTagName('head')[0].appendChild(stylesheet);
    }
}
window.onload = function(){
    console.log("Pencere Tamamen Yüklendi");
    loadStyleSheet('./style2.css');
}
```
Bir fonksiyon oluşturduk bu fonksiyonun içine bir css hrefi yolladık bu hrefte bir css var mı kontrolu yaptıktan sonra eğer yok ise bir Link elementi oluşturduk. Link elementinin href,type ve rel gibi attiribute belirledik. Ve oluşturup attiribute'lerini yazdığımız değişkeni header'a child olarak ekledik. Bu ekleme işlemini sayfa yüklenmesinden sonra istediğimiz için window.onload fonksiyonuna yani pencere yüklendikten sonra css dosyamızı üretip heade eklemiş olduk. Görselde yüklenme işlemi çok daha kolay gözükmekte.
![Critical Render Path](https://raw.githubusercontent.com/basyusuf/basyusuf.github.io/master/_posts/RenderedCrop.png)
