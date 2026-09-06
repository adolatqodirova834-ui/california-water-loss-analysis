# Quvurlardan oqib ketayotgan suv: qayerdan boshlash kerak

Kaliforniya suv korxonalarining 3541 ta yillik hisoboti tahlil qilindi.
Savol: yo'qotishni kamaytirishga mablag' ajratilsa, u qaysi tizimlarga
berilishi kerak?

**Qisqacha javob:** eng ko'p ishlatiladigan o'lchov — yo'qotish foizi —
ro'yxat tuzish uchun yetarli aniq emas. Uy boshiga hisoblangan yo'qotish
boshqa tizimlarni ko'rsatadi, pul qiymati esa uchinchi xil ro'yxat beradi.
Uchalasini birga ko'rish kerak.

Taqdimot uchun qisqa variant: [`xulosa.md`](xulosa.md)

Kodni brauzerda ochish (o'rnatish shart emas):
[![Colab'da ochish](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adolatqodirova834-ui/california-water-loss-analysis/blob/main/waterloss.ipynb)

---

## Muammo nima

Suv quvurlardan oqib ketadi — sizib chiqadi, hisoblanmaydi yoki ruxsatsiz
olinadi. Korxona ham suvni, ham daromadni yo'qotadi. Savol shuki, qayerni
birinchi ta'mirlash kerak.

Yo'qotishni o'lchashning ikki yo'li bor:

| O'lchov | Qanday o'qiladi |
|---|---|
| **Foiz** | "Berilgan suvning 10 foizi yo'qoldi" |
| **Uy boshiga** | "Har bir ulangan uyga kuniga 30 gallon yo'qoladi" |
| **ILI** | "Tarmoq texnik minimumdan 3 barobar ko'p yo'qotadi" |

Birinchisi keng tarqalgan. Ikkinchisi kamroq ishlatiladi, lekin
taqqoslash uchun to'g'riroq.

### Nima uchun foiz chalg'itadi

Ikki oila misoli. Birinchisi oyiga 1 million so'm ishlaydi va 200 mingini
yo'qotadi — 20 foiz. Ikkinchisi 20 million ishlaydi va 1 millionini
yo'qotadi — 5 foiz.

Foizga qarasak birinchisi yomonroq. Aslida ikkinchisi besh barobar ko'p
pul yo'qotmoqda.

Suv tizimlarida ham shunday. Kam suv ishlatadigan hududda ozgina yo'qotish
katta foiz beradi; ko'p suv ishlatadigan hududda katta yo'qotish kichik
foiz bo'lib ko'rinadi.

## Ma'lumot

Kaliforniya suv resurslari departamenti, tasdiqlangan suv yo'qotish
auditlari. Korxonalar bu hisobotni qonun bo'yicha topshiradi va ular
mustaqil tekshiruvdan o'tadi.

- Manba: [data.ca.gov](https://data.ca.gov/dataset/ca-urban-retail-water-system-water-loss-annual-loss-audit-data)
- Yuklab olingan: 2026-09-04
- Xom hajm: 609 tizim, 4924 hisobot, 2015-2025
- Tahlilga olingan: 428 tizim, 3541 hisobot, 2016-2024

Nima uchun hammasi emas: juda kichik tizimlar va suvni aholiga emas,
boshqa korxonalarga sotadigan ulgurji ta'minotchilar chiqarildi. Ularda
"uy boshiga" hisoblash mantiqsiz natija beradi. Batafsil: quyidagi texnik
bo'lim.

## Natijalar

### 1. Uch o'lchov, uch xil ro'yxat — lekin foiz chetda qoladi

Bir xil tizimlarni ikki o'lchov bo'yicha tartiblaganda ba'zilari 300 dan
ortiq o'ringa siljiydi.

| Tizim | Foiz bo'yicha o'rni | Uy boshiga o'rni |
|---|---|---|
| Groveland | 22 (yomon) | 326 (yaxshi) |
| Big Bear | 51 (yomon) | 368 (yaxshi) |
| Livingston | 311 (yaxshi) | 28 (yomon) |
| El Segundo | 419 (juda yaxshi) | 253 (o'rtacha) |

*428 tizim ichida. 1-o'rin — eng ko'p yo'qotadigan.*

Groveland kichik kurort hududi: kam suv ishlatiladi, shuning uchun
har qanday yo'qotish katta foiz bo'lib ko'rinadi. El Segundo esa aksincha —
ko'p suv ishlatiladi, shuning uchun sezilarli yo'qotish ham kichik foiz
bo'lib chiqadi.

**Lekin foiz butunlay noto'g'ri emas.** Umuman olganda ikki o'lchov bir
yo'nalishda harakat qiladi — bog'liqlik kuchli. Muammo aniqlikda: foizi
bir xil bo'lgan tizimlar orasida uy boshiga yo'qotish ikki-uch barobar
farq qilishi mumkin. Ro'yxat tuzish uchun bu yetarli emas.

Buni `sochma.png` da ko'rish mumkin: nuqtalar yuqoriga qarab ko'tariladi
(bog'liqlik bor), lekin keng tarqalgan (aniqlik yo'q).

**Uchinchi o'lchov masalani hal qiladi.** ILI (Infrastructure Leakage
Index) — real yo'qotishning texnik minimumga nisbati. Minimum tarmoq
uzunligi, ulanishlar soni va bosim asosida hisoblanadi, ya'ni ILI tarmoq
xususiyatlarini emas, boshqaruv sifatini o'lchaydi. U manba faylida
tayyor keladi.

Mablag' odatda "eng yomon 20 talik" bo'yicha taqsimlanadi. Uch o'lchov
bo'yicha shunday ro'yxat tuzilganda:

| Taqqoslash | 20 tadan ustma-ust tushadi |
|---|---|
| Gallon va ILI | **16** |
| Foiz va gallon | 7 |
| Foiz va ILI | 6 |
| Uchalasida ham | 5 |

**Ikkita mustaqil texnik ko'rsatkich bir-biriga mos keladi, foiz esa
ikkalasidan ham chetda qoladi.**

Bu tanlov masalasi emas. Agar foiz shunchaki boshqacha, lekin teng
darajada asosli o'lchov bo'lganida, u ikkalasidan bir xil masofada
turardi. Aslida gallon va ILI bir joyni ko'rsatadi, foiz esa boshqa joyni.

Bu AWWA yigirma yildan beri aytib kelayotgan tavsiyaning Kaliforniya
ma'lumotidagi o'lchangan tasdig'i.

### 2. To'qqiz yilda holat yaxshilanmadi

| Yil | O'rtacha yo'qotish (uy boshiga, kuniga) | Hisobot sifati bali |
|---|---|---|
| 2016 | 33.7 gallon | 61.1 |
| 2024 | 33.0 gallon | 66.1 |

Yo'qotish deyarli o'zgarmadi. Hisobotlarning sifati esa sezilarli oshdi.

**Tarozida tez-tez turish vaznni kamaytirmaydi.** O'lchash zarur, lekin
o'zi yetarli emas.

### 3. Uch xil savol, uch xil ro'yxat

| Savol | Javob |
|---|---|
| Qaysi tarmoq eng yomon holatda? | Casitas, Atwater, Reedley |
| Qayerda eng ko'p pul yo'qolmoqda? | Los-Anjeles (252 mln $), San-Diego (172 mln $) |
| Kimning raqamlariga ishonish mumkin? | Ba'zi yirik tizimlarda sifat past |

Uchalasi ham o'rinli savol, lekin javoblari mos kelmaydi. Shuning uchun
bitta reyting yetarli emas.

### 4. Yaxshi o'lchaydiganlar kamroq yo'qotadi

| Hisobot sifati | Nechta hisobot | O'rtacha yo'qotish |
|---|---|---|
| Past | 165 | 47.7 gallon |
| O'rta | 2200 | 34.3 gallon |
| Yuqori | 1176 | 25.7 gallon |

Naqsh aniq, lekin sababi noaniq. Ikkita tushuntirish bir xil natija
beradi: yaxshi boshqariladigan korxona ham yaxshi o'lchaydi, ham kam
yo'qotadi — yoki yomon o'lchov shunchaki yo'qotishni oshirib ko'rsatadi.
Bu ma'lumot ikkalasini ajrata olmaydi.

Shuning uchun quyidagi tavsiya ikkalasiga ham to'g'ri keladi.

## Tavsiya: tizimlarni uch toifaga bo'lish

**1. Darhol ta'mirlash.** Sifat yuqori, yo'qotish katta. Raqamga ishonish
mumkin, muammo haqiqiy.

**2. Avval o'lchashni to'g'rilash.** Sifat past, yo'qotish katta
ko'rinadi. Birinchi qadam — hisoblagichlarni tekshirish, quvur ta'mirlash
emas. Sababi: yo'qotish to'g'ridan-to'g'ri o'lchanmaydi, u ayirma orqali
topiladi, shuning uchun har qanday o'lchov xatosi shu raqamga yig'iladi.

Bu toifaning zarurligi uch mustaqil belgidan ko'rinadi: 15 auditda NRW
manfiy, 40 tasida real yo'qotish manfiy, va 1200 tasida (34 foiz) ILI
texnik minimumdan past chiqadi. Uchalasi ham bir xil manbaga ishora
qiladi — o'lchov noaniqligi qoldiq ko'rsatkichga yig'iladi.

**3. Kuzatuvda saqlash.** Katta shaharlar, o'rtacha holat. Kichik
yaxshilanish ham katta hajmda ko'p pul tejaydi.

## Ish qanday bajarildi

| Bosqich | Vosita | Natija |
|---|---|---|
| Tozalash, hisoblash, tahlil | Python (pandas) | `waterloss.ipynb` |
| Pivot jadvallar | Excel | `pivot_tahlil.xlsx` |
| Metodologik grafiklar | Python (matplotlib) | `taqsimot.png`, `sochma.png` |
| Panel | Power BI | `panel.png` |

Har bir muhim raqam kamida ikki xil vositada hisoblandi va natijalar
solishtirildi. Masalan yillik ko'rsatkichlar Python'da ham, Excel pivot
jadvalida ham hisoblanib, aynan bir xil chiqdi.

**Topilgan xato.** Manba faylining hujjatida bitta ustun "foiz" deb
yozilgan, aslida esa u foiz emas — barcha qiymatlar 100 barobar kichik
saqlangan. Bu tekshirilmasa, butun tahlil noto'g'ri chiqar edi.

## Nimalar qilinmadi

- **Sabab izlanmadi.** Qaysi tizimda nima uchun ko'p yo'qotayotgani bu
  ma'lumotdan aniqlanmaydi. Quvurlarning yoshi, bosim va tuproq haqida
  ma'lumot kerak.
- **Bashorat qilinmadi.** Mashinali o'qitish loyiha doirasiga kirmaydi.
- **Kichik tizimlar chiqarildi.**

**Pul raqamlari haqida.** Har bir korxona suvning tannarxini o'zi
belgilaydi, va bu narx to'rt barobar farq qiladi. Katta farqlarga ishonish
mumkin, yaqin o'rinlarni taqqoslamaslik kerak.

## Qadamlar

1. Ma'lumotni tanlash va yaroqliligini tekshirish — bajarildi
2. Savol, ko'rsatkichlar va chegaralarni belgilash — bajarildi
3. Tozalash va uchta jadval tayyorlash — bajarildi
4. Python'da tahlil, uch ko'rsatkich bo'yicha — bajarildi
5. Excel'da tekshiruv va pivot jadvallar — bajarildi
6. Power BI paneli — bajarildi
7. Grafiklar — bajarildi
8. Xulosa — bajarildi (`xulosa.md`)
9. GitHub'ga joylash

## Repozitoriya tarkibi

| Fayl | Nima |
|---|---|
| `README.md` | Shu hujjat |
| `xulosa.md` | Taqdimot uchun qisqa variant |
| `waterloss.ipynb` | Python: tozalash, hisoblash, tahlil, grafiklar |
| `pivot_tahlil.xlsx` | Excel pivot jadvallari |
| `taqsimot.png` | Yo'qotish taqsimoti |
| `sochma.png` | Ikki o'lchov bog'liqligi |
| `panel.png` | Power BI paneli |

Ma'lumot fayllari repozitoriyaga qo'shilmagan: manba ochiq va yuqoridagi
havoladan olinadi, tozalash bosqichi esa daftarda to'liq keltirilgan.

---

# Texnik tafsilotlar

Quyidagi qism metodika bilan qiziqadiganlar uchun: chegaralar qanday
tanlangani, qanday tekshiruvlar o'tkazilgani, qaysi qarorlar nima uchun
qabul qilingani.

## Formulalar

Loyihada ishlatilgan har bir formula: nima hisoblaydi, qaysi ma'lumotga
qo'llanadi, nima uchun aynan shu tanlangan.

### Ko'rsatkichlar

**Hisobga olinmagan suv foizi**

```
nrw_percent = nrw_af / water_supplied_af × 100
```

Hisobga olinmagan suv hajmini tizimga berilgan suvga bo'lamiz. Ikkalasi
ham akr-futda, shuning uchun birlik qisqaradi va sof foiz qoladi.

*Nima uchun:* bu sohada eng keng tarqalgan ko'rsatkich va hisobotlarda
shu ko'rinishda talab qilinadi. Loyihaning savoli aynan shu ko'rsatkich
haqida bo'lgani uchun uni chetlab o'tib bo'lmaydi.

**Ulanish boshiga kunlik real yo'qotish**

```
real_losses_gcd = real_losses_af × 325851 / kunlar / service_connections
```

Uch amal: akr-futni gallonga aylantiramiz (1 akr-fut = 325 851 gallon),
davr kunlariga bo'lamiz, ulanishlar soniga bo'lamiz.

*Nima uchun:* foiz iste'mol hajmiga bog'liq, bu esa emas. Bir xil
ta'minotchi turli hajmdagi hududlarga xizmat qilsa, faqat shu ko'rsatkich
ularni taqqoslashga imkon beradi. AWWA ham foiz o'rniga shuni tavsiya
qiladi.

**ILI (Infrastructure Leakage Index)**

```
ILI = CARL / UARL

UARL (gallon) = (5.41 × Lm + 0.15 × Nc + 7.5 × Lc) × P × D
```

CARL — joriy real yo'qotish. UARL — texnik minimum: yaxshi holatdagi,
yaxshi boshqariladigan tarmoqda erishish mumkin bo'lgan eng past sizish.
Lm quvur uzunligi (mil), Nc ulanishlar soni, Lc xususiy ulanish
quvurlarining uzunligi (mil), P bosim (psi), D davr kunlari.

Natija birliksiz: 1 texnik minimum, 4 esa minimumdan to'rt barobar ko'p
yo'qotish.

*Nima uchun:* gal/ulanish/kun bosimni ham, tarmoq geometriyasini ham
hisobga olmaydi. Yuqori bosimdagi tarmoq tabiiy ravishda ko'proq sizadi —
bu boshqaruv sifati emas, jismoniy qonuniyat. ILI shu ikkisini bo'luvchiga
kiritadi va boshqaruv sifatini o'lchaydi.

*Manba:* IWA Water Loss Task Force tenglamasi (Lambert va boshq., 1999).
Ma'lumot faylida ILI tayyor keladi, qayta hisoblanmagan.

*Cheklov:* UARL tenglamasi 3000 dan kam ulanishli tizimlarda ishonchsiz —
kichik tizimlar UARL bergan qiymatdan pastroq sizish ko'rsatishi mumkin.
Loyihadagi 3000 ulanish chegarasi shu bilan mos tushadi.

*Natija:* median ILI 1.38, ya'ni tipik tizim texnik minimumdan 40 foiz
ko'p yo'qotadi. Xalqaro me'yorda bu yaxshi ko'rsatkich.

*Muhim ogohlantirish:* auditlarning 34 foizida (1200 ta) ILI birdan past
chiqadi, 40 tasida esa manfiy. Manfiy ILI jismonan mumkin emas va u aynan
manfiy real yo'qotish uchragan 40 ta audit — bir xil son, tasodif emas.
Sabab: ILI ning suratida real yo'qotish turadi, u esa AWWA balansida
qoldiq sifatida hisoblanadi. Ya'ni ILI gal/ulanish/kun bilan bir xil zaif
joyni meros qiladi: o'lchov noaniqligi to'g'ridan-to'g'ri unga o'tadi.

Birdan past qiymatlarning uchta mumkin bo'lgan sababi bor: o'lchov xatosi
(ko'rinma yo'qotish oshirib baholansa qoldiq kamayadi), UARL tenglamasining
bosim oralig'idan chetga chiqish, yoki haqiqatan yaxshi tizimlar. Bu
ma'lumot ularni ajrata olmaydi.

### Yordamchi hisoblar

**Davr uzunligi**

```
kunlar = period_end − period_start
```

*Nima uchun:* qat'iy 365 qo'yilmagan. Auditlarning hammasi ham kalendar
yilini qamramaydi, ba'zilari iyuldan iyulgacha boradi. 365 qo'yilsa,
qisqa davrli auditlarda yo'qotish oshirib ko'rsatilardi.

**Ulanish zichligi**

```
zichlik = service_connections / mains_miles
```

*Nima uchun:* chakana va ulgurji ta'minotchini ajratish uchun. Ulgurji
ta'minotchida quvur uzun, ulanishlar esa o'nlab — ulanish boshiga
hisoblash u yerda mantiqsiz natija beradi (kuniga 148 000 gallongacha).

### Tekshiruv formulalari

**Suv balansi**

```
water_supplied_af − auth_consumption_af = apparent_losses_af + real_losses_af
```

*Nima uchun:* AWWA metodikasining asosiy tenglamasi. Har bir auditda
tekshirildi; chetlanish yaxlitlash darajasida chiqdi, ya'ni ma'lumot
ichida ziddiyat yo'q.

**Formulani manba bilan solishtirish**

```
farq = o'z hisobimiz − manbaning tayyor ustuni
```

*Nima uchun:* o'z formulamiz to'g'riligini mustaqil tasdiqlash uchun.
Aynan shu tekshiruvda birlik nomuvofiqligi topildi: manbaning NRW ustuni
lug'atda foiz deb ta'riflangan, aslida ulush sifatida saqlangan
(100 barobar farq).

### Statistik o'lchovlar

| O'lchov | Qayerda | Nima uchun |
|---|---|---|
| O'rtacha (`mean`) | Guruhlar taqqoslanganda | Guruhning umumiy og'irligini ko'rsatadi |
| Median | Tipik holat tavsiflanganda | Taqsimot o'ngga cho'zilgan, o'rtachani bir necha katta qiymat yuqoriga tortadi |
| 90-protsentil | Taqsimot tavsifida | Dumning qayerdan boshlanishini ko'rsatadi |
| Pearson korrelyatsiyasi | Ikki ko'rsatkich bog'liqligi | To'g'ri chiziqli bog'liqlik kuchini o'lchaydi |
| Spearman korrelyatsiyasi | Ikki ko'rsatkich bog'liqligi | O'rinlar bo'yicha o'lchaydi — reyting savoli uchun aynan shu kerak |

**Reyting va siljish**

```
o'rin = rank(ko'rsatkich, kamayish tartibida)
siljish = |o'rin_foiz − o'rin_gallon|
```

Kamayish tartibi tanlangan, ya'ni 1-o'rin eng ko'p yo'qotadigan tizim.
Modul olinadi, chunki siljish qaysi tomonga emas, qanchaligi muhim.

**Ro'yxatlar ustma-ustligi**

```
ustma-ustlik = |eng yomon N (A o'lchov) ∩ eng yomon N (B o'lchov)|
```

Ikki to'plamning kesishmasi olinadi.

*Nima uchun:* butun reytingdagi o'rtacha siljish chalg'itadi, chunki
ro'yxatning o'rtasida o'rinlar baribir beqaror. Qaror esa faqat tepadagi
ro'yxat bo'yicha qabul qilinadi, shuning uchun aynan o'sha qismning
barqarorligini o'lchash kerak.

### Excel formulalari

`pivot_tahlil.xlsx` da Python hisobidan mustaqil qayta hisoblash uchun
ishlatilgan.

| Formula | Varaq | Nima qiladi | Nima uchun |
|---|---|---|---|
| `COUNTIFS` | yillar_nazorat | Shartga mos qatorlarni sanaydi | Har yilgi auditlar soni |
| `AVERAGEIFS` | yillar_nazorat, reyting_farqi | Shartga mos qatorlarning o'rtachasi | Yil yoki tizim kesimida o'rtacha |
| `RANK` | reyting_farqi | Qiymatning ro'yxatdagi o'rni | Ikki ko'rsatkich bo'yicha reyting |
| `ABS` | reyting_farqi | Modul | O'rinlar orasidagi masofa |
| `SUM` | yillar_nazorat | Yig'indi | Jami auditlar soni |

*Nima uchun formulalar, tayyor qiymat emas:* natija qattiq yozilsa,
tekshiruv ma'nosini yo'qotadi. Formulalar ochiq turgani uchun har kim
manba ustunlaridan boshlab qayta hisoblab ko'rishi mumkin.

**Pivot jadvallardagi hisoblash turlari:** `Count` (auditlar soni) va
`Average` (uch ko'rsatkich bo'yicha). Pivot jadval median hisoblay
olmaydi — bu uning cheklovi va shuning uchun median faqat Python va
Power BI'da ishlatilgan.

### Power BI o'lchovlari

| O'lchov | Grafik | Nima uchun |
|---|---|---|
| `Median of real_losses_gcd` | Tizimlar reytingi | Bir tizimning bir necha yillik auditi bor; median chekka yilni yumshatadi |
| `Average of real_losses_gcd` by Year | Yillik tendentsiya | Yillar taqqoslanadi, guruh darajasida o'rtacha to'g'ri |
| `Sum of real_losses_cost_usd` | Pul reytingi | Savol "to'qqiz yilda jami qancha yo'qoldi" degani |
| `Average of validity_score` | Sochma diagramma | Tizimning o'rtacha o'lchov sifati |


## Ma'lumot sifati haqida eslatma

Auditlarda bo'sh qiymatlar deyarli yo'q, lekin bu ishonchlilik degani emas.
AWWA dasturi ba'zi maydonlarni majburiy qiladi va aniq ma'lumot bo'lmasa
standart taxminiy qiymat qo'yiladi. Shu sababli har bir auditning audit
ishonchliligi balli (0-100) tahlilda alohida o'lchov sifatida ishlatiladi,
filtr sifatida emas.

### Tekshiruv natijalari

**Suv balansi.** Barcha 4924 auditda tenglama tekshirildi: tizimga berilgan
suv minus ruxsat etilgan iste'mol, ko'rinma va real yo'qotishlar yig'indisiga
teng. Maksimal chetlanish 6e-10, ya'ni yaxlitlash xatosi darajasida.
Ma'lumot ichki ziddiyatga ega emas.

**Birlik nomuvofiqligi.** Manbadagi tayyor NRW ko'rsatkichi
(PI_FI_NON_REV_PERCENT_BY_VOL) ma'lumot lug'atida foiz sifatida
ta'riflangan, aslida esa ulush sifatida saqlangan. Farq aniq 100 barobar.
Bu ustunni tekshirmasdan ishlatish barcha foiz qiymatlarini yuz barobar
kichik ko'rsatgan bo'lardi.

**Formulalarni mustaqil tekshirish.** Ikkala ko'rsatkich ham mustaqil
hisoblanib, manbadagi tayyor qiymatlar bilan solishtirildi. Birlik
tuzatilgandan keyin ikkala farqning ham medianasi nolga teng (1e-13
darajasida). Tahlilda mustaqil hisoblangan qiymatlar ishlatiladi, manba
qiymatlari faqat tekshiruv uchun saqlanadi.

**Keyingi tekshiruvni talab qiladigan holatlar.** NRW foizining minimal
qiymati manfiy (-11.2%), maksimal qiymati esa aniq 100.0. Manfiy yo'qotish
jismonan mumkin emas, tekis 100 esa chegara qiymatiga o'xshaydi. Bu
holatlar tahlil bosqichida ko'rib chiqildi, natijasi 5-bo'limda.

### Audit ishonchliligi balli (validity_score)

Bu ball yo'qotish miqdorini emas, o'lchovning sifatini ko'rsatadi: auditdagi
raqamlar qanchalik haqiqiy o'lchovga tayanadi. 0 dan 100 gacha.

AWWA suv balansini to'ldirganda korxona har bir maydon uchun manba sifatiga
o'zi baho beradi: qiymat kalibrlangan hisoblagichdanmi, hujjatdanmi, yoki
taxminmi. Shu baholardan yig'indi ball chiqadi. Yuqori ball raqamlar
o'lchovga tayanishini, past ball ularning katta qismi taxmin ekanini
bildiradi.

Muhim: past ballli tizim ko'p ham, oz ham yo'qotayotgan bo'lishi mumkin.
Ball bu haqda hech narsa demaydi, u faqat raqamlarga qanchalik ishonish
mumkinligini ko'rsatadi.

## Taqqoslanadigan guruhni ajratish

Ulanish boshiga hisoblangan yo'qotish bo'yicha tuzilgan dastlabki reytingning
tepasidagi 15 ta auditning hammasi ulgurji ta'minotchilarga tegishli bo'lib
chiqdi (Water Agency, County Water Authority). Ular suvni aholiga emas,
boshqa korxonalarga sotadi: quvur uzunligi o'nlab mil, ulanishlar soni esa
4 dan 68 gacha. Natijada ulanish boshiga hisoblangan ko'rsatkich kuniga
148 000 gallongacha yetadigan mantiqsiz qiymat beradi.

Diqqatga sazovor holat: bir tizimda NRW foizi atigi 0.7% bo'lgani holda, u
ulanish boshiga hisoblangan reytingda birinchi o'rinlarda turadi.

**Ajratish mezoni.** Ulanish zichligi (ulanishlar soni / quvur uzunligi,
mil). AWWA qoidasiga ko'ra bir milga 30 dan kam ulanishi bor tizimlar uchun
ulanish boshiga hisoblash yaroqsiz; ular uchun bir mil quvurga kunlik
yo'qotish ishlatiladi.

**Natija:**

| Guruh | Auditlar | Tizimlar | O'rtacha gal/ulanish/kun |
|---|---|---|---|
| Chakana (zichlik >= 30) | 4524 | 560 | 37.4 |
| Ulgurji (zichlik < 30) | 400 | 79 | 764.2 |

Farq 20 barobar. Reytingdagilarning zichligi 0.3-2.9 oralig'ida, ya'ni
chegaradan o'n barobardan ko'proq past.

**Qaror.** Asosiy tahlil chakana tizimlar bilan cheklanadi. Ulgurji tizimlar
chiqarib tashlanmaydi, ular alohida ko'rsatkich bo'yicha ko'rsatiladi.

**Xulosa.** Boshlang'ich gipoteza kengaydi: muammo faqat foiz ko'rsatkichida
emas. Taqqoslanmaydigan tizimlar aralashtirilsa, ikkala ko'rsatkich ham
buziladi. Ko'rsatkichni tanlashdan oldin taqqoslanadigan guruhni ajratish
kerak.

## Tahlil natijalari

Quyidagilar chakana tizimlar bo'yicha (zichlik >= 30, ulanishlar >= 3000).
Ikkinchi chegara Kaliforniya qonunchiligidagi yirik chakana ta'minotchi
ta'rifiga va AWWA ogohlantirishiga mos keladi.

### Taqsimot: o'rtacha tipik holatni ko'rsatmaydi

| O'lchov | Qiymat |
|---|---|
| O'rtacha | 32.1 |
| Median | 24.3 |
| 90-protsentil | 65.2 |
| Maksimum | 505.3 |

Taqsimot o'ngga kuchli cho'zilgan: auditlarning 90 foizi 65 dan past, qolgan
10 foizi esa 505 gacha yetadi. Bir necha katta qiymat o'rtachani tortadi, va
u mediandan 32 foiz yuqori chiqadi.

Shakl `taqsimot.png` da ko'rinadi: chapda tik ko'tarilish, 15-25 oralig'ida
cho'qqi, keyin o'ngga uzun dum. Grafikning ko'rinish oralig'i 0-150 bilan
cheklangan (qiymatlarning 97 foizi), o'rtacha va median esa barcha 3541
auditdan hisoblangan.

**Ma'nosi:** tipik tizim ulanish boshiga kuniga taxminan 24 gallon
yo'qotadi, 32 emas. Quyidagi jadvallarda ikkala o'lchov ham keltiriladi.
Guruhlar orasidagi taqqoslash uchun o'rtacha qulay, tipik holatni tavsiflash
uchun median to'g'riroq.

### 1. Foiz ko'rsatkichi reyting uchun yetarli aniq emas

**Ikki ko'rsatkich qarama-qarshi emas.** Ularning o'rinlar bo'yicha
bog'liqligi kuchli: Spearman 0.81, Pearson 0.77. Ya'ni foiz umumiy
yo'nalishni to'g'ri ko'rsatadi, va "foiz butunlay noto'g'ri" degan da'vo
ma'lumot bilan tasdiqlanmaydi.

**Muammo aniqlikda.** Foizi 9 dan 11 gacha bo'lgan 438 auditda ulanish
boshiga yo'qotish quyidagicha tarqalgan:

| O'lchov | gal/ulanish/kun |
|---|---|
| 25-protsentil | 25.4 |
| Median | 33.5 |
| 75-protsentil | 41.8 |
| Maksimum | 304.8 |

Deyarli bir xil foizga ega tizimlarning yarmi 25 dan 42 gallongacha
oraliqda joylashgan, chekkalarda esa 300 dan oshadi. Sochma diagrammada
(`sochma.png`) bulut yelpig'ich shaklida kengayib boradi: foiz qancha
yuqori bo'lsa, noaniqlik shuncha katta.

**Nima uchun bu muhim.** Ustuvorlik reytingi alohida tizimning o'rnini
talab qiladi, umumiy yo'nalishni emas. Mablag' odatda "eng yomon 20 talik"
bo'yicha taqsimlanadi — shuning uchun hal qiluvchi savol shu ro'yxatning
o'lchovga qanchalik bog'liqligi.

Ikki ko'rsatkich bo'yicha tuzilgan
reytinglar solishtirildi: taqqoslash audit darajasida bajarilgan, ya'ni
2022 yildan keyingi har bir audit ikkala ko'rsatkich bo'yicha alohida o'rin
oladi va bir tizim bir necha marta qatnashadi. O'rinlar o'rtasidagi farq
850 gacha yetadi.

**Foiz oshirib ko'rsatadigan holat.** Iste'moli past hududlarda (Groveland,
Cambria, Big Bear, Santa Barbara) oz miqdordagi yo'qotish katta foiz beradi.
Groveland auditi foiz bo'yicha 99-o'rinda, ulanish boshiga esa
953-o'rinda.

**Foiz yashiradigan holat.** Iste'moli yuqori hududlarda katta hajm surat
sifatida turganda foiz kichik chiqadi. El Segundo foiz bo'yicha 976-o'rinda
(deyarli namunali), ulanish boshiga esa 171-o'rinda.

**Oqibati.** Mablag' foiz reytingiga qarab taqsimlansa, u kam iste'molli
hududlarga ketadi, El Segundo kabi tizimlardagi haqiqiy yo'qotish esa
e'tibordan chetda qoladi.

### 2. O'lchov sifati va o'lchangan yo'qotish o'rtasidagi bog'liqlik

| Audit ishonchliligi balli | Auditlar | O'rtacha gal/ulanish/kun | Median | O'rtacha NRW % |
|---|---|---|---|---|
| Past (<50) | 165 | 47.7 | 33.5 | 13.1 |
| O'rta (50-69) | 2200 | 34.3 | 26.0 | 9.8 |
| Yuqori (70+) | 1176 | 25.7 | 20.8 | 7.6 |

Bog'liqlik ikkala o'lchovda ham bir yo'nalishda, ya'ni u bir necha
chetlanish hisobiga yuzaga kelmagan. Ammo kuchi o'lchovga bog'liq: o'rtacha
bo'yicha past va yuqori guruh orasidagi farq 1.9 barobar, median bo'yicha
1.6 barobar. O'rtacha bog'liqlikni biroz kuchliroq ko'rsatadi.

Sababi mavjud ma'lumot bilan aniqlanmaydi, chunki ikkita
tushuntirish bir xil naqshni beradi: (a) ma'lumotini yomon yuritadigan
korxona tarmoqni ham yomon boshqaradi; (b) AWWA metodikasida real yo'qotish
qoldiq sifatida hisoblanadi, shuning uchun balansdagi barcha noaniqlik shu
ustunga yig'iladi.

**Bog'liqlikning kuchi cheklangan.** Har bir tizimning barcha yillari
o'rtachalanib, audit ishonchliligi balliga qarshi nuqtali diagrammada
tasvirlanganda aniq yo'nalish ko'rinmaydi: nuqtalar 35 dan 90 ballgacha
bo'lgan butun oraliqda bir tekis tarqalgan. Ya'ni bog'liqlik guruh
o'rtachalarida namoyon bo'ladi, alohida tizim darajasida esa kuchsiz.
Bitta tizimning yo'qotishini uning audit ishonchliligi balliga qarab bashorat
qilib bo'lmaydi.

**Tavsiya.** Past ballli auditlardagi yuqori yo'qotish qiymatlariga tayanib
ustuvorlik belgilash tavsiya etilmaydi. Bunday tizimlarda birinchi qadam
o'lchov sifatini yaxshilash bo'lishi kerak. Ayni paytda past ball
o'z-o'zidan tizimni ustuvor ro'yxatga kiritish uchun asos ham emas.

### 3. Yillar bo'yicha o'zgarish

Tahlil davri: 2016-2024, to'qqiz to'liq yil. 2015 yil (6 audit) va 2025 yil
(23 audit) chiqarildi: birinchisida ma'lumot yig'ish endi boshlangan,
ikkinchisi hali yopilmagan. Qolgan yillarda 375-402 audit.

| Yil | Auditlar | gal/ulanish/kun | NRW % | Audit ishonchliligi |
|---|---|---|---|---|
| 2016 | 396 | 33.7 | 9.4 | 61.1 |
| 2017 | 394 | 34.6 | 9.6 | 62.8 |
| 2018 | 402 | 31.4 | 9.1 | 64.0 |
| 2019 | 394 | 31.5 | 9.3 | 65.4 |
| 2020 | 389 | 34.7 | 9.4 | 65.7 |
| 2021 | 390 | 28.8 | 8.5 | 66.2 |
| 2022 | 387 | 29.9 | 8.8 | 64.4 |
| 2023 | 388 | 30.8 | 9.5 | 65.6 |
| 2024 | 375 | 33.0 | 9.6 | 66.1 |

**Yo'qotishda tendentsiya yo'q.** 2016 yilda 33.7, 2024 yilda 33.0. NRW
foizi ham o'zgarmagan: 9.4 va 9.6. Oraliqdagi tebranish 28.8 dan 34.7
gacha, yo'nalishsiz.

**Audit ishonchliligi balli oshgan, lekin 2021 yildan keyin barqarorlashgan.**
61.1 dan 66.2 gacha ko'tarilib, keyin shu darajada qolgan.

**Xulosa.** To'qqiz yil davomida o'rtacha yo'qotish o'zgarmadi, garchi shu
davrda korxonalar 3500 dan ortiq validatsiyadan o'tgan audit topshirgan va
o'lchov sifati sezilarli yaxshilangan bo'lsa ham. O'lchashning o'zi
yo'qotishni kamaytirmaydi: audit talabi zarur, lekin yetarli emas.

**Kuzatuv.** 2021 yilda ikkala ko'rsatkich ham eng past qiymatga tushgan
(28.8 va 8.5), keyin qaytib ko'tarilgan. Sabab bu ma'lumot bilan
aniqlanmaydi.

### 4. Pul qiymati bo'yicha reyting

Pul bo'yicha reyting butunlay boshqa tizimlarni ko'rsatadi. Los Angeles
birinchi o'rinda (252 mln USD), lekin ulanish boshiga yo'qotishi 32 gallon,
ya'ni o'rtachadan bir oz yuqori. Sabab: tizim juda katta, o'rtacha
samaradorlikda ham mutlaq yo'qotish ulkan chiqadi.

Ikkala reyting ham to'g'ri, lekin har xil savolga javob beradi:
- Gallon reytingi: qaysi tarmoq eng yomon holatda
- Pul reytingi: qayerda eng ko'p mablag' qaytariladi

**Pul raqamlarining ishonchliligi.** Xarajat ustuni tekshirildi. Auditlarning
kamida yarmida u yo'qotilgan hajm va korxonaning o'zgaruvchan tannarxi
ko'paytmasiga aniq teng, chekkalarda esa boshqa narx ishlatilgan: AWWA
metodikasi tarmoq quvvat chegarasida ishlaganda yo'qotilgan suvni chakana
narxda baholashga ruxsat beradi. Tannarxning o'zi ham keskin farq qiladi:
akr-fut uchun 307 dollardan (25%) 1284 dollargacha (75%), ya'ni to'rt
barobar. To'qqiz yillik summada inflyatsiya hisobga olinmagan.

Shu sababli katta farqlar ishonchli (Los Angeles ikkinchi o'rindagidan 1.5
barobar, o'ninchidan o'n barobardan ko'p oldinda), yaqin o'rinlarni esa
taqqoslab bo'lmaydi.

### 5. Manfiy qiymatlar: metodologiyaning izi

Tekshiruv bosqichida NRW foizining minimal qiymati manfiy (-11.2%), maksimali esa aniq
100.0 ekani qayd etilgan edi. Chegaralar qo'llangandan keyin tekshirildi.

| Holat | Auditlar | Ulushi |
|---|---|---|
| Manfiy NRW | 15 | 0.4% |
| Manfiy real yo'qotish | 40 | 1.1% |
| Aniq 100% NRW | 0 | — |

Aniq 100 foizli auditlar chakana yirik tizimlar orasida umuman yo'q: ular
chegaradan o'tmagan kichik tizimlarga tegishli bo'lgan.

**Manfiy qiymat nima anglatadi.** Hisobga olinmagan suv yoki tarmoqdan
sizib chiqqan suv jismonan manfiy bo'lolmaydi. Sabab metodologik: AWWA
balansida real yo'qotish qoldiq sifatida hisoblanadi (berilgan suvdan
ruxsat etilgan iste'mol va ko'rinma yo'qotishlar ayiriladi). Agar korxona
ko'rinma yo'qotishni oshirib baholasa, qoldiq manfiy chiqadi.

**Kutilmagan natija.** Bu auditlarning ishonchlilik balli past emas.
Ballar 52 dan 78 gacha, medianasi 66, ya'ni umumiy medianadan (64) hatto
biroz yuqori.

Bu ikkinchi topilmani mustahkamlaydi: ball metodikaning qanchalik puxta
qo'llanganini o'lchaydi, natijaning jismoniy ishonchliligini emas. Yaxshi
ball olgan korxona ham qoldiqni manfiy chiqaradigan baholash qilishi
mumkin.

**Qaror: bu auditlar tahlildan chiqarilmaydi.** Ular xato emas,
metodologiyaning tabiiy natijasi. Qiymatlari kichik (eng kattasi -11.2%,
qolganlari -2% atrofida), reytinglarga tushmaydi va o'rtachaga sezilarli
ta'sir qilmaydi. Ma'lumotni ko'rinishi uchun tozalash tahlil sifatini
oshirmaydi.

### Filtrlarning ta'siri

Chegaralar biror yilni nomutanosib kesmasligini tekshirish uchun har bir
filtrdan keyin qolgan auditlar sanaldi:

- Quvur uzunligi barcha auditlarda ko'rsatilgan (hech narsa kesilmaydi)
- Zichlik filtri har yili 7-8% ni chiqaradi (ulgurji ta'minotchilar)
- O'lcham filtri yana 22-24% ni chiqaradi (kichik tizimlar)
- Har yili taxminan 72% qoladi, ulush yillar bo'yicha barqaror

## Mustaqil tekshiruv

Barcha hisob-kitoblar bitta zanjirda bajarilgan: Python o'qigan, Python
hisoblagan, Python guruhlagan. Birinchi bosqichdagi xato keyingi
bosqichlarda takrorlanardi va o'zini ko'rsatmasdi.

Zanjirni uzish uchun ikkita mustaqil tekshiruv o'tkazildi.

**1. Manba ustunlari bilan solishtirish** (daftarning 6-bo'limi). Manba
faylida har ikkala ko'rsatkichning tayyor qiymati bor. O'z formulamiz
bilan hisoblangan natija ular bilan taqqoslandi: farq nolga teng chiqdi.
Aynan shu tekshiruvda birlik nomuvofiqligi aniqlandi (yuqoriga qarang).

**2. Excel'da qayta guruhlash** (`pivot_tahlil.xlsx`). Yillik
ko'rsatkichlar Excel formulalari bilan — `AVERAGEIFS` va `COUNTIFS` —
noldan qayta hisoblandi. Natija Python hisobiga aynan mos keldi:
2016 da 33.7, 2024 da 33.0 gal/ulanish/kun.

Ikki xil vosita, ikki xil formula yozilishi, bir xil javob.

## Excel: pivot jadvallar

`pivot_tahlil.xlsx` butun ma'lumot to'plamini Excel tomonidan mustaqil
ravishda qayta guruhlaydi.

| Varaq | Nima |
|---|---|
| `malumot` | 3541 audit, pivot manbasi |
| `pivot_yillar` | Yillar bo'yicha, 2016-2024 |
| `pivot_tizimlar` | 428 tizim bo'yicha |
| `yillar_nazorat` | AVERAGEIFS/COUNTIFS bilan nazorat |
| `reyting_farqi` | Ikki reytingdagi o'rinlar farqi, pws_id darajasida |
| `izoh` | Varaqlar va ustunlar izohi |

**Natija.** Yillik pivot Python hisobi bilan aynan mos keldi (2016:
33.7 gal/ulanish/kun, 2024: 33.0). Ikki mustaqil vosita, ikki xil formula
yozilishi, bir xil javob.

**Tahlil birligi haqida ogohlantirish.** `reyting_farqi` varag'i tizimlarni
taqqoslaydi (428 ta, barcha yillar o'rtachasi), yuqoridagi "850 pozitsiya"
raqami esa auditlarni (2022 yildan). Boshqa birlik, boshqa raqam; topilma
bir xil. Tizim darajasida eng katta siljish 317 pozitsiya (Big Bear
Community Services District: foiz bo'yicha 51-o'rin, gallon bo'yicha 368).

**Pivotning cheklovi.** Excel pivot jadvali median hisoblay olmaydi, faqat
o'rtacha. Panel medianada qurilgani uchun raqamlar farq qiladi, yo'nalish
esa bir xil.

## Grafiklar

Ikkita grafik Python'da (matplotlib) chizilgan. Ular Power BI panelidagi
grafiklarni takrorlamaydi, balki metodologik qarorlarni asoslaydi.

| Fayl | Nima ko'rsatadi | Nima uchun kerak |
|---|---|---|
| `taqsimot.png` | Yo'qotish taqsimoti, o'rtacha va median chiziqlari bilan | Medianani tanlash qarorining asosi |
| `sochma.png` | NRW foizi va gal/ulanish/kun bog'liqligi | Birinchi topilmaning ko'rinishi |


## Panel haqida eslatma

Reyting grafigi median bo'yicha qurilgan, o'rtacha bo'yicha emas: taqsimot
o'ngga cho'zilgani uchun o'rtacha bitta yomon yili bo'lgan tizimni barqaror
muammoli tizimdan yuqoriga chiqarib yuborardi. Yillik tendentsiya grafigida
o'rtacha qoldirilgan, chunki u yillarni o'zaro taqqoslaydi.

Yillar bo'yicha grafikning Y o'qi noldan boshlanadi. Qisqartirilgan o'q
29-36 oralig'idagi tebranishni keskin o'zgarishdek ko'rsatadi va
"yaxshilanish bor" degan noto'g'ri taassurot beradi. Noldan boshlangan
o'qda chiziq deyarli gorizontal, bu esa haqiqiy holatga mos.

### Panel va tahlil bir xil ma'lumotda

Dastlab panelga faqat o'lcham chegarasi (>= 3000 ulanish) qo'llangan edi,
zichlik chegarasi esa qo'llanmagan: zichlik ikkita ustunning nisbati
bo'lgani uchun uni Power BI'ning brauzer versiyasida oddiy filtr sifatida
berib bo'lmaydi.

Farq sanab chiqilgan: zichligi 30 dan past bo'lgan 20 ta tizimning 111 ta
auditi ortiqcha kirib qolgan edi, ya'ni panel ma'lumotining taxminan 3
foizi. Keyin manba fayllari ikkala chegara qo'llangan holda qayta
saqlanib, panelga yuklandi. Hozir panel ham, Python tahlili ham, Excel
pivotlari ham bir xil 3541 ta auditda ishlaydi.

**Metodologik izoh.** O'sha 111 ta audit ulgurji ta'minotchilarga tegishli
emas edi. Ularning zichligi 15 dan 30 gacha, ya'ni chegaraga yaqin; ulgurji
tizimlarda esa zichlik 0.3-2.9 oralig'ida. Ro'yxatda Joshua Basin, Phelan
Pinon Hills, Twentynine Palms, California City kabi cho'l va tog'li
hududlardagi chakana korxonalar bor: uylar bir-biridan uzoq, quvur uzun,
ulanishlar soni nisbatan kam.

Bu AWWA chegarasining tabiatini ko'rsatadi: 30 raqami model qo'llanish
doirasini belgilaydi, tizim turini emas. Zichligi 28.6 va 30.1 bo'lgan
ikkita tizim amalda bir xil, faqat biri chegaradan o'tadi, ikkinchisi
o'tmaydi. Chegara zarur, lekin u tabiiy chegara emas, kelishilgan chegara.

### Tashkilot va tizim bir xil narsa emas

Bir tashkilot bir necha alohida suv tizimini boshqarishi mumkin, va ular
xarakteri bo'yicha keskin farq qiladi. Masalan Santa Clarita Valley Water
Agency nomi ostida yettita tizim bor:

| pws_id | Ulanishlar | Zichlik |
|---|---|---|
| CA1910240 | 36 750 | 87.9 |
| CA1910017 | 32 385 | 89.9 |
| CA1910096 | 3 921 | 61.0 |
| CA1910250 | 2 786 | 78.1 |
| CA1910247 | 1 941 | 55.0 |
| CA1910255 | 1 204 | 72.5 |
| CA1910048 | 346 | 9.7 |

Chegaralar `pws_id` darajasida qo'llanadi, ya'ni to'g'ri darajada: 346
ulanishli va 9.7 zichlikdagi tizim chiqarib tashlanadi, 36 750 ulanishli
tizim esa qoladi.

Panelda esa guruhlash `supplier_name` bo'yicha ketadi. Pul reytingi uchun bu
to'g'ri, chunki savol "qaysi tashkilot ko'proq pul yo'qotmoqda" degani.
Ulanish boshiga hisoblangan reytingda esa bir tashkilotning turli
xarakterdagi tizimlari o'rtachalanadi va natija aniqligini yo'qotadi.

Aniq taqqoslash `pws_id` darajasida qilinishi kerak; panelda tashkilot nomi
o'qilishi qulay bo'lgani uchun tanlangan.
