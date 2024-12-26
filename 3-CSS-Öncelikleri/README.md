# CSS Öncelik Sistemi Rehberi

Bu rehber, CSS (Cascading Style Sheets) öncelik sistemini detaylı bir şekilde açıklamaktadır. CSS öncelik sistemi, bir HTML elemanına birden fazla stil kuralı uygulandığında hangi kuralın geçerli olacağını belirler. CSS önceliklerini anlamak, stil çakışmalarını çözmek ve temiz bir kod yazmak için kritik öneme sahiptir.

---

## CSS Öncelik Sistemi Nedir?
CSS, bir eleman için tanımlanan birden fazla stil kuralını değerlendirirken bir "öncelik puanı" hesaplar. Bu öncelik puanına göre hangi stil kuralının uygulanacağına karar verir.

### Genel Öncelik Sırası
1. **Öncelikli Stil Kuralları:** `!important` ile tanımlanmış kurallar.
2. **Inline CSS:** Elemanın `style` özelliği içinde tanımlanmış stiller.
3. **ID Seçicileri:** `#id` ile belirtilen stiller.
4. **Class, Pseudo-class ve Attribute Seçicileri:** `.class`, `:hover`, `[type="text"]` gibi stiller.
5. **Eleman Seçicileri:** `div`, `p`, `h1` gibi HTML elemanlarını hedefleyen stiller.
6. **Genel Seçici:** `*` ile belirtilen stiller.

---

## Öncelik Puanı Hesaplama
Her bir seçici türüne bir puan atanır. Bu puanlar, stiller arasındaki önceliği belirlemek için kullanılır.

| Seçici Türü                  | Puan (Ağırlık)  |
|------------------------------|-----------------|
| Inline CSS                   | 1000            |
| ID Seçici (`#id`)            | 100             |
| Class, Pseudo-class (`.class`, `:hover`) | 10  |
| Eleman Seçicisi (`div`, `p`) | 1               |
| Evrensel Seçici (`*`)        | 0               |

### Örnek:
Bir eleman için şu kurallar tanımlanmış olsun:

```css
/* 1 puan */
div {
    color: black;
}

/* 10 puan */
.alert {
    color: blue;
}

/* 100 puan */
#header {
    color: green;
}
```
```html
/* 1000 puan */
<style>
    div {
        color: red;
    }
</style>
```
Bu durumda, stil kuralları arasındaki öncelik şu şekilde sıralanır:

1. Inline CSS (1000 puan): Kırmızı renk uygulanır.
2. ID Seçici (100 puan): Eğer inline CSS yoksa, yeşil renk uygulanır.
3. Class Seçici (10 puan): Eğer ID seçici yoksa, mavi renk uygulanır.
4. Eleman Seçici (1 puan): Eğer başka bir stil tanımlanmamışsa, siyah renk uygulanır.

---

## `!important` Deklarasyonu
CSS'de bir özelliği `!important` ile tanımlarsanız, bu kural tüm diğer kuralları geçersiz kılar.

### Kullanım:
```css
p {
    color: blue !important;
}
```
Eğer bir kural `!important` ile tanımlanmışsa, öncelik sıralamasına bakılmaksızın uygulanır. Ancak `!important` kullanımı dikkatli yapılmalıdır, çünkü:
- Kodun bakımını zorlaştırır.
- Normal öncelik sırasını bozar.

### Örnek:
```css
p {
    color: red !important;
}
#para {
    color: green;
}
```
Yukarıdaki durumda, `<p id="para">` elemanı kırmızı renk alır.

---

## Özel Durumlar

### Daha Spesifik Seçiciler
Seçici ne kadar spesifikse, öncelik sıralamasında o kadar üstte yer alır.

#### Örnek:
```css
/* Daha az spesifik */
div {
    background-color: yellow;
}

/* Daha spesifik */
div.alert {
    background-color: orange;
}
```
Bu durumda, `class="alert"` özelliğine sahip bir `<div>` elemanı turuncu arka plana sahip olur.

### Daha Sonra Yazılan Kurallar
Eğer seçicilerin öncelik puanları aynıysa, CSS dosyasında daha sonra yazılan kural geçerli olur.

#### Örnek:
```css
h1 {
    font-size: 18px;
}
h1 {
    font-size: 24px;
}
```
Bu durumda, `<h1>` elemanı 24 piksel boyutunda görünür.

---

## Özet
CSS öncelik sistemi, stil kuralları arasında bir düzen sağlar ve çakışmaları çözer. Öncelik sistemini anlamak için şunlara dikkat edin:

1. **Seçici Türlerine Göre Öncelik:** ID > Class > Eleman > Evrensel.
2. **Spesifiklik:** Daha spesifik kurallar daha genel kuralları geçersiz kılar.
3. **`!important` Kullanımı:** Son çare olarak tercih edin.
4. **Sıralama:** Aynı öncelik puanına sahip kurallarda, daha sonra yazılan uygulanır.

---

## İpuçları
- Fazla `!important` kullanmaktan kaçının.
- Daha spesifik kurallar tanımlayarak önceliği kontrol edin.
- Karmaşıklığı azaltmak için ID yerine Class kullanmayı tercih edin.

---

## Kaynaklar
- [MDN Web Docs: CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [W3Schools: CSS Priority](https://www.w3schools.com/css/css_specificity.asp)

Bu rehberi inceleyerek CSS öncelik sistemini daha iyi anlayabilir ve stil kurallarınızı etkili bir şekilde yönetebilirsiniz!
