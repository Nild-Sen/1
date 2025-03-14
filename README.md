# Оптимізація зображень за допомогою Squoosh

##     1. Аналіз вихідних файлів
        
|       |Вхідні дані|Формат|Розмір|Вага|
|-------|-----------|------|----|------|
|Фото|<img src="img/1.jpg" width="250">|JPG|3072x4080|2.3 mb
|Скріншот|<img src="img/2.png" width="250" height="150">|PNG|1920x1080|510 kb
|Графічне зображення з текстом|<img src="img/3.1.jpg" width="250">|JPG|1920x1080|375 kb

    
    
##    2. Стиснення без втрати якості(lossless)

### **Фото**
    
|JPG|Browser PNG|WebP|
|---|-----------|----|
|<img src="img/1.jpg" width="300"> |<img src="img/1 browser png lossless.png" width="300">|<img src="img/1 webp lossless.webp" width="300">|
|2.3 mb|10.7 mb|4.93 mb

### **Скріншот**
    
|PNG|Browser PNG|WebP|
|---|-----------|----|
|<img src="img/2.png" width="500" height=""> |<img src="img/2 webp lossless.webp" width="500">|<img src="img/2 webp lossless.webp" width="500">|
|510 kb|7 mb|275 kb|

### **Графічне зображення з текстом**
    
|JPG|Browser PNG|WebP|
|---|-----------|----|
|<img src="img/3.1.jpg">|<img src="img/3.1 webp lossless.webp">|<img src="img/3.1 webp lossless.webp">|
|375 kb|3 mb|1.33 mb|

##     3. Стиснення з втратою якості (lossy)

### **Фото**

|JPG|MozJPEG|WebP(lossy)|AVIF|
|---|-----------|-------|----|
|<img src="img/1.jpg" width="300"> |<img src="img/1 mozjpeg lossy 100.jpg" width="300">|<img src="img/1 webp lossy 75%25.webp" width="300">|<img src="img/1 avif lossy 50 %25.avif" width="350">
|3072x4080|3072x4080|1536x2040|1536x2040

### **Скріншот**
    
|JPG|MozJPEG|WebP(lossy)|AVIF|
|---|-----------|-------|----|
|<img src="img/2.png" width="500" height=""> |<img src="img/2 mozjpeg lossy 100 %25.jpg" width="500">|<img src="img/2 webp lossy 75%25.webp" width="500">|<img src="img/2 avif lossy 50 %25.avif" width="700">
|1920x1080|1920x1080|1020x630|960x518|

### **Графічне зображення з текстом**
    
|JPG|MozJPEG|WebP(lossy)|AVIF|
|---|-----------|-------|----|
|<img src="img/3.1.jpg">|<img src="img/3.1 mozjpeg 100%25.jpg">|<img src="img/3.1 webp lossy 75%25.webp">|<img src="img/3.1 avif 50%25.avif">
|1920x1080|1920x1080|960x540|960x540

### Висновок: При значенні Quality ~= 20 рівень якості зображення залишается прийнятним

##     4. Оптимізація розміру відповідно до цільового використання

|Для вебу|Для мобільних пристроїв|Для Retina-дисплеїв|
|--------|-----------------------|-------------------|
|<img src="img/1 web 1200.jpg">|<img src="img/1 mob 600.jpg">|<img src="img/1 3x retina.jpg">|
|90 kb|35.2 kb|2.35 mb|
|<img src="img/2 1200 web.jpg">|<img src="img/2 600 mob.jpg">|<img src="img/2 2x retina.jpg">|
|73.8 kb|20.8 kb|345 kb|
|<img src="img/3.1 1200 web.jpg">|<img src="img/3.1 600 mob.jpg">|<img src="img/3.1 2x retina.jpg">|
|141 kb|47.8 kb|652 kb|
