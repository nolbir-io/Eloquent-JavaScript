{{meta {docid: values}}}

# Values, Types, and Operators

{{quote {author: "Master Yuan-Ma", title: "The Book of Programming", chapter: true}

Mashinaning yuzasi ostida dastur harakat qiladi. Harakat qilmasdan, u kengayadi va qisqaradi. Katta uyg'unlikda elektronlar tarqaladi va qayta guruhlanadi. Monitordagi shakllar faqat suv ustidagi to'lqinlardir. Mohiyat ko'rinmas holda quyida qoladi.
quote}}

{{index "Yuan-Ma", "Book of Programming"}}

{{figure {url: "img/chapter_picture_1.jpg", alt: "Picture of a sea of bits", chapter: framed}}}

{{index "binary data", data, bit, memory}}

Kompyuter dunyosida faqat ma'lumotlar mavjud. Siz ma'lumotlarni o'qishingiz, ma'lumotlarni o'zgartirishingiz, yangi ma'lumotlarni yaratishingiz mumkin, ammo ma'lumot bo'lmagan narsalarni eslatib bo'lmaydi. Bu ma'lumotlarning barchasi bitlarning uzun ketma-ketligi sifatida saqlanadi va shuning uchun printsipial jihatdan o'xshashdir.

{{index CD, signal}}

_Bits_ har qanday ikki qiymatli narsalar bo'lib, odatda nol va birliklar sifatida tavsiflanadi. Kompyuterning ichida ular yuqori yoki past elektr zaryadi, kuchli yoki zaif signal yoki CD yuzasida porloq yoki xira nuqta kabi shakllarni oladi. Diskret ma'lumotlarning har qanday qismi nol va birlar ketma-ketligiga qisqartirilishi va shu bilan bitlarda ifodalanishi mumkin.

{{index "binary number", radix, "decimal number"}}

Masalan, 13 raqamini bit bilan ifodalashimiz mumkin. U o'nlik son bilan bir xil ishlaydi, lekin 10 xil ((raqam)) o'rniga sizda faqat 2 bor va har birining og'irligi o'ngdan chapga 2 marta ortadi. Mana 13 raqamini tashkil etuvchi bitlar, ularning ostida raqamlarning og'irligi ko'rsatilgan:

```{lang: null}
   0   0   0   0   1   1   0   1
 128  64  32  16   8   4   2   1
```

Demak, bu ikkilik raqam 00001101. Uning nolga teng bo'lmagan raqamlari 8, 4 va 1 ni bildiradi va qo'shilib 13 ga etadi.

## Values

{{index [memory, organization], "volatile data storage", "hard drive"}}

Bitlar dengizini tasavvur qiling - ularning okeani. Oddiy zamonaviy kompyuterda o'zgaruvchan ma'lumotlarni saqlashda (ishchi xotira) 30 milliarddan ortiq bit mavjud. O'zgaruvchan xotira (qattiq disk yoki ekvivalenti) odatda bir necha marta ko'proq kattalikka ega.

Bunday miqdordagi bitlar bilan yo'qolmasdan ishlash uchun biz ularni ma'lumot bo'laklarini ifodalovchi qismlarga ajratishimiz kerak. JavaScript muhitida bu qismlar _((qiymat))s_ deb ataladi. Garchi barcha qiymatlar bitlardan iborat bo'lsa-da, ular turli rollarni o'ynaydi. Har bir qiymat o'z rolini belgilaydigan ((turi)) ga ega. Ayrim qiymatlar raqamlar, ba'zi qiymatlar matn bo'laklari, ba'zi qiymatlar funksiyalar va hokazo.

{{index "garbage collection"}}

Qiymat yaratish uchun siz shunchaki uning nomini chaqirishingiz kerak. Bu qulay. Siz o'zingizning qadriyatlaringiz uchun qurilish materialini yig'ishingiz yoki ular uchun pul to'lashingiz shart emas. Siz shunchaki bitta chaqirasiz va _whoosh_, sizda bor. Ular, albatta, havodan yaratilmagan. Har bir qiymat biror joyda saqlanishi kerak va agar siz ularning katta miqdorini bir vaqtning o'zida ishlatmoqchi bo'lsangiz, xotirangiz tugashi mumkin. Yaxshiyamki, bu bir vaqtning o'zida hammasi kerak bo'lgandagina muammo. Siz boshqa qiymatdan foydalanmasligingiz bilan, u o'z qismlarini keyingi avlod qadriyatlari uchun qurilish materiali sifatida qayta ishlash uchun qoldirib, tarqalib ketadi.

Ushbu bobda JavaScript dasturlarining atom elementlari, ya'ni oddiy qiymat turlari va bunday qiymatlar ustida ishlay oladigan operatorlar tanishtiriladi.

## Numbers

{{index [syntax, number], number, [number, notation]}}

_son_ turidagi qiymatlar, ajablanarli emas, raqamli qiymatlardir. JavaScript dasturida ular quyidagicha yoziladi:

```
13
```

{{index "binary number"}}

Buni dasturda ishlating va u kompyuter xotirasida 13 raqami uchun bit naqshini paydo bo'lishiga olib keladi.

{{index [number, representation], bit}}

JavaScript bitta raqam qiymatini saqlash uchun ma'lum miqdordagi bitlardan foydalanadi, ulardan 64 tasi. 64 bit bilan yaratishingiz mumkin bo'lgan naqshlar juda ko'p, ya'ni ifodalanishi mumkin bo'lgan turli raqamlar soni cheklangan. _N_ o'nlik ((raqam)) bilan siz 10^N^ sonni ifodalashingiz mumkin. Xuddi shunday, 64 ta ikkilik raqamni hisobga olsak, siz 2^64^ turli xil raqamlarni ifodalashingiz mumkin, bu taxminan 18 kvintillion (18, undan keyin 18 nol bilan). Bu juda ko'p.

Ilgari kompyuter xotirasi ancha kichikroq edi va odamlar o'z raqamlarini ifodalash uchun 8 yoki 16 bitli guruhlardan foydalanishga moyil edilar. Bunday kichik raqamlarni tasodifan _((toshib ketish))_ oson bo'lgan - berilgan bitlar soniga to'g'ri kelmaydigan raqam bilan yakunlanadi. Bugungi kunda, hatto cho'ntagingizga sig'adigan kompyuterlar ham juda ko'p xotiraga ega, shuning uchun siz 64-bitli qismlardan foydalanishingiz mumkin va siz faqat astronomik raqamlar bilan ishlaganda to'lib ketish haqida tashvishlanishingiz kerak.

{{index sign, "floating-point number", "sign bit"}}

18 kvintilliondan kam bo'lgan barcha butun sonlar JavaScript raqamiga mos kelmaydi. Bu bitlar manfiy raqamlarni ham saqlaydi, shuning uchun bitta bit raqamning belgisini bildiradi. Kattaroq muammo shundaki, butun bo'lmagan raqamlar ham ifodalanishi kerak. Buning uchun ba'zi bitlar kasr o'rnini saqlash uchun ishlatiladi. Saqlanishi mumkin bo'lgan haqiqiy maksimal butun son 9 kvadrillion (15 nol) oralig'ida ko'proq - bu hali ham yoqimli darajada katta.

{{index [number, notation], "fractional number"}}
Kasr sonlar nuqta yordamida yoziladi.

```
9.81
```

{{index exponent, "scientific notation", [number, notation]}}

Juda katta yoki juda kichik raqamlar uchun _e_ (_eksponent_ uchun) qo'shib, keyin raqamning ko'rsatkichini qo'shish orqali ilmiy belgilardan ham foydalanishingiz mumkin.

```
2.998e8
```

Bu  2.998 × 10^8^ = 299,800,000 ni anglatadi

{{index pi, [number, "precision of"], "floating-point number"}}

Yuqorida aytib o'tilgan 9 kvadrilliondan kichik butun sonlar (shuningdek, _((integer))s_ deb ataladi) bilan hisoblar har doim aniq bo'lishi kafolatlanadi. Afsuski, kasr raqamlari bilan hisob-kitoblar odatda emas. P (pi) ni o'nlik sonli sonlar bilan aniq ifodalab bo'lmagani kabi, ularni saqlash uchun faqat 64 bit mavjud bo'lsa, ko'p sonlar aniqligini yo'qotadi. Bu sharmandalik, lekin u faqat muayyan vaziyatlarda amaliy muammolarni keltirib chiqaradi. Muhimi, bundan xabardor bo'lish va kasrli raqamli raqamlarga aniq qiymatlar sifatida emas, balki yaqinlashish sifatida qarashdir.

### Arithmetic

{{index [syntax, operator], operator, "binary operator", arithmetic, addition, multiplication}}

Raqamlar bilan bog'liq asosiy narsa arifmetikdir. Qo'shish yoki ko'paytirish kabi arifmetik amallar ikkita raqam qiymatini oladi va ulardan yangi son hosil qiladi. Mana ular JavaScript-da qanday ko'rinishga ega:
```
100 + 4 * 11
```

{{index [operator, application], asterisk, "plus character", "* operator", "+ operator"}}

`+` va `*` belgilari _operatorlar_ deb ataladi. Birinchisi qo'shishni, ikkinchisi esa ko'paytirishni anglatadi. Operatorni ikkita qiymat orasiga qo'yish uni ushbu qiymatlarga qo'llaydi va yangi qiymat hosil qiladi.

{{index grouping, parentheses, precedence}}

Ammo misol "4 va 100 ni qo'shing va natijani 11 ga ko'paytiring" degan ma'noni anglatadimi yoki ko'paytirish qo'shishdan oldin amalga oshiriladimi? Siz taxmin qilganingizdek, ko'payish birinchi bo'lib sodir bo'ladi. Ammo matematikada bo'lgani kabi, qo'shimchani qavs ichiga o'rash orqali buni o'zgartirishingiz mumkin.

```
(100 + 4) * 11
```

{{index "hyphen character", "slash character", division, subtraction, minus, "- operator", "/ operator"}}

For subtraction, there is the `-` operator, and division can be done
with the `/` operator.

Operatorlar qavssiz birga paydo bo'lganda, ularni qo'llash tartibi operatorlarning _((ustunlik))_ bilan belgilanadi. Misol ko'paytirish qo'shishdan oldin kelishini ko'rsatadi. `/` operatori `*` bilan bir xil ustunlikka ega. `+` va `-` uchun ham xuddi shunday. `1 - 2 + 1` da bo'lgani kabi bir xil ustunlikka ega bir nechta operatorlar yonma-yon paydo bo'lganda, ular chapdan o'ngga qo'llaniladi: `(1 - 2) + 1`.

Ushbu ustuvorlik qoidalari sizni tashvishga soladigan narsa emas. Agar shubhangiz bo'lsa, shunchaki qavslar qo'shing.

{{index "modulo operator", division, "remainder operator", "% operator"}}

Yana bitta arifmetik operator bor, uni darhol taniy olmasligingiz mumkin. `%` belgisi _remainder_ operatsiyasini ifodalash uchun ishlatiladi. `X % Y` - `X`ni `Y`ga bo`lishning qolgan qismi. Masalan, `314 % 100` `14` ni, `144 % 12` esa `0`ni beradi. Qolgan operatorning ustuvorligi ko'paytirish va bo'lish bilan bir xil. _modulo_ deb ataladigan ushbu operatorni ham tez-tez ko'rasiz.

### Special numbers

{{index [number, "special values"]}}

JavaScript-da uchta maxsus qiymat mavjud bo'lib, ular raqamlar deb hisoblanadi, lekin oddiy raqamlar kabi harakat qilmaydi.

{{index infinity}}

Birinchi ikkitasi 'Infinity' va ' Infinity' bo'lib, ular ijobiy va salbiy cheksizliklarni ifodalaydi. `Infinity - 1` hali ham `Infinity` va hokazo. Biroq, cheksizlikka asoslangan hisob-kitoblarga juda ko'p ishonmang. Bu matematik jihatdan to'g'ri emas va u tezda keyingi maxsus raqamga olib keladi: `NaN'.

{{index NaN, "not a number", "division by zero"}}

`NaN` "raqam emas" degan ma'noni anglatadi, garchi u raqam turining qiymati bo'lsa ham. Siz, masalan, `0/0` (nol nolga bo`lingan), `Infinity - Infinity` yoki mazmunli natija bermaydigan boshqa raqamli amallarni hisoblashga harakat qilganingizda bu natijaga erishasiz.

## Strings

{{indexsee "grave accent", backtick}}

{{index [syntax, string], text, character, [string, notation], "single-quote character", "double-quote character", "quotation mark", backtick}}

Keyingi asosiy ma'lumotlar turi _((string))_. Satrlar ishlatiladi
matnni ifodalaydi. Ular o'z mazmunini qo'shtirnoq ichiga olish orqali yoziladi.

```
`Down on the sea`
"Lie on the ocean"
'Float on the ocean'
```

Satrning boshida va oxiridagi qo'shtirnoqlar bir-biriga mos kelsa, satrlarni belgilash uchun bitta tirnoq, qo'sh tirnoq yoki teskari belgilardan foydalanishingiz mumkin.

{{index "line break", "newline character"}}

Qo'shtirnoq orasiga deyarli hamma narsani qo'yish mumkin va JavaScript undan string qiymatini yaratadi. Ammo bir nechta belgilar qiyinroq. Qo'shtirnoq orasiga qo'shtirnoq qo'yish qanchalik qiyin bo'lishi mumkinligini tasavvur qilishingiz mumkin. _Newlines_ ([enter]{keyname} tugmachasini bosganingizda olinadigan belgilar) faqat satr teskari belgilar bilan iqtibos qilinganda qochmasdan kiritilishi mumkin.
(`` ` ``).

{{index [escaping, "in strings"], ["backslash character", "in strings"]}}

Bunday belgilarni satrga kiritish imkoniyatini yaratish uchun quyidagi belgi qo'llaniladi: iqtibosli matn ichida teskari chiziq (`\`) topilsa, undan keyingi belgi alohida ma'noga ega ekanligini bildiradi. Bu belgidan _qochish_ deyiladi. Teskari qiyshiq chiziq oldidan kelgan tirnoq satrni tugatmaydi, balki uning bir qismi bo'ladi. Teskari chiziqdan keyin `n` belgisi paydo bo'lsa, u yangi qator sifatida talqin qilinadi. Xuddi shunday, teskari chiziqdan keyin `t` belgisi ((tab belgisi)) degan ma'noni anglatadi.

Quyidagi qatorni oling:

```
"This is the first line\nAnd this is the second"
```

The actual text contained is this:

```{lang: null}
This is the first line
And this is the second
```

Albatta, qatordagi teskari chiziq maxsus kod emas, balki faqat teskari chiziq bo'lishini xohlaydigan vaziyatlar mavjud. Agar ikkita teskari chiziq bir-birining ortidan kelsa, ular birgalikda yiqilib tushadi va natijada olingan satr qiymatida faqat bittasi qoladi. "_Yangi qator belgisi `"`\n`"`._ kabi yoziladi" qatorini shunday ifodalash mumkin:

```
"A newline character is written like \"\\n\"."
```

{{id unicode}}

{{index [string, representation], Unicode, character}}

Satrlar ham kompyuter ichida mavjud bo'lishi uchun bir qator bitlar sifatida modellashtirilishi kerak. JavaScript-ning buni amalga oshirish usuli _((Unicode))_ standartiga asoslanadi. Ushbu standart sizga kerak bo'lgan deyarli barcha belgilarga raqam beradi, jumladan yunon, arab, yapon, arman va boshqalar. Agar bizda har bir belgi uchun raqam bo'lsa, qatorni raqamlar ketma-ketligi bilan tasvirlash mumkin.

{{index "UTF-16", emoji}}

Va JavaScript shunday qiladi. Ammo bir murakkablik bor: JavaScript-ning taqdimoti har bir satr elementi uchun 16 bitdan foydalanadi, bu esa 2^16^ gacha turli belgilarni tavsiflashi mumkin. Ammo Unicode bundan ko'proq belgilarni aniqlaydi - hozirgi paytda ikki baravar ko'p. Shunday qilib, ba'zi belgilar, masalan, ko'plab emojilar JavaScript satrlarida ikkita "belgi o'rnini" egallaydi. Biz bunga [bob ?](yuqori_tartib#kod_birliklari)da qaytamiz.

{{index "+ operator", concatenation}}

Satrlarni bo'lish, ko'paytirish yoki ayirish mumkin emas, lekin ularda `+` operatori _ ishlatilishi mumkin. U qo'shmaydi, lekin u _birlashtiradi_—ikkita ipni bir-biriga yopishtiradi. Quyidagi satr "birlashtiruvchi" qatorini hosil qiladi:

```
"con" + "cat" + "e" + "nate"
```

String qiymatlari ular ustida boshqa operatsiyalarni bajarish uchun ishlatilishi mumkin bo'lgan bir qator bog'langan funktsiyalarga (_methods_) ega. Bular haqida ko'proq [bo'lim?](ma'lumotlar#metodlar)da aytib o'taman.
{{index interpolation, backtick}}

Bitta yoki qo'sh tirnoq bilan yozilgan satrlar deyarli bir xil bo'ladi - yagona farq ularning ichida qaysi turdagi tirnoqdan qochish kerakligida. Odatda _((shablon literallari))_ deb ataladigan backtick iqtibosli satrlari yana bir nechta fokuslarni bajarishi mumkin. Chiziqlarni kengaytirish imkoniyatidan tashqari, ular boshqa qiymatlarni ham joylashtirishlari mumkin.
```
`half of 100 is ${100 / 2}`
```

Shablon literalida “${}” ichiga biror narsa yozsangiz, uning natijasi hisoblab chiqiladi, satrga aylantiriladi va shu pozitsiyaga kiritiladi. Misol "100 ning _yarmi 50_" ni hosil qiladi.

## Unary operators

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

Biz biror narsani baholash natijasini ko'rishni xohlayotganimizni ko'rsatish uchun misol kodida "console.log" dan foydalanamiz. Bu haqda ko'proq [keyingi bobda](dastur_structure).

{{index negation, "- operator", "binary operator", "unary operator"}}

Ko'rsatilgan boshqa operatorlarning barchasi ikkita qiymatda ishlaydi, ammo "typeof" faqat bitta qiymatni oladi. Ikki qiymatdan foydalanadigan operatorlar _binary_ operatorlar, bittasini oladiganlar esa _unary_ operatorlar deb ataladi. Minus operatoridan ikkilik operator sifatida ham, unar operator sifatida ham foydalanish mumkin.

```
console.log(- (10 - 2))
// → -8
```

## Boolean values

{{index Boolean, operator, true, false, bit}}

Ko'pincha "ha" va "yo'q" yoki "yoqish" va "o'chirish" kabi ikkita imkoniyatni ajratib turadigan qiymatga ega bo'lish foydalidir. Buning uchun JavaScript-da _Boolean_ turi mavjud bo'lib, u faqat ikkita qiymatga ega, haqiqiy va noto'g'ri, ular o'sha so'zlar sifatida yoziladi.

### Comparison

{{index comparison}}

Mantiqiy qiymatlarni ishlab chiqarishning bir usuli:

```
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
```

{{index [comparison, "of numbers"], "> operator", "< operator", "greater than", "less than"}}

`>` va `<` belgilari mos ravishda "kattaroq" va "kichikroq" ning an'anaviy belgilaridir. Ular ikkilik operatorlardir.

Ularni qo'llash mantiqiy qiymatga olib keladi, bu ularning bu holatda to'g'riligini ko'rsatadi.

Satrlarni xuddi shu tarzda solishtirish mumkin.

```
console.log("Aardvark" < "Zoroaster")
// → true
```

{{index [comparison, "of strings"]}}

Satrlarni tartiblash usuli taxminan alifbo bo'yicha, lekin aslida siz lug'atda ko'rishni kutganingizdek emas: katta harflar har doim kichik harflardan "kamroq" bo'ladi, shuning uchun "Z" < "a"` va alifbo bo'lmagan belgilar (!, - va boshqalar) ham buyurtmaga kiritilgan. Satrlarni solishtirganda, JavaScript ((Unicode)) kodlarni birma-bir taqqoslab, belgilarni chapdan o'ngga o'tadi.

{{index equality, ">= operator", "<= operator", "== operator", "!= operator"}}

Boshqa shunga o'xshash operatorlar `>=` (katta yoki teng), `<=` (kichik yoki teng), `==` (teng) va `!=` (teng emas).

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

"NaN" bema'ni hisoblash natijasini bildirishi kerak va shuning uchun u hech qanday _boshqa_ bema'ni hisoblar natijasiga teng emas.
### Logical operators

{{index reasoning, "logical operators"}}

Mantiqiy qiymatlarga nisbatan qo'llanilishi mumkin bo'lgan ba'zi operatsiyalar ham mavjud. JavaScript uchta mantiqiy operatorni qo'llab-quvvatlaydi: _and_, _or_ va _not_. Bular mantiqiy so'zlar haqida "fikrlash" uchun ishlatilishi mumkin.

{{index "&& operator", "logical and"}}

`&&` operatori mantiqiy _va_ ni ifodalaydi. Bu ikkilik operator bo'lib, unga berilgan ikkala qiymat ham rost bo'lsagina uning natijasi to'g'ri bo'ladi.

```
console.log(true && false)
// → false
console.log(true && true)
// → true
```

{{index "|| operator", "logical or"}}

`||` operatori mantiqiy _yoki_ ni bildiradi. Agar unga berilgan qiymatlardan biri rost bo'lsa, u true hosil qiladi.

```
console.log(false || true)
// → true
console.log(false || false)
// → false
```

{{index negation, "! operator"}}

_Not_ undov belgisi (`!`) sifatida yoziladi. Bu unar operator bo'lib, unga berilgan qiymatni o'zgartiradi — `!true` `yolg'on`ni, `!false` esa `true`ni beradi.

{{index precedence}}

Ushbu mantiqiy operatorlarni arifmetik va boshqa operatorlar bilan aralashtirganda, qavslar kerak bo'lganda har doim ham aniq bo'lmaydi. Amalda, odatda, biz hozirgacha ko'rgan operatorlarning `||` eng past ustunlikka ega ekanligini, keyin `&&`, so'ngra taqqoslash operatorlari (`>`, `==` va hokazo), keyin qolganlari. Bu tartib shunday tanlanganki, quyidagi kabi tipik iboralarda iloji boricha kamroq qavs kerak bo'ladi:

```
1 + 1 == 2 && 10 * 10 > 50
```

{{index "conditional execution", "ternary operator", "?: operator", "conditional operator", "colon character", "question mark"}}

Men muhokama qiladigan oxirgi mantiqiy operator unary emas, ikkilik emas, balki uchta qiymatda ishlaydigan _ternary_ operatoridir. U savol belgisi va ikki nuqta bilan shunday yoziladi:

```
console.log(true ? 1 : 2);
// → 1
console.log(false ? 1 : 2);
// → 2
```

Bu _shartli_ operator deb ataladi (yoki ba'zan faqat _ternary_ operatori, chunki u tildagi yagona operatordir). Savol belgisining chap tomonidagi qiymat qolgan ikkita qiymatdan qaysi biri chiqishini "tanlaydi". To'g'ri bo'lsa, o'rta qiymatni, noto'g'ri bo'lsa, o'ngdagi qiymatni tanlaydi.

## Empty values

{{index undefined, null}}

Maʼnoli qiymat yoʻqligini bildirish uchun “null” va “noandefined” deb yozilgan ikkita maxsus qiymat mavjud. Ular o'zlari qadriyatlardir, lekin ular hech qanday ma'lumotga ega emaslar.

Ma'noli qiymatni keltirmaydigan tildagi ko'plab operatsiyalar (ba'zilarini keyinroq ko'rasiz) shunchaki "aniqlanmagan" ni beradi, chunki ular _ba'zi_ qiymat berishi kerak.

"Aniqlanmagan" va "null" o'rtasidagi ma'no farqi JavaScript dizaynidagi tasodifdir va bu ko'pincha muhim emas. Agar siz haqiqatan ham ushbu qadriyatlar bilan o'zingizni tashvishga solishingiz kerak bo'lsa, men ularni asosan bir-birini almashtiradigan deb hisoblashni tavsiya qilaman.

## Automatic type conversion

{{index NaN, "type coercion"}}

Kirish qismida men JavaScript siz bergan deyarli har qanday dasturni, hatto g'alati ishlarni bajaradigan dasturlarni ham qabul qilish uchun o'z yo'lidan chiqib ketishini aytib o'tdim. Bu quyidagi iboralar bilan yaxshi namoyon bo'ladi:

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

Agar operator "noto'g'ri" qiymat turiga qo'llanilsa, JavaScript ko'pincha siz xohlagan yoki kutmagan qoidalar to'plamidan foydalanib, bu qiymatni kerakli turga o'zgartiradi. Bunga _((turi majburlash))_ deyiladi. Birinchi ifodadagi “null” “0” ga, ikkinchi ifodadagi “5” esa “5”ga (satrdan raqamga) aylanadi. Uchinchi iborada `+` son qo`shishdan oldin qatorni birlashtirishga harakat qiladi, shuning uchun `1` ``1`` ga (raqamdan qatorga) aylantiriladi.

{{index "type coercion", [number, "conversion to"]}}

Raqamga aniq tarzda mos kelmaydigan narsa (masalan, “besh” yoki “aniqlanmagan”) raqamga aylantirilsa, siz “NaN” qiymatini olasiz. "NaN" bo'yicha keyingi arifmetik operatsiyalar "NaN" ni ishlab chiqarishda davom etadi, shuning uchun agar siz ulardan birini kutilmagan joyda topsangiz, tasodifiy turdagi konvertatsiyalarni qidiring.

{{index null, undefined, [comparison, "of undefined values"], "== operator"}}

`==` yordamida bir xil turdagi qiymatlarni solishtirganda, natijani bashorat qilish oson: har ikkala qiymat bir xil bo'lganda haqiqatga erishishingiz kerak, `NaN` hollari bundan mustasno. Ammo turlar har xil bo'lsa, JavaScript nima qilish kerakligini aniqlash uchun murakkab va chalkash qoidalar to'plamidan foydalanadi. Aksariyat hollarda u qiymatlardan birini boshqa qiymat turiga aylantirishga harakat qiladi. Biroq, operatorning har ikki tomonida "null" yoki "aniqlanmagan" bo'lsa, u faqat ikkala tomon "null" yoki "aniqlanmagan" dan biri bo'lsa, rost hosil qiladi.

```
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```

Bunday xatti-harakatlar ko'pincha foydalidir. Qiymatning “null” yoki “aniqlanmagan” o‘rniga haqiqiy qiymatga ega ekanligini tekshirmoqchi bo‘lsangiz, uni “==” (yoki “!=`) operatori yordamida “null” bilan solishtirishingiz mumkin.

{{index "type coercion", [Boolean, "conversion to"], "=== operator", "!== operator", comparison}}

Agar biror narsa "false" aniq qiymatiga tegishli yoki yo'qligini tekshirmoqchi bo'lsangiz-chi? `0 == false` va `"" == false` kabi iboralar ham avtomatik turdagi konvertatsiya tufayli rostdir. Har qanday turdagi konvertatsiyalar sodir bo'lishini _xohlamasangiz, ikkita qo'shimcha operator mavjud: `===` va `!==`. Birinchisi, qiymat boshqasiga _aniq teng yoki yo'qligini tekshiradi, ikkinchisi esa uning aniq teng emasligini tekshiradi. Demak, `"" === false` kutilganidek noto'g'ri.

Kutilmagan turdagi konvertatsiyalar sizni qo'zg'atib yubormasligi uchun uchta belgi taqqoslash operatoridan himoyalangan holda foydalanishni tavsiya qilaman. Ammo ikkala tomonning turlari bir xil bo'lishiga ishonchingiz komil bo'lsa, qisqaroq operatorlardan foydalanishda muammo bo'lmaydi.

### Short-circuiting of logical operators

{{index "type coercion", [Boolean, "conversion to"], operator}}

`&&` va `||` mantiqiy operatorlari har xil turdagi qiymatlarni o`ziga xos tarzda boshqaradi. Ular nima qilish kerakligini hal qilish uchun chap tomonidagi qiymatni mantiqiy turga o'zgartiradilar, lekin operatorga va ushbu konvertatsiya natijasiga qarab ular _original_ chap tomon qiymatini yoki o'ng qo'l qiymatini qaytaradilar.

{{index "|| operator"}}

TMasalan, `||` operatori, agar u true ga aylantirilishi mumkin bo'lsa, qiymatni chap tomoniga qaytaradi va aks holda uning o'ng tomonidagi qiymatni qaytaradi. Bu qiymatlar mantiqiy bo'lsa va boshqa turdagi qiymatlar uchun o'xshash biror narsa qilsa, kutilgan ta'sirga ega.

```
console.log(null || "user")
// → user
console.log("Agnes" || "user")
// → Agnes
```

{{index "default value"}}

Biz ushbu funksiyadan standart qiymatga qaytish usuli sifatida foydalanishimiz mumkin. Agar sizda bo'sh bo'lishi mumkin bo'lgan qiymat bo'lsa, uning o'rniga `||` belgisini qo'yishingiz mumkin. Agar boshlang'ich qiymat noto'g'ri ga aylantirilishi mumkin bo'lsa, siz uning o'rniga almashtirasiz. Satrlar va raqamlarni mantiqiy qiymatlarga aylantirish qoidalari `0`, `NaN` va bo`sh qator (`""`) `yolg`on`, qolgan barcha qiymatlar esa `rost` deb hisoblanadi. Shunday qilib, `0 || -1` `-1` va `"" || hosil qiladi "!?"` `"!?"` beradi.

{{index "&& operator"}}

`&&` operatori xuddi shunday ishlaydi, lekin aksincha. Uning chap tomonidagi qiymat yolg'onga aylanadigan narsa bo'lsa, u bu qiymatni qaytaradi, aks holda u o'ng tomonidagi qiymatni qaytaradi.

Ushbu ikki operatorning yana bir muhim xususiyati shundaki, ularning o'ng tomonidagi qism faqat kerak bo'lganda baholanadi. `haqiqiy || holatida X`, `X` nima bo`lishidan qat`i nazar, hatto u dahshatli narsani qiladigan dastur bo`lsa ham, natija haqiqat bo`ladi va `X` hech qachon baholanmaydi. Xuddi shu narsa "false && X" uchun ham amal qiladi, bu noto'g'ri va "X" ni e'tiborsiz qoldiradi. Bunga _((qisqa tutashuvni baholash))_ deyiladi.

{{index "ternary operator", "?: operator", "conditional operator"}}

Shartli operator ham xuddi shunday ishlaydi. Ikkinchi va uchinchi qiymatlardan faqat tanlangani baholanadi.

## Summary

Ushbu bobda biz JavaScript qiymatlarining to'rt turini ko'rib chiqdik: raqamlar, satrlar, mantiqiy qiymatlar va aniqlanmagan qiymatlar.

Bunday qiymatlar ularning nomini (`true`, `null`) yoki qiymatini (`13`, `"abc"`) kiritish orqali yaratiladi. Siz qiymatlarni operatorlar bilan birlashtirishingiz va o'zgartirishingiz mumkin. Biz arifmetik (`+`, `-`, `*`, `/` va `%`), qatorlarni birlashtirish (`+`), taqqoslash (`==`, `!=`, `===`) uchun ikkilik operatorlarni ko'rdik. , `!==`, `<`, `>`, `<=`, `>=`) va mantiq (`&&`, `||`), shuningdek, bir nechta unar operatorlar ( Raqamni inkor qilish uchun `-`, mantiqiy inkor qilish uchun `!` va qiymat turini topish uchun `typeof`) va uchinchi qiymat asosida ikkita qiymatdan birini tanlash uchun uchlik operator (`?:`).

Bu sizga JavaScript-ni cho'ntak kalkulyatori sifatida ishlatish uchun etarli ma'lumot beradi, lekin ko'p emas. [Keyingi bob](dastur_structure) bu ifodalarni asosiy dasturlarga birlashtira boshlaydi.
