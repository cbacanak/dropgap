# Dropgap — Plan

**Slogan:** See the bounce. Guess the rest.

**Depo:** `dropgap` · Web önce, mobil sonra.

**İsim gerekçesi:** Bu kategoride isimler tarif eder, çağrıştırmaz —
link paylaşıldığında kendini açıklaması gerekir. "Drop" ve "gap" ikisi
de gerçek kelime ve mekaniği anlatıyor: düşen bir şey ve senin açtığın
boşluk. Uydurma birleşimler (Blindspan, Arcmargin, VanishArc) zeki ama
ne olduğunu söylemiyor. Wordle da uydurma değildi — içinde "word" var.

Slogan mekaniği üç saniyede öğretiyor; ismin tek başına yapamayacağı
işi o yapıyor.

Karar acele değil, son güne kadar değişebilir. Alan adı müsaitliğini
Aşama 3'te kontrol et.

## 0. Mekanik

Bir top yukarıdan bırakılıyor, birkaç platformdan sekiyor. Sadece ilk
sekmeyi görüyorsun, sonra top görünmez oluyor. Nereye düşecek?

Oyuncu altta bir **kova** yerleştiriyor: tek jestle hem konumunu hem
**genişliğini** ayarlıyor — yatay hareket konum, dikey hareket genişlik
(yukarı = dar). Tutamaç yok, ekranın herhangi bir yerine dokunup çekmek
yeter; sürüklemeden sonra bırakmak düşürür.

- Dar kova = eminim = yüksek puan
- Geniş kova = emin değilim = düşük puan

**Neden kova, soyut bir aralık çubuğu değil:** Aynı mekanik ama kendini
açıklıyor. "Aralık genişliği" anlatmayı gerektirir, kova genişliği
gerektirmez. Öğrenme süresi sıfıra iniyor.

**Neden genişlik ayarlanabilir:** Sabit genişlikte bir kova, oyunun
bütün kimliğini siler. "Ne kadar eminsin" sorusu genişlikten geliyor;
sadece sağa sola kaydırmak onu ortadan kaldırır.

**Neden böyle:** Güveni ayrı bir soru yapmak turu ikiye böler ve akışı
kırar. Kova genişliği, kalibrasyonu ayrı bir adım olmaktan çıkarıp
seçimin kendisi yapıyor. Tek jest, tek ekran, tur ~15 saniye.

**Neden top görünmez oluyor:** Görünür kalsaydı oyun tahmin değil
refleks olurdu. Refleksin tavanı var, tahminin yok.

### Puanlama: toleranslı

İkili değil kademeli. Tam ortada / kenarda / dışarıda — üç seviye.

Salt tuttu-tutmadı puanlaması oyuncuyu sürekli sıfırla bırakır ve
oyunu sildirir. "Az kaldı" hissi devam ettiren şey.

Puan hâlâ kova genişliğiyle ters orantılı: dar kovada tam isabet en
yüksek, geniş kovada tam isabet düşük.

### Fizik öğrenilebilir olmalı

Sonuç oyuncuya rastgele hissettirirse sezgisini geliştiremez ve bırakır.
Yerçekimi, ivme ve sekme tutarlı olmalı; kaosa yaklaşan parametreler
"sezgimle çözemiyorum" hissi yaratır ve oyunu öldürür.

Bu, kapsam kuralı kadar bağlayıcı: her yeni tur tipi bu testten geçmeli.

**Sonsuz varyasyon:** Her turda platform açıları, boyutlar ve topun
ağırlığı değişiyor — ama çözülebilir sınırlar içinde. Ezber işe
yaramıyor, içerik üretmeye gerek yok. İçerik editörü yok — bu, kriter
listesinin en önemli maddesiydi.

## 0.1 Tur tipi havuzu

Aynı motor, aynı jest, farklı soru. Hepsi simülasyondan türüyor — yeni
oyun değil, aynı oyunun tur tipleri. Çeşitlilik ek içerik maliyeti
olmadan buradan geliyor.

Aşama 2'de sırayla eklenecek, hepsi birden değil:

- **Ne zaman?** — çizgiye kaç saniyede ulaşır (Aşama 1'in temel turu)
- **Ne kadar ileri?** — ekran dışına çıktıktan sonra nereye kadar gider
- **Nerede?** — duvarın arkasından hangi noktadan çıkar
- **Ne kadar hızlı?** — gözlemlenen hareketin hızı
- **Hangisi önce?** — iki nesneden hangisi hedefe önce varır
- **Sonraki kare** — animasyon durdurulur, devamı tahmin edilir
- **Tahmin et, sonra değiştir** — tahminini yaparsın, simülasyon çalışır,
  sonucu görürsün, ardından tek bir değişkene müdahale hakkın olur.
  Fizik anlayışını öngörmekten düzeltmeye taşıyor. Aynı motor, tek
  ek kontrol.
- **Müdahale noktası** — simülasyon ilerlerken tek bir anda müdahale
  hakkın var. Asıl soru ne yapacağın değil, ne zaman yapacağın.
  Yukarıdakinin keskin hali: müdahale sonuçtan sonra değil, sürecin
  ortasında.
- **Eşiği bul** — sistem iki farklı sonuca gidebilir; sen sonucu değil,
  sonucun değiştiği sınırı aralıkla işaretlersin. Diğerlerinden farklı
  bir zihin işi: çıktıyı değil, çatallanma noktasını tahmin ediyorsun.
  *Uyarı:* eşik fazla hassas olursa oyuncu haksızlık hisseder ve
  kandırılmış hisleri oyunu bıraktırır. Eşik bandını cömert tut,
  kaosa yaklaştırma.
- **Hangi taraf?** — aralık değil, ikili seçim. Kalibrasyon katmanını
  kaybettiği için ana tur olamaz; yalnızca ısınma/giriş turu olarak
  kullanılabilir.

Kural: her yeni tur tipi aynı aralık jestiyle oynanabilmeli. Jest
değişiyorsa tur tipi değil, başka oyundur — eklenmez.

**Havuz doldu.** Bundan sonra gelecek "ne kadar / nereye / kaç tane"
varyasyonları yeni mekanik değil, aynı motorun farklı parametresi.
Sekiz tur mekanik taraması sonunda üç şartı geçen tip sayısı sekiz.
Daha fazla tip çeşitlilik değil, dağınıklık getirir. Havuzu genişletmek
yerine mevcut tiplerin zorluk eğrisini işle.

## 1. Kapsam kuralı

Bu dosyada yazmayan yapılmaz. Yeni fikir "Sonraki tur"a yazılır.

**Kesin kapsam dışı:**
- Hesap ve giriş (Aşama 3'e kadar)
- Reklam
- Satın alma, para birimi, kozmetik
- Ses

## 2. Aşamalar

### Aşama 1 — Mekanik testi (2–3 gün)
Tek tur, tek sayfa, skor yok, paylaşım yok. Sadece oynanış.

**Test:** Kendin ve 5 kişi oynasın. Tek soru: **"bir daha" diyorlar mı?**
Demiyorlarsa dur. Mekanik tutmadıysa günlük mod, paylaşım ve mobil
hiçbir şeyi kurtarmaz.

Bu testin tamamı 3 günlük iş. Bir hafta kod yazdıktan sonra öğrenmekten
çok ucuz.

#### Aşama 1 durumu (10 Eyl 2026)

Kod yazıldı, `main`'de, GitHub Pages açık:
`https://cbacanak.github.io/dropgap/`

**Yapıldı:** Tek HTML, vanilla JS, canvas. Pointer olayları, sabit fizik,
tohumlu PRNG (`?seed=N`, tohum sol üstte, her turda artıyor). Üç seviyeli
sonuç; dar kovayla tam isabet büyük, geniş kovayla sessiz. Son yarım
saniyede %50 yavaşlama. Geri sayım yok. 600 tohum iki kez aynı sonucu
üretti.

**Canlı kontrol sonuçları (kullanıcı):** Sürükleme hissi, görünürlük
süresi, yavaşlama, fizik öğrenilebilirliği, sonuç vurgusu ve iOS Safari
— hepsi geçti. Ayar gerektiren bir şey çıkmadı.

**Plandan sapmalar (kabul edildi, gerekçeleriyle):**

- ~~**Gövde sürüklemesi genişliği de değiştiriyor** (yukarı = dar)~~ →
  **Jest üçüncü kez değişti, tutamaçlar kalktı (10 Eyl, PR #18).**
  Merdiven dar oynamaya itince tutamaç vuruş alanı dar kovada gövdeyi
  kapladı; parmak ortaya konsa bile tek duvar hareket ediyordu. Kullanıcı
  çözümü: tutamaç yok, yön var. Ekranın alt bandı tek dokunma alanı,
  hareket göreli (kova parmağa zıplamaz): yatay = konum, dikey = genişlik
  (yukarı = dar). İkisi aynı anda, her eksende 6 birim ölü bölge.
  Zihinsel model tek cümle — yatay nerede, dikey ne kadar emin — ve bu,
  oyunun zaten söylediği şeyin jest hali. Kaybedilen tek şey tek duvarı
  oynatmak; kimse asimetrik kova kurmuyor. Tutamaçların "boyut
  değişir" ipucu ilk tur metnine taşındı: "drag sideways to move, up to
  narrow." Eski jesti öğrenen beş kişiden ikisiyle yeniden kontrol
  gerekiyor. Jest tarihçesi: mokupta iki tutamaç → uygulamada gövde
  dikeyi de genişlik → şimdi sadece yön.
- **Fizik yumuşatıldı:** sekme 0.6, sürtünme 0.75, platform açıları
  6–18°. Sert değerlerle top duvara çarpıyordu; duvar sekmesi gizli
  dördüncü sekme olacağı için üretici duvara çarpan turları kabul
  etmiyor — reddetmek yerine eğimi ters çevirip yumuşatarak onarıyor.
- **Top hep platformun alçak yarısına düşüyor.** Yüksek yarıda eğim
  boyunca iki kez sekiyordu.
- **Tekrar oynatma kaybolma noktasından başlıyor,** görülen kısım soluk
  iz olarak çiziliyor.
- **Düşüşten önce 0,55 sn vuruş** — karar öncesi, §8.3'e aykırı değil.
- Arayüz İngilizce, ilk turda iki satır ipucu, sonuçtan sonra dokunmak
  yeni tur.

**İzlenecek risk:** Dar açı aralığı + hep alçak yarı = turlar
birbirine benzeyebilir. İlk testte hissedilmedi ama tavan riski (§8)
burada yaşıyor. On turdan sonra "hepsi aynı" hissi gelirse Aşama 2b
öne çekilir. Sonsuz modda 0,55 sn vuruş her turda tekrarlanacak; 2e'de
kısaltılabilir.

**Kalan:** Beş kişi testi. Sonuç CHANGELOG'a.

#### Çarpan merdiveni (10 Eyl, PR #5)

İlk sürümde çarpan `sabit / genişlik` idi: dar uçta sıkışık, geniş
uçta yayvan. ×2→×1 arası ekranın yarısı, ×1 altında kova büyümeye
devam ediyor ama rakam değişmiyordu — geri bildirim ölüyordu.

**Karar:** Kova genişliği on geometrik adıma kilitli, oran
`BUCKET_STEP_RATIO`. İlk değer 1,29 (×1 = 260, alanın %65'i) — 2c'de
geniş kovanın bedava devam hakkı olduğu görülünce 1,22'ye indirildi.
Güncel merdiven: ×10 = 26, ×9 = 32, ×8 = 39, ×7 = 47, ×6 = 58, ×5 = 70,
×4 = 86, ×3 = 105, ×2 = 128, ×1 = 156. ×1 alanın %49'u — güvenli ama
bedava değil. Çarpan artık genişliği tarif etmiyor, genişliğin kendisi.
Sürüklerken akıcı, bırakınca en yakın adıma oturuyor. ×1 ötesinde
genişleme yok. Varsayılan ×4.

Yan kazanç: paylaşım kartındaki "uzunluk = risk" artık tam olarak on
seviye.

**Sıradaki kaldıraç, gerekirse:** oran değil, orta bölge payı.

### Aşama 2 — Oyun döngüsü (3–5 gün)

**Sırayla eklenecek, hepsi birden değil.** Her adımdan sonra oyna ve
oynanışın bozulup bozulmadığına bak. Üç katman aynı anda girerse
hangisinin işe yaradığını ayırt edemezsin.

**2a — Seans.** 5 turluk seans, toplam skor. Başka hiçbir şey yok.
Bu, Aşama 1'in tek turunun çoğaltılmış hali; temeli sağlamlaştırır.

*2a durumu (10 Eyl, PR #7 + #8): geçti, ikinci denemede.*
İlk sürümde beş tur bir seans gibi hissetmedi — birikme ve ıskanın
bedeli görünmüyordu. Düzeltme: üst bantta tur tur dolan çubuk şeridi
(paylaşım kartı oyun sırasında kendiliğinden oluşuyor) ve sonuç anında
kovanın üstünde kazanılan puan ("+3"), adım değil. Kova genişliğinin
turlar arası taşınması hipotezi ayrı test için bekletildi, şerit
sonrası gerek kalmadı — kova her tur ×4'e sıfırlanmaya devam ediyor.
Puanlama: tam orta = çarpanın tamamı, kenar = yarısı yukarı
yuvarlanmış (`EDGE_SCORE = 0.5`), ıska = 0. ~~Iska turu götürür, seansı
değil~~ — *2c ile değişti: ıska seansı bitirir, birinci tur dahil.*
*İzlenecek:* ×8 ve üstünde orta ile kenar arası bir top yarıçapı;
orada tam mı yarım mı şans. Oyunda hissedilirse dar adımlarda orta
bölgeye mutlak alt sınır konur.

**2b — Zorluk eğrisi: bilgiyi azalt, hızı değil.** Duvar genişler, top
daha kısa süre görünür, ivme daha geç belli olur. Aynı fizik, daha az
veri. Hız ve ivme artırmak refleksi zorlar; bilgi azaltmak çıkarımı
zorlar — ve bu oyun bir çıkarım oyunu.
*Kontrol:* 5. tur hâlâ adil hissettiriyor mu, yoksa keyfi mi.

*2b durumu (10 Eyl, PR #9): adil, ama hissedilmedi.*
Tablo (`DIFFICULTY`, tur başına satır): sekme sonrası görünürlük
0,22→0,06 sn, düşüş öncesi vuruş 0,55→0,35 sn, platform gücü
%100→%60. Beşinci tur "yanlış tahmin ettim" hissettirdi — adil. Ama
zorluk hiç hissedilmedi.

**Tasarım gerçeği (bu turdan):** Karar, ilk sekmenin yönü ve platform
açılarından oluşuyor. Sekme sonrası süre kararda neredeyse rol
oynamıyor; oyuncu o pencereye bakmıyor. Platformları %60'a soldurmak
bilgi kaybı değil, hâlâ tam okunuyor. Yani 2b bilgiyi azalttı ama
kararın beslendiği bilgiyi değil.

**Karar:** Tablo zararsız, kalıyor; körlemesine ayarlanmıyor. Zorluk
bu oyunda zaten oyuncunun seçtiği şey (kova genişliği) ve tavanın
gerçekten var olup olmadığı ancak sonsuz modda (2e) görünür. Orada
tavan görünürse doğru kaldıraç belli: **platform okunurluğu** (açı
bilgisini azaltmak), sekme süresi değil.

*Dar kova tam/kenar meselesi:* ×8+ hissedilmedi, bekliyor.

**2c — Risk/ödül katmanı (§2.1).** Bir buton. Seans seviyesinde
devam et / dur kararı.
*Kontrol:* Oyuncu gerçekten duruyor mu, yoksa hep sonuna kadar mı
gidiyor? Hep gidiyorsa risk yeterince acıtmıyor demektir.

*2c durumu (10 Eyl, PR #10 + #11): kapandı, buton kaldırıldı, kural
kaldı.*
İki bulgu. Birincisi: geniş kova bedava devam hakkıydı — ×1 alanın
%65'i, ıskalanmıyordu; "genişle ve devam et" her zaman "al ve
bitir"den iyiydi. Düzeltme: `BUCKET_STEP_RATIO` 1,29→1,22, ×1 = 156
(alanın %49'u), ×4 varsayılanı 86. Geniş kova artık risk taşıyor,
×4 daha doğal hissettirdi.

İkincisi ve yapısal: daraltmadan sonra da buton hiç kullanılmadı, ve
kullanılmaması **doğru oyun.** Beş turluk seansta beşinci tur otomatik
aldığı için "devam"ın en kötü hali iki turluk kayıp; durmak neredeyse
hiç kârlı değil. Beş tur, şansını zorlama mekaniği için fazla kısa.

**Sonuç:** Seans riski butondan değil, **ıska-seansı-bitirir**
kuralından geliyor (birinci tur dahil — tek kural, özel durum yok;
"cepte bir şey yokken ıska turu götürür" alternatifi sıfırı güvenli
bölge yapacağı için reddedildi). Kural "kaybettim" dedirtti, buton
dedirtmedi. Genişlik zaten risk kadranı, kural zaten seans bedeli;
buton beş turluk seansta bir tasarımın iki kez konuşması. Kaldırıldı.
Buton 2e'de sonsuz modun çekirdeği olarak geri geliyor — açık uçlu
koşuda "al ve bitir" gerçekten karar.

Plandaki 2c teşhisi ("hep gidiyorsa risk acıtmıyor") yanlıştı: risk
acıtıyordu, durmak sadece kârsızdı.

**Sıra değişikliği:** 2e, 2d'nin önüne alındı. İki açık soru — tavan
var mı (2b), buton işe yarar mı (2c) — ikisi de yalnızca sonsuz modda
görünür.

**2e — Sonsuz mod: ne kadar ileri.** Açık uçlu koşu. Iskalayana kadar
oyna; skor, ıskalamadan önce ulaşılan en yüksek toplam. Yerel en iyi
skor (`localStorage`), üst bantta görünür. Sıralama yok, paylaşım yok.

*2e durumu (10 Eyl, PR #13, #14, #15): "al ve bitir" kalıcı olarak
kaldırıldı.*
Önce şansını zorlama olarak kuruldu (hap + ıska her şeyi götürür).
Kullanılmadı. Alınan puanın gideceği yer olmadığı teşhisiyle yerel en
iyi skor eklendi, hapta "best 41" göründü. Yine kullanılmadı — bu
sefer gerçek testle. Üç testte, iki modda, iki düzeltmeyle sıfır
kullanım.

**§2.1 kapanış:** Seans seviyesinde devam/dur kararı, bu oyunda bir
katman değil. Genişlik zaten "ne kadar eminsin" sorusu; buton aynı
soruyu ikinci kez soruyordu. Bir tasarım iki kez konuşuyorsa biri
fazladır — oyuncu hangisinin fazla olduğunu üç kez söyledi. Kod
duruyor, `BANK_OFFERED = false`; bir test kullanıcısı "durmak
istiyorum" derse tek satırla geri gelir.

Risk katmanı bu oyunda iki şeyden oluşuyor ve ikisi de çalışıyor:
**kova genişliği** (tur riski) ve **ıska-seansı-bitirir** (seans
riski). Üçüncüsüne yer yok.

*Süreç dersi:* Bir ara, düzeltme merge edilmeden "yine almadım"
denildi ve kaldırma kararı test edilmemiş sürüme dayandı. Fark edildi,
geri çekildi, gerçek testle tekrarlandı. Bundan sonra test raporuna
tohum numarası yazılır — hangi sürümün oynandığı oradan bellidir.

*Kontrol 2 sonucu — tavan doğrulandı:* Onuncu turdan sonra "hepsi
aynı" hissi geldi, 2b'nin öngördüğü yerde. İlk kaldıraç (PR #16,
`ENDLESS_PLATFORM_STYLE`: 6–10 %45, 11–15 uç noktalar, 16+ %60)
uygulandı ama "çubuklar çok erken gitti" — tek eksenli ve fazla dik.
*Kontrol 3:* 0,55 sn vuruş uzun koşuda sıkmadı; dokunulmuyor.

### 2e.1 Sonsuz mod zorluk merdiveni (kullanıcı tasarımı, 10 Eyl)

2b ve PR #16'daki tek eksenli tablolar çalışmadı. Kullanıcı dört ekseni
ve sıralama ilkesini buldu; ikisi yeni:

- **Platform sayısı.** Daha çok platform = daha çok gizli sekme. Adil,
  hepsi görünüyor. Hiç denenmemişti.
- **Alt kova adımının yükselmesi.** ×1 kalkar, sonra ×2. Saklanacak
  geniş kova kalmaz. 2c/2e'de üç kez çarpılan "geniş kova = bedava
  devam" sorununun doğrudan ve dürüst çözümü.
- **Topun sönme yeri, saniye değil geometri.** "İkinci platforma yakın"
  → "yolun yarısı" → "ilk sekmeden hemen sonra." 2b'nin neden hiçbir şey
  hissettirmediğini bu açıklıyor: 0,22 ile 0,06 sn ikisi de "sadece ilk
  sekme." Anlamlı fark, ikinci sekmeyi görmek ile görmemek.
- **Platform gücü ve çizimi** (önceki tablo, artık daha geç ve yumuşak).

**Sıralama ilkesi: her bantta tek şey değişir.** Oyuncu bir şeyin
değiştiğini fark eder ama iki şey birden değişmediği için "ne oldu"
demez. Eğri uçurum değil, merdiven.

`ENDLESS_LADDER` — tur bandı başına satır, sonsuz mod, tek yer:

| Tur | Platform | Top sönme yeri | Alt adım | Güç | Çizim |
|---|---|---|---|---|---|
| 1–3 | 2 | 2. platforma yakın | ×1 | %100 | çubuk |
| 4–6 | **3** | 2. platforma yakın | ×1 | %100 | çubuk |
| 7–9 | 3 | **yolun yarısı** | ×1 | %100 | çubuk |
| 10–12 | **4** | yolun yarısı | ×1 | %100 | çubuk |
| 13–15 | 4 | yolun yarısı | **×2** | %100 | çubuk |
| 16–18 | 4 | yolun yarısı | ×2 | **%65** | çubuk |
| 19–21 | 4 | **ilk sekmeden hemen sonra** | ×2 | %65 | çubuk |
| 22–24 | **5** | hemen sonra | ×2 | %65 | çubuk |
| 25–27 | 5 | hemen sonra | **×3** | %65 | çubuk |
| 28–30 | 5 | hemen sonra | ×3 | **%45** | çubuk |
| 31+ | 5 | hemen sonra | ×3 | %100 | **uç noktalar** |

Otuz turluk merdiven. Başlangıç mevcut sonsuzdan kolay (2 platform,
ikinci sekme görünür); çoğu oyuncu son satırları görmez — uzun kuyruk
sonsuz modun doğası, rekor bu yüzden anlamlı. İlk sekme her satırda
tam görünür. Alt adım yükselince merdivenden adım görünür şekilde
kalkar, sessiz değil. Varsayılan ×4 değişmez.

*Teknik risk:* 5 platform, 400 birimde duvara çarpmama + alçak yarı
kuralıyla sığmayabilir; üretici zorlanırsa 4'te kesilir.

*Test sorusu değişti:* "hepsi aynı mı" değil, **hangi satırda öldün ve
neden.** Sürekli öldüren bant genişletilir, fark edilmeyen bant
daraltılır.

*Uygulama notları (PR #17):* 5 platform sığdı — deneme başına başarı
%3,6, ortalama 29 deneme, en kötü 214, seviye başına 44 ms. Fark
edilmez; ama 22. turdan sonra tur geçişinde takılma hissedilirse çözüm
üretim değil önceden üretim (sıradaki tur bir önceki oynanırken
hazırlanır). 11. satır iki sütun değiştiriyor (güç %45→%100, çizim
çubuk→nokta) — bilerek öyle: kural sütun saymak için değil, oyuncunun
tek bir değişiklik algılaması için. 31. turda oyuncu tek şey görüyor,
çubuklar nokta oldu; noktaların tam güçte olması o değişikliğin gereği,
silik nokta "göremedim"e en yakın şey. Alt adım kalkınca eski kova
kesikli çizgiyle yenisine çöküyor, altında "×1 gone" — animasyon zaten
söylüyorsa yazı gider, oynarken hissedilecek.

### 2e.2 Gizli kurallar — sonraki tur, merdiven test edildikten sonra

Üreticinin iki sadeleştirmesi var, ikisi de oyuncuya büyük ipucu ve
ikisi de öğrenilebilir örüntü:

- **Temas garantisi.** Top her platforma değiyor; "n platform = n
  sekme." Çıkarımın yarısını hazır veriyor.
- **Alçak yarı.** Top hep eğimin aşağı tarafına düşüyor.

İkisi de sona doğru gevşetilebilir. Temas garantisini kaldırmak eldeki
en güçlü kaldıraç — soru "hangi açıdan sekecek"ten "sekecek mi"ye
dönüyor. **Adalet şartı:** es geçme, ilk sekmenin yönünden geometrik
olarak okunabilir olmalı; rastgele es geçme yazı turadır ve oyunu
öldürür. Üretici es geçmeyi belirgin üretmeli.

Yeri: merdivenin en sonu, uç noktalardan sonra, altıncı sütun olarak
("temas garantisi: evet/hayır", 34+ hayır). Diğer kaldıraçlar bilgiyi
azaltıyor, bu bilginin anlamını değiştiriyor — oyuncu önce görsel
zorluğa alışsın, sonra kural değişsin.

**Şimdi eklenmiyor.** Önce otuz satırlık merdiven oynansın; hangi
bantların çalıştığı görülsün. Aynı anda girerse ölçülen şey merdiven mi
kural değişikliği mi bilinmez.

### 2e.3 Merdiven testi ve kontrol noktası (10 Eyl)

**Merdiven testi geçti.** Ölümler 3, 5, 15, 20, 30 civarı — tek bantta
yığılma yok, uçurum değil. Sebep "yakalayamama", "göremedim" değil.
Merdiven adil ve çalışıyor.

**Yeni bulgu: sıfırdan başlamak sıkıcı.** Yirmide ölüp bir-on dokuzu
yeniden oynamak. Canı sıkan şey ölüm değil, kolay başlangıcın tekrarı.

**Su dökme modeli (bölüm bazlı, ıska = aynı bölümü tekrar) reddedildi.**
O modelde ıskanın maliyeti on beş saniye; kovayı en dara çek, tutana
kadar tekrar dene — risk sıfır. Oyunun kimliği yanılmanın bedelinde,
o model bedeli siler. Ayrıca bölüm sayısına, yani içeriğe dönüşür —
hibrit-casual yolu, bilerek girilmedi.

**Karar: bant kontrol noktası.** Iska koşuyu bitirmez, bandın başına
döndürür (yirmide ıska → 19). Kaybedilen şey birkaç tur, otuz tur
değil. Risk kalıyor, tekrar gidiyor. Ulaşılan en yüksek toplam ve best
korunuyor; koşu oyuncu çıkınca biter.

*Test:* Beş koşu, sıkılma gitti mi? Gittiyse 2e kapanır.
Gitmediyse sorun tekrar değil **aynılık** — her koşu aynı biçimde
başlıyor — ve o zaman 2d (ikinci tur tipi) devreye girer.

### 2e.4 Kontrol noktası testi ve dört bulgu (11 Eyl)

Kontrol noktası (PR #22) sıkılmayı çözdü — "1. round'a geri düşme
güzel." Ama dört bulgu çıkardı:

1. **Kural açığı: kontrol noktası + deterministik tohum = ezber.**
   Yirmide ıskala, on dokuza dön, aynı tur aynı yörüngeyle gelir; düşüş
   yerini gördün, ×10 çek, al. Su dökme modelinde korkulan şey arka
   kapıdan girdi. *Düzeltme:* tur tohumu (koşu tohumu, tur, o turun
   deneme sayısı) üçlüsünden türer; URL tohumu tekrarlanabilir kalır
   ama aynı tur iki kez görülmez.
2. **İlk sekme hep aynı yerde.** Top başlangıç x'i ve ilk platform dar
   aralıkta değiştiği için ilk sekme bilgi taşımıyor — oyuncu ona
   bakmayı bırakıyor. *Düzeltme:* üretici düşüş noktasını ve ilk
   platformu bütün genişliğe dağıtır, sekme yönü gerçekten değişir.
3. **Kesikli iz.** Görülen yol, top kaybolduktan sonra kesikli çizgi
   olarak kalır. Yeni bilgi vermez, hatırlatır — ama merdivenin sönme
   adımlarını görünür kılar: çizgi adım adım kısalır, yeni dünyada tam
   geri gelir. Oyuncu yapıyı anlatılmadan anlar.
4. **Merdiven fazla dik ve bantlar kısa.** → §2e.5.

*Sıra:* açık düzeltmesi (kural), ilk sekme (üretici), sonra iz +
merdiven v3 birlikte.

### 2e.5 Merdiven v3 — iki iç içe testere (kullanıcı tasarımı)

§2e.1'deki düz merdivenin yerine. Dış dişli platform sayısı, orta
dişli kesik seviyesi, iç dişli topun sönmesi. Her dünyada kesik
seviyesi tırmanır; her kesik seviyesinde top sönmesi baştan iner. Yeni
dünya: bir platform daha, çubuklar tama döner.

**Neden testere:** her yeni platform sayısı tam bilgiyle tanıtılıp
sonra sıkıştırılıyor — adil giriş. Sıfırlanma anı nefes veriyor ama
kolaylaşma değil, çünkü aynı anda platform ekleniyor. Kesikli izle
birleşince dünyanın içindeki düşüş görünür.

**Sönme tavanı 3. platforma yakın.** 4–5 platformda daha görünür olmak
saçma; 3 civarında kısıtlandı.

**Sönme dizileri:**
- 2 platform: 2. sekmeden sonra → 2.'ye yakın → 1–2 ortası → 1.'den
  hemen sonra (4)
- 3+ platform: 3.'ye yakın → 2–3 ortası → 2. sekmeden sonra → 2.'ye
  yakın → 1–2 ortası → 1.'den hemen sonra (6)

**Kesik türleri:** tam, hafif kesikli (uzun çizgi, küçük boşluk),
kesikli (eşit), daha kesikli (kısa çizgi, geniş boşluk), seyrek
noktalar. "Kaybolmaya yakın" ve "uç noktalar" **saklandı** — oyun
bitmiş hissi verir, sonraki dünyalara yer kalmaz.

`ENDLESS_LADDER` — adım başına 2 tur, kontrol noktası adım başı:

| Dünya | Plat. | Çubuk | Sönme | Adım | Tur | En geniş |
|---|---|---|---|---|---|---|
| 1 | 2 | tam | 4'lük | 4 | 1–8 | ×1 |
| 2 | 3 | tam | 6'lık | 6 | 9–20 | ×1 |
| 2 | 3 | hafif kesikli | 6'lık | 6 | 21–32 | ×1 |
| 2 | 3 | kesikli | 6'lık | 6 | 33–44 | ×1 |
| 3 | 4 | tam | 6'lık | 6 | 45–56 | ×2 |
| 3 | 4 | hafif kesikli | 6'lık | 6 | 57–68 | ×2 |
| 3 | 4 | kesikli | 6'lık | 6 | 69–80 | ×2 |
| 3 | 4 | daha kesikli | 6'lık | 6 | 81–92 | ×2 |
| 4 | 5 | tam | 6'lık | 6 | 93–104 | ×2 |
| 4 | 5 | hafif kesikli | 6'lık | 6 | 105–116 | ×3 |
| 4 | 5 | kesikli | 6'lık | 6 | 117–128 | ×3 |
| 4 | 5 | daha kesikli | 6'lık | 6 | 129–140 | ×3 |
| 4 | 5 | seyrek noktalar | 6'lık | 6 | 141–152 | ×3 |

Dünya 1 tanıtım, tek kesik seviyesi. Kesik seviyesi her dünyada bir
artıyor. En geniş kova tek yönlü: Dünya 3'te ×1, Dünya 4'ün ikinci
seviyesinde ×2 gidiyor. 152 tur, sonra Dünya 5+.

*Risk:* her dünyanın ilk yarısı bir öncekinin tekrarı gibi
hissedebilir. Oynayınca görülür.

*Test:* hangi dünyada, hangi kesik seviyesinde, hangi sönme adımında
öldün. Dağılım merdivenin haritası.

### 2e.6 Gelecek dünyalar — kesin eklenecek, sırayla

Yapının değeri bu: dünya = tek yeni kaldıraç, tam netlikle tanıtılıp
sıkıştırılır. Tablo veri, dünya eklemek satır eklemek. **Kural:** yeni
dünya, birileri sona ulaşınca eklenir; best skor verisi 153'e ulaşan
var mı gösterir.

Oyunun ilkeleriyle uyumlu olanlar — prosedürel, tek jest, bilgi
azaltan ama refleks istemeyen — sırayla:

1. **Temas garantisi kalkıyor** (§2e.2). Top bir platformu es
   geçebilir. Adalet şartı: es geçme ilk sekme yönünden okunabilir
   olmalı.
2. **Alçak yarı kalkıyor** (§2e.2). Top platformun yukarı tarafına da
   düşebilir, eğim boyunca iki kez sekebilir.
3. **Top ağırlığı boyuttan belli.** Her turda sekme katsayısı farklı
   ama boyut söylüyor: büyük top az seker. Fizik değişmiyor, okunacak
   değişken ekleniyor.
4. **Platformlar başta görünüp kayboluyor.** Tur başında bir saniye
   tam, sonra uç noktalar. Hafıza dünyası.
5. **Saklanan kesik türleri:** kaybolmaya yakın, sadece uç noktalar.
6. **Alt kova adımı yükselmeye devam:** ×4, ×5.

Bilerek dışarıda: hareketli platform (zamanlama, refleks) ve rüzgar
(sabit ve görünür olsa adil ama "kaosa yaklaştırma" çizgisi).

### Aşama 2 kapanış koşulu

2e kapanınca Aşama 2 biter. **2d ve 2f atlanıyor** — sıkılma kontrol
noktasıyla gittiyse çeşitliliğe ihtiyaç gösterilmedi; hiçbir test
"keşke bir kere bakabilsem" demedi. Yerini kazanmayan katman eklenmez;
bank katmanı bu kuralla çıktı, bu ikisi aynı kuralla girmiyor.
Gerekirse Aşama 3 sonrası dönülür.

Aşama 3'e kalan: günlük tohum, paylaşım kartı, yayın. Sonra üç-dört
hafta bekleme. Bütün proje o beklemenin cevabına bağlı.

### İki mod sorusu — Aşama 3'ten sonra cevaplanacak

Neden iki mod: günlük tek başına "bir daha"yı öldürür, sonsuz onu
günlüğün değerini bozmadan karşılar. Wordle'ın sonsuzu yoktu, "Wordle
Unlimited" klonları o yüzden çıktı. İki sayfa değil — tek sayfa, mod
parametresi, seans sonundaki "endless" kelimesi.

Ama karmaşıklık vergisi gerçek: kurallar ayrıştı (seansta ıska
sıfırlar, sonsuzda ulaşılan kalır). Ve günlük mod Aşama 3'e kadar
gerçekten günlük değil — o gelene kadar seans, sonsuzdan sadece tur
sınırıyla ayrılıyor.

**Açık soru:** Aşama 3'ten sonra hangi modda oynanıyor? Biri terk
edilirse gider.

**2d — İkinci tur tipi (§0.1'den bir tane).** Çeşitlilik testi.
*Kontrol:* Aynı jest ikinci tipte de doğal mı hissettiriyor.

**2f — Bilgiyi satın al (§2.2).** En son. Diğer katmanlar oturmadan
eklenirse dengeyi ölçemezsin.

**Aşama 2 testi:** Bir oturumda kaç seans oynanıyor? Tek seansta
bırakılıyorsa "bir daha" dürtüsü yok demektir.

**Durma kuralı:** Bir adım oynanışı kötüleştiriyorsa geri al ve sonrakine
geçme. Katman eklemek her zaman iyileştirmez.

### 2.1 Risk/ödül katmanı

Aralık genişliği tur seviyesinde bir risk kararı. Bu katman aynı kararı
seans seviyesine taşıyor: biriken puanı al ve dur, ya da devam et ve
hepsini riske at.

İki katman birleşince oyun "fizik tahmini" olmaktan çıkıp **kendini ne
kadar tanıyorsun** oyununa dönüşüyor — ve paylaşılabilir olan asıl şey
oydu. İnsanlar puanlarını değil, kendileri hakkında öğrendiklerini
paylaşır.

Maliyeti: sıfır ek içerik, bir buton.

### 2.2 Bilgiyi satın al

Duvarın arkasındaki topu bir anlığına görebilirsin — ama puandan düşer.

Aynı psikolojiyi üçüncü bir eksende çalıştırıyor. Oyunun temel sorusu
artık üç yerde soruluyor: tur içinde risk (aralık genişliği), seans
içinde risk (devam et / dur), ve bilgi seviyesi (bak / bakma).

Hepsi tek soru: belirsizliği azaltmak mı, puanı korumak mı.

### Aşama 3 — Günlük mod ve paylaşım (3–5 gün)
- Tohumlu rastgelelik: tarih = tohum, herkes aynı simülasyonu görüyor
- Paylaşım kartı (bkz. §4)
- Dünkü kendinle yarışma (§3.1)
- Yayınla

**Test:** 3–4 hafta. Paylaşım geliyor mu. Gelmiyorsa dur — bu kategoride
ürünü iyileştirerek kurtarmak işlemiyor.

### 3.1 Dünkü kendinle yarışma

Bugünkü performansın yarınki rakibin oluyor. Günlük seansta dünkü
skorun referans olarak gösteriliyor.

**Neden bu, plandaki bir riskin doğrudan panzehiri:** §8'de "oyuncu
kendi tavanına ulaşıp bırakır" yazılı. Sabit bir hedef tavan yaratır;
seninle birlikte hareket eden bir hedef yaratmaz.

Ayrıca kalabalık gerektirmiyor — rakip sensin. Sıfır kullanıcıyla da
çalışıyor, ki elimizdeki durum bu.

Paylaşımı da doğal ve spoiler'sız: "dünkü halimi 0.3 saniye farkla
yendim" fizikten hiçbir şey ele vermiyor.

Maliyeti: dünkü skoru saklamak.

### Aşama 4 — Mobil
**Şarta bağlı, kesin değil.** Ancak Aşama 3 sinyal verirse. Paylaşım
gelmezse mobil hiç olmaz — mobili kesin bir gelecek olarak görmek, web
tarafında ona hazırlık yaptırır ve kapsamı şişirir. Detay §6.

## 3. Modlar

**Günlük** — 5 tur, tek hak, tohum sabit, paylaşılabilir.
**Sonsuz** — sınırsız, sıralama yok, paylaşım yok.

**Neden ikisi birden:** Günlük mod tek başına "bir daha" dürtüsünü
öldürür — bir kere oynadın, bitti. Sonsuz mod o dürtüyü günlüğün
değerini bozmadan karşılıyor.

## 4. Paylaşım kartı

**Spoiler testi zorunlu.** Wordle'ın asıl sihri günlük olması değil, o
ızgaranın kelimeyi söylemeden skoru göstermesiydi. Sonuç kartı cevabı
ele verirse arkadaşının turu biter ve zincir kırılır.

**İki boyut, iki görsel özellik.** Wordle'ın ızgarası tek boyutluydu
(kaçıncı denemede bildin). Burada iki boyut var: ne kadar risk aldın ve
tuttu mu. İkisini tek sembole sıkıştırmak kartı okunmaz yapar veya bir
boyutu düşürür.

**Uzunluk = risk. İşaret = sonuç.**

```
Yörünge #45

▪️ ✅
▪️▪️▪️▪️ ✅
▪️ ❌
▪️▪️ ✅
▪️▪️▪️▪️▪️▪️ ✅

×24
```

Kısa dizi = dar kova = cesur. Uzun dizi = geniş kova = temkinli.

**Kartın asıl gücü silüetinde.** Cesaret şeklin kendisinde görünüyor —
beş satırı da kısa olan biri, arkadaşının uzun satırlarının yanında
anında fark ediliyor. Kimse "riskli oynadım" demek zorunda kalmıyor,
kart söylüyor. Ve şekil iki farklı oyun tarzını anlatıyor: hepsi kısa
ve bir ıska olan kart bir hikâye, hepsi uzun ve tam isabet olan kart
başka bir hikâye.

**Alttaki tek sayı toplam çarpan.** Karşılaştırılabilir tek rakam o
olmalı, yoksa insanlar neyi kıyaslayacağını bilemez.

**Spoiler kontrolü:** Fizikten hiçbir şey sızmıyor — ne süre, ne konum,
ne yön. Kova genişliği ve isabet oyuncunun kendi kararı, simülasyonun
cevabı değil.

**Sembol seçimi Aşama 3'e bırakılıyor.** Kartın gerçek testi WhatsApp,
X ve farklı işletim sistemlerinde nasıl render edildiği. Bazı semboller
platformlar arasında farklı genişlikte çiziliyor ve hizalama dağılıyor.
Unicode'da genişliği sabit olan temel geometrik şekillerle ilerle;
kağıtta güzel duran kart telefonda bozulabilir. Yayından önce en az
üç platformda test et.

## 5. Web (Aşama 1–3)

- Tek sayfa, canvas, çerçevesiz. Fizik motoru gerekmiyor — basit iki
  boyutlu kinematik, birkaç yüz satır.
- Tohumlu rastgelelik (deterministik PRNG). Günlük challenge bunun
  bedava yan ürünü.
- **Backend yok.** Skor `localStorage`'da. Lider tablosu Aşama 4'e
  ertelendi; sunucu eklemek maliyet ve bakım başlatır.

### 5.1 Girdi: tek jest, tek kod yolu

**Pointer olayları kullan.** Fare ve dokunmatik tek kod yolundan geçer;
ayrı fare ve dokunma işleyicisi yazma.

Masaüstünde sürükle, telefonda parmak — aynı jest. Bunu Aşama 1'de
doğru kurmak, sonradan düzeltmekten çok daha ucuz ve mobil geçişini
neredeyse bedava yapan şey bu.

### 5.2 Barındırma

**Aşama 1–2: GitHub Pages.** Backend yok, skor tarayıcıda, tek sayfa —
fazlasıyla yeterli. İçerik dağıtım ağı üzerinden çalıştığı için siten
zaten dünyanın her yerinden açılır; "globale açmak" diye ayrı bir işlem
yok.

**Aşama 3: Cloudflare Pages'e taşı.** Taşıma bir saatlik iş, ortada
sadece statik dosyalar var. Gerekçe iki şey: paylaşım linkinin sosyal
medyada kişiye özel önizleme kartı göstermesi (statik barındırmada
üretilemez), ve ileride lider tablosu gibi sunucu tarafı ihtiyaçlar.

**Alan adı: Aşama 3'te.** Önce gerekmiyor — Aşama 1'de beş kişiye kendi
bilgisayarında gösteriyorsun. Cloudflare'de alan adı bağlama ve SSL
otomatik. `dropgap.com` büyük ihtimalle alınmıştır; `.app`, `.game`,
`.fun` hem müsait hem uygun.

## 6. Mobil (Aşama 4)

**Önce PWA.** Oyun zaten canvas ve tek jest; native'e ihtiyaç duyduğu
bir şey yok. Curalis'te PWA tarafını zaten kurmuşsun, o birikim burada
doğrudan işe yarıyor.

**Native ancak şu ikisinden biri gerekirse:** günlük hatırlatma bildirimi
veya mağaza görünürlüğü. İkisi de Aşama 3 sinyal verdikten sonra
konuşulur.

Mağazaya girmek geliştirici hesabı, yıllık ücret ve inceleme süreci
demek — sinyal yokken ödenecek bir maliyet değil.

### 6.1 Mağazaya girilirse — doğrulanmış ASO notları

Bu bölüm Aşama 4 içindir; erken uygulamaya çalışma. Başka bir mobil
projede de geçerli.

**Gerçekten işe yarayanlar:**

- **Başlık + alt başlık + anahtar kelime alanı** en yüksek kaldıraçlı
  alanlar; hangi aramalarda görünmeye hak kazandığını onlar belirler.
  Başlığı anahtar kelimeyle doldurma, en iyi kelimeyi alt başlığa koy.
- **iOS'ta açıklama metni sıralamaya girmez** — sadece insanlar için.
  Fayda önce, özellik sonra.
- **Yerelleştirme 2026'da ilk üç sıralama faktöründen biri.** En çok
  atlanan, en çok getiren madde.
- **Ekran görüntüsü metni OCR ile indeksleniyor** (2025–26 değişikliği).
  Görsellerdeki yazı artık hem dönüşüm hem anahtar kelime alanı.
- **Puan eşiği gerçek:** 4.0 altı görünürlüğü düşürüyor, 3.5 altı
  öldürüyor. Ve ortalama değil **yörünge** önemli — yeni puanlar eskiden
  daha ağır.
- **Kötü yoruma gerçek cevap ver** (şablon değil, 24–48 saat içinde).
  Mekanizma algoritma değil: cevap alan kullanıcılar puanlarını
  sıklıkla yukarı çekiyor.
- **Kurulum sonrası sinyaller belirleyici:** kalıcılık, tekrar açma,
  kaldırma oranı. Mağaza taktikleri seni yarışa sokar, yarışı ürün
  kazanır.

**Folklor — uğraşma:**

- "Her 10–14 günde bir güncelle." Kazanan kalıp sık güncellemek değil,
  değerli güncelleyip iyi anlatmak. Boş güncelleme takvimi zaman kaybı.
- "Apple geliştirici duyarlılığını güven sinyali olarak izler." Böyle
  bir şey yok.
- "Dönüşüm %25'in altındaysa sorun var." Uydurma sayı; dönüşüm trafik
  kaynağına göre uçuk değişir, tek eşik yoktur.
- "Az izin isteyen uygulama hızlı onaylanır." Kanıtı yok.

**Riskli — yapma:**

- Organize yorum toplamak App Store kurallarına aykırı ve yaptırımı
  ağır. Arkadaşının indirip dürüst yorum yazması ayrı; "ilk 20 yorumu
  ayarlamak" ayrı şey.

**Atlanan asıl değişiklik:** Kullanıcılar hangi uygulamayı indireceğini
giderek mağazadan önce yapay zekâya soruyor. Keşif katmanı mağazanın
dışına taşınıyor — ASO tek başına yeterli değil.

## 7. Tasarım dili

**Risk geri bildirimi: çarpan, renk değil.**

Kovanın üstünde tek bir rakam — kova daraldıkça büyüyor, parmağın
altında canlı değişiyor.

Renk kodlu risk uyarısı reddedildi. Üç gerekçe: bilgi zaten ekranda
(kova dar görünüyor), renk soyut bir dil ve öğrenilmesi gerekir, ve
karar anında uyarı vermek oyuncuyu geri çekilmeye iter — oysa oyunun
istediği şey cesaret.

Çarpan somut ("riskli" değil, "×7"), turlar arası karşılaştırılabilir,
ve oyuncuya kendi risk eğrisini öğretiyor. Kalibrasyon oyununun asıl
istediği şey bu.

**Vurgu kararda değil sonuçta.** Dar kovayla tam isabet belirgin olsun,
geniş kovayla tutturmak sessiz geçsin. Oyun cesareti ödüllendirdiğini
söylemek yerine gösteriyor.

**Renk yalnızca iki iş için:** tuttu / tutmadı, ve tam isabet / kenar.
Üç durum, üç ton. Başka yerde renk yok.

### 7.1 Düzen — ilk çok kullanıcılı testten (10 Eyl)

İki kişi oynadı, "ne yapacağımı anlamadım" anları yaşandı. Bulgular
ve ayrım:

**"iOS oyun mantığı" iki şey.** Kullanılabilirlik gelenekleri — uyarı
nerede durur, dokunma hedefi ne kadar büyük, "devam et" nasıl
anlaşılır — alınır. Stil gelenekleri — konfeti, parlayan buton, çarpı
işaretli popup — alınmaz. Kullanıcı zorlanıyorsa sorun ilkinde ve stil
değiştirmeden düzelir.

- **Yazılar gözün olduğu yerde.** "Tap for the next round" alttaydı,
  göz topta ve kovadaydı, kimse görmedi. Tur sonrası ipucu ekranın
  ortasına, yarı saydam, topun durduğu bölgenin yakınına. Seans ve koşu
  sonu ortalanmış tek kart: toplam, çubuklar, "tap anywhere." Buton
  yok — bu popup değil, sonuç kartı; "vurgu sonuçta" ile uyumlu.
  *Bekleyen:* ipucu bazen topun izinin üstüne geliyor; çözüm kaydırmak
  değil sıralamak — ipucu, iz sönümlendikten yarım saniye sonra
  belirsin. "Önce bak, sonra devam et" ritmi. Test sonrası.
- **Üst bant iki katına.** 34 birim ve 7 birimlik çubuk telefonda
  küçüktü. Beş yuva her zaman sığar (seansta beş, sonsuzda son beş),
  büyütmek serbest.
- **Dokunma alanı tüm ekran, düşürme sürüklemeden sonra.** İlk karar
  alt yarıydı: bırakmak topu düşürdüğü için tüm ekran kazara düşüş
  demekti. Ama test kullanıcıları parmağı yukarı koyuyorsa alanı
  küçük tutmak onları eğitmeye çalışmaktır. Çözüm alanı değil, kuralı
  değiştirmek: sürükleme her yerden başlar; parmak ölü bölgeyi en az
  bir kez geçtiyse bırakınca top düşer; hiç hareket etmemiş dokunuş
  üst yarıda hiçbir şey yapmaz, alt yarıda mevcut kovayla düşürür.
  Ekranın her yeri kovayı kontrol eder, kazara dokunuş oyunu bozmaz.

Genel çerçeve: sakin ve enstrüman gibi. Simülasyon zaten hareketli,
arayüz onu bastırmamalı.

- Ekranda aynı anda tek karar: aralık
- Renk yalnızca sonucu ayırmak için (tuttu / ıskaladı)
- Sonuç anı animasyonun kendisi olmalı, ayrı bir kutlama ekranı değil
- Curalis'in tasarım sistemi taşınmayacak — o bir kayıt uygulamasıydı

## 8. Riskler

- **Fizik tahmini geniş kitleye eğlenceli gelmeyebilir.** Teknik
  zihinlere doğal gelir. En büyük risk bu ve Aşama 1'in tüm amacı onu
  ucuza öğrenmek.
- **Skill ceiling.** Oyuncu kendi sınırına ulaşıp bırakabilir. Zorluk
  eğrisi ve parametre çeşitliliği Aşama 2'de bunun için var.
- **Kapsam patlaması.** Lider tablosu, hesap, rozet, seri takibi —
  hepsi cazip, hepsi Aşama 4 sonrası.
- **Gelir yok.** Bu kategori eğlence bandında (~4 dolar RPM) ve reklamla
  kazanmıyor. Beklenti ilgi ve öğrenme olmalı, aylık gelir değil.
  Gelir arayışı ayrı yürütülecek.

### 8.1 Değerlendirilip reddedilen gelir modelleri

Kayıt için — bu öneriler tekrar gelirse baştan tartışılmasın.

- **Ödüllü reklamla tekrar deneme** ("kovayı büyütmek için video izle").
  Günlük modun tek hak kuralını bozar; paylaşılan skor anlamını
  yitirir ve yayılma zinciri kırılır. Gelir mekaniği, ürünün tek
  dağıtım mekanizmasını kesiyor.
- **Hipercasual reklam modeli.** iOS izleme kısıtlarından sonra reklam
  geliri %15–25 düştü ve model kullanıcı edinme bütçesi gerektiriyor.
  Milyonlarca oturumda çalışır, tek kişilik geliştiricide çalışmaz.
- **Kozmetik ekonomi** (top rengi, iz efekti, kova tasarımı). Hepsi
  üretilecek varlık — birinci kuralı ("içerik editörü gerektirmeyecek")
  arka kapıdan ihlal eder. Ayrıca büyük kullanıcı tabanı olmadan
  anlamsız.

## 8.2 Gelir modeli — eğer sinyal gelirse

Aşama 3'ten önce hiçbiri yapılmayacak. Sinyal yoksa gelir konuşulmaz.

**Kural: günlük mod dokunulmaz.** Ücretsiz, reklamsız, tek hak. Yayılma
motoru orası; ona dokunan her gelir fikri reddedilir.

- **Tek seferlik kilit açma.** Sonsuz mod ve geçmiş günler arşivi tek
  ödemeyle açılır. Abonelik değil, reklam değil, kozmetik değil —
  üretilecek varlık yok, içerik editörü kuralı korunuyor.
- **Bahşiş kutusu.** Ayarlarda sade bir destek butonu. Hiçbir şeyi
  kilitlemez.

**Reddedilen: zorluk çarpanı / premium hard mode.** İki sebeple.
Rüzgar gibi ek faktörler "öğrenilebilir fizik" kuralını (§0) deler.
Ve premium kullanıcıya farklı fizik vermek günlük tohumun tek anlamını
— herkesin aynı simülasyonu oynamasını — bozar; iki katmanlı bir günlük
skorları karşılaştırılamaz hale getirir.

Zorluk isteyen oyuncunun cevabı zaten mekanikte: dar kova.

## 8.3 Tempo kararı: geri sayım yok

Parmağı çektiğin an simülasyon tetiklenir. Araya bekleme konmaz.

Gerekçe: tur 15 saniye, üç saniyelik geri sayım turun beşte biri —
atıştırmalık bir oyunda ağır vergi. Gerilim zaten simülasyonun
kendisinde ve o bekleme bilgi taşıyor; geri sayım boş bekleme. Ve
karar parmağı çektiğin an bitmiş oluyor — sonrasında beklemek oyuna
hiçbir şey eklemiyor.

**Gerilim isteniyorsa doğru yer:** top kovaya yaklaşırken son yarım
saniyeyi hafifçe yavaşlat. Bekleme eklemeden aynı etki, ve bilgiyle
dolu bir an.

## 9. Denenip elenen mekanik aileleri

Kayıt için — aynı fikirler tekrar gündeme gelmesin.

- **Algısal keşif** (bir şey yanlış, ne değişti, yanlış perspektif,
  gölgeyi oku): prosedürel üretimi zor. "Yanlışlık" ancak ışık kaynağı
  olan bir sahne modeli varsa üretilebilir; alternatifi elle sahne
  hazırlamak, o da içerik editörü demek. Hafıza/fark bulma alt kolu
  (aynısını bul, fazla olanı bul) üretilebilir ama tavanı düşük ve
  karakteri yok — ancak çeşitlilik turu olarak düşünülebilir.
- **Kural keşfi** (kuralı çal, gizli sıra, sınırı bul): keşif birkaç
  tur gözlem ister, günlük challenge o süreyi vermez. Ayrıca çözüm
  paylaşılamaz — spoiler testini geçmiyor. Doğru formatı seviyeli bir
  oyun, ki o başka bir ürün.
- **Serbest zamanlı karar** (karar noktası): "istediğin anda karar ver"
  tek jest kuralını deliyor.

## 10. Sonraki tur (şimdi yapılmayacak)

**Devretme zinciri.** Bir oyuncunun bıraktığı durum sonraki oyuncuya
geçiyor; ya da ödülü alıp çıkmak yerine sonrakine devretmek. Yayılma
mekaniğin içine gömülü oluyor ve kalabalık gerektirmiyor — iki kişiyle
çalışıyor. İncelenen bütün sosyal mekanikler içinde soğuk başlangıç
problemi olmayan tek aile bu.

Neden şimdi değil: aralık oyunu tek kişilik bir beceri oyunu, bu ise
iki kişilik bir devir oyunu. Aynı kabuğa zorlamak ikisini de bozar.
Aşama 3 sinyal verirse ayrı bir ürün olarak açılır.

- Lider tablosu ve sıralama
- Arkadaşa doğrudan meydan okuma linki
- Farklı fizik senaryoları (sekme, yerçekimi, çarpışma)
- Ses
- Bildirim
