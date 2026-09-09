Dropgap — Plan
Slogan: See the bounce. Guess the rest.
Depo: dropgap · Web önce, mobil sonra.
İsim gerekçesi: Bu kategoride isimler tarif eder, çağrıştırmaz —
link paylaşıldığında kendini açıklaması gerekir. “Drop” ve “gap” ikisi
de gerçek kelime ve mekaniği anlatıyor: düşen bir şey ve senin açtığın
boşluk. Uydurma birleşimler (Blindspan, Arcmargin, VanishArc) zeki ama
ne olduğunu söylemiyor. Wordle da uydurma değildi — içinde “word” var.
Slogan mekaniği üç saniyede öğretiyor; ismin tek başına yapamayacağı
işi o yapıyor.
Karar acele değil, son güne kadar değişebilir. Alan adı müsaitliğini
Aşama 3’te kontrol et.
0. Mekanik
Bir top yukarıdan bırakılıyor, birkaç platformdan sekiyor. Sadece ilk
sekmeyi görüyorsun, sonra top görünmez oluyor. Nereye düşecek?
Oyuncu altta bir kova yerleştiriyor: tek jestle hem konumunu hem
genişliğini ayarlıyor.
	•	Dar kova = eminim = yüksek puan
	•	Geniş kova = emin değilim = düşük puan
Neden kova, soyut bir aralık çubuğu değil: Aynı mekanik ama kendini
açıklıyor. “Aralık genişliği” anlatmayı gerektirir, kova genişliği
gerektirmez. Öğrenme süresi sıfıra iniyor.
Neden genişlik ayarlanabilir: Sabit genişlikte bir kova, oyunun
bütün kimliğini siler. “Ne kadar eminsin” sorusu genişlikten geliyor;
sadece sağa sola kaydırmak onu ortadan kaldırır.
Neden böyle: Güveni ayrı bir soru yapmak turu ikiye böler ve akışı
kırar. Kova genişliği, kalibrasyonu ayrı bir adım olmaktan çıkarıp
seçimin kendisi yapıyor. Tek jest, tek ekran, tur ~15 saniye.
Neden top görünmez oluyor: Görünür kalsaydı oyun tahmin değil
refleks olurdu. Refleksin tavanı var, tahminin yok.
Puanlama: toleranslı
İkili değil kademeli. Tam ortada / kenarda / dışarıda — üç seviye.
Salt tuttu-tutmadı puanlaması oyuncuyu sürekli sıfırla bırakır ve
oyunu sildirir. “Az kaldı” hissi devam ettiren şey.
Puan hâlâ kova genişliğiyle ters orantılı: dar kovada tam isabet en
yüksek, geniş kovada tam isabet düşük.
Fizik öğrenilebilir olmalı
Sonuç oyuncuya rastgele hissettirirse sezgisini geliştiremez ve bırakır.
Yerçekimi, ivme ve sekme tutarlı olmalı; kaosa yaklaşan parametreler
“sezgimle çözemiyorum” hissi yaratır ve oyunu öldürür.
Bu, kapsam kuralı kadar bağlayıcı: her yeni tur tipi bu testten geçmeli.
Sonsuz varyasyon: Her turda platform açıları, boyutlar ve topun
ağırlığı değişiyor — ama çözülebilir sınırlar içinde. Ezber işe
yaramıyor, içerik üretmeye gerek yok. İçerik editörü yok — bu, kriter
listesinin en önemli maddesiydi.
0.1 Tur tipi havuzu
Aynı motor, aynı jest, farklı soru. Hepsi simülasyondan türüyor — yeni
oyun değil, aynı oyunun tur tipleri. Çeşitlilik ek içerik maliyeti
olmadan buradan geliyor.
Aşama 2’de sırayla eklenecek, hepsi birden değil:
	•	Ne zaman? — çizgiye kaç saniyede ulaşır (Aşama 1’in temel turu)
	•	Ne kadar ileri? — ekran dışına çıktıktan sonra nereye kadar gider
	•	Nerede? — duvarın arkasından hangi noktadan çıkar
	•	Ne kadar hızlı? — gözlemlenen hareketin hızı
	•	Hangisi önce? — iki nesneden hangisi hedefe önce varır
	•	Sonraki kare — animasyon durdurulur, devamı tahmin edilir
	•	Tahmin et, sonra değiştir — tahminini yaparsın, simülasyon çalışır,
sonucu görürsün, ardından tek bir değişkene müdahale hakkın olur.
Fizik anlayışını öngörmekten düzeltmeye taşıyor. Aynı motor, tek
ek kontrol.
	•	Müdahale noktası — simülasyon ilerlerken tek bir anda müdahale
hakkın var. Asıl soru ne yapacağın değil, ne zaman yapacağın.
Yukarıdakinin keskin hali: müdahale sonuçtan sonra değil, sürecin
ortasında.
	•	Eşiği bul — sistem iki farklı sonuca gidebilir; sen sonucu değil,
sonucun değiştiği sınırı aralıkla işaretlersin. Diğerlerinden farklı
bir zihin işi: çıktıyı değil, çatallanma noktasını tahmin ediyorsun.
Uyarı: eşik fazla hassas olursa oyuncu haksızlık hisseder ve
kandırılmış hisleri oyunu bıraktırır. Eşik bandını cömert tut,
kaosa yaklaştırma.
	•	Hangi taraf? — aralık değil, ikili seçim. Kalibrasyon katmanını
kaybettiği için ana tur olamaz; yalnızca ısınma/giriş turu olarak
kullanılabilir.
Kural: her yeni tur tipi aynı aralık jestiyle oynanabilmeli. Jest
değişiyorsa tur tipi değil, başka oyundur — eklenmez.
Havuz doldu. Bundan sonra gelecek “ne kadar / nereye / kaç tane”
varyasyonları yeni mekanik değil, aynı motorun farklı parametresi.
Sekiz tur mekanik taraması sonunda üç şartı geçen tip sayısı sekiz.
Daha fazla tip çeşitlilik değil, dağınıklık getirir. Havuzu genişletmek
yerine mevcut tiplerin zorluk eğrisini işle.
1. Kapsam kuralı
Bu dosyada yazmayan yapılmaz. Yeni fikir “Sonraki tur”a yazılır.
Kesin kapsam dışı:
	•	Hesap ve giriş (Aşama 3’e kadar)
	•	Reklam
	•	Satın alma, para birimi, kozmetik
	•	Ses
2. Aşamalar
Aşama 1 — Mekanik testi (2–3 gün)
Tek tur, tek sayfa, skor yok, paylaşım yok. Sadece oynanış.
Test: Kendin ve 5 kişi oynasın. Tek soru: “bir daha” diyorlar mı?
Demiyorlarsa dur. Mekanik tutmadıysa günlük mod, paylaşım ve mobil
hiçbir şeyi kurtarmaz.
Bu testin tamamı 3 günlük iş. Bir hafta kod yazdıktan sonra öğrenmekten
çok ucuz.
Aşama 2 — Oyun döngüsü (3–5 gün)
Sırayla eklenecek, hepsi birden değil. Her adımdan sonra oyna ve
oynanışın bozulup bozulmadığına bak. Üç katman aynı anda girerse
hangisinin işe yaradığını ayırt edemezsin.
2a — Seans. 5 turluk seans, toplam skor. Başka hiçbir şey yok.
Bu, Aşama 1’in tek turunun çoğaltılmış hali; temeli sağlamlaştırır.
2b — Zorluk eğrisi: bilgiyi azalt, hızı değil. Duvar genişler, top
daha kısa süre görünür, ivme daha geç belli olur. Aynı fizik, daha az
veri. Hız ve ivme artırmak refleksi zorlar; bilgi azaltmak çıkarımı
zorlar — ve bu oyun bir çıkarım oyunu.
Kontrol: 5. tur hâlâ adil hissettiriyor mu, yoksa keyfi mi.
2c — Risk/ödül katmanı (§2.1). Bir buton. Seans seviyesinde
devam et / dur kararı.
Kontrol: Oyuncu gerçekten duruyor mu, yoksa hep sonuna kadar mı
gidiyor? Hep gidiyorsa risk yeterince acıtmıyor demektir.
2d — İkinci tur tipi (§0.1’den bir tane). Çeşitlilik testi.
Kontrol: Aynı jest ikinci tipte de doğal mı hissettiriyor.
2e — Sonsuz mod. “Bir daha” dürtüsünün yaşadığı yer.
2f — Bilgiyi satın al (§2.2). En son. Diğer katmanlar oturmadan
eklenirse dengeyi ölçemezsin.
Aşama 2 testi: Bir oturumda kaç seans oynanıyor? Tek seansta
bırakılıyorsa “bir daha” dürtüsü yok demektir.
Durma kuralı: Bir adım oynanışı kötüleştiriyorsa geri al ve sonrakine
geçme. Katman eklemek her zaman iyileştirmez.
2.1 Risk/ödül katmanı
Aralık genişliği tur seviyesinde bir risk kararı. Bu katman aynı kararı
seans seviyesine taşıyor: biriken puanı al ve dur, ya da devam et ve
hepsini riske at.
İki katman birleşince oyun “fizik tahmini” olmaktan çıkıp kendini ne
kadar tanıyorsun oyununa dönüşüyor — ve paylaşılabilir olan asıl şey
oydu. İnsanlar puanlarını değil, kendileri hakkında öğrendiklerini
paylaşır.
Maliyeti: sıfır ek içerik, bir buton.
2.2 Bilgiyi satın al
Duvarın arkasındaki topu bir anlığına görebilirsin — ama puandan düşer.
Aynı psikolojiyi üçüncü bir eksende çalıştırıyor. Oyunun temel sorusu
artık üç yerde soruluyor: tur içinde risk (aralık genişliği), seans
içinde risk (devam et / dur), ve bilgi seviyesi (bak / bakma).
Hepsi tek soru: belirsizliği azaltmak mı, puanı korumak mı.
Aşama 3 — Günlük mod ve paylaşım (3–5 gün)
	•	Tohumlu rastgelelik: tarih = tohum, herkes aynı simülasyonu görüyor
	•	Paylaşım kartı (bkz. §4)
	•	Dünkü kendinle yarışma (§3.1)
	•	Yayınla
Test: 3–4 hafta. Paylaşım geliyor mu. Gelmiyorsa dur — bu kategoride
ürünü iyileştirerek kurtarmak işlemiyor.
3.1 Dünkü kendinle yarışma
Bugünkü performansın yarınki rakibin oluyor. Günlük seansta dünkü
skorun referans olarak gösteriliyor.
Neden bu, plandaki bir riskin doğrudan panzehiri: §8’de “oyuncu
kendi tavanına ulaşıp bırakır” yazılı. Sabit bir hedef tavan yaratır;
seninle birlikte hareket eden bir hedef yaratmaz.
Ayrıca kalabalık gerektirmiyor — rakip sensin. Sıfır kullanıcıyla da
çalışıyor, ki elimizdeki durum bu.
Paylaşımı da doğal ve spoiler’sız: “dünkü halimi 0.3 saniye farkla
yendim” fizikten hiçbir şey ele vermiyor.
Maliyeti: dünkü skoru saklamak.
Aşama 4 — Mobil
Ancak Aşama 3 sinyal verirse. Detay §6.
3. Modlar
Günlük — 5 tur, tek hak, tohum sabit, paylaşılabilir.
Sonsuz — sınırsız, sıralama yok, paylaşım yok.
Neden ikisi birden: Günlük mod tek başına “bir daha” dürtüsünü
öldürür — bir kere oynadın, bitti. Sonsuz mod o dürtüyü günlüğün
değerini bozmadan karşılıyor.
4. Paylaşım kartı
Spoiler testi zorunlu. Wordle’ın asıl sihri günlük olması değil, o
ızgaranın kelimeyi söylemeden skoru göstermesiydi. Sonuç kartı cevabı
ele verirse arkadaşının turu biter ve zincir kırılır.
İki boyut, iki görsel özellik. Wordle’ın ızgarası tek boyutluydu
(kaçıncı denemede bildin). Burada iki boyut var: ne kadar risk aldın ve
tuttu mu. İkisini tek sembole sıkıştırmak kartı okunmaz yapar veya bir
boyutu düşürür.
Uzunluk = risk. İşaret = sonuç.