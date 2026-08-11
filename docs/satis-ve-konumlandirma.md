# Satış ve Konumlandırma Rehberi

Bu doküman, projenin **hangi problemi çözdüğünü**, **kime satılabileceğini** ve
**farklı muhataplara nasıl anlatılacağını** tanımlar. Teknik dokümantasyon için
`README.md` dosyasına bakınız.

---

## 1. Tek cümlelik konumlandırma

> **Su kaynaklarındaki değişimi uydu görüntüsünden otomatik ölçüp, GIS uzmanı
> gerektirmeden dakikalar içinde kurumsal karar raporuna dönüştüren sistem.**

Alternatif vurgular (muhataba göre seç):

| Muhatap | Cümle |
|---|---|
| Kurum / belediye | "Göletlerinizin ve barajlarınızın nasıl değiştiğini, uzman istihdam etmeden periyodik raporla takip edin." |
| Danışmanlık firması | "ÇED ve izleme raporlarınızın su bölümünü günler yerine dakikalar içinde üretin." |
| Yatırımcı | "Uzaktan algılama verisini, uzman olmayan kullanıcı için karar çıktısına çeviren dikey bir SaaS." |
| Jüri / akademik | "BCE+Dice kayıplı geliştirilmiş U-Net ile piksel seviyesinde su segmentasyonu ve zamansal değişim analizi." |

---

## 2. Çözülen gerçek problem

### Yaygın hata: "Su tespiti yapıyoruz" demek

Su tespiti çözülmüş bir problemdir. NDWI indeksi onlarca yıldır kullanılıyor,
Sentinel-2 ve Landsat verisi ücretsiz, Google Earth Engine herkese açık.
Ürünü "su tespiti" olarak konumlandırırsan alacağın cevap: *"Bunu biz zaten
Earth Engine'de yaparız."*

### Doğru konumlandırma: veri ile karar arasındaki boşluk

Problem verinin yokluğu değil, **veriden karara giden yolun pahalı ve kişiye
bağımlı olması.** Bugünkü durum:

1. **Uzmanlık darboğazı.** "Bu gölet geçen yıla göre ne kadar çekildi?" sorusunu
   cevaplamak için uzaktan algılama bilen personel, QGIS/SNAP kurulumu ve
   saatlerce manuel işlem gerekiyor. Çoğu belediyede, sulama birliğinde ve KOBİ
   ölçekli danışmanlıkta bu kişi yok.
2. **Standart eksikliği.** Analiz kişiye göre değişiyor; iki farklı personelin
   iki farklı sonucu çıkıyor. Çıktı Word'de elle hazırlanıyor, formatı her
   seferinde farklı, karşılaştırılabilir ve arşivlenebilir değil.
3. **Gecikmeli müdahale.** Saha ölçümü periyodik ve pahalı. Kayıp ya da taşkın
   çoğu zaman *olduktan sonra* fark ediliyor.

**Ürünün değeri:** bu üç darboğazı da ortadan kaldıran son adımı otomatikleştirmesi.
Girdi: iki tarihli görüntü. Çıktı: ölçülmüş değişim + risk kademesi + eylem
önerisi + imzalanabilir PDF. Aradaki uzman emeği yazılıma gömülü.

### Üç katmanlı fayda (satış konuşmasında bu sırayla anlat)

| Katman | Ne sağlıyor | Muhatabın diliyle |
|---|---|---|
| Ölçüm | Piksel seviyesinde su alanı ve değişim yüzdesi | "Ne kadar değişti, tahminle değil ölçümle." |
| Yorum | 7 kademeli risk sınıflandırması + eylem önerisi | "Bu rakam iyi mi kötü mü, ne yapmalıyım?" |
| Belge | Otomatik PDF raporu | "Üst yazıya ekleyebileceğim, arşivlenebilir çıktı." |

Üçüncü katman en çok hafife alınan ama satın alma kararını en çok etkileyen
katmandır. Kurumlar analiz değil, **savunulabilir belge** satın alır.

---

## 3. Kime satılır — önceliklendirilmiş

Satış döngüsü kısa olandan uzun olana doğru sıralanmıştır. İlk müşteriyi
1. ve 2. gruptan aramak en gerçekçi yoldur.

### 1. Çevre ve ÇED danışmanlık firmaları — **en kolay ilk satış**
- **Acıları:** Rapor üretmek işlerinin kendisi. Her ÇED / izleme raporunda su
  varlığı ve değişimi bölümü var. Şu anda elle hazırlanıyor.
- **Neden alırlar:** Çıktın (PDF rapor) zaten onların teslim ettiği ürünün
  parçası. Değeri anlatmana gerek kalmıyor, doğrudan maliyet kalemi düşüyor.
- **Argüman:** "Rapor başına 3-4 saatlik uzman emeğini 10 dakikaya indiriyorsunuz."

### 2. Tarımsal sulama birlikleri ve büyük tarım işletmeleri
- **Acıları:** Gölet ve rezervuar doluluğunu takip edemiyorlar; su tahsisini
  hisle planlıyorlar.
- **Argüman:** "Sezon başında hangi göletin ne durumda olduğunu görüp tahsisi
  buna göre planlayın."

### 3. Belediyeler, su ve kanalizasyon idareleri, DSİ bölge müdürlükleri
- **Acıları:** Baraj/gölet doluluk takibi, kuraklık erken uyarısı, kamuoyuna
  ve üst kuruma raporlama.
- **Argüman:** "Periyodik, standart formatta kuraklık izleme raporu."
- **Not:** Bütçe büyük ama satın alma süreci uzun (ihale, referans şartı).
  Pilot/protokol ile girmek daha gerçekçi.

### 4. Sigorta ve tarım sigortası ekosistemi
- **Acıları:** Taşkın hasar tespiti, hasar ihbarının doğrulanması.
- **Argüman:** "Taşkının yayılım alanını sahaya gitmeden, tarihli görüntüyle
  belgeleyin."

### 5. Maden, enerji ve altyapı şirketleri
- **Acıları:** Atık havuzu (tailings pond) izleme, HES rezervuar takibi,
  ruhsat/çevre yükümlülüğü uyumu.
- **Argüman:** "Yükümlülük raporlarınız için düzenli, tarihli kanıt."

### 6. Afet yönetimi ve kamu araştırma kurumları
- Olay sonrası taşkın yayılım tespiti. Değerli ama satıştan çok iş birliği/
  protokol ilişkisi.

---

## 4. Hazır anlatım metinleri

### Asansör konuşması (15 saniye)

> "Uydu görüntülerinden su alanlarındaki değişimi otomatik ölçen bir sistem
> geliştirdik. İki tarihli görüntüyü yüklüyorsunuz, derin öğrenme modeli su
> alanını piksel piksel çıkarıyor, ne kadar arttığını ya da azaldığını
> hesaplıyor ve risk değerlendirmesiyle birlikte hazır PDF rapor veriyor.
> Uzaktan algılama uzmanı olmadan kullanılabiliyor."

### 30 saniye — problem odaklı (kurumsal müşteri)

> "Bugün bir göletin geçen yıla göre ne kadar çekildiğini öğrenmek isteseniz,
> uzaktan algılama bilen birine, GIS yazılımına ve birkaç saate ihtiyacınız var.
> Çoğu kurumda bu kişi yok, olsa bile çıktı her seferinde farklı formatta
> çıkıyor ve karşılaştırılamıyor.
>
> Biz bu işi otomatikleştirdik. İki tarihli uydu görüntüsünü yüklüyorsunuz;
> sistem su alanını tespit ediyor, değişimi yüzde olarak ölçüyor, riski yedi
> kademede sınıflandırıp somut eylem önerisi veriyor ve bunu imzalanabilir bir
> PDF raporuna döküyor. Teknik personeliniz eğitim almadan kullanabiliyor,
> sonuçlar her dönem aynı standartta çıktığı için trend takibi yapabiliyorsunuz."

### 2 dakika — teknik değerlendirici / jüri

> "Problemi piksel tabanlı ikili segmentasyon olarak modelledik. Geliştirilmiş
> bir U-Net mimarisi kullandık: batch normalizasyonlu çift konvolüsyon blokları,
> dört seviyeli encoder-decoder, 1024 filtreli bottleneck ve skip connection'lar.
>
> Kayıp fonksiyonu olarak Binary Cross Entropy ile Dice Loss'un toplamını
> kullandık. Bunun nedeni sınıf dengesizliği: bir uydu görüntüsünde su pikselleri
> azınlıkta kalabiliyor ve tek başına BCE bu durumda yanıltıcı biçimde iyi
> sonuç veriyor. Dice terimi örtüşmeyi doğrudan optimize ederek bunu dengeliyor.
>
> 2.841 görüntülük veri setinde %80-20 ayrımıyla eğittik. Doğrulama setinde Dice
> katsayısı 0.80, IoU 0.75, precision 0.86, recall 0.85 elde ettik. Precision'ın
> recall'dan yüksek olması modelin temkinli davrandığını, yani su olmayan yeri
> su olarak işaretleme eğiliminin düşük olduğunu gösteriyor; karar destek
> senaryosunda tercih edilen davranış bu.
>
> Model tek başına yeterli değil, üzerine bir değişim analizi katmanı kurduk:
> iki tarihli maskenin farkından değişim haritası ve yüzdesel değişim
> hesaplanıyor, sonuç yedi kademeli bir risk sınıflandırmasına giriyor. Burada
> önemli bir tasarım kararı verdik: %3'ün altındaki değişimleri model
> belirsizliği olarak işaretliyoruz, çünkü modelin doğruluk payı içinde kalan
> bir farkı anlamlı değişim gibi raporlamak yanıltıcı olur."

### Yatırımcı / iş fikri sunumu

> "Uydu verisi ücretsiz ve bol; eksik olan onu kullanabilen insan. Uzaktan
> algılama uzmanı pahalı ve az, ihtiyaç duyan kurum ise çok: belediyeler,
> sulama birlikleri, çevre danışmanlıkları, sigorta şirketleri. Biz aradaki
> uzman emeğini yazılıma gömüyoruz — kullanıcı görüntüyü yüklüyor, karara
> hazır rapor alıyor. Su ile başlıyoruz çünkü kuraklık ve taşkın bugün en acil
> ve en bütçelenen başlık; aynı mimari orman kaybı, kentsel yayılma ve maden
> sahası izlemeye doğrudan genişliyor."

---

## 5. Demo senaryosu (3 dakika)

Demoda **kullanıcının tanıdığı bir bölgeyi** seç. Soyut bir göl kimseyi
etkilemez; kendi ilindeki gölü gören kişi ikna olur.

Güçlü örnekler: Marmara Gölü, Burdur Gölü, Tuz Gölü, Beyşehir Gölü, Akşehir
Gölü (kuraklık anlatısı) — taşkın anlatısı için tarihli bir sel olayının
öncesi/sonrası.

**Akış:**
1. **Bağlam (20 sn).** "Bu, X gölü. 2014 ve 2023 görüntüleri." — Ham görüntüleri
   göster, henüz analiz yok.
2. **Soru (10 sn).** "Bakarak ne kadar çekildiğini söyleyebilir misiniz?"
   Kimse söyleyemez. Problemi karşı taraf kendi kendine kabul etmiş olur.
3. **Analiz (30 sn).** Yükle, çalıştır. Maskeler ve fark haritası ekrana gelir.
4. **Rakam (20 sn).** "Sistem %X azalma ölçtü ve bunu 'Yüksek Düzeyde Su Kaybı'
   olarak sınıflandırdı."
5. **Belge (30 sn).** PDF'i aç. "Bu rapor 30 saniyede üretildi ve dosyaya
   konabilir durumda." — Satışı kapatan an genellikle burasıdır.
6. **Dürüstlük (20 sn).** Sınırları kendin söyle (bkz. bölüm 8). Sınırını bilen
   satıcı, sınırı olmadığını iddia eden satıcıdan daha güvenilirdir.

---

## 6. Fiyatlama modelleri

Aşağıdaki aralıklar **çıpalama mantığını** göstermek içindir, piyasa doğrulaması
yapılmadan teklif haline getirilmemelidir. Fiyatı maliyetine göre değil,
**müşterinin alternatifine göre** kur: alternatif, bir uzaktan algılama
danışmanının gün ücreti ya da bir personelin harcadığı saatlerdir.

| Model | Nasıl işler | Kime uygun |
|---|---|---|
| **Rapor başına** | Sabit ücret / analiz | Danışmanlık firmaları, tek seferlik ihtiyaçlar. Girişi en kolay model. |
| **Abonelik (izlenen saha başına)** | Aylık/yıllık, N saha × M periyot | Belediye, sulama birliği, maden. Tekrarlayan gelir burada. |
| **Proje paketi** | Belirli bölge için tarihsel seri + tek teslim rapor seti | ÇED ve fizibilite projeleri. |
| **Lisans / beyaz etiket** | Mevcut bir GIS veya çevre yazılımına modül olarak | Ölçeklenebilir ama satış döngüsü uzun. |
| **Kamu-akademi protokolü** | Ücretsiz pilot karşılığı referans ve veri | İlk referansı kazanmak için. Bunu bilinçli bir yatırım olarak yap, ücretsiz iş olarak değil. |

**Taktik:** İlk müşteriden para almaktan çok **referans ve gerçek veri** almaya
odaklan. Gerçek sahada doğrulanmış tek bir vaka, ikinci satışı beş kat
kolaylaştırır.

---

## 7. İtirazlar ve cevapları

| İtiraz | Cevap |
|---|---|
| "Bunu Google Earth Engine / Sentinel Hub'da ücretsiz yaparım." | "Doğru — eğer uzaktan algılama bilen bir personeliniz varsa. Bizim ürünümüz o personelin işini değil, o personeli **bulundurma zorunluluğunu** ortadan kaldırıyor. Ayrıca EE size veri veriyor, biz karar ve belge veriyoruz." |
| "NDWI zaten var, neden derin öğrenme?" | "NDWI eşik tabanlıdır; bulanık su, sığ kıyı, gölge ve bitki örtüsü karışımında bozulur ve eşiği her sahne için elle ayarlamak gerekir. U-Net şekil ve doku bağlamını da öğrendiği için eşik ayarı olmadan çalışır. NDWI'yi rakip değil, doğrulama referansı olarak kullanıyoruz." |
| "Doğruluğu nedir?" | "Halka açık doğrulama setinde Dice 0.80, IoU 0.75, precision 0.86, recall 0.85. Precision'ın yüksek olması yanlış su alarmının düşük olduğu anlamına gelir. Sizin sahanızdan etiketli örnek verirseniz o bölge için ince ayar yapıp size özel doğruluk raporu çıkarırız." |
| "Bulut varsa ne oluyor?" | "Şu anda bulut maskeleme yok, bulutsuz görüntü seçilmesi gerekiyor. Sentinel-2 SCL bandıyla otomatik bulut maskeleme yol haritasının ilk maddesi." |
| "Sonuç piksel cinsinden, bana km² lazım." | "Şu an değişimi **oransal** olarak veriyoruz ve bu oran doğru. Mutlak alana çevirmek için coğrafi referanslı görüntü (GeoTIFF) desteği gerekiyor; bu yol haritasının en öncelikli maddesi ve teknik olarak küçük bir adım." |
| "Kim kullanıyor?" | Referansın yoksa uydurma. "Henüz pilot aşamasındayız, ilk kurumsal kullanıcımızı arıyoruz ve bu yüzden ilk uygulamada koşullarımız çok avantajlı." Erken olmak, yalan söylemekten daha iyi bir pozisyondur. |

---

## 8. Söylenmemesi gerekenler

Bunları iddia edersen ilk teknik değerlendirmede güvenilirliğini kaybedersin:

- ❌ "Kuraklığı önceden tahmin ediyoruz." — Sistem **geçmiş iki tarih arasındaki
  değişimi ölçer**, tahmin modeli değildir.
- ❌ "X km² su kaybı tespit ettik." — Coğrafi referans olmadan çıktı piksel
  sayısıdır. Oransal değişimi söyle, mutlak alanı söyleme.
- ❌ "Her koşulda çalışır." — Bulut, atmosferik gürültü ve farklı çözünürlük
  performansı düşürür.
- ❌ "%99 doğruluk." — Gerçek rakamlar (Dice 0.80 / IoU 0.75) zaten iyi ve
  savunulabilir. Şişirilmiş rakam savunulamaz.
- ⚠️ **Kadraj uyarısı:** İki görüntünün aynı bölgeyi aynı kadrajla kapsaması
  gerekir. Farklı alanları kapsayan iki görüntünün yüzdesel karşılaştırması
  anlamsızdır. Demo hazırlarken buna dikkat et.

Bunun yerine söylenecek dürüst cümle:

> "Bu bir karar **destek** sistemi. Kararı vermez, kararı verecek kişinin
> önüne ölçülmüş, sınıflandırılmış ve belgelenmiş veriyi koyar."

---

## 9. Satılabilirliği en çok artıracak 5 teknik adım

Öncelik sırasına göre. İlk ikisi olmadan kurumsal satış zordur.

1. **Piksel → km² dönüşümü (coğrafi referans).** GeoTIFF girdisi ve piksel
   çözünürlüğü ile gerçek alan hesabı. Her ciddi alıcının soracağı ilk soru
   budur ve teknik maliyeti düşüktür. **En yüksek getirili tek madde.**
2. **Otomatik Sentinel-2 çekimi.** Kullanıcı koordinat ve iki tarih girsin,
   görüntüyü sistem indirsin. Manuel görüntü yükleme zorunluluğu, uzman
   gerektirmeme vaadini şu anda zayıflatan tek şey.
3. **Bulut maskeleme + NDWI doğrulaması.** SCL bandı ile bulutlu pikselleri
   ele, NDWI'yi ikinci görüş olarak rapora ekle. Güvenilirlik algısını
   doğrudan yükseltir.
4. **İkiden fazla tarih — zaman serisi.** Tek bir çift yerine trend grafiği.
   "Azalıyor mu?" sorusunun cevabı tek bir farkta değil, eğridedir.
5. **Kalıcı web uygulaması + rapor arşivi.** Colab notebook'u demo için yeterli
   ama satın alınabilir bir ürün değil. Kullanıcı hesabı ve geçmiş raporlara
   erişim, aboneliğin gerekçesidir.

---

## 10. Özet — akılda kalması gerekenler

1. **Su tespitini değil, uzman bağımlılığının ortadan kalkmasını sat.**
2. **En kolay ilk müşteri: rapor üretmeyi iş edinmiş çevre danışmanlık firmaları.**
3. **PDF çıktısı bir detay değil, ürünün satın alınan kısmı.**
4. **Sınırlarını kendin söyle; güvenilirlik en güçlü satış argümanın.**
5. **Bir sonraki teknik adım: piksel yerine km².**
