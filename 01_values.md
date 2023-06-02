{{meta {docid: values}}}

# Qiymat, Tur, va Operatorlar

{{quote {author: "Master Yuan-Ma", title: "Dasturlash Kitobi", chapter: true}

Mashinaning yuzasi ostida dastur ishga tushadi. Dastur hech qanday qiyinchiliksiz kengayadi va qisqaradi. Katta uyg'unlikda elektronlar tarqaladi va qayta guruhlanadi. Monitordagi shakllar faqat suv ustidagi to'lqinlardir. Mohiyat ko'rinmas holda quyida qoladi.
quote}}

{{index "Yuan-Ma", "Dasturlash Kitobi"}}

{{figure {url: "img/chapter_picture_1.jpg", alt: "Picture of a sea of bits", chapter: framed}}}

{{index "binary data", data, bit, memory}}

Kompyuter dunyosida faqat ma'lumotlar mavjud. Siz ma'lumotlarni o'qishingiz, ma'lumotlarni o'zgartirishingiz, yangi ma'lumotlarni yaratishingiz mumkin, ammo ma'lumot bo'lmagan narsalarni ta'kidlab ham bo'lmaydi. Bu ma'lumotlarning barchasi bitlarning uzun ketma-ketligi sifatida saqlanadi va shuning uchun tuzilishi jihatidan o'xshashdir.

{{index CD, signal}}

_Bit_ har qanday ikki qiymatli narsalar bo'lib, odatda nol va birliklar sifatida tavsiflanadi. Kompyuterning ichida ular yuqori yoki past elektr zaryadi, kuchli yoki zaif signal yoki CD yuzasida porloq yoki xira nuqta kabi shakllarni oladi. Diskret ma'lumotlarning har qanday qismi nol va birlar ketma-ketligiga qisqartirilishi va shu bilan bitlarda ifodalanishi mumkin.

{{index "binary number", radix, "decimal number"}}

Masalan, 13 raqamini bit bilan ifodalashimiz mumkin. U o'nlik son bilan bir xil ishlaydi, lekin 10 xil ((raqam)) o'rniga sizda faqat 2 xil raqam bor va har birining qiymati o'ngdan chapga 2 martalab ortib boradi. Mana 13 raqamini tashkil etuvchi bitlar, ularning ostida raqamlarning qiymati ko'rsatilgan:

```{lang: null}
   0   0   0   0   1   1   0   1
 128  64  32  16   8   4   2   1
```

Demak, bu ikkilik raqam 00001101. Uning nolga teng bo'lmagan raqamlari 8, 4 va 1 ni bildiradi va ular qo'shilib 13 ni hosil qiladi.

## Qiymat

{{index [memory, organization], "volatile data storage", "hard drive"}}

Bitlar dengizini, yoyinki ularning okeanini tasavvur qilib ko'ring. Oddiy zamonaviy kompyuterda o'zgaruvchan ma'lumotlarni saqlashda (ishchi xotira) 30 milliarddan ortiq bit mavjud. O'zgaruvchan xotira (qattiq disk yoki ekvivalenti) odatda bir necha marta ko'proq hajmga ega.

Bunday miqdordagi bitlar bilan yo'qolmasdan ishlash uchun biz ularni ma'lumot bo'laklarini ifodalovchi qismlarga ajratishimiz kerak. JavaScript muhitida bu qismlar _((value))qiymat_ deb ataladi. Garchi barcha qiymatlar bitlardan iborat bo'lsa-da, ular turli vazifalarni bajaradi. Har bir qiymat o'z rolini belgilaydigan ((tur)) ga ega. Ayrim qiymatlar raqamlar, ba'zi qiymatlar matn bo'laklari, ba'zi qiymatlar funksiyalar va hokazo.

{{index "garbage collection"}}

Qiymat yaratish uchun siz shunchaki uning nomini chaqirishingiz kerak. Bu juda oson. Siz o'zingizning qiymatlaringiz uchun xomashyodan foydalanishingiz yoki ular uchun pul to'lashingiz shart emas. Siz shunchaki ularni chaqirasiz va _bum_, qiymatlar tayyor. Ular, albatta, havodan yaratilmagan. Har bir qiymat biror joyda saqlanishi kerak va agar siz ularning katta miqdorini bir vaqtning o'zida ishlatmoqchi bo'lsangiz, xotira maydonida joy yetishmasligi mumkin. Lekin bu bir vaqtning o'zida xotira maydonining hammasi kerak bo'lgandagina yuzaga keluvchi muammo. Siz boshqa qiymatdan foydalanmasligingiz bilan, u o'z qismlarini keyingi avlod qiymatlari uchun joy sifatida qayta ishlash uchun qoldirib, tarqalib ketadi.

Ushbu bobda JavaScript dasturlarining mayda elementlari, ya'ni oddiy qiymat turlari va bunday qiymatlar ustida ishlay oladigan operatorlar tanishtiriladi.

## Sonlar

{{index [syntax, number], number, [number, notation]}}

_son_ turidagi qiymatlar, tabiiy xolda, raqamli qiymatlardir. JavaScript dasturida ular quyidagicha yoziladi:

```
13
```

{{index "binary number"}}

 Ushbu sondan dasturda foydalanilsa, u kompyuter xotirasida 13 raqami uchun bit ketma-ketligi paydo bo'lishiga olib keladi.

{{index [number, representation], bit}}

JavaScript bitta raqam qiymatini saqlash uchun ma'lum miqdordagi, aniqrog'i, 64 ta bitlardan foydalanadi. 64 bit bilan yaratishingiz mumkin bo'lgan ketma-ketliklar juda ko'p, lekin ifodalanishi mumkin bo'lgan turli raqamlar soni cheklangan. _N_ o'nlik ((raqam)) bilan siz 10^N^ sonni ifodalashingiz mumkin. Demak, 64 ta ikkilik raqamn orqali 2^64^ ta turli xil raqamlarni ifodalashingiz mumkin, bu taxminan 18 kvintillion (18, undan keyin 18 nol bilan). Bu juda ko'p raqamlar demakdir.

Ilgari kompyuter xotirasi ancha kichikroq edi va odamlar o'z raqamlarini ifodalash uchun 8 yoki 16 bitli guruhlardan foydalanishga moyil edilar. Bunday holatda kichik raqamlarni tasodifan _((meyordan ortib ketish))i_ oson bo'lgan, ya'ni berilgan bitlar soniga to'g'ri kelmaydigan raqam bilan yakunlanish holatlari ko'p uchrab turgan. Bugungi kunda, hatto cho'ntagingizga sig'adigan kompyuterlar ham juda ko'p xotiraga ega, shuning uchun siz 64-bitli qismlardan foydalanishingiz mumkin va siz faqat astronomik raqamlar bilan ishlagandagina me'yirdan ortib ketish haqida tashvishlansangiz bo'ladi.

{{index sign, "floating-point number", "sign bit"}}

Lekin, 18 kvintilliondan kam bo'lgan barcha butun sonlar ham JavaScriptdagi raqamlar turiga mos kelavermaydi. Bu bitlar manfiy raqamlarni ham o'zida saqlaydi, shuning uchun bitta bit raqamning belgisini bildiradi. Kattaroq muammo shundaki, butun bo'lmagan raqamlar ham ifodalanishi kerak. Buning uchun ba'zi bitlar qoldiqni ifodalovchi nuqta o'rnini saqlash uchun ishlatiladi. Saqlanishi mumkin bo'lgan haqiqiy maksimal butun son 9 kvadrillion (15 nol) oralig'idagi sonlardir- bu hali ham yetarlicha katta daraja hisoblanadi.

{{index [number, notation], "fractional number"}}
Qoldiqli sonlar nuqta yordamida yoziladi.

```
9.81
```

{{index exponent, "scientific notation", [number, notation]}}

Juda katta yoki juda kichik raqamlar uchun _e_ (_eksponent_ning qisqartmasi) qo'shib, keyin raqamning ko'rsatkichini qo'shish kabi ilmiy belgilardan ham foydalanishingiz mumkin.

```
2.998e8
```

Bu  2.998 × 10^8^ = 299,800,000 ni anglatadi

{{index pi, [number, "precision of"], "floating-point number"}}

Yuqorida aytib o'tilgan 9 kvadrilliondan kichik butun sonlar ( _((integer))_ deb ham ataladi) bilan hisoblar har doim aniq bo'lishi kafolatlanadi. Afsuski, qoldiqli sonlar bilan hisob-kitoblar bundan mustasno. P (pi) ni o'nlik sonli sonlar bilan aniq ifodalab bo'lmagani kabi, ularni saqlash uchun faqat 64 bit mavjud bo'lsa, ko'p sonlar aniqligini yo'qotadi. Bu maqtashga arzigulik holat emas albatta, lekin u faqat muayyan vaziyatlarda amaliy muammolarni keltirib chiqaradi. Muhimi, bundan xabardor bo'lish va qoldiqli raqamlarga aniq qiymatlar sifatida emas, balki yaqinlashish sifatida qarashdir.

### Arifmetika

{{index [syntax, operator], operator, "binary operator", arithmetic, addition, multiplication}}

Raqamlar bilan bog'liq asosiy narsa arifmetikadir. Qo'shish yoki ko'paytirish kabi arifmetik amallar ikkita raqam qiymatini oladi va ulardan yangi son hosil qiladi. Mana ular JavaScript-da qanday ko'rinishga ega:
```
100 + 4 * 11
```

{{index [operator, application], asterisk, "plus character", "* operator", "+ operator"}}

`+` va `*` belgilari _operatorlar_ deb ataladi. Birinchisi qo'shishni, ikkinchisi esa ko'paytirishni anglatadi. Operatorni ikkita qiymat orasiga qo'yish uni ushbu qiymatlarga qo'llaydi va yangi qiymat hosil qiladi.

{{index grouping, parentheses, precedence}}

Ammo yuqoridagi holat "4 ga 100 ni qo'shing va natijani 11 ga ko'paytiring" degan ma'noni anglatadimi yoki ko'paytirish qo'shishdan avval amalga oshiriladimi? Siz taxmin qilganingizdek, ko'paytirish birinchi bo'lib sodir bo'ladi. Ammo matematikada bo'lgani kabi, qo'shimchani qavs ichiga o'rash orqali buni o'zgartirishingiz mumkin.

```
(100 + 4) * 11
```

{{index "hyphen character", "slash character", division, subtraction, minus, "- operator", "/ operator"}}

Ayirish uchun `-` dan, bo'lish uchun esa, `/` belgisidan foydalaniladi.

Operatorlar qavssiz birga paydo bo'lganda, ularni qo'llash tartibi operatorlarning _((ustunligi))_ bilan belgilanadi. Masalan yuqoridagi amal ko'paytirish qo'shishdan avval kelishini ko'rsatadi. `/` operatori `*` bilan bir xil ustunlikka ega. `+` va `-` uchun ham xuddi qoida amal qiladi. `1 - 2 + 1` da bo'lgani kabi bir xil ustunlikka ega bir nechta operatorlar yonma-yon paydo bo'lganda, ular chapdan o'ngga qo'llaniladi: `(1 - 2) + 1`.

Ushbu ustuvorlik qoidalari sizni tashvishga soladigan narsa emas. Agar shubhangiz bo'lsa, shunchaki qavslar qo'shish orqali muammoni hal qilish mumkin.

{{index "modulo operator", division, "remainder operator", "% operator"}}

Ko'rishingiz bilanoq tushunib olishingiz qiyin bo'lgan yana bir arifmetik operator bor. `%` belgisi _qoldiq_ operatsiyasini ifodalash uchun ishlatiladi. `X % Y` - `X` ni `Y` ga bo'lganda qolgan qoldiqni ifidalaydi. Masalan, `314 % 100` `14` ni, `144 % 12` esa `0`ni beradi. Qoldiq operatorining ustuvorligi ko'paytirish va bo'lish bilan bir xil. Bu operatorning _modulo_ deb atalishiga ham tez-tez duch kelishingiz mumkin.

### Mahsus sonlar

{{index [number, "special values"]}}

JavaScripda son deb hisoblanadigan lekin songa oid sifatlarga ega bo'lmagan 3ta qiymat bor.

{{index infinity}}

Birinchi ikkitasi 'Infinity' va ' - Infinity' bo'lib, ular ijobiy va salbiy cheksizliklarni ifodalaydi. `Infinity - 1` hali ham `Infinity` va hokazo. Biroq, cheksizlikka asoslangan hisob-kitoblarga juda ko'p ishonish kerak emas. Bu matematik jihatdan to'g'ri emas va u bizni `NaN` deb ataluvchi keyingi maxsus songa olib keladi.

{{index NaN, "not a number", "division by zero"}}

`NaN` son turidagi qiymat bo'lishiga qaramasdan "Not a number (raqam emas)" degan ma'noni anglatadi. Siz, masalan, `0/0` (nol nolga bo'lingan), `Infinity - Infinity` yoki mazmunli natija bermaydigan boshqa raqamli amallarni hisoblashga harakat qilganingizda bu natijaga erishishingiz mumkin.

## String (Satrlar)

{{indexsee "grave accent", backtick}}

{{index [syntax, string], text, character, [string, notation], "single-quote character", "double-quote character", "quotation mark", backtick}}

Keyingi asosiy ma'lumotlar turi _((string))(satrlar)_. Satrlar matnni ifodalash uchun ishlatiladi. Ular o'z mazmunini qo'shtirnoq ichiga olish orqali yoziladi.

```
`Down on the sea`
"Lie on the ocean"
'Float on the ocean'
```

Satrlarni ifodalashda "" , '', ``, kabi tinish belgilaridan foydalanish mumkin, faqat satr boshida va ohirida bir xil tinish belgisidan foydalanish talab qilinadi.

{{index "line break", "newline character"}}

Qo'shtirnoq orasiga deyarli hamma narsani yozish mumkin va JavaScript undan string qiymatini yaratadi. Ammo bir nechta belgilarbilan bu jarayon qiyinroq kechadi. Qo'shtirnoq orasiga qo'shtirnoq qo'yish qanchalik qiyin bo'lishi mumkinligini tasavvur qilishingiz mumkin. _Newlines_ ([enter]{keyname} tugmachasini bosganingizda olinadigan belgilar) faqat ular `` ` `` `` ` `` belgisi orasida yozilgandagina belgi sifatida qabul qilinadi.

{{index [escaping, "in strings"], ["backslash character", "in strings"]}}

Bunday belgilarni satrga kiritish imkoniyatini yaratish uchun quyidagi belgi qo'llaniladi: iqtibosli matn ichida teskari chiziq (`\`) topilsa, undan keyingi belgi alohida ma'noga ega ekanligini bildiradi. Bu belgidan _qochish_ deyiladi. Teskari qiyshiq chiziq oldidan kelgan ' yoki " belgisi satrni tugatmaydi, balki uning bir qismi bo'ladi. Teskari chiziqdan keyin `n` belgisi paydo bo'lsa, u yangi qator sifatida talqin qilinadi. Xuddi shunday, teskari chiziqdan keyin `t` belgisi ((tab icon)) degan ma'noni anglatadi.

Quyidagi satrni ko'raylik:

```
"This is the first line\nAnd this is the second"
```

Aslida bu satr quyidagidek ifodalanishni anglatadi:

```{lang: null}
This is the first line
And this is the second
```

Albatta, qatordagi teskari chiziq maxsus kod emas, balki faqat teskari chiziq bo'lishini xohlaydigan vaziyatlar mavjud. Agar ikkita teskari chiziq bir-birining ortidan kelsa, ular birlashadi va natijada olingan satr qiymatida faqat bittasi qoladi. _"A newline character is written like`"`\n`"`."_ degan satrni quyidagidek ifodalash mumkin:

```
"A newline character is written like \"\\n\"."
```

{{id unicode}}

{{index [string, representation], Unicode, character}}

Satrlar ham kompyuter ichida mavjud bo'lishi uchun bir qator bitlar sifatida modellashtirilishi kerak. JavaScript-ning buni amalga oshirish usuli _((Unicode))_ standartiga asoslanadi. Ushbu standart sizga kerak bo'lgan deyarli barcha belgilarga raqam beradi, jumladan yunon, arab, yapon, arman va boshqalarga ham. Agar bizda har bir belgi uchun raqam bo'lsa, qatorni raqamlar ketma-ketligi bilan tasvirlash mumkin.

{{index "UTF-16", emoji}}

Va JavaScript shunday qiladi. Ammo bir murakkablik bor: JavaScript-ning taqdimoti har bir satr elementi uchun 16 bitdan foydalanadi, bu esa 2^16^ gacha turli belgilarni tavsiflashi mumkin. Ammo Unicode bundan ko'proq belgilarni ifodalaydi, va ular hozirgi paytda ikki baravar ko'p. Shunday qilib, ba'zi belgilar, masalan, ko'plab emojilar JavaScript satrlarida ikkita "belgi o'rnini" egallaydi. Biz bu mavzuga [Chapter 5](top_order#code_units)da qaytamiz.

{{index "+ operator", concatenation}}

Satrlarni bo'lish, ko'paytirish yoki ayirish mumkin emas, lekin ularda `+` operatori ishlatilishi _mumkin_. Bu operator satrlarni bir-biriga qo'shmaydi, lekin ularni _birlashtiradi_ . Quyidagi satr "concateenate" so'zini hosil qiladi:

```
"con" + "cat" + "e" + "nate"
```

String qiymatlari ular ustida boshqa operatsiyalarni bajarish uchun ishlatilishi mumkin bo'lgan bir qator bog'langan funktsiyalar(_metodlar_)ga ega. Bular haqida kengroq [Chapter 4](data_#methods) da so'z yuritamiz.

{{index interpolation, backtick}}

Bitta yoki qo'sh tirnoq bilan yozilgan satrlar deyarli bir xil bo'ladi - yagona farq ularning ichida qaysi turdagi tinish belgisidan qochish kerakligida. Odatda _((shablon literallari))_ deb ataladigan `` `    `` `` ` `` belgili  satrlari yana bir nechta ishlarni bajarishi mumkin. Qatorlarni kengaytirish imkoniyatidan tashqari, ular boshqa qiymatlarni ham joylashtirishlari mumkin.
```
`half of 100 is ${100 / 2}`
```

Shablon literalida “${}” ichiga biror narsa yozsangiz, uning natijasi hisoblab chiqiladi, satrga aylantiriladi va shu pozitsiyaga kiritiladi. Misol "100 ning _yarmi 50_" ni hosil qiladi.

## Birlik operatorlari

{{index operator, "typeof operator", type}}

Hamma operatorlar ham belgilar emas. Ba'zilari so'z sifatida yoziladi. Bir misol, siz bergan qiymat turini nomlovchi satr qiymatini ishlab chiqaradigan `typeof` operatori.

```
console.log(typeof 4.5)
// → number
console.log(typeof "x")
// → string
```

{{index "console.log", output, "JavaScript console"}}

{{id "console.log"}}

Biz biror narsani baholash natijasini ko'rishni xohlayotganimizni ko'rsatish uchun misol kodida "console.log" dan foydalanamiz. Bu haqda ko'proq [keyingi bobda](program_structure).

{{index negation, "- operator", "binary operator", "unary operator"}}

Ko'rsatilgan boshqa operatorlarning barchasi ikkita qiymatda ishlaydi, ammo `typeof` faqat bitta qiymatni oladi. Ikkilik qiymatdan foydalanadigan operatorlar _binary_ operatorlar, bittasini oladiganlar esa _unary_ operatorlar deb ataladi. Minus " - " operatoridan ikkilik operator sifatida ham, unar operator sifatida ham foydalanish mumkin.

```
console.log(- (10 - 2))
// → -8
```

## Bulean qiymatlar 

{{index Boolean, operator, true, false, bit}}

Ko'pincha "ha" va "yo'q" yoki "yoqish" va "o'chirish" kabi ikkita imkoniyatni ajratib turadigan qiymatga ega bo'lish foydalidir. Buning uchun JavaScript-da _Boolean_ turi mavjud bo'lib, u faqat ikkita qiymatga ega: True(rost) va False(yolg'on). Ular ushbu so'zlar bilan ifodalanadi.

### Taqqoslash

{{index comparison}}

Mantiqiy qiymatlarni ishlab chiqarishning bir usuli:

```
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
```

{{index [comparison, "of numbers"], "> operator", "< operator", "greater than", "less than"}}

`>` va `<` belgilari mos ravishda "katta" va "kichik" ning an'anaviy belgilaridir. Ular ikkilik operator hisoblanadi.

Ular qo'llanilganda, bu vaziyatda qo'llanilishi mumkinligini bildiruvchi mantiqiy qiymat hosil bo'ladi..

Satrlarni xuddi shu tarzda solishtirish mumkin.

```
console.log("Aardvark" < "Zoroaster")
// → true
```

{{index [comparison, "of strings"]}}

Satrlarni tartiblash usuli taxminan alifbo bo'yicha, lekin aslida siz lug'atda ko'rishni kutganingizdek emas: bosh harflar har doim kichik harflardan "kichik" bo'ladi, shuning uchun `"Z" < "a"` va alifbo tarkibida bo'lmagan belgilar (!, - va boshqalar) ham ushbu qatorga kiritilgan. Satrlarni solishtirganda, JavaScript ((Unicode)) kodlarni birma-bir taqqoslab, belgilarni chapdan o'ngga o'tadi.

{{index equality, ">= operator", "<= operator", "== operator", "!= operator"}}

Boshqa shunga o'xshash operatorlar `>=` (katta yoki teng), `<=` (kichik yoki teng), `==` (teng) va `!=` (teng emas) kabilar ham mavjud.

```
console.log("Itchy" != "Scratchy")
// → true
console.log("Apple" == "Orange")
// → false
```

{{index [comparison, "of NaN"], NaN}}

JavaScript-da o'ziga teng bo'lmagan faqat bitta qiymat mavjud va u "NaN" ("raqam emas").
```
console.log(NaN == NaN)
// → false
```

"NaN" mantiqsiz hisoblash natijasini bildirishi kerak va shuning uchun u hech qanday _boshqa_ mantiqsiz hisoblar natijasiga teng emas.

### Mantiqiy operatorlar

{{index reasoning, "logical operators"}}

Mantiqiy qiymatlarga nisbatan qo'llanilishi mumkin bo'lgan ba'zi operatsiyalar ham mavjud. JavaScript uchta mantiqiy operator, _and_, _or_ va _not_ ni qo'llab-quvvatlaydi. Bularni Buleanlarga nisbatan "sabab" uchun qo'llash mumkin.

{{index "&& operator", "logical and"}}

`&&` operatori mantiqiy _and_ ni ifodalaydi. Bu ikkilik operator bo'lib, unga berilgan ikkala qiymat ham True bo'lsagina uning natijasi to'g'ri bo'ladi.

```
console.log(true && false)
// → false
console.log(true && true)
// → true
```

{{index "|| operator", "logical or"}}

`||` operatori mantiqiy _or_ ni bildiradi. Agar unga berilgan qiymatlardan biri True bo'lsa, u True hosil qiladi.

```
console.log(false || true)
// → true
console.log(false || false)
// → false
```

{{index negation, "! operator"}}

_Not_ undov belgisi (`!`) sifatida yoziladi. Bu unar operator bo'lib, unga berilgan qiymatni o'zgartiradi — `!true` `false` ni, `!false` esa `true` ni beradi.

{{index precedence}}

Ushbu mantiqiy operatorlarni matematika va boshqa operatorlar bilan ishlatganda qavslar kerakmi yoki yo'qmi har doim ham aniq bilib bo'lmaydi. Amalda, biz hozirgacha ko'rgan operatorlar orasida `||` eng past ustunlikka ega ekanligini, keyin `&&`, so'ngra taqqoslash operatorlari (`>`, `==` va hokazo), va boshqalar shu tartibda davom etadi. Bu tartib shunday tanlanganki, quyidagi kabi tipik iboralarda iloji boricha kamroq qavs kerak bo'ladi:

```
1 + 1 == 2 && 10 * 10 > 50
```

{{index "conditional execution", "ternary operator", "?: operator", "conditional operator", "colon character", "question mark"}}

Quyida muhokama qilinadigan oxirgi mantiqiy operator unary yoki emas, balki uchta qiymatda ishlaydigan _ternary_ operatoridir. U savol belgisi va ikki nuqta bilan bunday yoziladi:

```
console.log(true ? 1 : 2);
// → 1
console.log(false ? 1 : 2);
// → 2
```

Bu _shartli_ operator deb ataladi (yoki ba'zan faqat _ternary_ operatori, chunki u bu turdagi yagona operatordir). Savol belgisining chap tomonidagi qiymat qolgan ikkita qiymatdan qaysi biri chiqishini "tanlaydi". To'g'ri bo'lsa, o'rtadagi qiymatni, noto'g'ri bo'lsa, o'ngdagi qiymatni tanlaydi.

## Bo'sh qiymatlar

{{index undefined, null}}

Maʼnoli qiymat yoʻqligini bildirish uchun “null” va “undefined” deb yozilgan ikkita maxsus qiymat mavjud. Bu ikki holatning o'zi qiymat hisoblanadi, lekin ular hech qanday ma'lumotga ega emaslar.

Ma'noli qiymatni keltirmaydigan tildagi ko'plab operatsiyalar (ba'zilarini keyinroq ko'rasiz) shunchaki "undefined" ni beradi, chunki ular _biroz_ bo'lsa ham qiymat qaytarishi kerak.

"Undefined" va "null" o'rtasidagi ma'no farqi JavaScript dizaynidagi xatolik desak ham bo'ladi chunki ular ko'oincha bir-biridan faqr qilmaydi. Agar siz ushbu qiymatlardan foydalanishda muammolarga duch kelishdan qo'rqsangi,z ularni bir-biri bilan almashtirib ishlatish mumkinligini ta'kidlab o'tmoqchiman.

## Turlarning avtomatik o'rgarishi

{{index NaN, "type coercion"}}

Kirish qismida men JavaScript siz bergan deyarli har qanday dasturni, hatto g'alati ishlarni bajaradigan dasturlarni ham qabul qilish uchun o'z qoidalarini chetlab o'tishi haqida aytib o'tgandim. Buni quyidagi holatlarorqali yaqqolroq ko'rish mumkin:

```
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```

{{index "+ operator", arithmetic, "* operator", "- operator"}}

Agar operator "noto'g'ri" qiymat turiga qo'llanilsa, JavaScript ko'pincha siz xohlagan yoki kutmagan qoidalar to'plamidan foydalanib, bu qiymatni kerakli turga o'zgartiradi. Bunga _((tur majburlash))_ deyiladi. Birinchi ifodadagi “null” “0” ga, ikkinchi ifodadagi “5” esa 5ga (satrdan raqamga) aylanadi. Uchinchi iborada `+` son qo'shishdan oldin qatorni birlashtirishga harakat qiladi, shuning uchun 1  "1" ga (raqamdan satrga) aylantiriladi.

{{index "type coercion", [number, "conversion to"]}}

Raqamga aniq tarzda mos kelmaydigan narsa (masalan, “five” yoki “undefined”) raqamga aylantirilsa, siz “NaN” qiymatini olasiz. "NaN" bo'yicha keyingi arifmetik operatsiyalar "NaN" ni ishlab chiqarishda davom etadi, shuning uchun agar siz ulardan birini kutilmagan joyda topsangiz, tasodifiy turdagi konvertatsiyalarni qidiring.

{{index null, undefined, [comparison, "of undefined values"], "== operator"}}

`==` yordamida bir xil turdagi qiymatlarni solishtirganda, natijani tahmin qilish oson: har ikkala qiymat bir xil bo'lganda true qiymatga erishishingiz kerak, `NaN` hollari bundan mustasno. Ammo turlar har xil bo'lsa, JavaScript nima qilish kerakligini aniqlash uchun murakkab va chalg'ituvchi qoidalar to'plamidan foydalanadi. Aksariyat hollarda u qiymatlardan birini boshqa qiymat turiga aylantirishga harakat qiladi. Biroq, operatorning har ikki tomonida "null" yoki "undefined" bo'lsa, u faqat ikkala tomon "null" yoki "undefined" bo'lsagina, true qiymat hosil qiladi.

```
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```

Bunday qoidalar ko'pincha foydalidir. Qiymatning “null” yoki “undefined” o‘rniga haqiqiy qiymatga ega ekanligini tekshirmoqchi bo‘lsangiz, uni “==” (yoki “!=`) operatori yordamida “null” bilan solishtirishingiz mumkin.

{{index "type coercion", [Boolean, "conversion to"], "=== operator", "!== operator", comparison}}

Agar biror narsa "false" aniq qiymatiga tegishli yoki yo'qligini tekshirmoqchi bo'lsangiz, `0 == false` va `" " == false` kabi iboralar ham avtomatik turdagi konvertatsiya tufayli true ni hosil qiladi. Hech qanday turdagi konvertatsiyalar sodir bo'lishini _xohlamasangiz_, ikkita qo'shimcha operator mavjud: `===` va `!==`. Birinchisi, qiymat boshqasiga _aniq_ teng yoki yo'qligini tekshiradi, ikkinchisi esa uning _aniq_ teng emasligini tekshiradi. Demak, `"" === false` kutilganidek false natijaga ega.

Kutilmagan turdagi konvertatsiyalar sizni chalg'itib yubormasligi uchun uchta belgili taqqoslash operatoridan himoyalangan holda foydalanishni tavsiya qilaman. Ammo ikkala tomonning turlari bir xil bo'lishiga ishonchingiz komil bo'lsa, qisqaroq operatorlardan foydalanishda muammo bo'lmaydi.

## Mantiqiy operatorlarning qisqa tutashuvi

{{index "type coercion", [Boolean, "conversion to"], operator}}

`&&` va `||` mantiqiy operatorlari har xil turdagi qiymatlarni o`ziga xos tarzda boshqaradi. Ular nima qilish kerakligini hal qilish uchun chap tomonidagi qiymatni mantiqiy turga o'zgartiradilar, lekin operatorga va ushbu konvertatsiya natijasiga qarab ular  chap yoki o'ng tomodagi qiymatni _asl_ holatini qaytaradilar.

{{index "|| operator"}}

Masalan, `||` operatori, agar u true ga aylantirilishi mumkin bo'lsa, qiymatni chap tomondagi qiymatni qaytaradi va aks holda o'zining o'ng tomonidagi qiymatni qaytaradi. Bu qiymatlar boolean bo'lsa va boshqa turdagi qiymatlar uchun ta'sir ko'rsatsa, kutilgan natijaga erishish mumkin.

```
console.log(null || "user")
// → user
console.log("Agnes" || "user")
// → Agnes
```

{{index "default value"}}

Biz ushbu funksiyadan standart qiymatga qaytish usuli sifatida foydalanishimiz mumkin. Agar sizda bo'sh bo'lishi mumkin bo'lgan qiymat bo'lsa, uning o'rniga `||` belgisini qo'yishingiz mumkin. Agar boshlang'ich qiymat false ga aylantirilishi mumkin bo'lsa, siz uning o'rniga konvertatsiyani amalga oshira olasiz. Satrlar va raqamlarni mantiqiy qiymatlarga aylantirish qoidalari `0`, `NaN` va bo'sh satr (`"  "`) `false`, qolgan barcha qiymatlar esa `true` deb hisoblanadi. Shunday qilib, `0 || -1`, `-1` ni va `" " || "!?" `, `"!?"` ni hosil qiladi.

{{index "&& operator"}}

`&&` operatori ham xuddi shunday ko'rinishda, lekin aksincha teskari tartibda ishlaydi. Uning chap tomonidagi qiymat false ga aylanadigan qiymat bo'lsa, u bu qiymatni qaytaradi, aks holda u o'ng tomonidagi qiymatni qaytaradi.

Ushbu ikki operatorning yana bir muhim xususiyati shundaki, ularning o'ng tomonidagi qism faqat kerak bo'lganda baholanadi. `true || X` xolatida `X` nima bo'lishidan qat'i nazar, hatto u tushunarsiz ishlarni bajaruvchi dasturning bir qismi bo'lsa ham, natija true bo'ladi va `X` hech qachon baholanmaydi. Xuddi shu narsa "false && X" uchun ham amal qiladi, bu false "X" ni e'tiborsiz qoldiradi demakdir. Bunga _((qisqa tutashuvni baholash))_ deyiladi.

{{index "ternary operator", "?: operator", "conditional operator"}}

Shartli operator ham xuddi shunday ishlaydi. Ikkinchi va uchinchi qiymatlardan faqat tanlangani baholanadi.

## Xulosa

Ushbu bobda biz JavaScript qiymatlarining to'rt turini ko'rib chiqdik: raqamlar, satrlar, boolean qiymatlar va undefined qiymatlar.

Bunday qiymatlar ularning nomini (`true`, `null`) yoki qiymatini (`13`, `"abc"`) kiritish orqali yaratiladi. Siz qiymatlarni operatorlar bilan birlashtirishingiz va o'zgartirishingiz mumkin. Biz arifmetik (`+`, `-`, `*`, `/` va `%`), satrlarni birlashtirish (`+`), taqqoslash (`==`, `!=`, `===` ,`!==`, `<`, `>`, `<=`, `>=` ) va mantiq (`&&`, `||`) kabi binary operatorlari, shuningdek, bir nechta unar operatorlar (raqamni inkor qilish uchun `-`, mantiqiy inkor qilish uchun `!` va qiymat turini topish uchun `typeof`) va uchinchi qiymat asosida ikkita qiymatdan birini tanlash uchun uchlik operator (`?:`) kabilarni ko'rib chiqdik.

Bu sizga JavaScript-ni cho'ntak kalkulyatori sifatida ishlatish uchun yetarli ma'lumot beradi, lekin undan ko'p emas. [Keyingi bob](program_structure) bu ifodalarni asosiy dasturlarga birlashtira boshlaydi.
