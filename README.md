# LoggerJS
New Console.log Texture messages Javascript Library

## Add script

<h2>HTML:</h2>

```js
<script src="https://cdn.jsdelivr.net/gh/Qwyua/LoggerJS/loggerv2.min.js"></script>
```

<h2>Tampermonkey:</h2>

```js
// @require      https://cdn.jsdelivr.net/gh/Qwyua/LoggerJS/loggerv2.min.js
```

<h4>or</h4>

```js
var script = document.createElement('script');
script.src = 'https://cdn.jsdelivr.net/gh/Qwyua/LoggerJS/loggerv2.min.js';
document.body.appendChild(script);
```

## How to use script
```js
const logger = new Logger();
window.logger = logger;
//unsafeWindow.logger = logger; // Tampermonkey
```

```js
logger.log("Merhaba, bu bir özel log mesajıdır.");
logger.success("İşlem başarılı!");
logger.error("Bir hata oluştu!");
logger.warning("Dikkat! İşlemde sorun oluşabilir.");
logger.image("path/to/image.jpg");
```

### log
`log(message, level = "default", group = null)`: Bu yöntem, bir log mesajını yazdırmak için kullanılır. İlk parametre `message`, yazdırılacak mesajdır. İkinci parametre olan `level`, mesajın hangi seviyede olduğunu belirtir ve varsayılan olarak "default" değerini alır. Üçüncü parametre `group`, mesajın ait olduğu bir grup varsa belirtilir.

Örnek kullanım:
```js
logger.log("Bu bir log mesajıdır.");
logger.log("Bir hata oluştu!", "error");
logger.log("Dikkat!", "warning", "Grup 1");
```

### success
`success(message, group = null)`: Bu yöntem, bir başarı mesajı yazdırmak için kullanılır. `log` yöntemini "success" seviyesiyle çağırır.

Örnek kullanım:
```js
logger.success("İşlem başarıyla tamamlandı.");
```

### error
`error(message, group = null)`: Bu yöntem, bir hata mesajı yazdırmak için kullanılır. `log` yöntemini "error" seviyesiyle çağırır.

Örnek kullanım:
```js
logger.error("Bir hata oluştu!");
```


### warning
`warning(message, group = null)`: Bu yöntem, bir uyarı mesajı yazdırmak için kullanılır. `log` yöntemini "warning" seviyesiyle çağırır.

Örnek kullanım:
```js
logger.warning("Dikkat!");
```


### applyAnimation
`applyAnimation(message, animation, style)`: Bu yöntem, bir log mesajını animasyonlu bir şekilde yazdırmak için kullanılır. `message` parametresi yazdırılacak mesajdır. `animation` parametresi kullanılacak animasyonun adını belirtir. `style` parametresi ise mesajın stilini belirtir.

Örnek kullanım:
```js
logger.applyAnimation("Animasyonlu mesaj", "fade", "color: red;");
```


### filter
`filter(level)`: Bu yöntem, belirli bir seviyeye göre logları filtrelemek için kullanılır. Belirtilen seviyeye uyan log mesajları `console.log` ile yazdırılır.

Örnek kullanım:
```js
logger.filter("error");
```

 `onLog(callback)`: Bu yöntem, bir geri çağırma fonksiyonunu `logCallback` değişkenine atar. `callback` parametresi olarak bir fonksiyon alır.
 
Örnek kullanım:
```js
logger.onLog((log) => {
  console.log("Yeni log mesajı:", log.message);
});
```
