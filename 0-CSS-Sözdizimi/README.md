# CSS Sözdizimi

CSS, web sayfalarının görünümünü ve düzenini tasarlamak için kullanılır.

## CSS Nedir?
CSS, HTML gibi işaretleme dilleriyle birlikte çalışarak bir web sayfasının görsel tasarımını ve düzenini belirler. CSS ile yazı tipi, renkler, kenar boşlukları, arka planlar, hizalamalar ve daha fazlasını kontrol eder.

## CSS Sözdizimi
CSS, bir **seçici (selector)** ve bir **bildirim bloğu (declaration block)** olmak üzere iki ana kısımdan oluşur:

```css
seçici {
    özellik: değer;
    özellik: değer;
}
```

### Örnek:

```css
body {
    background-color: #f0f0f0;
    color: #333;
}
```

- **`body`**: HTML belgesindeki `<body>` elemanını seçer.
- **`background-color` ve `color`**: Özelliklerdir.
- **`#f0f0f0` ve `#333`**: Özellik değerleridir.

---

## Temel Kavramlar

### 1. **Seçiciler (Selectors)**
Seçiciler, hangi HTML elemanlarının stillendirileceğini belirler. Aşağıda yaygın olarak kullanılan seçici türleri listelenmiştir:

- **Evrensel Seçici (`*`)**: Tüm elemanları seçer.
  ```css
  * {
      margin: 0;
      padding: 0;
  }
  ```

- **Eleman Seçiciler (Element Selectors)**: Belirli bir HTML elemanını seçer.
  ```css
  h1 {
      font-size: 24px;
  }
  ```

- **Sınıf Seçicileri (`.class`)**: Belirli bir sınıfa sahip elemanları seçer.
  ```css
  .highlight {
      background-color: yellow;
  }
  ```

- **ID Seçicileri (`#id`)**: Belirli bir ID'ye sahip elemanları seçer.
  ```css
  #header {
      text-align: center;
  }
  ```

- **Grup Seçiciler**: Birden fazla elemanı aynı anda seçmek için kullanılır.
  ```css
  h1, h2, h3 {
      font-weight: bold;
  }
  ```

---

### 2. **Özellikler ve Değerler (Properties and Values)**
CSS'de, her bir özellik bir değerle eşleştirilir. Yaygın kullanılan özellikler şunlardır:

- **Renk Özellikleri**:
  ```css
    * {
      color: red; /* Yazı rengi */
      background-color: blue; /* Arka plan rengi */
    }
    ```

- **Yazı Tipi Özellikleri**:
  ```css
   * {
      font-size: 16px; /* Yazı boyutu */
      font-family: Arial, sans-serif; /* Yazı tipi */
    }
  ```

- **Kutu Modeli Özellikleri (Box Model)**:
  ```css
  * {
      margin: 10px; /* Dış boşluk */
      padding: 15px; /* İç boşluk */
      border: 1px solid black; /* Çerçeve */
  }
  ```

---

### 3. **CSS Yorumları**
CSS dosyalarınıza yorum eklemek için `/* yorum */` formatını kullanabilirsiniz. Yorumlar kodunuzu daha anlaşılır hale getirir ve tarayıcı tarafından yok sayılır.

```css
/* Bu bir yorumdur */
h1 {
    color: green; /* Başlık rengini belirler */
}
```

---

## CSS'nin Uygulanma Yöntemleri

1. **Satır İçi (Inline) CSS**:
   HTML elemanlarına `style` özelliği ile uygulanır.
   ```html
   <p style="color: blue; font-size: 14px;">Bu bir paragraf.</p>
   ```

2. **Dahili (Internal) CSS**:
   HTML belgesinin `<head>` bölümünde `<style>` etiketi içinde kullanılır.
   ```html
   <style>
       body {
           font-family: Arial, sans-serif;
       }
   </style>
   ```

3. **Harici (External) CSS**:
   Ayrı bir `.css` dosyasına yazılır ve HTML belgesine `<link>` etiketiyle bağlanır.
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

---

## İleri Seçiciler

- **Alt Seçiciler (Descendant Selector)**:
  ```css
  div p {
      color: red;
  }
  ```
  Bir `<div>` içindeki tüm `<p>` elemanlarını seçer.

- **Çocuk Seçiciler (Child Selector)**:
  ```css
  div > p {
      color: blue;
  }
  ```
  Sadece bir `<div>` elemanının doğrudan çocuklarını seçer.

- **Komşu Kardeş Seçiciler (Adjacent Sibling Selector)**:
  ```css
  h1 + p {
      margin-top: 20px;
  }
  ```
  Bir `<h1>` elemanından hemen sonraki `<p>` elemanını seçer.

- **Genel Kardeş Seçiciler (General Sibling Selector)**:
  ```css
  h1 ~ p {
      font-style: italic;
  }
  ```
  Bir `<h1>` ile aynı seviyede bulunan tüm `<p>` elemanlarını seçer.

---

## Medya Sorguları (Media Queries)
Medya sorguları, farklı cihazlar ve ekran boyutları için CSS yazmanızı sağlar.

```css
@media (max-width: 768px) {
    body {
        font-size: 14px;
    }
}
```

Yukarıdaki örnek, ekran genişliği 768 pikselden küçük olduğunda yazı boyutunu 14 piksel olarak ayarlar.

---

## İpuçları

- CSS kodunuzu organize tutmak için mantıksal bir sıralama izleyin.
- Farklı tarayıcılar için uyumluluk sorunlarını kontrol edin.
- Tekrar eden stiller için CSS değişkenleri ve sınıfları kullanın.

---

## Kaynaklar

- [MDN Web Docs: CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3Schools: CSS](https://www.w3schools.com/css/)

Bu rehberi dikkatlice okuyarak CSS sözdizimiyle ilgili temel ve ileri düzey bilgileri öğrenebilirsiniz. Daha fazla pratik yaparak kendinizi geliştirin!
