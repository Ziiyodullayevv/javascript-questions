<div align="center">
  <img height="60" src="https://img.icons8.com/color/344/javascript.png">
  <h1>JavaScript Savollari (JavaScript Questions)</h1>
</div>

> [!NOTE]  
> Ushbu repozitoriy 2019-yilda yaratilgan bo'lib, bu yerdagi savollar o'sha davrdagi JavaScript sintaksisi va xulq-atvoriga asoslangan. JavaScript uzluksiz rivojlanib borayotgan til bo'lgani sababli, ba'zi yangi xususiyatlar bu yerdagi savollarda qamrab olinmagan bo'lishi mumkin.

---

<p align="center">
Boshlang'ich darajadan mukammalgacha: JavaScript bilimlaringizni sinab ko'ring, bilimlaringizni yangilang yoki texnik suhbatlarga tayyorlaning! :muscle: :rocket: Men ushbu repozitoriyni muntazam ravishda yangi savollar bilan boyitib boraman. Javoblarni savollar ostidagi **butilgan (collapsed) bo'limlarga** joylashtirganman, ularni ko'rish uchun shunchaki ustiga bosing. Omad yor bo'lsin! :heart:</p>

<p align="center">Menga murojaat qilishingiz mumkin! 😊</p>

<p align="center">
  <a href="https://www.instagram.com/theavocoder">Instagram</a> || <a href="https://www.twitter.com/lydiahallie">Twitter</a> || <a href="https://www.linkedin.com/in/lydia-hallie">LinkedIn</a> || <a href="https://www.lydiahallie.io/">Blog</a>
</p>

| Ularni o'z loyihalaringizda bemalol ishlatishingiz mumkin! 😃 Ushbu repozitoriyga havola bersangiz juda mamnun bo'lar edim. Savollar va tushuntirishlarni men yarataman, hamjamiyat esa uni saqlash va takomillashtirishda menga katta yordam beradi! 💪🏼 Rahmat va maroqli hordiq chiqaring! |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

<details><summary><strong> 21 ta Mavjud Tarjimalarni Ko'rish 🇸🇦🇪🇬🇧🇦🇩🇪🇪🇸🇫🇷🇮🇩🇯🇵🇰🇷🇳🇱🇧🇷🇷🇺🇹🇭🇹🇷🇺🇦🇻🇳🇨🇳🇹🇼🇽🇰🇺🇿</strong></summary>
<p>

- [🇸🇦 العربية](../ar-AR/README_AR.md)
- [🇪🇬 اللغة العامية](../ar-EG/README_ar-EG.md)
- [🇧🇦 Bosanski](../bs-BS/README-bs_BS.md)
- [🇩🇪 Deutsch](../de-DE/README.md)
- [🇪🇸 Español](../es-ES/README-ES.md)
- [🇫🇷 Français](../fr-FR/README_fr-FR.md)
- [🇮🇩 Indonesia](../id-ID/README.md)
- [🇮🇹 Italiano](../it-IT/README.md)
- [🇯🇵 日本語](../ja-JA/README-ja_JA.md)
- [🇰🇷 한국어](../ko-KR/README-ko_KR.md)
- [🇳🇱 Nederlands](../nl-NL/README.md)
- [🇵🇱 Polski](../pl-PL/README.md)
- [🇧🇷 Português Brasil](../pt-BR/README_pt_BR.md)
- [🇷o Română](../ro-RO/README.ro.md)
- [🇷🇺 Русский](../ru-RU/README.md)
- [🇽🇰 Shqip](../sq-KS/README_sq_KS.md)
- [🇹🇭 ไทย](../th-TH/README-th_TH.md)
- [🇹🇷 Türkçe](../tr-TR/README-tr_TR.md)
- [🇺🇦 Українська мова](../uk-UA/README.md)
- [🇺🇿 O'zbekcha](./README-uz_UZ.md)
- [🇻🇳 Tiếng Việt](../vi-VI/README-vi.md)
- [🇨🇳 简体中文](../zh-CN/README-zh_CN.md)
- [🇹🇼 繁體中文](../zh-TW/README_zh-TW.md)

</p>
</details>

---

###### 1. Natija qanday bo'ladi?

```javascript
function sayHi() {
  console.log(name);
  console.log(age);
  var name = 'Lydia';
  let age = 21;
}

sayHi();
```

- A: `Lydia` va `undefined`
- B: `Lydia` va `ReferenceError`
- C: `ReferenceError` va `21`
- D: `undefined` va `ReferenceError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: D

Funktsiya ichida biz avval `name` o'zgaruvchisini `var` kalit so me'yori orqali e'lon qilamiz. Bu shuni anglatadiki, o'zgaruvchi **hoisted** qilinadi (yaratish bosqichida xotiradan joy ajratiladi) va koding ijro chizig'i o'zgaruvchi qiymati berilgan joyga yetib bormaguncha ko'rsatuvchisi `undefined` bo'ladi. Biz `name` ni konsolga chiqarishga urinayotgan satrda uni hali qiymat bilan ta'minlamaganmiz, shuning uchun u `undefined` qiymatini saqlaydi.

`let` (va `const`) kalit so'zlari bilan e'lon qilingan o'zgaruvchilar ham hoist qilinadi, lekin `var`dan farqli o'laroq, ularga *initsializatsiya* (boshlang'ich qiymat) berilmaydi. Ular e'lon qilingan satrgacha ularga kirish imkonsiz. Bu holat **"Temporal Dead Zone"** (Vaqtinchalik o o'lik hudud) deb ataladi. Ular e'lon qilinishidan oldin o'zgaruvchilarga kirishga harakat qilganimizda, JavaScript `ReferenceError` xatosini tashlaydi.

</p>
</details>

---

###### 2. Natija qanday bo'ladi?

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}

for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}
```

- A: `0 1 2` va `0 1 2`
- B: `0 1 2` va `3 3 3`
- C: `3 3 3` va `0 1 2`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

JavaScript'dagi hodisalar navbati (event queue) sababli, `setTimeout` qayta chaqiruv (callback) funktsiyasi sikl to'liq bajarib bo'linganidan *keyin* chaqiriladi. Birinchi sikldagi `i` o'zgaruvchisi `var` kalit so'zi yordamida e'lon qilinganligi sababli, bu qiymat global bo'ladi. Sikl davomida biz unar `++` operatori yordamida `i` qiymatini har safar `1` ga oshirib borganmiz. `setTimeout` callback funktsiyasi chaqirilgan vaqtda, birinchi misoldagi `i` qiymati `3` ga teng bo'lib bo'lgan edi.

Ikkinchi siklda `i` o'zgaruvchisi `let` kalit so'zi yordamida e'lon qilingan: `let` (va `const`) bilan e'lon qilingan o'zgaruvchilar blok doirasiga (block-scoped) ega (blok - bu `{ }` qavslar orasidagi har qanday kod). Har bir iteratsiya davomida `i` yangi qiymatga ega bo'ladi va har bir qiymat sikl ichidagi o'zining alohida konyunkturasida (scope) saqlanib qoladi.

</p>
</details>

---

###### 3. Natija qanday bo'ladi?

```javascript
const shape = {
  radius: 10,
  diameter() {
    return this.radius * 2;
  },
  perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter());
console.log(shape.perimeter());
```

- A: `20` va `62.83185307179586`
- B: `20` va `NaN`
- C: `20` va `63`
- D: `NaN` and `63`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: B

E'tibor bering, `diameter` qiymati oddiy funktsiya, `perimeter` qiymati esa ko'rsatkichli (arrow) funktsiyadir.

Arrow funktsiyalarda `this` kalit so'zi oddiy funktsiyalardan farqli o'laroq, o'zi o me'yorida joylashgan tashqi qamrovga (surrounding scope) ishora qiladi! Bu shuni anglatadiki, biz `perimeter`ni chaqirganimizda, u `shape` ob'ektiga emas, balki uning tashqi qamroviga (masalan, `window` ob'ektiga) ishora qiladi.

Arrow funktsiya qamrovida `radius` qiymati mavjud bo'lmagani uchun, `this.radius` ifodasi `undefined` qaytaradi, bu esa `2 * Math.PI` ga ko'paytirilganda `NaN` natijasini beradi.

</p>
</details>

---

###### 4. Natija qanday bo'ladi?

```javascript
+true;
!'Lydia';
```

- A: `1` va `false`
- B: `false` va `NaN`
- C: `false` va `false`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

Unar plyus operatori operandni songa aylantirishga harakat qiladi. `true` - bu `1`, `false` esa `0`.

`'Lydia'` satri rost (truthy) qiymatdir. Biz aslida "Ushbu rost qiymat yolg'onmi?" deb so'ramoqdamiz. Bu `false` qaytaradi.

</p>
</details>

---

###### 5. Mantiqan qaysi biri to'g'ri?

```javascript
const bird = {
  size: 'small',
};

const mouse = {
  name: 'Mickey',
  small: true,
};
```

- A: `mouse.bird.size` haqiqiy emas (not valid)
- B: `mouse[bird.size]` haqiqiy emas
- C: `mouse[bird["size"]]` haqiqiy emas
- D: Hamma javoblar haqiqiy

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

JavaScript-da barcha ob'ekt kalitlari satr (string) hisoblanadi (Symbol bo'lmagan holatda). Biz ularni satr sifatida yozmasak ham, ular kapot ostida har doim satrga o'giriladi.

JavaScript ifodalarni izohlaydi va baholaydi. Qavs notatsiyasidan (`[]`) foydalanganimizda, u birinchi ochiluvchi `[` qavsni ko'radi va yopiluvchi `]` qavsni topguncha davom etadi. Shundan keyingina u qavs ichidagi ifodani hisoblaydi.

`mouse[bird.size]`: Dastlab u `bird.size` ni hisoblaydi va u `"small"` ga teng. `mouse["small"]` esa `true` qaytaradi.

Biroq, nuqta notatsiyasi bilan bunday bo'lmaydi. `mouse` ob'ektida `bird` degan kalit yo'q, ya'ni `mouse.bird` - `undefined` ga teng. Keyin biz nuqta notatsiyasi yordamida `size` ni so'raymiz: `mouse.bird.size`. `mouse.bird` - `undefined` bo'lgani uchun, biz aslida `undefined.size` ni so'rayapmiz. Bu noto'g'ri va `Cannot read property "size" of undefined` kabi xatolikni keltirib chiqaradi.

</p>
</details>

---

###### 6. Natija qanday bo'ladi?

```javascript
let c = { greeting: 'Hey!' };
let d;

d = c;
c.greeting = 'Hello';
console.log(d.greeting);
```

- A: `Hello`
- B: `Hey!`
- C: `undefined`
- D: `ReferenceError`
- E: `TypeError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

JavaScript-da barcha ob'ektlar bir-biriga tenglashtirilganda *havola (reference)* bo'yicha o'zaro ta'sir qiladi.

Birinchidan, `c` o'zgaruvchisi ob'ektga havolani saqlaydi. Keyinchalik, biz `d` ga `c` saqlayotgan o'sha ob'ekt havolasini tayinlaymiz.

<img src="https://i.imgur.com/ko5k0fs.png" width="200">

Bitta ob'ektni o'zgartirganingizda, siz barcha havolalar ko'rsatib turgan ob'ektni o'zgartirasiz.

</p>
</details>

---

###### 7. Natija qanday bo'ladi?

```javascript
let a = 3;
let b = new Number(3);
let c = 3;

console.log(a == b);
console.log(a === b);
console.log(b === c);
```

- A: `true` `false` `true`
- B: `false` `false` `true`
- C: `true` `false` `false`
- D: `false` `true` `true`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

`new Number()` - bu ichki funktsiya konstruktori. U songa o'xshab ko'rinsa-da, haqiqiy son emas: u ko'plab qo'shimcha xususiyatlarga ega va u ob'ektdir.

Biz `==` (tenglik) operatoridan foydalanganimizda, u faqat ularning bir xil *qiymatga* ega yoki yo me'yorida ekanligini checks qiladi. Ikkalasining ham qiymati `3` ga teng, shuning uchun u `true` qaytaradi.

Biroq, `===` (qat'iy tenglik) operatoridan foydalanganimizda, qiymat *va* tur bir xil bo'lishi kerak. Bizning holatda unday emas: `new Number()` son emas, u **ob'ekt**. Shuning uchun ikkinchi va uchinchi tengliklar `false` qaytaradi.

</p>
</details>

---

###### 8. Natija qanday bo'ladi?

```javascript
class Chameleon {
  static colorChange(newColor) {
    this.newColor = newColor;
    return this.newColor;
  }

  constructor({ newColor = 'green' } = {}) {
    this.newColor = newColor;
  }
}

const freddie = new Chameleon({ newColor: 'purple' });
console.log(freddie.colorChange('orange'));
```

- A: `orange`
- B: `purple`
- C: `green`
- D: `TypeError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: D

`colorChange` funktsiyasi statik (`static`) hisoblanadi. Statik metodlar faqat ular yaratilgan konstruktorda yashash uchun mo'ljallangan va ularni har qanday vorislarga o'tkazish yoki sinf nusxalari (instances) orqali chaqirish mumkin emas. `freddie` sinf nusxasi (instance) bo'lgani uchun, statik metodni u orqali chaqirib bo'lmaydi. Shuning uchun `TypeError` xatosi tashlanadi.

</p>
</details>

---

###### 9. Natija qanday bo me'yorda bo'ladi?

```javascript
let greeting;
greetign = {}; // Typo! (Imlo xatosi)
console.log(greetign);
```

- A: `{}`
- B: `ReferenceError: greetign is not defined`
- C: `undefined`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

U konsolga ob'ektni chiqaradi, chunki biz global ob'ektda shunchaki bo'sh ob'ekt yaratdik! Biz `greeting` so'zini adashib `greetign` deb yozganimizda, JS interpretatori buni quyidagicha ko'rdi:

1. Node.js'da `global.greetign = {}`
2. Brauzerlarda `window.greetign = {}`, `frames.greetign = {}` va `self.greetign`
3. Web worker'larda `self.greetign`
4. Barcha muhitlarda `globalThis.greetign`

Bunday holatning oldini olish uchun `"use strict"` (qat'iy rejim)dan foydalanishimiz mumkin. Bu o'zgaruvchiga qiymat berishdan oldin u e'lon qilinganligiga ishonch hosil qiladi.

</p>
</details>

---

###### 10. Buni qilganimizda nima sodir bo'ladi?

```javascript
function bark() {
  console.log('Woof!');
}

bark.animal = 'dog';
```

- A: Hech narsa, bu mutlaqo joyida!
- B: `SyntaxError`. Funktsiyaga bu tarzda xususiyat qo'shib bo'lmaydi.
- C: `"Woof"` konsolga chiqariladi.
- D: `ReferenceError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

Bu JavaScript-da mumkin, chunki funktsiyalar ob'ektdir! (Primitiv turlardan tashqari barcha narsa ob'ektdir).

Funktsiya - bu ob'ektning maxsus turi. Siz yozgan kodingiz haqiqiy funktsiyaning o me me'yori emas. Funktsiya xususiyatlarga ega ob'ektdir va ushbu xususiyat chaqiriluvchi (invocable) hisoblanadi.

</p>
</details>
