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
---

###### 11. Natija qanday bo'ladi?

```javascript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}

const member = new Person('Lydia', 'Hallie');
Person.getFullName = function() {
  return `${this.firstName} ${this.lastName}`;
};

console.log(member.getFullName());
```

- A: `TypeError`
- B: `SyntaxError`
- C: `Lydia Hallie`
- D: `undefined` `undefined`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

JavaScript-da funktsiyalar ob'ektdir, shuning uchun `getFullName` metodi funktsiya-konstruktor ob'ektining o'ziga qo'shiladi. Shu sababli biz `Person.getFullName()` ni chaqirishimiz mumkin, lekin `member.getFullName()` chaqirilsa `TypeError` xatosi tashlanadi.

Agar biror metod ob'ektning barcha nusxalari (instances) uchun mavjud bo'lishini xohlasangiz, uniy prototip (`prototype`) xususiyatiga qo'shishingiz kerak:

```js
Person.prototype.getFullName = function() {
  return `${this.firstName} ${this.lastName}`;
};
```

</p>
</details>

---

###### 12. Natija qanday bo'ladi?

```javascript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}

const lydia = new Person('Lydia', 'Hallie');
const sarah = Person('Sarah', 'Smith');

console.log(lydia);
console.log(sarah);
```

- A: `Person {firstName: "Lydia", lastName: "Hallie"}` va `undefined`
- B: `Person {firstName: "Lydia", lastName: "Hallie"}` va `Person {firstName: "Sarah", lastName: "Smith"}`
- C: `Person {firstName: "Lydia", lastName: "Hallie"}` va `{}`
- D: `Person {firstName: "Lydia", lastName: "Hallie"}` va `ReferenceError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

`sarah` uchun biz `new` kalit so'zidan foydalanmadik. `new` ishlatilganda, `this` biz yaratgan yangi bo'sh ob'ektga ishora qiladi. Biroq, agar `new` qo'shmasangiz, `this` **global ob'ekt**ga ishora qiladi!

Biz `this.firstName` ni `"Sarah"` ga va `this.lastName` ni `"Smith"` ga teng deb aytdik. Biz aslida `global.firstName = 'Sarah'` va `global.lastName = 'Smith'` ni belgilab qo'ydik. `sarah`ning o'zi esa `undefined` bo'lib qoladi, chunki biz `Person` funktsiyasidan hech qanday qiymat qaytarmaymiz.

</p>
</details>

---

###### 13. Hodisalarning tarqalishi (event propagation)ning 3 ta bosqichi qaysilar?

- A: Target > Capturing > Bubbling
- B: Bubbling > Target > Capturing
- C: Target > Bubbling > Capturing
- D: Capturing > Target > Bubbling

<details><summary><b>Javob</b></summary>
<p>

#### Javob: D

**Capturing** (Tutilish) bosqichida hodisa ajdod elementlar orqali nishon (target) elementgacha tushib boradi. So'ngra u **target** (nishon) elementga yetib boradi va **bubbling** (ko'piklanish/yuqoriga ko'tarilish) bosqichi boshlanadi.

<img src="https://i.imgur.com/N18oRgd.png" width="200">

</p>
</details>

---

###### 14. Barcha ob'ektlar prototipga ega.

- A: rost (true)
- B: yolg'on (false)

<details><summary><b>Javob</b></summary>
<p>

#### Javob: B

**Baza ob'ekt (base object)**dan tashqari barcha ob me'yori ob'ektlar prototipga ega. Baza ob'ekt - bu foydalanuvchi tomonidan yaratilgan yoki `new` kalit so'zi yordamida yaratilgan ob'ekt. Baza ob'ekt `.toString` kabi ba'zi metod va xususiyatlarga kirish imkoniga ega. Shuning uchun siz JavaScript-ning ichki metodlaridan foydalanishingiz mumkin! Bunday metodlarning barchasi prototipda mavjud. JavaScript metodni to'g'ridan-to me'yori ob'ektda topa olmasa ham, u prototiplar zanjiri (prototype chain) bo'ylab pastga tushadi va uni o'sha yerdan topadi.

</p>
</details>

---

###### 15. Natija qanday bo'ladi?

```javascript
function sum(a, b) {
  return a + b;
}

sum(1, '2');
```

- A: `NaN`
- B: `TypeError`
- C: `"12"`
- D: `3`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

JavaScript **dinamik tiplangan til**dir: biz o'zgaruvchilarning tiplarini belgilamaymiz. Qiymatlar siz bilmagan holda avtopilotda boshqa tipga o'girilishi mumkin, bu **yashirin tiplarni o'g'irish (implicit type coercion)** deb ataladi. **Coercion** - bu bir tipdan boshqasiga o'girishdir.

Ushbu misolda, funktsiya mantiqan to'g'ri ishlashi va qiymat qaytarishi uchun JavaScript `1` sonini satrga (string) o'g'iradi. Sonli tip (`1`) va satrli tip (`'2'`) qo'shilayotganda, son satr sifatida ko'riladi. Biz satrlarni `"Hello" + "World"` kabi birhtirishimiz mumkin, shuning uchun bu yerda `"1" + "2"` sodir bo'ladi va `"12"` qaytaradi.

</p>
</details>

---

###### 16. Natija qanday bo'ladi?

```javascript
let number = 0;
console.log(number++);
console.log(++number);
console.log(number);
```

- A: `1` `1` `2`
- B: `1` `2` `2`
- C: `0` `2` `2`
- D: `0` `1` `2`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

**Postfiks** unar `++` operatori:
1. Qiymatni qaytaradi (bu `0` qaytaradi)
2. Qiymatni oshiradi (son endi `1` ga teng)

**Prefiks** unar `++` operatori:
1. Qiymatni oshiradi (son endi `2` ga teng)
2. Qiymatni qaytaradi (bu `2` qaytaradi)

Natijada `0 2 2` chiqadi.

</p>
</details>

---

###### 17. Natija qanday bo'ladi?

```javascript
function getPersonInfo(one, two, three) {
  console.log(one);
  console.log(two);
  console.log(three);
}

const person = 'Lydia';
const age = 21;

getPersonInfo`${person} is ${age} years old`;
```

- A: `"Lydia"` `21` `["", " is ", " years old"]`
- B: `["", " is ", " years old"]` `"Lydia"` `21`
- C: `"Lydia"` `["", " is ", " years old"]` `21`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: B

Siz **tagged template literals** (teglangan shablon satrlari)dan foydalansangiz, birinchi argumentning qiymati har doim satr qiymatlari massivi bo'ladi. Qolgan argumentlar esa uzatilgan ifodalarning qiymatlarini oladi!

</p>
</details>

---

###### 18. Natija qanday bo'ladi?

```javascript
function checkAge(data) {
  if (data === { age: 18 }) {
    console.log('You are an adult!');
  } else if (data == { age: 18 }) {
    console.log('You are still an adult.');
  } else {
    console.log(`Hmm.. You don't have an age I guess`);
  }
}

checkAge({ age: 18 });
```

- A: `You are an adult!`
- B: `You are still an adult.`
- C: `Hmm.. You don't have an age I guess`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

Tenglikni tekshirayotganda, primitivlar ularning *qiymati* bo'yicha taqqoslanadi, ob'ektlar esa ularning *havolasi (reference)* bo'yicha taqqoslanadi. JavaScript ob'ektlar xotiradagi bir xil joyga havola ko'rsatayotganini tekshiradi.

Biz taqqoslayotgan ikkita ob'ektda unday emas: parametr sifatida uzatilgan ob'ekt tenglikni tekshirish uchun ishlatgan ob'ektimizdan xotirada boshqa joyga ishora qiladi.

Shu sababli `{ age: 18 } === { age: 18 }` va `{ age: 18 } == { age: 18 }` ikkalasi ham `false` qaytaradi.

</p>
</details>

---

###### 19. Natija qanday bo'ladi?

```javascript
function getAge(...args) {
  console.log(typeof args);
}

getAge(21);
```

- A: `"number"`
- B: `"array"`
- C: `"object"`
- D: `"NaN"`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

Rest parametri (`...args`) bizga barcha qolgan argumentlarni massivga "yig'ish" imkonini beradi. Massiv bu ob'ektdir, shuning uchun `typeof args` `"object"` qaytaradi.

</p>
</details>

---

###### 20. Natija qanday bo'ladi?

```javascript
function getAge() {
  'use strict';
  age = 21;
  console.log(age);
}

getAge();
```

- A: `21`
- B: `undefined`
- C: `ReferenceError`
- D: `TypeError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

`"use strict"` yordamida adashib global o'zgaruvchilar e'lon qilib qo'ymasligingizga ishonch hosil qilishingiz mumkin. Biz hech qachon `age` o'zgaruvchisini e'lon qilmaganmiz va `"use strict"` ishlatganimiz uchun u `ReferenceError` tashlaydi. Agar `"use strict"` ishlatmaganimizda edi, u ishlagan bo'lardi, chunki `age` xususiyati global ob'ektga qo'shilgan bo'lardi.

</p>
</details>

---

###### 21. `sum` qiymati nimaga teng bo'ladi?

```javascript
const sum = eval('10*10+5');
```

- A: `105`
- B: `"105"`
- C: `TypeError`
- D: `"10*10+5"`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: A

`eval` satr sifatida uzatilgan kodni hisoblaydi va bajaradi. Agar u ushbu holatdagidek ifoda bo'lsa, u ifodani hisoblaydi. `10 * 10 + 5` ifodasi `105` sonini qaytaradi.

</p>
</details>

---

###### 22. `cool_secret` qancha vaqt davomida foydalanish mumkin bo'ladi?

```javascript
sessionStorage.setItem('cool_secret', 123);
```

- A: Abadiy, ma'lumotlar yo'qolmaydi.
- B: Foydalanuvchi ilovani/vkladkani (tab) yopganigacha.
- C: Foydalanuvchi nafaqat vkladkani, balki butun brauzerni yopganigacha.
- D: Foydalanuvchi kompyuterni o'chirganigacha.

<details><summary><b>Javob</b></summary>
<p>

#### Javob: B

`sessionStorage`da saqlangan ma'lumotlar *vkladka (tab)* yopilgandan keyin o'chirib tashlanadi.

Agar siz `localStorage`dan foydalanganingizda edi, ma'lumotlar masalan `localStorage.clear()` chaqirilmaguncha abadiy u yerda saqlanib qolardi.

</p>
</details>

---

###### 23. Natija qanday bo'ladi?

```javascript
var num = 8;
var num = 10;

console.log(num);
```

- A: `8`
- B: `10`
- C: `SyntaxError`
- D: `ReferenceError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: B

`var` kalit so'zi bilan siz bir xil nomli bir nechta o'zgaruvchilarni e'lon qilishingiz mumkin. O'zgaruvchi keyin oxirgi tayinlangan qiymatni saqlab qoladi.

Siz buni `let` yoki `const` bilan qila olmaysiz, chunki ular blok doirasiga ega va shuning uchun qayta e'lon qilinishi mumkin emas.

</p>
</details>

---

###### 24. Natija qanday bo'ladi?

```javascript
const obj = { 1: 'a', 2: 'b', 3: 'c' };
const set = new Set([1, 2, 3, 4, 5]);

obj.hasOwnProperty('1');
obj.hasOwnProperty(1);
set.has('1');
set.has(1);
```

- A: `false` `true` `false` `true`
- B: `false` `true` `true` `true`
- C: `true` `true` `false` `true`
- D: `true` `true` `true` `true`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

Barcha ob'ekt kalitlari (Symbol'lardan tashqari) o'zingiz satr sifatida yozmasangiz ham kapot ostida satrlardir. Shuning uchun `obj.hasOwnProperty('1')` ham true qaytaradi.

Set uchun bu tarzda ishlamaydi. Bizning setda `'1'` (satr) yo'q: `set.has('1')` `false` qaytaradi. Unda sonli `1` tipi bor, `set.has(1)` `true` qaytaradi.

</p>
</details>

---

###### 25. Natija qanday bo'ladi?

```javascript
const obj = { a: 'one', b: 'two', a: 'three' };
console.log(obj);
```

- A: `{ a: "one", b: "two" }`
- B: `{ b: "two", a: "three" }`
- C: `{ a: "three", b: "two" }`
- D: `SyntaxError`

<details><summary><b>Javob</b></summary>
<p>

#### Javob: C

Agar bir xil nomli ikkita kalit bo'lsa, kalit ustidan qayta yoziladi. Uninig o'rni saqlanib qoladi, lekin qiymati oxirgi ko'rsatilgan qiymat bo'ladi.

</p>
</details>
