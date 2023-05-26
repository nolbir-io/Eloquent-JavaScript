{{meta {load_files: ["code/intro.js"]}}}

# Kirish

{{quote {author: "Ellen Ullman", title: "Qurilmaga yaqindan nazar: texnofiliya va uning noroziliklari", chapter: true}

 Biz tizimni o'z maqsadlarimiz uchun yaratmoqdamiz deb o'ylaymiz. Biz buni o'zimiz xohlagandek yaratayotganimizga ishonamiz ... Lekin kompyuter aslida bizga o'xshamaydi. U bizning juda nozik bir qismimiz: mantiq,tartib, qoida va ravshanlik tarafidan yaratilgan qurilmadir.

quote}}

{{figure {url: "img/chapter_picture_00.jpg", alt: "Picture of a screwdriver and a circuit board", chapter: "framed"}}}

Bu kitob ((kompyuter))larga ko'rsatma berish haqida. Kompyuterlar bugungi kunda huddi oddiy vint buragichlar kabi keng tarqalganiga qaramasdan biroz murakkab tuzilishga ega va har doim ham kompyuterlar orqali o'zimiz xohlagan ishlarni amalga oshirish oson kechavermaydi.


Agar siz kompyuterga elektron pochtadagi habarlarni ko'rsatish yoki hisoblash amallarini bajarish kabi oddiy va tushunish oson bo'lgan vazifalarni yuklatsangiz, shunchaki topshiriqqa oid ((ilova))dan foydalanishning o'zi kifoya qiladi. Lekin siz kompyuterga yuklatayotgan vazifa o'ziga xos, avvaldan belgilangan chegara va cheklovlarga ega bo'lmasa, unda bu vazifaga mo'ljallangan dasturning mavjud emaslik ehtimoli yuqori.

Bu masalada sizga ((dasturlash)) yordam beradi. _Dasturlash_ kompyuterga qanday vazifa bajarishi kerakligi haqida ma'lumot beruvchi buyruqlar jamlanmasi bo'lgan _dastur_ yaratish jarayonidir. Kompyuterlar indamas lekin juda sinchkov ekanligi dasturlashni zerikarli va asabbuzar qilib ko'rsatadi.

{{index [Dasturlash, tezlik], "lazzati"}}

Lekin buning yaxshi tarafi shundaki agar siz ushbu kamchiliklarni yengib o'tib, bu 'indamas' qurilma bilan til topisha olsangiz, dasturlash juda foydali mashg'ulot bo'ladi. Bu sizga qo'l bilan bajarganda _bir umr_ vaqt olishi mumkin bo'lgan vazifalarni soniyalar ichida bajarishga yordam beradi. Bu sizning kompyuteringiz avvallari bajara olmagan topshiriqlarni bajarishiga imkoniyat yaratib berish yo'li. Dasturlash abstrakt fikrlash uchun ham ajoyib mashg'ulot bo'la oladi.

Dasturlashning asosiy qismi ((dasturlash tillari)) orqali amalga oshiriladi. _Dasturlash tili_ kompyuterlarga ko'rsatmalar berish uchun sun'iy ravishda tuzilgan til hisoblanadi. Qizig'i shundaki, kompyuterlar bilan muloqotga kirishishning ko'plab taraflari biz o'zaro muloqot qilishimizdan andoza olgan. Huddi biz so'zlashadigan tillar singari dasturlash tillari ham so'zlar va iboralarni yangi usullarda birlashtirishga imkon beradi, bu esa doimo yangi tushunchalarni ifodalash imkoni demakdir.

{{index [JavaScript, "kompyuterdan kundalik foydalanish"], "qobiliyati"}}

1980 va 1990 yillardagi BASIC va DOS buyruqlari kabi tilga asoslangan interfeyslar kompyuterlar bilan o'zaro aloqa qilishning asosiy usuli edi. Ular o'rganish osonroq, lekin kamroq erkinlik imkonini beradigan interfeyslar bilan almashtirildi. Atrofga nazar soladigan bo'lsak, komyuter uchun mo'ljallangan ko'plab tillar hozir ham mavjud. Shunday tillardan biri JavaScript bo'lib, u har bir zamonaviy internet ((brauzer))iga o'rnatilgan va shuning uchun deyarli barcha qurilmalarda mavjud.

{{index "veb brauzer"ga qarang, brauzer}}

Qo'lingizdagi kitob sizga bu til bilan yaqinroqdan tanishish va uning yordamida ajoyib ishlarni amalga oshirishingizga hizmat qiladi.

## Dasturlash haqida

{{index [dasturlashning, "qiyinchiliklari"]}}

Kitobda JavaScriptga oid ma'lumotlardan tashqari dasturlashning asosiy tamoyillari bilan bilan ham tanishtirib o'tilgan. Dasturlash juda murakkab jarayon sifatida ma'lum bo'lib kelmoqda. Dasturlashdagi asosiy qoidalar sodda va tushunarli, ammo bu qoidalar asosida tuzilgan dasturlar o'z qoidalari va murakkabligini joriy qilish uchun yetarlicha murakkablashib boradi. Siz qaysidir ma'noda o'zingiz labirint qurmoqdasiz va unda shunchaki adashib qolishingiz ham mumkin.

{{index O'rganish}}

Bu kitobni o'qish davomida ko'plab qiyinchiliklarga duch keladigan paytlar bo'ladi. Agar siz dasturlashda yangi bo'lsangiz, kitob sizga o'rganib chiqish uchun juda ko'p yangi materiallar taqdim etadi. Keyinchalik ushbu materialning ko'p qismi qo'shimcha bog'liqliklar talab qiladigan usullar bilan _birlashtiriladi_.

Shunga yarasha harakat qilish bo'lsa o'zingizga bog'liq. Kitobdagi ma'lumotlarni to'liq anglab yetishga qiynalayotganingizda, o'zingizning imkoniyatlaringiz haqida hech qanday xulosa chiqarishga shoshilmang. Siz aqllisiz - siz shunchaki o'rganishdan to'xtamasligingiz kerak. Tanaffus qiling, ba'zi materiallarni qayta o'qing va misol qilib ko'rsatilgan dasturlarni va ((mashqlar))ni o'qib, tushunganingizga ishonch hosil qiling. O'rganish qiyin ish, lekin siz o'rgangan hamma narsa sizniki va ular keyingi o'rganish jarayonlarini osonlashtiradi.

{{quote {author: "Ursula K. Le Guin", title: "Zulmatning chap qo'li"}

{{index "Le Guin, Ursula K."}}

Harakat foydasiz bo'lib qolsa, ma'lumot to'plang; ma'lumot foydasiz bo'lib qolganda, uxlang.

quote}}

{{index [dasturning "o'ziga hosligi"], ma'lumot}}

Dastur juda ko'p narsalardan iborat. Bu dasturchi tomonidan yozilgan matn bo'lib, u kompyuterni o'zi bajaradigan ishni qilishga majburlovchi va yo'naltiruvchi kuchdir, u kompyuter xotirasidagi ma'lumotlardir, lekin shu bilan birqatorda u xuddi shu xotirada bajariladigan amallarni boshqaradi ham. Dasturlarni bizga tanish bo'lgan obyektlar bilan solishtirishga harakat qiladigan tahlillar biz kutgan natijani bermaydi. Yuzaki mos keladigan tahlillar asosan  qurilmaga oid bo'lib, unda juda ko'p alohida qismlar ishtirok etadi va hamma narsani aniq qilish uchun biz ushbu qismlarning o'zaro bog'lanishi va butun holda ishlashiga hissa qo'shish usullarini ko'rib chiqishimiz kerak.

((Kompyuter)) nomoddiy mashinalar uchun xost vazifasini bajaradigan jismoniy mashinadir. Kompyuterlarning o'zi faqatgina hayratlanarli darajada sodda va to'g'ri ishlarnigina amalga oshira oladi. Ularning juda foydali ekanligining sababi shundaki, ular bu ishlarni nihoyatda yuqori ((tezlik))da bajaradilar. Dastur bo'lsa o'z o'rnida juda murakkab ishlarni bajarish uchun ushbu oddiy harakatlarning juda ko'p sonini mohirona birlashtira oladi.

{{index [dasturlash, "lazzati"]}}

Dastur fikr homashyosi asosida vujudga keladi. Uni yaratish katta mablag' talab qilmaydi, u hech qanday og'irlikka ham ega emas, va u bizning matn yozayotgan qo'llarimiz ostida osongina rivojlanib boradi.

Lekin dastur yetarlicha nazorat ostida bo'lmasa uning  hajmi va ((murakkabligi)) nazoratdan chiqib ketadi va hatto uni yaratgan odamni ham chalkashtirib yuboradi. Dasturlashning asosiy muammosi ham ularni nazorat ostida ushlab turishdir. Dasturning go'zalligi uning yaxshi ishlashida. Dasturlash san'ati murakkablikni boshqarish qobiliyatidir. Ajoyib dastur shu murakkablik ichida sodda va tushunarli bo'ladi.

{{index "dasturlash usullari", "eng zo'r amaliyot"}}

Ba'zi dasturchilar bu murakkablikni o'z dasturlarida yaxshi tushunilgan kichik texnikalar to'plamidan foydalangan holda eng yaxshi tarzda boshqarishga ishonishadi. Ular qat'iy qoidalarni ("eng zo'r amaliyotlar") tuzib, dasturlarda bo'lishi kerak bo'lgan shakllarni belgilab qo'ydilar va ehtiyotkorlik bilan o'zlarining xavfsiz zonalarida qolishdi.

{{index Tajriba}}

Lekin bu nafaqat zerikarli, balki samarasiz usul hamdir. Yangi muammolar ko'pincha yangi yechimlarni talab qiladi. Dasturlash sohasi yosh va hali ham jadal rivojlanmoqda va u juda xilma-xil yondashuvlarga ega. Dasturni loyihalashda ko'plab dahshatli xatolarga yo'l qo'yiladi va siz ularni tushunishingiz uchun oldinga intilishingiz kerak. Yaxshi dastur qanday ko'rinishini his qilish qoidalar ro'yxatidan o'rganilmaydi, amalda ishlab chiqiladi.

## Nima uchun til muhim

{{index "dasturlash tili", "mashina kodi", "ikkilik ma'lumotlar"}}

Dastlab, hisoblash texnikasi paydo bo'lganida, dasturlash tillari mavjud emas edi. U paytdagi dasturlar quyidagi ko'rinishga ega bo'lgan:

```{lang: null}
00110001 00000000 00000000
00110001 00000001 00000001
00110011 00000001 00000010
01010001 00001011 00000010
00100010 00000010 00001000
01000011 00000001 00000000
01000001 00000001 00000001
00010000 00000010 00000000
01100010 00000000 00000000
```

{{index [dasturlash, "tarix"], "perfokarta", murakkablik}}

Bu 1 dan 10 gacha raqamlarni qo'shish va natijani chop etish uchun dastur: `1 + 2 + ... + 10 = 55'. U oddiy va virtual mashinada ishlash imkoniyatiga ega. Dastlabki kompyuterlarni dasturlash uchun katta hajmli svitchlarni to'g'ri chiziq bo'ylab o'rnatish yoki karton lentalarida teshiklarni teshib, ularni kompyuterga berish kerak edi. Ushbu jarayon qanchalik zerikarli va xatolarga moyilligini tasavvur qilishingiz mumkin. Hatto oddiy dasturlarni yozish ham juda katta aql va intizomni talab qilardi. Murakkab dasturlarni esa deyarli tasavvur qilib bo'lmas edi.

{{index bit, "sehrgar (qudratli)"}}

Albatta, bitlarning (bir va nol) bu sirli tuzilmasi  qo'lda kiritish dasturchiga kuchli sehrgar bo'lish hissini berdi. Va bu ishdan qoniqish nuqtai nazaridan qaralganda juda katta natija edi.

{{index xotira, ko'rsatma}}

Avvalgi dasturning har bir satri bitta ko'rsatmani o'z ichiga oladi. Va u ko'rsatmlarni quyidagicha ifodalash mumkin

 1. 0 raqamini 0-xotira joyida saqlang.
  2. 1-raqamni 1-xotirada saqlang.
  3. 1-xotira joyining qiymatini 2-xotira joyida saqlang.
  4. 2-xotira joyidagi qiymatdan 11 raqamini ayiring.
  5. Agar 2-xotira joyidagi qiymat 0 raqami bo'lsa, 9-ko'rsatma bilan davom eting.
  6. Xotira joyi 1 bo'lgan qiymatni 0-xotira joyiga qo'shing.
  7. Xotira joyi 1 bo'lgan qiymatga 1 raqamini qo'shing.
  8. 3-ko'rsatma bilan davom eting.
  9. Xotira joyi 0 bo'lgan qiymatni chop eting.

{{index o‘qilishi, nomlanishi, bog‘lanishi}}

Ushbu ko'rsatmalar nol va birdan tashkil topgan bitlar yig'indisidan ko'ra o'qilishi osonroq bo'lsa-da, u hali ham noaniq. Ko'rsatmalar va xotira joylari uchun raqamlar o'rniga nomlardan foydalanish yanada yaxshiroq tushunishga yordam beradi.

```{lang: "text/plain"}
 Set “total” to 0. // "Total" ni 0 ga qo'ying.
 Set “count” to 1. // "count" ni 1 ga qo'ying.
[loop]
 Set “compare” to “count”. // "compare" ni "count"ga qo'ying
 Subtract 11 from “compare”. // "compare" dan 11ni ayiring
 If “compare” is zero, [end] da davom eting. // Agar "compare" nol bo'lsa, 
 Add “count” to “total”. // "count"ni "total"ga qo'shing
 Add 1 to “count”. // "count"ga 1ni qo'shing
 Continue at [loop]. // [loop]da davom eting
[end]
 Output “total”. // Natija "total"
```

{{index loop, jump, "jamlash misoli"}}

Ushbu dastur qanday ishlashini ko'rdingizmi? Birinchi ikkita qator ikkita xotira joyining boshlang'ich qiymatlarini beradi: "total" hisoblash natijasini yaratish uchun ishlatiladi va "count" biz hozir ko'rayotgan raqamni hisoblab boradi. "compare" dan foydalanilgan qatorlar tushunarsiz bo'lishi mumkin. Dastur ishlashni to'xtishi mumkinmi yoki yo'qligini hal qilish uchun "count" 11 ga teng yoki yo'qligini bilishni xohlaydi. Bizning virtual mashinamiz ancha ibtidoiy bo'lgani uchun u faqat raqamning nolga teng yoki yo'qligini tekshira oladi va shunga asoslanib qaror qabul qiladi. Shunday qilib, u "count - 11" qiymatini hisoblash va shu qiymat asosida qaror qabul qilish uchun "compare" deb nomlangan xotira joyidan foydalanadi. Keyingi ikkita qator natijaga “count” qiymatini qo'shadi va har safar dastur “count” hali 11 emas deb qaror qilganda “count” ni 1 ga oshiradi.

Bu yerda ayni dasturning JavaScriptdagi ko'rinishi aks ettirilgan

```
let total = 0, count = 1;
while (count <= 10) {
  total += count;
  count += 1;
}
console.log(total);
// → 55
```

{{index "while loop", loop, [qavslar, bloklar]}}

Bu versiya bizga yana yangi ko'proq imkoniyatlar yaratib beradi. Eng muhimi, dasturning oldinga va orqaga o'tib amallarni bajarish usullarini belgilashning hojati yo'q. Buni "while" konstruktsiyasi bajaradi. U berilgan shart bajarilgunga qadar uning ostidagi blokni (qavslarga o'ralgan) bajarishda davom etadi. Bu shart `count <= 10` bo'lib, bu "_count_ 10 dan kichik yoki teng" degan ma'noni anglatadi. Biz endi  shunchaki muhim bo'lmagan tafsilot sifatida vaqtinchalik qiymat yaratishimiz va uni nolga solishtirishimiz shart emas. Dasturlash tillarining kuchli taraflaridan biri shundaki, ular biz uchun qiziq bo'lmagan tafsilotlarni mustaqil hal qila oladi.

{{index "console.log"}}

Dastur oxirida `while` konstruktsiyasi tugallangandan so'ng, natijani yozish uchun `console.log` operatsiyasidan foydalaniladi.

{{index "sum funksiyasi", "range funksiyasi", abstrakt, funksiya}}

Va nihoyat, agar bizda mos ravishda diapazondagi raqamlarning ((to'plam))ini yaratadigan va raqamlar to'plamining yig'indisini hisoblaydigan qulay “range” va “sum” amallari mavjud bo'lsa, dastur qanday ko'rinishga ega bo'lishi mumkin:

```{startCode: true}
console.log(sum(range(1, 10)));
// → 55
```

{{index readability}}

Yuqoridagi holatdan shuni xulosa qilish mumkinki, bir xil dastur ham uzun, ham qisqa, o'qilmaydigan va o'qilishi mumkin bo'lgan tarzda ifodalanishi mumkin. Dasturning birinchi versiyasi juda noaniq edi, oxirgisi esa deyarli inglizcha: 1 dan 10 gacha bo'lgan "`range`" dagi sonlarni  `sum`(yig'indisini) `log` (kiriting) dan iborat bo'ldi. (Biz [keyingi boblarda](ma'lumotlar) `sum` va `range` kabi amallarni qanday e'lon qilinishini ko'rib chiqamiz.)

{{index ["programming language", "power of"], composability}}

Yaxshi dasturlash tili dasturchiga kompyuter yuqori darajada bajarishi kerak bo'lgan harakatlar haqida gapirishga imkon beradi. Bu tafsilotlarni o'tkazib yuborishga yordam beradi, qulay dastur qurilishi uchun bloklarni taqdim etadi (masalan, `while` va `console.log`), o'z qurilish bloklarini (masalan, `sum` va `range`) aniqlashga imkon beradi va bu bloklarni tuzishni osonlashtiradi. .

## JavaScript nima?

{{index history, Netscape, brauzer, "veb ilova", JavaScript, [JavaScript, "tarix"], "World Wide Web"}}

{{indexsee WWW, "World Wide Web"}}

{{indexsee Web, "World Wide Web"}}

JavaScript 1995 yilda Netscape Navigator brauzerida veb-sahifalarga dasturlar qo'shish usuli sifatida taqdim etilgan. O'shandan beri til boshqa barcha asosiy grafik veb-brauzerlar tomonidan qabul qilingan. Bu zamonaviy veb-ilovalarni har bir harakat uchun sahifani qayta yuklamasdan to'g'ridan-to'g'ri ishlashingiz mumkin bo'lgan ilovalarni yaratishga imkon berdi. JavaScript an'anaviy veb-saytlarda ham interaktivlik va aqllilikning turli shakllarini ta'minlash uchun ishlatiladi.

{{index Java, naming}}

Shuni ta'kidlash kerakki, JavaScriptning Java deb nomlangan dasturlash tiliga deyarli hech qanday aloqasi yo'q. Shunchaki markting nuqtai nazaridan yetarlicha o'ylab chiqmasdan yaxshi nom tanlangan. JavaScript vujudga kelgan vaqtda, Java dasturlash tili juda ko'p sotildi va mashhurlikka erishdi. Kimdir bu muvaffaqiyatga erishish uchun harakatnig yaxshi usuli deb fikr bildirdi. Hozirda biz faqat ularning o'xshash nomlari haqida o'ylash bilan chegaralanib qoldik.

{{index ECMAScript, compatibility}}

Netscape'dan tashqarida tan olonganidan so'ng, JavaScript tilini qo'llab-quvvatlaydigan turli xil dasturiy ta'minot qismlari aslida bir xil til haqida gaplashishini ta'minlash maqsadida JavaScript tilining ishlash usulini tasvirlash uchun ((standart)) hujjat yozilgan. Bu standartlashtirishni amalga oshirgan Ecma International tashkiloti nomi bilan ECMAScript standarti deb ataladi. Amalda, ECMAScript va JavaScript atamalari bir-birining o'rnida ishlatilishi mumkin - ular bir xil til uchun ikkita nomdir.

{{index [JavaScript, "weaknesses of"], debugging}}

JavaScript haqida _salbiy_ fikr bildiradiganlar ham uchrab turadi. Va bu gaplarning aksariyati haqiqat. Mendan birinchi marta JavaScript-da biror narsa yozishni talab qilishganda, men tezda undan nafratlana boshladim. Dastur men yozgan deyarli hamma buyruqni qabul qilar, lekin uni men nazarda tutganimdan butunlay boshqacha tarzda talqin qilardi. Bu men dastur bilan nima qilayotganimni bilmasligim bilan bog'liq muammo edi, albatta, lekin bu yerda boshqa haqiqiy muammo ham bor: JavaScript o'zi ruxsat bergan narsalarda yuqori darajada liberaldir. Ushbu dizayndan maqsad yangi foydalanuvchilar uchun JavaScript-da dasturlashni osonlashtirish edi. Aslida, bu dasturlardagi muammolarni topishni qiyinlashtiradi, chunki tizim ularni foydalanuvchiga ko'rsatmaydi.

{{index [JavaScript, "flexibility of"], flexibility}}

Biroq, bu moslashuvchanlikning afzalliklari ham bor. Bu murakkab tillarda imkonsiz bo'lgan ko'plab texnikalar uchun imoniyat yaratadi, va siz ko'rib turganingizdek (masalan, [Chapter 10](modullar)) JavaScript-ning ba'zi kamchiliklarini bartaraf etish uchun ishlatilishi mumkin. Tilni to'g'ri ((o'rgangan)) va u bilan bir muddat ishlaganimdan so'ng, men JavaScript-ni _yoqtirishni_ o'rgandim.

{{index future, [JavaScript, "versions of"], ECMAScript, "ECMAScript 6"}}

JavaScript-ning bir nechta versiyalari mavjud. ECMAScript-ning 3-versiyasi JavaScript-ni eng ommaviy darajaga ko'tarilishi davrida, taxminan 2000 va 2010 yillar oralig'ida keng qo'llab-quvvatlanadigan versiya edi. Bu vaqt ichida tilni bir qator tubdan yaxshilangan va kengaytmalari rejalashtirilgan 4-versiyasi ustida ish olib borildi. Keng qo'llaniladigan tilni bunday tubdan o'zgartirish siyosiy jihatdan qiyin bo'lib chiqdi va 4-versiya ustida ishlash 2008 yilda to'xtatildi, bu esa 2009 yilda paydo bo'lgan juda kam shuhratga erishgan 5-versiyasiga olib keldi. Keyin 2015-yilda 6-versiya chiqdi, u 4-versiya uchun rejalashtirilgan baʼzi gʻoyalarni oʻz ichiga olgan katta yangilanishlarni  o'z ichiga oladi.
Shu yildan boshlab har yili uning versiyasida kichik o'zgarishlar bo'lib turadi.

Tilning rivojlanayotgani brauzerlar doimo yangilanib turishi kerakligini anglatadi va agar siz eski brauzerdan foydalansangiz, u barcha funksiyalarni qo'llab-quvvatlamasligi mumkin. Til dizaynerlari mavjud dasturlarni buzishi mumkin bo'lgan o'zgarishlarni amalga oshirishdan ehtiyot bo'lishadi, shuning uchun yangi brauzerlar hali ham eski dasturlarni ishga tushirishlari mumkin. Ushbu kitobda JavaScript-ning 2017- yilgi versiyasidan foydalanilgan.

{{index [JavaScript, "uses of"]}}

Veb-brauzerlar JavaScript ishlatiladigan yagona platformalar emas. MongoDB va CouchDB kabi ba'zi ma'lumotlar bazalari JavaScript-ni skript va so'rovlar tili sifatida ishlatadilar. Ish stoli va server dasturlash uchun bir nechta platformalar, ayniqsa ((Node.js)) loyihasi ([Chapter ](node)  mavzusi), brauzerdan tashqari JavaScript-ni dasturlash uchun muhitni ta'minlaydi.

## Kod va u bilan nima qilish kerak

{{index "reading code", "writing code"}}

_Kod_ - bu dasturlarni tashkil etuvchi matn. Ushbu kitobning aksariyat boblarida juda ko'p kod mavjud. Men kodni o'qish va yozish ((kod)) dasturlashning ((o'rganish)) ajralmas qismi ekanligiga ishonaman. Misollarni ko'rib chiqmaslikka harakat qiling - ularni diqqat bilan o'qing va tushuning. Avvaliga bu sekin va chalkash bo'lishi mumkin, lekin men va'da qilamanki, siz buni tezda o'zlashtirasiz. Xuddi shu narsa ((mashqlar)) uchun ham amal qiladi. Ishchi yechimni yozmaguningizcha, ularni tushunasiz deb o'ylamang.
solution.

{{index interpretation}}

Men sizga haqiqiy JavaScript tarjimonida mashqlar yechimlarini sinab ko'rishni tavsiya qilaman. Shunday qilib, qilayotgan ishingiz ish beryaptimi yoki yo‘qmi degan zudlik bilan fikr-mulohaza olasiz va umid qilamanki, siz ((tajriba)) vasvasasiga tushib, mashqlardan tashqariga chiqasiz.

{{if interactive

Ushbu kitobni brauzeringizda o'qiyotganda, siz barcha misol dasturlarni ularni bosish orqali tahrirlashingiz (va ishga tushirishingiz) mumkin.

if}}

{{if book

{{index download, sandbox, "running code"}}

Kitobdagi misol kodini ishga tushirish va u bilan tajriba o‘tkazishning eng oson yo‘li uni kitobning onlayn versiyasida [_https://eloquentjavascript.net_] (https://eloquentjavascript.net/) orqali izlashdir. U yerda siz har qanday kod misolini bosishingiz va uni tahrirlash va ishga tushirishingiz va u ishlab chiqaradigan natijani ko'rishingiz mumkin. Mashqlar ustida ishlash uchun [_https://eloquentjavascript.net/code_] (https://eloquentjavascript.net/code) saytiga o'ting, bu har bir kodlash mashqi uchun boshlang'ich kodni taqdim etadi va yechimlarni ko'rib chiqishga imkon beradi.

if}}

{{index "developer tools", "JavaScript console"}}

Agar siz ushbu kitobda belgilangan dasturlarni kitob veb-saytidan tashqarida ishga tushirishni istasangiz, biroz ehtiyot bo'lishingiz kerak bo'ladi. Ko'pgina misollar o'z-o'zidan va har qanday JavaScript muhitida ishlashi kerak. Ammo keyingi boblardagi kod ko'pincha ma'lum bir muhit uchun (brauzer yoki Node.js) yoziladi va faqat o'sha muhitda ishlashi mumkin. Bundan tashqari, ko'pgina boblar kattaroq dasturlarni taqdim etadi va ulardagi kod qismlari bir-biriga yoki tashqi fayllarga bog'liq. Veb-saytdagi [sandbox](https://eloquentjavascript.net/code) ma'lum bo'lim uchun kodni ishga tushirish uchun zarur bo'lgan barcha skriptlar va ma'lumotlar fayllarini o'z ichiga olgan Zip fayllarga havolalarni taqdim etadi.                              

## Ushbu kitob haqida 

Ushbu kitob taxminan uch qismdan iborat. Birinchi 12 bobda JavaScript dasturlash tili muhokama qilinadi. Keyingi yetti bob veb ((brauzerlar)) va ularni dasturlashda JavaScript dan foydalanish usullari haqida. Nihoyat, ohirgi ikkita bob ((Node.js)) deb ataluvchi JavaScript-ni dasturlashga mo'ljallangan boshqa muhitga bag'ishlangan.

Kitob davomida beshta _loyiha boblari_ mavjud bo'lib, ular sizga haqiqiy dasturlashning ta'mini berish uchun kattaroq misol dasturlarini tavsiflaydi. Tashqi ko'rinishi bo'yicha biz [yetkazib berish roboti](robot), [dasturlash tili](language), [platforma o'yini](game), [piksel chizish dasturi](paint) va [dinamik veb-sayt] yaratish bilan ishlaymiz.

Kitobning dasturlash tiliga bag'ishlangan qismi JavaScript tilining asosiy tuzilishi bilan tanishtiruvchi to'rtta bobdan boshlanadi. Ular [boshqaruv tuzilmalari] (dastur_strukturasi) (masalan, ushbu kirishda ko'rgan "while" so'zi), [funktsiyalar](funktsiyalar) (o'z qurilish bloklarini yozish) va [ma'lumotlar tuzilmalari](ma'lumotlar)ni joriy qiladi. Shundan so'ng siz asosiy dasturlarni yozishingiz mumkin bo'ladi. Keyingi, boblar [13](yuqori_tartib) va [19](ob'ekt) ko'proq _abstrakt_ kod yozish va murakkablikni nazorat ostida ushlab turish uchun funktsiyalar va ob'ektlardan foydalanish usullarini joriy qiladi.
[Birinchi loyiha bobidan](robot) soʻng kitobning dasturlash tili uchun ajratilgan qismi [xatolarni qayta ishlash va tuzatish](Error), [muntazam ifodalar](regexp) (matn bilan ishlash uchun muhim vosita), (murakkablikka qarshi boshqa himoya) va [sinxron dasturlash](async) (vaqt talab qiladigan hodisalar bilan ishlash)boʻlimlari bilan davom etadi. Loyihaning [ikkinchi loyihasi](language) kitobning birinchi qismini yakunlaydi.

Ikkinchi qism, [chapter 13] (brauzer) dan [19](paint) ga, JavaScript brauzeriga kirish huquqiga ega vositalarni tavsiflaydi. Siz narsalarni ekranda ko‘rsatishni ([14](dom) va [17] (canvas) bo‘limlari), foydalanuvchi kiritishiga javob berishni ([bob 18](voqea)) va tarmoq orqali muloqot qilishni o‘rganasiz. Ushbu qismda yana ikkita loyiha bobi mavjud.

Shundan so'ng, [bo'lim 20](node) Node.js-ni tavsiflaydi va [bo'lim 21](skillsharing) ushbu vosita yordamida kichik veb-sayt yaratadi.

{{if commercial

Nihoyat, [bob 20](tezkor) JavaScript dasturlarini tezlik uchun optimallashtirishda yuzaga keladigan ba'zi fikrlarni tavsiflaydi.

if}}

## Tipografik konventsiyalar

{{index "factorial function"}}

Ushbu kitobda "monospace" shriftda yozilgan matn dasturlarning elementlarini ifodalaydi - ba'zida ular o'z-o'zidan yetarli bo'lgan qismlardir va ba'zida ular faqat yaqin atrofdagi dasturning bir qismiga ishora qiladi. Dasturlar (ulardan bir nechtasini allaqachon ko'rgansiz) quyidagicha yozilgan:

```
function factorial(n) {
  if (n == 0) {
    return 1;
  } else {
    return factorial(n - 1) * n;
  }
}
```

{{index "console.log"}}

Ba'zan, dastur ishlab chiqaradigan natijani ko'rsatish uchun, kutilgan natija "// ->" bilan yoziladi.

```
console.log(factorial(8));
// → 40320
```

Omad yor bo'lsin!
