# Program Structure

{{quote {author: "_why", title: "Why's (Poignant) Guide to Ruby", chapter: true}

Va mening yuragim shaffof terim ostida yorqin qizil porlaydi va ular meni hayotga qaytib kelishim uchun 10ml JavaScript-ni taqdim etishlari kerak bo'ladi. (Men qondagi toksinlarga chidamliman.) Do'stim, bu narsa juda kuchli.

quote}}

{{index why, "Poignant Guide"}}

{{figure {url: "img/chapter_picture_2.jpg", alt: "Picture of tentacles holding objects", chapter: framed}}}

Ushbu bobda biz aslida _dasturlash_ deb atalishi mumkin bo'lgan narsalarni qilishni boshlaymiz. Biz JavaScript tilidagi buyruqlarimizni kengaytiramiz va hozirgacha ko‘rgan ot va gap bo‘laklaridan tashqari,
mazmunli matnlarni ifodalay oladigan darajaga ko'tarilamiz.

## Ifodalar and bayonotlar

{{index grammar, [syntax, expression], [code, "structure of"], grammar, [JavaScript, syntax]}}

[1-Bob](values) da biz qiymatlar yaratdik va yangi qiymatlarni olish uchun ularga operatorlar qoʻlladik. Bu kabi qiymatlarni yaratish har qanday JavaScript dasturining asosiy mazmunidir. Ammo bu tuzilma foydali bo'lishi uchun kattaroq tuzilishga ega bo'lishi kerak. Shunday qilib, biz keyingi mavzuni ko'rib chiqamiz.

{{index "literal expression", [parentheses, expression]}}

Qiymat hosil qiluvchi kod bo'lagi _((ifoda(expression)))_ deb ataladi. To'g'ridan-to'g'ri yozilgan har bir qiymat (masalan, "22" yoki "psixoanaliz") ifodadir. Qavslar orasidagi ifoda ham ikkita ifodaga qo'llaniladigan (
(binary operator)) yoki biriga qo'llaniladigan ((unary operator)) kabi ifodadir.

{{index [nesting, "of expressions"], "human language"}}

Bu tilga asoslangan interfeys go'zalligining bir qismini ko'rsatadi. Ifodalar inson tillaridagi ergash gaplar qanday joylashtirilganiga o'xshash holda boshqa iboralarni o'z ichiga olishi mumkin - ergash gap o'z bo'laklarini o'z ichiga olishi mumkin va hokazo. Bu bizga o'z xohishlarimiz asosida murakkab hisob-kitoblarni tavsiflovchi ifodalarni yaratish imkonini beradi.

{{index statement, semicolon, program}}

Agar ifoda gap bo'lagiga mos kelsa, JavaScript _bayonoti_ to'liq gapga to'g'ri keladi. Dastur bo'lsa, bayonotlar yig'indisidir.

{{index [syntax, statement]}}

Eng oddiy bayonot turi o'zidan keyin nuqta-vergul qo'yilgan ifodadir. Bu dastur:

```
1;
!false;
```

Biroq, bu hech qanday foyda keltirmaydigan dastur. ((Ifoda)) faqat qiymat hosil qilishdan iborat bo'lishi mumkin, keyinchalik u qo'shimcha kod tomonidan ishlatilishi mumkin. ((Bayonot)) o'zi mustaqil tuzilishga ega, va u tashqi ta'sirga ega bo'lgan "biror narsa" sifatida tan olinishi mumkin. U ekranda dunyoni o'zgartiruvchi narsani ko'rsatishi yoki mashinaning ichki holatini keyingi tasdiqlarga ta'sir qiladigan tarzda o'zgartirishi mumkin. Bu o'zgarishlar _((salbiy ta'sir))_ deb ataladi. Avvalgi misoldagi iboralar shunchaki “1” va “true” qiymatlarini hosil qiladi va keyin ularni darhol xotiradan o'chirib yuboradi. Bu hech qanday tashqi taassurot qoldirmaydi. Ushbu dasturni ishga tushirganingizda, e'tiborli hech narsa kuzatilmaydi.

{{index "programming style", "automatic semicolon insertion", semicolon}}

Ba'zi hollarda JavaScript bayonot oxiridagi nuqtali vergulni tushurib qoldirishga  ruhsat beradi. Boshqa hollarda bo'lsa uning tushurub qoldirilishi keyingi qatorni ham ayni shu bayonotning bir qismi sifatida ko'rib chiqilishiga sabab bo'ladi. Nuqtali vergul qachon xavfsiz tarzda tushirib qoldirilishi mumkinligi haqidagi qoidalar biroz murakkab va xatolarga moyil. Shunday qilib, bu kitobda nuqtali vergul kerak bo'lgan har bir bayonot doimo nuqtali vergul bilan yozilishi shart. Men sizga ham ularni xuddi shunday yozishingizni tavsiya qilaman, hech bo'lmaganda, tushurib qoldiriluvchi nuqtali vergullarning nozik jihatlari haqida ko'proq ma'lumotga ega bo'lmaguningizcha.

## Bog'lovchilar

{{indexsee variable, binding}}
{{index [syntax, statement], [binding, definition], "side effect", [memory, organization], [state, in binding]}}

Qanday qilib dastur ichki holatni saqlaydi? U ma'lumotlarni qanday eslab qoladi? Biz eski qiymatlardan qanday qilib yangi qiymatlarni ishlab chiqarilishini ko'rdik, lekin bu eski qiymatlarni o'zgartirmaydi va yangi qiymat darhol ishlatilishi kerak yoki u yana o'chib ketadi. Qiymatlarni saqlash va ushlab turish uchun JavaScript _binding_ yoki _variable(o'zgaruvchi)_ deb nomlangan tushunchani taqdim etadi:

```
let caught = 5 * 5;
```

{{index "let keyword"}}

Bu bayonotning ikkinchi ko'rinishidir. Maxsus (_((kalit so'z))_) `let` bu jumla bog'lanishni belgilashini bildiradi. Undan keyin bog‘lanish nomi va agar unga darhol qiymat berishni istasak, `=` operatori va ifoda keladi.

Oldingi ibora "caught" deb nomlangan bog'lashni yaratadi va undan 5 ni 5 ga ko'paytirish orqali hosil bo'lgan raqamni ushlab turish uchun foydalanadi.

Bog'lanish aniqlangandan so'ng, uning nomi ((ifoda)) sifatida ishlatilishi mumkin. Bunday iboraning qiymati hozirda bog'lanishning qiymati deb hisoblanadi. Mana bir misol:

```
let ten = 10;
console.log(ten * ten);
// → 100
```

{{index "= operator", assignment, [binding, assignment]}}

Agar bog'lanish qiymatga ishora qilsa, bu uning ushbu qiymatga abadiy bog'langanligini anglatmaydi. `=` operatori istalgan vaqtda mavjud bogʻlanishlarda ularni joriy qiymatidan uzib qoʻyish va yangisiga ishora qilish uchun ishlatilishi mumkin.

```
let mood = "light";
console.log(mood);
// → light
mood = "dark";
console.log(mood);
// → dark
```

{{index [binding, "model of"], "tentacle (analogy)"}}

Bog'lanishlarni qutilar emas, balki uychalar sifatida tasavvur qilish to'g'riroq bo'ladi. Ular qiymatlarni o'z ichiga olmaydi, aksincha  _ushlab turadi_ - ikkita bog'lanish bir xil qiymatga murojaat qilishi mumkin. Dastur faqat havola qilingan qiymatlarga kirishi mumkin. Biror narsani eslab qolish kerak bo'lganda, siz uni ushlab turish uchun uycha yaratasiz yoki mavjud uychalaringizdan birini unga qayta bog'laysiz.

Keling, yana bir misolni ko'rib chiqaylik. Luiji sizga hali ham qarzdor bo'lgan pul miqdorini eslab qolish uchun siz bog'lanish yaratasiz. Va keyin u 35 dollar to'laganida, siz bu bog'lanishga yangi qiymat berasiz.

```
let luigisDebt = 140;
luigisDebt = luigisDebt - 35;
console.log(luigisDebt);
// → 105
```

{{index undefined}}

Bog'lanishni unga qiymat bermasdan aniqlaganingizda, uychalar hech qanday tushunchaga ega emas va bo'sh bo'ladi. Agar siz boʻsh bogʻlanish qiymatini soʻrasangiz, “undefined” qiymatini olasiz.

{{index "let keyword"}}

Bitta "let" iborasi bir nechta bog'lanishlarni belgilashi mumkin. Ta'riflar vergul bilan ajratilishi kerak.

```
let one = 1, two = 2;
console.log(one + two);
// → 3
```

"Var" va "const" so'zlari "let" ga o'xshash tarzda bog'lanishlarni yaratish uchun ham ishlatilishi mumkin.

```
var name = "Ayda";
const greeting = "Hello ";
console.log(greeting + name);
// → Hello Ayda
```

{{index "var keyword"}}

Avvalo, “var” ("variable" - o'zgaruvchi so'zining qisqartmasi), 2015-yildan oldingi JavaScript-da bogʻlanishlar eʼlon qilingan usuldir. Men [keyingi bobda](functions) `let`- dan farqli bo'lgan tomonlari haqida kengroq so'z yuritaman. Hozircha, esda tutingki, u asosan bir xil ishni bajaradi, lekin biz uni bu kitobda kamdan-kam ishlatamiz, chunki u ba'zi chalkashliklarga ega.

{{index "const keyword", naming}}

"Const" so'zi _(( constant - doimiy))_ ma'nosini bildiradi. U doimiy bog'lanishni belgilaydi, u umri davomida bir xil qiymatga ishora qiladi. Bu qiymatga nom beradigan bog'lashlar uchun foydali bo'lib, keyinchalik unga osongina murojaat qilishingiz mumkin.

## Bog'lovchi nomlari

{{index "underscore character", "dollar sign", [binding, naming]}}

Bog'lovchi nomlar har qanday so'z bo'lishi, raqamlar bog'lovchi nomning bir qismini tashkil etishi mumkin, masalan,  `catch22` to'g'ri nom, ekin nom raqam bilan boshlanmasligi kerak. Bog'lovchi nomi dollar belgisi (`$`) yoki pastki chiziqni (`_`) o'z ichiga olishi mumkin, lekin boshqa tinish belgilari yoki maxsus belgilardan foydalanish mumkin emas.

{{index [syntax, identifier], "implements (reserved word)", "interface (reserved word)", "package (reserved word)", "private (reserved word)", "protected (reserved word)", "public (reserved word)", "static (reserved word)", "void operator", "yield (reserved word)", "enum (reserved word)", "reserved word", [binding, naming]}}

“Let” kabi maxsus maʼnoga ega soʻzlar _((kalit soʻz))_ boʻlib, ularni bogʻlovchi nom sifatida ishlatib boʻlmaydi. JavaScript-ning ((kelgusi)) versiyalarida “foydalanish uchun band qilingan” bir qancha soʻzlar ham mavjud boʻlib, ularni bogʻlovchi nom sifatida ham ishlatib boʻlmaydi. Kalit so'zlar va band qilingan so'zlarning to'liq ro'yxati ancha uzun.

```{lang: "text/plain"}
break case catch class const continue debugger default delete do else enum export extends false finally for function if implements import interface in instanceof let new package private protected public return static super swtich this throw true try typeof var void  while with yield
```

{{index [syntax, error]}}

Ushbu ro'yhatni eslab qolish haqida qayg'urmasangiz ham bo'ladi. Bog'lanishlar yaratish paytida agar band qilingan so'zlardan foydalansangiz sintaktik xato(syntax error) yuzaga keladi va band qilingan so'zdan foydalanganingiz haqida ogohlantiradi


## Muhit

{{index "standard environment", [browser, environment]}}

Bog'lanishlar va ma'lum vaqt davomida ularga berilgan qiymatlar yig'indisi _(muhit - environment)_ deb ataladi. Dastur ishga tushgan vaqtda bu muhit bo'sh bo'lmaydi. U har doim tilning bir qismi bo'lgan ((standart)) bog'lanishlarni o'z ichiga oladi va ko'pincha u atrofdagi tizim bilan o'zaro ta'sir qilish usullarini ta'minlovchi bog'lanishlarga ega. Misol uchun, brauzerda hozirda yuklangan veb-sayt bilan o'zaro ishlash va ((sichqoncha)) va ((klaviatura)) orqali kiritilgan ma'lumot va buyruqlarni o'qish uchun funktsiyalar mavjud.

## Funksiyalar

{{indexsee "application (of functions)", [function, application]}}
{{indexsee "invoking (of functions)", [function, application]}}
{{indexsee "calling (of functions)", [function, application]}}
{{index output, function, [function, application], [browser, environment]}}

Standart muhitda taqdim etilgan ko'pgina qiymatlar _((funktsiya))_ turiga ega. Funktsiya - bu qiymatga o'ralgan dasturning bir qismi. Bunday qiymatlar o'ralgan dasturni ishga tushirish uchun _qo'llanilishi_ mumkin. Misol uchun, brauzer muhitida bog'lovchi `prompt`(so'rov) foydalanuvchi ma'lumot kiritishini so'rab ((muloqot oynasi))ni ko'rsatadigan funktsiyaga ega. U shunday ishlatiladi:

```
prompt("Enter passcode");
```

{{figure {url: "img/prompt.png", alt: "A prompt dialog", width: "8cm"}}}

{{index parameter, [function, application], [parentheses, arguments]}}

Funktsiyani bajarish _uyg'otish(invoking)_, _chaqirish(calling)_ yoki _qo'llash(applying)_ deb ataladi. Funktsiya qiymatini hosil qiluvchi ifodadan keyin qavslar qo'yish orqali funktsiyani chaqirishingiz mumkin. Odatda siz to'g'ridan-to'g'ri funktsiyaga ega bo'lgan bog'lash nomidan foydalanasiz. Qavslar orasidagi qiymatlar funksiya ichidagi dasturga beriladi. Misolda, "prompt" funksiyasi muloqot oynasida ko'rsatish uchun matn sifatida biz beradigan satrdan foydalanadi. Funksiyalarga berilgan qiymatlar _((argument))s_ deyiladi. Turli funktsiyalar uchun boshqa raqam yoki turli turdagi argumentlar kerak bo'lishi mumkin.

“Prompt” funksiyasi zamonaviy veb-dasturlashda unchalik qo'llanilmaydi, chunki siz natijada paydo bo'lgan muloqotning ko'rinishini nazorat qila olmaysiz, lekin u mashq uchun dasturlar va tajribalarda foydali bo'lishi mumkin.

## console.log funksiyasi

{{index "JavaScript console", "developer tools", "Node.js", "console.log", output, [browser, environment]}}

Misollarda men qiymatlarni chiqarish uchun "console.log" dan foydalandim. Ko'pgina JavaScript tizimlari (shu jumladan, barcha zamonaviy veb-brauzerlar va Node.js) o'z argumentlarini _ba'zi_ matn chiqarish qurilmasiga yozadigan "console.log" funksiyasini ta'minlaydi. Brauzerlarda chiqish ((JavaScript konsoli)) ga tushadi. Brauzer interfeysining bu qismi boshlang'ich holatda yashirin, lekin ko'pchilik brauzerlar uni F12 tugmachasini bosganingizda yoki Mac-da [command] {keyname}-[option]{keyname}-I tugmachasini bosganingizda ochadi. Agar bu ishlamasa, menyular orqali Dasturchi vositalari(Developer Tools) yoki shunga o'xshash narsalarni qidirish orqali topishingiz mumkin.

{{if interactive

Ushbu kitob sahifalarida misollar (yoki o'z kodingiz) ishga tushganda, brauzerning JavaScript konsolida emas, misoldan keyin `console.log` chiqishi ko'rsatiladi.

```
let x = 30;
console.log("the value of x is", x);
// → the value of x is 30
```

if}}

{{index [object, property], [property, access]}}

Bog'lovchi nomlar ((davr belgisi))dan foydalana olmaydi lekin `console.log`da buning imkoni bor. Buning sababi, "console.log" oddiy bog'lash emas. Bu, aslida, "konsol" ulanishi tomonidan ushlab turilgan qiymatdan "log" xususiyatini oladigan iboradir. Bu nimani anglatishini biz [4-bob](data#properties)da bilib olamiz.

{{id return_values}}
## Return (qaytariluvchi) qiymatlar

{{index [comparison, "of numbers"], "return value", "Math.max function", maximum}}

Muloqot oynasini ko'rsatish yoki ekranga matn yozish _((uning ta'siri))_ hisoblanadi. Ko'pgina funktsiyalar ular ishlab chiqaradigan ta'sirlar tufayli foydalidir. Funktsiyalar qiymatlarni ham ishlab chiqishi mumkin, bu holda foydali bo'lishi uchun ular qo'shimcha ta'sirga ega bo'lishi shart emas. Masalan, “Math.max” funksiyasi istalgan miqdordagi son argumentlarini oladi va eng kattasini qaytaradi..

```
console.log(Math.max(2, 4));
// → 4
```

{{index [function, application], minimum, "Math.min function"}}

Funktsiya qiymat hosil qilganda, bu qiymatni _qaytaradi_ deb aytiladi. Qiymat yaratadigan har qanday narsa JavaScript-da ((ifoda)), ya'ni funksiya chaqiruvlaridan kattaroq ifodalarda foydalanish mumkin. Bu yerda “Math.max” ga qarama-qarshi boʻlgan “Math.min” chaqiruvi qo'shish ifodasining bir qismi sifatida ishlatilgan:

```
console.log(Math.min(2, 4) + 100);
// → 102
```

[Keyingi bob](functions) o'z funksiyalaringizni qanday yozishni tushuntiradi.

## NAzorat oqimi

{{index "execution order", program, "control flow"}}

Agar dasturingiz bir nechta ((bayonot))ni o'z ichiga olgan bo'lsa, bayonotlar xuddi hikoya kabi, yuqoridan pastga qarab bajariladi. Ushbu misol dasturda ikkita bayonot mavjud. Birinchisi foydalanuvchidan raqamni so'raydi va keyingisi ushbu raqamning ((kvadrat))ini ko'rsatadi.

```
let theNumber = Number(prompt("Pick a number"));
console.log("Your number is the square root of " +
            theNumber * theNumber);
```

{{index [number, "conversion to"], "type coercion", "Number function", "String function", "Boolean function", [Boolean, "conversion to"]}}

“Number” funksiyasi qiymatni raqamga aylantiradi. Bizga bu konvertatsiya kerak, chunki “prompt” natijasi satr qiymati lekin biz raqamli qiymatni xohlaymiz. Qiymatlarni shu turlarga o'zgartiruvchi "String" va "Boolean" deb nomlangan va shunga o'xshash funksiyalar mavjud.

To'g'ri chiziqli boshqaruv oqimining  sxematik ko'rinishi:

{{figure {url: "img/controlflow-straight.svg", alt: "Trivial control flow", width: "4cm"}}}

## Shartli bajarish

{{index Boolean, ["control flow", conditional]}}

Hamma dasturlar ham to'g'ri oqim bo'ylab amalga oshavermaydi. Biz, masalan, dastur mavjud vaziyatdan kelib chiqib, tegishli bo'limni oladigan tarmoqli yo'lni yaratmoqchi bo'lishimiz mumkin. Bunga _((shartli bajarish))_ deyiladi.

{{figure {url: "img/controlflow-if.svg", alt: "Conditional control flow",width: "4cm"}}}

{{index [syntax, statement], "Number function", "if keyword"}}

Shartli bajarish JavaScript-da `if` kalit so`zi bilan yaratiladi. Oddiy holatda, biz ma'lum bir shart bajarilgan taqdirdagina ba'zi kodlar bajarilishini xohlaymiz. Biz, masalan, kiritilgan raqamning kvadratini ko'rsatishni xohlaymiz, _agar_ kiritilgan ma'lumot raqam bo'lsa.

```{test: wrap}
let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
  console.log("Your number is the square root of " +
              theNumber * theNumber);
}
```

Ushbu modifikatsiya bilan, agar siz "to'tiqush" ko'rinishida ma'lumot kiritsangiz, hech qanday natija ko'rsatilmaydi.

{{index [parentheses, statement]}}

`if` kalit so'zi mantiqiy ifoda qiymatiga qarab bayonotni bajaradi yoki o`tkazib yuboradi. Hal qiluvchi ifoda kalit so‘zdan so‘ng, qavslar orasiga, so‘ngra bajariladigan bayonot yoziladi.

{{index "Number.isNaN function"}}

“Number.isNaN” funksiyasi standart JavaScript funksiyasi boʻlib, unga berilgan argument “NaN” boʻlsagina “true” qiymatini qaytaradi. “Number” funksiyasi yaroqli raqamni bildirmaydigan qatorni berganingizda “NaN”ni qaytaradi. Shunday qilib, shart "agar "Number" raqam bo'lmasa, buni bajaring" deb tarjima qilinadi.

{{index grouping, "{} (block)", [braces, "block"]}}

Bu misolda `if` dan keyingi gap qavslar (`{` va `}`) ichiga o`ralgan. Qavslar istalgan sonli gaplarni _((blok))_ deb nomlangan bitta bayonotga guruhlash uchun ishlatilishi mumkin. Bu holatda siz ularni o'tkazib yuborishingiz ham mumkin edi, chunki ular faqat bitta bayonotga ega, ammo ular kerak yoki yo'qligini o'ylamaslik uchun JavaScript dasturchilarining ko'pchiligi ulardan har bir o'ralgan bayonotda foydalanadilar. Biz bu kitobda asosan o'sha konventsiyaga amal qilamiz, vaqti-vaqti bilan bir qatordangina iborat kodlar bundan mustasno bo'lishi mumkin.

```
if (1 + 1 == 2) console.log("It's true");
// → It's true
```

{{index "else keyword"}}

Sizda ko'pincha shart to'g'ri bo'lganda bajariladigan kod emas, balki boshqa holatni hal qiluvchi kod ham bo'ladi. Ushbu muqobil yo'l diagrammadagi ikkinchi o'q bilan ifodalanadi. Ikki alohida, muqobil bajarish yoʻllarini yaratish uchun “if” bilan birga “else” kalit soʻzidan foydalanishingiz mumkin.

```{test: wrap}
let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
  console.log("Your number is the square root of " +
              theNumber * theNumber);
} else {
  console.log("Hey. Why didn't you give me a number?");
}
```

{{index ["if keyword", chaining]}}

Agar sizda ikkitadan ortiq yoʻl boʻlsa, bir nechta “if”/”else” juftlarini “zanjirlashingiz” mumkin. Mana bir misol:

```
let num = Number(prompt("Pick a number"));

if (num < 10) {
  console.log("Small");
} else if (num < 100) {
  console.log("Medium");
} else {
  console.log("Large");
}
```

Dastur avval `num` 10 dan kichik yoki yo'qligini tekshiradi. Agar shunday bo'lsa, u o'sha filialni tanlaydi, `"Small"`ni ko'rsatadi va ishini to'htatadi. Agar shunday bo'lmasa, u ikkinchi "if" ni o'z ichiga olgan "else" filialini oladi. Agar ikkinchi shart (`< 100`) bajarilsa, bu raqam kamida 10, lekin 100 dan past ekanligini bildiradi va `"Medium"` ligi bildiriladi. Agar shunday bo'lmasa, ikkinchi va oxirgi "else" filiali tanlanadi.

Ushbu dastur uchun sxema quyidagicha ko'rinadi:

{{figure {url: "img/controlflow-nested-if.svg", alt: "Nested if control flow", width: "4cm"}}}

{{id loops}}
## while va do halqa(loop)lari

0 dan 12 gacha bo'lgan barcha ((juft son)) larni chop etadigan dasturni ko'rib chiqaylik. Buni yozishning bir usuli quyidagicha:

```
console.log(0);
console.log(2);
console.log(4);
console.log(6);
console.log(8);
console.log(10);
console.log(12);
```

{{index ["control flow", loop]}}

Bu kod ishlaydi albatta, lekin dastur yozishdan maqsad ko'proq emas, balki _kamroq_ ish qilishdir. Agar bizga 1000 dan kichik bo'lgan barcha juft raqamlar kerak bo'lsa, bu yondashuv ish bermasligi aniq. Bizga kerak bo'lgan narsa - kod qismini bir necha marta ishlatish usuli. Boshqarish oqimining bu shakli _((loop - halqa))_ deb ataladi.

{{figure {url: "img/controlflow-loop.svg", alt: "Loop control flow",width: "4cm"}}}

{{index [syntax, statement], "counter variable"}}

Loopli boshqaruv oqimi bizga dasturning avval bo'lgan nuqtasiga qaytish va uni joriy dastur holati bilan takrorlash imkonini beradi. Agar biz buni muhim bo'lgan bog'lash bilan birlashtirsak, biz shunday qilishimiz mumkin:

```
let number = 0;
while (number <= 12) {
  console.log(number);
  number = number + 2;
}
// → 0
// → 2
//   … etcetera
```

{{index "while loop", Boolean, [parentheses, statement]}}

`while` kalit so`zi bilan boshlangan ((bayonot)) sikl hosil qiladi. “While” soʻzidan keyin qavs ichida ((ifoda)) soʻng “if” ga oʻxshash gap keladi. Ifoda mantiqiyga aylantirilganda "true" qiymatini hosil qilganda, sikl ushbu bayonotni kiritishda davom etadi.

{{index [state, in binding], [binding, as state]}}

`number` bog'lanishi ((bog'lash)) dasturning borishini kuzatish usulini ko'rsatadi. Har safar sikl takrorlanganda, `number` oldingi qiymatidan 2 ga ko'p qiymatga ega bo'ladi. Har bir takrorlashning boshida dastur ishi tugallanganligini aniqlash uchun 12 raqami bilan taqqoslanadi.

{{index exponentiation}}

 Misol tariqasida foydaliroq biror dastur yozib ko'raylik, masalan 2^10^(2ning 10-darajasi)ni hosoblab ko'rsatib beruvchi dastur. Bunda biz 2ta bog'lanishdan foydalanishimiz kerak bo'ladi. Birinchisi natijani saqlash uchun boshqa biri bo'lsa biz natijani necha marta 2ga ko'paytirganimizni hisoblab borish uchun. Loop ikkinchi bog'lanishni 10ga teng ekanligi yoki yo'qligini uzluksiz tekshirib boradi, agar u 10ga teng bo'lsa, ishni yakunlaydi, aks holda faoliyatni davom ettiradi. 

```
let result = 1;
let counter = 0;
while (counter < 10) {
  result = result * 2;
  counter = counter + 1;
}
console.log(result);
// → 1024
```

Biz "counter" ni hisoblashni 1dan to `<=10`gacha hiisoblashimiz ham mumkin edi, lekin [4-bobda](data#array_indexing) kengroq yoritiladigan sabablarga ko'ra sanoqni 0dan boshlashga odatlanganimiz ma'qulroq. 

{{index "loop body", "do loop", ["control flow", loop]}}

`do` loopi ham `while` ga o'xshash boshqaruv tuzilishiga ega. `do` `while` dan faqatgina bir jihati: unga biriktirilgan bayonot avval bir marta amalga oshirilib, undan keyingina bayonot amalga oshirilishi yoki to'xtatilishi shartlarini ko'rib chiqishni boshlashi bilangina ajralib turadi. Bunga quyidagi misol orqali guvoh bo'lishimiz mumkin:

```
let yourName;
do {
  yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);
```

{{index [Boolean, "conversion to"], "! operator"}}

Bu dastur sizni ismingizni kiritishga undaydi. Siz unga bo'sh satrdan farq qiluvchu qandaydir ma'lumot kiritmaguningizga qadar u sizdan qayta qayta ismingizni kiritishingizni so'rayveradi. `!` ooperatorian foydalanish qiymatni Boolean turga o'zgartirib beradi va u `""` kabi bo'sh satrdan boshqa har qanday ma'lumotni `true` deb qabul qiladi. Bu siz satr ko'rinishidagi ma'lumot kiritmaguningizga qadar dastur takroran ishga tushaverishini anglatadi.

## Indenting Code

{{index [code, "structure of"], [whitespace, indentation], "programming style"}}

Yuqoridagi misollarda katta bayonotlarning bir qismi hisoblangan kichik bayonotlar oldida bo'sh joy tashlab keytilganini guvohi bo'ldingiz. Lekin ular majburiy emas, kompyuter kodni uarsiz ham bemalol tushuna oladi. Aslida koddagi yangi ((qator))ga o'tish holati ham ixtiyoriydir. Agar xohlasangiz butun boshli dasturni bitta qatorga yozishingiz mumkin.

The role of this ((indentation)) inside ((block))s is to make the
structure of the code stand out. In code where new blocks are opened
inside other blocks, it can become hard to see where one block ends
and another begins. With proper indentation, the visual shape of a
program corresponds to the shape of the blocks inside it. I like to
use two spaces for every open block, but tastes differ—some people use
four spaces, and some people use ((tab character))s. The important
thing is that each new block adds the same amount of space.

```
if (false != true) {
  console.log("That makes sense.");
  if (1 < 2) {
    console.log("No surprise there.");
  }
}
```

Most code ((editor)) programs[ (including the one in this book)]{if
interactive} will help by automatically indenting new lines the proper
amount.

## for looplari 

{{index [syntax, statement], "while loop", "counter variable"}}

Many loops follow the pattern shown in the `while` examples. First a
"counter" binding is created to track the progress of the loop. Then
comes a `while` loop, usually with a test expression that checks whether the
counter has reached its end value. At the end of the loop body, the
counter is updated to track progress.

{{index "for loop", loop}}

Because this pattern is so common, JavaScript and similar languages
provide a slightly shorter and more comprehensive form, the `for`
loop.

```
for (let number = 0; number <= 12; number = number + 2) {
  console.log(number);
}
// → 0
// → 2
//   … etcetera
```

{{index ["control flow", loop], state}}

This program is exactly equivalent to the
[earlier](program_structure#loops) even-number-printing example. The
only change is that all the ((statement))s that are related to the
"state" of the loop are grouped together after `for`.

{{index [binding, as state], [parentheses, statement]}}

The parentheses after a `for` keyword must contain two
((semicolon))s. The part before the first semicolon _initializes_ the
loop, usually by defining a binding. The second part is the
((expression)) that _checks_ whether the loop must continue. The final
part _updates_ the state of the loop after every iteration. In most
cases, this is shorter and clearer than a `while` construct.

{{index exponentiation}}

This is the code that computes 2^10^ using `for` instead of `while`:

```{test: wrap}
let result = 1;
for (let counter = 0; counter < 10; counter = counter + 1) {
  result = result * 2;
}
console.log(result);
// → 1024
```

## Breaking Out of a Loop

{{index [loop, "termination of"], "break keyword"}}

Having the looping condition produce `false` is not the only way a
loop can finish. There is a special statement called `break` that has
the effect of immediately jumping out of the enclosing loop.

This program illustrates the `break` statement. It finds the first number
that is both greater than or equal to 20 and divisible by 7.

```
for (let current = 20; ; current = current + 1) {
  if (current % 7 == 0) {
    console.log(current);
    break;
  }
}
// → 21
```

{{index "remainder operator", "% operator"}}

Using the remainder (`%`) operator is an easy way to test whether a
number is divisible by another number. If it is, the remainder of
their division is zero.

{{index "for loop"}}

The `for` construct in the example does not have a part that checks
for the end of the loop. This means that the loop will never stop
unless the `break` statement inside is executed.

If you were to remove that `break` statement or you accidentally write
an end condition that always produces `true`, your program would get
stuck in an _((infinite loop))_. A program stuck in an infinite loop
will never finish running, which is usually a bad thing.

{{if interactive

If you create an infinite loop in one of the examples on these pages,
you'll usually be asked whether you want to stop the script after a
few seconds. If that fails, you will have to close the tab that you're
working in, or on some browsers close your whole browser, to recover.

if}}

{{index "continue keyword"}}

The `continue` keyword is similar to `break`, in that it influences
the progress of a loop. When `continue` is encountered in a loop body,
control jumps out of the body and continues with the loop's next
iteration.

## Updating bindings succinctly

{{index assignment, "+= operator", "-= operator", "/= operator", "*= operator", [state, in binding], "side effect"}}

Especially when looping, a program often needs to "update" a binding
to hold a value based on that binding's previous value.

```{test: no}
counter = counter + 1;
```

JavaScript provides a shortcut for this.

```{test: no}
counter += 1;
```

Similar shortcuts work for many other operators, such as `result *= 2`
to double `result` or `counter -= 1` to count downward.

This allows us to shorten our counting example a little more.

```
for (let number = 0; number <= 12; number += 2) {
  console.log(number);
}
```

{{index "++ operator", "-- operator"}}

For `counter += 1` and `counter -= 1`, there are even shorter
equivalents: `counter++` and `counter--`.

## Dispatching on a value with switch

{{index [syntax, statement], "conditional execution", dispatch, ["if keyword", chaining]}}

It is not uncommon for code to look like this:

```{test: no}
if (x == "value1") action1();
else if (x == "value2") action2();
else if (x == "value3") action3();
else defaultAction();
```

{{index "colon character", "switch keyword"}}

There is a construct called `switch` that is intended to express such
a "dispatch" in a more direct way. Unfortunately, the syntax
JavaScript uses for this (which it inherited from the C/Java line of
programming languages) is somewhat awkward—a chain of `if` statements
may look better. Here is an example:

```
switch (prompt("What is the weather like?")) {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}
```

{{index fallthrough, "break keyword", "case keyword", "default keyword"}}

You may put any number of `case` labels inside the block opened by
`switch`. The program will start executing at the label that
corresponds to the value that `switch` was given, or at `default` if
no matching value is found. It will continue executing, even across
other labels, until it reaches a `break` statement. In some cases,
such as the `"sunny"` case in the example, this can be used to share
some code between cases (it recommends going outside for both sunny
and cloudy weather). But be careful—it is easy to forget such a
`break`, which will cause the program to execute code you do not want
executed.

## Capitalization

{{index capitalization, [binding, naming], [whitespace, syntax]}}

Binding names may not contain spaces, yet it is often helpful to use
multiple words to clearly describe what the binding represents. These
are pretty much your choices for writing a binding name with several
words in it:

```{lang: null}
fuzzylittleturtle
fuzzy_little_turtle
FuzzyLittleTurtle
fuzzyLittleTurtle
```

{{index "camel case", "programming style", "underscore character"}}

The first style can be hard to read. I rather like the look of the
underscores, though that style is a little painful to type. The
((standard)) JavaScript functions, and most JavaScript programmers,
follow the bottom style—they capitalize every word except the first.
It is not hard to get used to little things like that, and code with
mixed naming styles can be jarring to read, so we follow this
((convention)).

{{index "Number function", constructor}}

In a few cases, such as the `Number` function, the first letter of a
binding is also capitalized. This was done to mark this function as a
constructor. What a constructor is will become clear in [Chapter
?](object#constructors). For now, the important thing is not
to be bothered by this apparent lack of ((consistency)).

## Comments

{{index readability}}

Often, raw code does not convey all the information you want a program
to convey to human readers, or it conveys it in such a cryptic way
that people might not understand it. At other times, you might just
want to include some related thoughts as part of your program. This is
what _((comment))s_ are for.

{{index "slash character", "line comment"}}

A comment is a piece of text that is part of a program but is
completely ignored by the computer. JavaScript has two ways of writing
comments. To write a single-line comment, you can use two slash
characters (`//`) and then the comment text after it.

```{test: no}
let accountBalance = calculateBalance(account);
// It's a green hollow where a river sings
accountBalance.adjust();
// Madly catching white tatters in the grass.
let report = new Report();
// Where the sun on the proud mountain rings:
addToReport(accountBalance, report);
// It's a little valley, foaming like light in a glass.
```

{{index "block comment"}}

A `//` comment goes only to the end of the line. A section of text
between `/*` and `*/` will be ignored in its entirety, regardless of
whether it contains line breaks. This is useful for adding blocks of
information about a file or a chunk of program.

```
/*
  I first found this number scrawled on the back of an old
  notebook. Since then, it has often dropped by, showing up in
  phone numbers and the serial numbers of products that I've
  bought. It obviously likes me, so I've decided to keep it.
*/
const myNumber = 11213;
```

## Summary

You now know that a program is built out of statements, which
themselves sometimes contain more statements. Statements tend to
contain expressions, which themselves can be built out of smaller
expressions.

Putting statements after one another gives you a program that is
executed from top to bottom. You can introduce disturbances in the
flow of control by using conditional (`if`, `else`, and `switch`) and
looping (`while`, `do`, and `for`) statements.

Bindings can be used to file pieces of data under a name, and they are
useful for tracking state in your program. The environment is the set
of bindings that are defined. JavaScript systems always put a number
of useful standard bindings into your environment.

Functions are special values that encapsulate a piece of program. You
can invoke them by writing `functionName(argument1, argument2)`. Such
a function call is an expression and may produce a value.

## Exercises

{{index exercises}}

If you are unsure how to test your solutions to the exercises, refer to the
[Introduction](intro).

Each exercise starts with a problem description. Read this description and try to
solve the exercise. If you run into problems, consider reading the
hints [after the exercise]{if interactive}[at the [end of the
book](hints)]{if book}. Full solutions to the exercises are
not included in this book, but you can find them online at
[_https://eloquentjavascript.net/code_](https://eloquentjavascript.net/code#2).
If you want to learn something from the exercises, I recommend looking
at the solutions only after you've solved the exercise, or at least
after you've attacked it long and hard enough to have a slight
headache.

### Looping a triangle

{{index "triangle (exercise)"}}

Write a ((loop)) that makes seven calls to `console.log` to output the
following triangle:

```{lang: null}
#
##
###
####
#####
######
#######
```

{{index [string, length]}}

It may be useful to know that you can find the length of a string by
writing `.length` after it.

```
let abc = "abc";
console.log(abc.length);
// → 3
```

{{if interactive

Most exercises contain a piece of code that you can modify to solve
the exercise. Remember that you can click code blocks to edit them.

```
// Your code here.
```
if}}

{{hint

{{index "triangle (exercise)"}}

You can start with a program that prints out the numbers 1 to 7, which
you can derive by making a few modifications to the [even number
printing example](program_structure#loops) given earlier in the
chapter, where the `for` loop was introduced.

Now consider the equivalence between numbers and strings of hash
characters. You can go from 1 to 2 by adding 1 (`+= 1`). You can go
from `"#"` to `"##"` by adding a character (`+= "#"`). Thus, your
solution can closely follow the number-printing program.

hint}}

### FizzBuzz

{{index "FizzBuzz (exercise)", loop, "conditional execution"}}

Write a program that uses `console.log` to print all the numbers from
1 to 100, with two exceptions. For numbers divisible by 3, print
`"Fizz"` instead of the number, and for numbers divisible by 5 (and
not 3), print `"Buzz"` instead.

When you have that working, modify your program to print `"FizzBuzz"`
for numbers that are divisible by both 3 and 5 (and still print
`"Fizz"` or `"Buzz"` for numbers divisible by only one of those).

(This is actually an ((interview question)) that has been claimed to
weed out a significant percentage of programmer candidates. So if you
solved it, your labor market value just went up.)

{{if interactive
```
// Your code here.
```
if}}

{{hint

{{index "FizzBuzz (exercise)", "remainder operator", "% operator"}}

Going over the numbers is clearly a looping job, and selecting what to
print is a matter of conditional execution. Remember the trick of
using the remainder (`%`) operator for checking whether a number is
divisible by another number (has a remainder of zero).

In the first version, there are three possible outcomes for every
number, so you'll have to create an `if`/`else if`/`else` chain.

{{index "|| operator", ["if keyword", chaining]}}

The second version of the program has a straightforward solution and a
clever one. The simple solution is to add another conditional "branch" to
precisely test the given condition. For the clever solution, build up a
string containing the word or words to output and print either this
word or the number if there is no word, potentially by making good use
of the `||` operator.

hint}}

### Chessboard

{{index "chessboard (exercise)", loop, [nesting, "of loops"], "newline character"}}

Write a program that creates a string that represents an 8×8 grid,
using newline characters to separate lines. At each position of the
grid there is either a space or a "#" character. The characters should
form a chessboard.

Passing this string to `console.log` should show something like this:

```{lang: null}
 # # # #
# # # # 
 # # # #
# # # # 
 # # # #
# # # # 
 # # # #
# # # # 
```

When you have a program that generates this pattern, define a
binding `size = 8` and change the program so that it works for
any `size`, outputting a grid of the given width and height.

{{if interactive
```
// Your code here.
```
if}}

{{hint

{{index "chess board (exercise)"}}

You can build the string by starting with an empty one (`""`) and
repeatedly adding characters. A newline character is written `"\n"`.

{{index [nesting, "of loops"], [braces, "block"]}}

To work with two ((dimensions)), you will need a ((loop)) inside of a
loop. Put braces around the bodies of both loops to make it
easy to see where they start and end. Try to properly indent these
bodies. The order of the loops must follow the order in which we build
up the string (line by line, left to right, top to bottom). So the
outer loop handles the lines, and the inner loop handles the characters
on a line.

{{index "counter variable", "remainder operator", "% operator"}}

You'll need two bindings to track your progress. To know whether to
put a space or a hash sign at a given position, you could test whether
the sum of the two counters is even (`% 2`).

Terminating a line by adding a newline character must happen after the
line has been built up, so do this after the inner loop but inside the outer loop.

hint}}
