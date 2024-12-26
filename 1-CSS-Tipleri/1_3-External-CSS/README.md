# External CSS Rehberi

Bu rehber, **External CSS**'in (Harici CSS) ne olduğunu, nasıl kullanıldığını ve en iyi uygulamalarını detaylı bir şekilde açıklamaktadır. External CSS, büyük ve organize projeler için ideal olan en yaygın CSS uygulama yöntemlerinden biridir. Bu doküman, hem yeni başlayanlar hem de deneyimli geliştiriciler için faydalı olacak şekilde düzenlenmiştir.

---

## External CSS Nedir?

External CSS, HTML belgesinden ayrı bir `.css` dosyasında yazılan ve birden fazla HTML belgesine uygulanabilen stil kurallarıdır. Bu yöntem, stillerle içerik arasında net bir ayrım yaparak kodun okunabilirliğini ve yönetilebilirliğini artırır.

### Temel Yapı:

1. **HTML dosyasının `<head>` kısmına bağlantı eklenir.**
   ```html
   <link rel="stylesheet" href="stil.css">
   ```
- Bunun `stil.css` olması zorunlu değildir, istediğiniz adı kullanabilirsiniz.

   
2. **Stil kuralları ayrı bir `.css` dosyasında tanımlanır.**
   ```css
   body {
       background-color: #f0f0f0;
       font-family: Arial, sans-serif;
   }
   h1 {
       color: blue;
       text-align: center;
   }
   ```

---

## External CSS Kullanımı

### HTML Dosyası:
HTML dosyasının `<head>` etiketine, harici CSS dosyasını bağlamak için `<link>` etiketi eklenir.

```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>External CSS Örneği</title>
    <link rel="stylesheet" href="stil.css">
</head>
<body>
    <h1>External CSS Örneği</h1>
    <p>Bu bir harici CSS örneğidir.</p>
</body>
</html>
```

### CSS Dosyası:
Bu CSS kuralları ayrı bir dosyada (`stil.css`) tanımlanır ve yukarıdaki HTML dosyasına uygulanır.

```css
body {
    background-color: #f8f9fa;
    color: #343a40;
    font-family: 'Verdana', sans-serif;
    margin: 0;
    padding: 0;
}

h1 {
    color: #007bff;
    text-align: center;
    font-size: 2em;
    margin-top: 20px;
}

p {
    font-size: 1em;
    line-height: 1.5;
    margin: 20px;
}
```

---

## External CSS'nin Avantajları ve Dezavantajları

### Avantajlar
- **Yeniden Kullanılabilirlik:** Birden fazla HTML dosyasına aynı CSS dosyasını uygulayabilirsiniz.
- **Kodun Ayrılması:** Stiller ve içerikler farklı dosyalarda yer alır, bu da okunabilirliği artırır.
- **Kolay Yönetim:** Değişiklik yapmak daha hızlıdır. Tek bir CSS dosyasını düzenlemek, tüm bağlı HTML dosyalarını etkiler.
- **Performans:** Tarayıcı, harici CSS dosyasını önbelleğe alarak yükleme hızını artırabilir.

### Dezavantajlar
- **Ekstra HTTP İstekleri:** Her harici dosya için tarayıcı bir HTTP isteği yapar, bu da yükleme süresini artırabilir.
- **Bağımlılık:** Harici CSS dosyası yüklenemezse veya bulunamazsa, HTML sayfası düzgün görünmeyebilir.

---

## En İyi Kullanım Örnekleri

### Büyük Projeler
External CSS, büyük ölçekli projelerde stilleri düzenlemek ve yönetmek için en iyi yöntemdir.

```css
/* global.css */
body {
    margin: 0;
    padding: 0;
    background-color: #ffffff;
    font-family: 'Helvetica', sans-serif;
}

.navbar {
    background-color: #333;
    color: white;
    padding: 10px 20px;
    text-align: center;
}

footer {
    background-color: #f1f1f1;
    text-align: center;
    padding: 10px;
    margin-top: 20px;
}
```

### Tasarımda Tutarlılık Sağlama
Tüm sayfaların aynı tasarıma sahip olmasını sağlamak için External CSS kullanabilirsiniz.

```html
<link rel="stylesheet" href="styles/reset.css">
<link rel="stylesheet" href="styles/layout.css">
<link rel="stylesheet" href="styles/theme.css">
```

---

## İpuçları

1. **Mantıksal Dosya Yapısı Kullanın:** CSS dosyalarınızı modüler yapıda organize edin (örneğin, `base.css`, `layout.css`, `components.css`).

2. **Tarayıcı Uyumluluğunu Kontrol Edin:** Harici CSS kullanırken tarayıcı uyumluluğunu test edin.

3. **Önbelleklemeden Yararlanın:** Harici CSS dosyalarını önbelleğe alarak performansı artırabilirsiniz.

4. **Sınıfları Kullanmayı Unutmayın:** Genel eleman seçicileri yerine sınıfları kullanarak daha spesifik ve yeniden kullanılabilir stiller oluşturun.

   ```css
   .btn-primary {
       background-color: #007bff;
       color: white;
       padding: 10px 20px;
       border: none;
       border-radius: 5px;
   }
   ```

---

## Kaynaklar

- [MDN Web Docs: External CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3Schools: CSS External](https://www.w3schools.com/css/css_howto.asp)

Bu rehberi dikkatlice okuyarak External CSS ile ilgili temel ve ileri düzey bilgileri öğrenebilirsiniz. Daha fazla pratik yaparak projelerinizi daha profesyonel hale getirin!
