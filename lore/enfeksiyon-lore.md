# Veba Ekolojisi

## Hastalık, Maruziyet, Karantina ve Enfekte Davranışı

Bu dosya `enfeksiyon-lore.md` adıyla tutulur, ancak kanon başlığı **Veba Ekolojisi**dir. Çünkü içerik yalnızca "enfeksiyon" anlatmaz; hastalık profillerini, maruziyet kaynaklarını, tedavi ekonomisini, karantina siyasetini, bölge baskısını ve zombi davranış ekosistemini birlikte tanımlar.

Bu başlık altında Veba, tek bir virüs veya tek bir zombi dönüşümü olarak değil, LPZ dünyasının beden, toplum, bölge ve otorite üzerindeki toplam çürüme düzeni olarak ele alınır.

## Belge Kapsamı

Bu belge dört ana omurgayı birleştirir:

- **Hastalık omurgası:** Grip, kan enfeksiyonu, mantar enfeksiyonu, çürüme hastalığı ve su kaynaklı hastalık.
- **Maruziyet omurgası:** Bölge, iklim, kirli su, kirli bandaj, yara, toksisite, ıslaklık, açlık ve susuzluk.
- **Karantina omurgası:** Doktor, asker, koloni, pazar, sürgün, kayıt, ihbar ve tedavi hakkı.
- **Enfekte ekolojisi:** Zombi tipleri, ses, koku, kan, yara, bölge ekolojisi ve karantina baskısı.

## Kaynak ve Kanon

Bu belge, LPZ enfeksiyon kurgusunu `C:\Program Files (x86)\gtaserver` içindeki mevcut sistemlere göre tanımlar. Ana referanslar:

- `docs/survival_disease_engine.md`
- `gamemodes/modules/survival/survival_disease.inc`
- `gamemodes/modules/survival/survival_exposure.inc`
- `gamemodes/modules/survival/survival_climate_core.inc`
- `gamemodes/modules/survival/survival_zone_core.inc`
- `gamemodes/modules/survival/survival_zone_ecology.inc`
- `gamemodes/modules/survival/survival_zombie_ai.inc`
- `gamemodes/modules/survival/zombie/*.inc`

LPZ'de enfeksiyon, tek bir "zombi virüsü" değildir. Oyun sisteminde hastalık; bölge riski, iklim, ıslaklık, vücut sıcaklığı, toksisite, kirli su, kirli bandaj, yara, açlık, susuzluk ve koruyucu ekipman üzerinden çalışan çok katmanlı bir hayatta kalma motorudur.

Lore tarafında halk bu karmaşık tabloya tek ad verir:

**Veba.**

Veba, mekanik olarak tek hastalık profili değildir. Veba; çöküş sonrası dünyada insanların grip, kan enfeksiyonu, mantar, çürüme ve su kaynaklı hastalıkları anlamlandırmak için kullandığı ortak korku dilidir.

## Temel İlke

Enfeksiyon sistemi üç şeyi aynı anda üretir:

- **Beden krizi:** Oyuncu maruziyet, kuluçka, semptom, tedavi ve iyileşme süreci yaşar.
- **Toplum krizi:** Koloni, karantina, ihbar, tedavi hakkı, sürgün ve kaynak paylaşımı kararı verir.
- **Bölge krizi:** Hastalık riski haritanın bazı bölgelerini ekonomik, askeri ve siyasi olarak değiştirir.

Bu yüzden enfeksiyon LPZ'de sadece can azaltan bir PvE sistemi değildir. Bir koloninin adalet anlayışını, doktorların değerini, temiz suyun gücünü ve karantina siyasetini belirleyen ana dünya motorudur.

## Veba Nedir?

Veba, halk dilinde çöküşten sonra görülen bütün salgın ve bozulma belirtilerinin ortak adıdır. Eski dünyanın tıbbi dosyaları hastalıkları ayrı ayrı sınıflandırır; halk ise ayrım yapmaz. Ateşlenen, yarası kararan, kirli sudan çöken, bodrum neminde mantar kapan veya ceset kokusuyla hastalanan herkes için aynı söz kullanılır:

**Vebaya yakalandı.**

Bu ayrım önemlidir.

Bir doktor için hasta "kan enfeksiyonu" taşıyor olabilir. Bir asker için aynı kişi "karantina riski"dir. Bir köylü için "Vebalı"dır. Bir kaçak doktor için ise doğru ilaç bulunursa kurtarılabilecek bir bedendir.

## Mekanik Hastalık Profilleri

gtaserver sisteminde beş ana hastalık profili bulunur.

| Sistem Anahtarı | Lore Adı | Kaynak Mantığı | Ana Risk |
| --- | --- | --- | --- |
| `flu` | Grip | Soğuk, ıslaklık, yağmur, yetersiz kıyafet | Ateş, öksürük, zayıflama |
| `blood_infection` | Kan Enfeksiyonu | Kirli yara, kirli bandaj, kesik ve travma | Yara iltihabı, hızlı kötüleşme |
| `fungal` | Mantar Enfeksiyonu | Nemli, toksik, kapalı ve çürümüş alanlar | Kaşıntı, deri bozulması, uzun baskı |
| `corpse_rot` | Çürüme Hastalığı | Ceset yoğunluğu, karantina alanı, çürüme baskısı | Bulantı, çöküş, yüksek ölüm baskısı |
| `waterborne` | Su Kaynaklı Hastalık | Kirli su, kontamine kap, arıtılmamış kaynak | Mide krizi, susuzluk, kusma |

Bu profillerin tamamı Veba başlığı altında anlatılabilir, ancak RP ve admin kararlarında hangi profilin çalıştığı açık olmalıdır. Çünkü grip ile çürüme hastalığı aynı sosyal korkuyu üretse de aynı tedaviyi, aynı karantina süresini veya aynı bölge politikasını doğurmaz.

## Hastalık Değerleri

Sistemde her hastalığın maruziyet eşiği, kuluçka süresi, evre sınırı, ilerleme hızı, iyileşme hızı ve beden baskısı vardır.

| Hastalık | Maruziyet Eşiği | Kuluçka | Aktif | Ağır | Kritik | İlerleme | İyileşme |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| Grip | 1250 | 900-5400 sn | 1400 | 5200 | 9000 | 16 | 12 |
| Kan Enfeksiyonu | 950 | 600-3600 sn | 1200 | 4200 | 7600 | 24 | 8 |
| Mantar Enfeksiyonu | 1150 | 1800-10800 sn | 1500 | 5600 | 8800 | 14 | 10 |
| Çürüme Hastalığı | 1400 | 1200-7200 sn | 1600 | 4600 | 7800 | 28 | 5 |
| Su Kaynaklı Hastalık | 850 | 600-5400 sn | 1100 | 3900 | 7200 | 22 | 9 |

Bu tablo lore açısından şunu söyler:

- **Kan enfeksiyonu** erken başlar ve hızlı ilerler.
- **Su kaynaklı hastalık** düşük eşikle tehlikeye girer; kirli su sıradan bir içecek değil, stratejik risktir.
- **Çürüme hastalığı** daha geç görünse bile ağırlaştığında ölüm baskısı yüksektir.
- **Mantar enfeksiyonu** yavaş işler; nemli ve kapalı bölgelerde kronik tehdit üretir.
- **Grip** basit görünür ama soğuk, yağmur ve yetersiz ekipmanla kitlesel soruna dönüşür.

## Hastalık Evreleri

Sistem evreleri şunlardır:

| Sistem Evresi | Lore Karşılığı | RP Anlamı |
| --- | --- | --- |
| `none` | Temiz | Kayıtlı hastalık yoktur. Risk yine de çevreden gelebilir. |
| `exposed` | Maruz | Beden risk almıştır; henüz toplum fark etmeyebilir. |
| `incubating` | Kuluçka | Hastalık içeride ilerler, belirti sınırlıdır. |
| `active` | Aktif | Semptomlar görünür hale gelir. Doktor ve karantina kararı başlar. |
| `severe` | Ağır | Hasta üretim, savaş ve yolculuk için risklidir. |
| `critical` | Kritik | Tıbbi müdahale, izolasyon veya siyasi karar gerekir. |
| `recovering` | İyileşme | Hastalık düşüştedir ama hasta hemen güvenli sayılmaz. |

Veba korkusunun temeli budur: toplum genellikle `active` evresini görür, ama hasta `exposed` veya `incubating` evresindeyken karar veremez. Bu belirsizlik sahte ihbar, panik karantina ve doktor baskısı üretir.

## Maruziyet Kaynakları

Hastalık sisteme altı ana kaynakla girer.

| Kaynak | Sistem Anlamı | Lore Kullanımı |
| --- | --- | --- |
| `zone` | Bölge hastalık riski | Karantina hastanesi, çürümüş mahalle, nemli bodrum |
| `climate` | İklim ve çevre baskısı | Soğuk, yağmur, nem, toksik hava, kapalı alan |
| `item` | Eşya kaynaklı risk | Kirli bandaj, kontamine kap, hatalı tedavi |
| `wound` | Yara ve travma | Paslı metal, kesik, açık yara, savaş sonrası enfeksiyon |
| `water` | Sıvı tüketimi | Kirli su, arıtılmamış bidon, kontamine kaynak |
| `admin` | Yetkili müdahalesi | Event, test, ceza değil hikaye aracı |

Bu yapı sayesinde hastalık "rastgele oldu" hissi vermemelidir. Her vaka bir iz bırakmalıdır: nereden geldi, kim sakladı, hangi eşya kirliydi, hangi bölge uyarı vermedi, hangi doktor geç kaldı?

## İklim ve Beden Baskısı

Sistem sadece hastalık değerlerine bakmaz. Oyuncunun bedeni de hesaplanır.

Ana baskılar:

- Islaklık
- Vücut sıcaklığı
- Toksisite
- Açlık
- Susuzluk
- Yaralanma
- Koruyucu ekipman puanı
- Hastalığa direnç

Açlık ve susuzluk düşükse beden daha savunmasız olur. Islaklık ve soğuk grip riskini yükseltir. Nem ve toksik alan mantar ile çürüme baskısını artırır. Yaralı beden kan enfeksiyonuna daha açık hale gelir.

Bu yüzden LPZ'de hayatta kalma sadece silah bulmak değildir. Kuru kalmak, temiz su bulmak, yarayı doğru sarmak ve doğru kıyafeti giymek doğrudan politik güçtür.

## Bölge Hastalık Mantığı

Bölgeler hastalık profili ve risk değeri taşıyabilir. Örnek teknik kullanım:

`/lootzonedisease quarantine_hospital corpse 750`

Bu komut mantığı lore'a şöyle çevrilir:

Bir hastane kalıntısı sadece loot noktası değildir. Çürüme hastalığı baskısı olan, eski sedyelerin, kapalı odaların ve başarısız karantina protokollerinin hala bedel ürettiği bir risk alanıdır.

Bölge hastalık tasarımı şu kurala uymalıdır:

- Veba Kenti: çürüme, kan enfeksiyonu, kapalı alan mantarı
- Hasat Hattı: su kaynaklı hastalık, nem, kirli sulama kanalları
- Hurda Harabesi: kan enfeksiyonu, kesik, toksik atölye, metal yarası
- Son Geçit: grip, yol yorgunluğu, yağmur, kirli su ticareti
- Sürgün Çukuru: kayıt dışı tedavi, kirli bandaj, karaborsa ilaç
- Sıfır Bölgesi: yüksek karantina baskısı, çürüme, toksisite, endgame olayları

## Koruyucu Ekipman

Sistemde koruyucu ekipman sadece kozmetik değildir. Biyolojik, toksik, soğuk, sıcak, ıslaklık ve filtre değerleri üzerinden maruziyeti etkiler.

Koruma mantığı:

- Biyolojik koruma hastalık maruziyetini azaltır.
- Toksik koruma çürüme ve mantar baskısını düşürür.
- Islaklık koruması grip ve mantar riskini azaltır.
- Soğuk koruması düşük vücut sıcaklığına bağlı grip riskini düşürür.
- Filtre isteyen ekipman, filtresiz veya bitmiş filtreyle tam değer vermez.
- Ekipman kondisyonu korumanın güvenilirliğini belirler.

Öne çıkan ekipmanlar:

| Eşya | Lore Rolü |
| --- | --- |
| `surgical_mask` | Ucuz, sınırlı biyolojik koruma |
| `respirator` | Daha güvenilir solunum koruması |
| `gas_mask` | Karantina ve toksik bölge sembolü |
| `filter_cartridge` | Maskenin gerçek ömrünü belirleyen kaynak |
| `safety_goggles` | Göz koruması, arşiv ve hastane görevleri |
| `hazmat_hood` | Baş ve yüz izolasyonu |
| `hazmat_suit` | Yüksek riskli bölge kıyafeti |
| `nbc_suit` | Askeri seviye karantina ekipmanı |
| `rubber_gloves` | Tedavi, ceset ve kirli su temasında kritik |
| `work_gloves` | Hurda ve yara riskini azaltan iş ekipmanı |
| `raincoat` | Yağmur, ıslaklık ve grip riskine karşı pratik çözüm |
| `winter_coat` | Soğuk bölgede beden sıcaklığını korur |
| `rubber_boots` | Su, kanal ve batak alanlarında değerli |
| `combat_boots` | Yolculuk ve çatışma dayanımı |
| `combat_helmet` | Doğrudan hastalık değil, saha güvenliği |

Bu ekipmanların varlığı koloniler arasında sınıf farkı üretir. Maskesi olan hastaya yaklaşabilir. Eldiveni olan ceset taşıyabilir. Filtresi olan karantinaya girebilir. Filtresi olmayan kapıda bekler.

## Tedavi Mantığı

Tedavi sistemi hastalığı tek tuşla silmez. Maruziyeti, ilerlemeyi, şiddeti veya direnci değiştirir. Bazı itemlar yanlış kullanılırsa riski artırır.

| Item Anahtarı | Hedef | Lore Etkisi |
| --- | --- | --- |
| `clean_bandage` | Kan enfeksiyonu | Yarayı kontrol altına alır, direnci artırır. |
| `dirty_bandage` | Kan enfeksiyonu | Tedavi gibi görünür ama kirli maruziyet ekler. |
| `antiseptic` | Kan enfeksiyonu | En güvenilir saha temizleyicisidir. |
| `antibiotics` | Kan, su, çürüme | Güçlü ama sınırlı ilaç; pazar değeri yüksektir. |
| `antifungal_meds` | Mantar | Nemli ve kapalı bölge hastalıklarına karşı özelleşir. |
| `flu_medicine` | Grip | Soğuk ve yağmur sonrası kitlesel kullanım görür. |
| `charcoal_tablets` | Su kaynaklı | Kirli su sonrası en değerli düşük teknoloji çözümlerden biridir. |
| `water_purifier` | Su kaynaklı | Kaynak savaşlarının ana stratejik itemıdır. |

Tedavi RP'sinde doğru soru "ilaç var mı?" değildir.

Doğru sorular:

- İlacı kim kontrol ediyor?
- Hasta tedaviye değer mi?
- İlaç temiz mi, tarihi geçmiş mi, karaborsa mı?
- Kirli bandajı kim sattı?
- Antibiyotik askere mi, çiftçiye mi, doktora mı verilecek?
- Bir koloninin son su arıtıcısı mültecilere açılacak mı?

## Sıvı ve Kirli Su

Sistemde sıvı tüketimi hastalıkla doğrudan bağlıdır. Kirli su içmek `waterborne` maruziyeti üretir. Kontamine kaplar da risk taşır.

Teknik davranış:

- Kirli su içildiğinde mide ve enfeksiyon riski artar.
- Maruziyet içilen miktar ve kontaminasyon seviyesine göre yükselir.
- Boş şişe ve bidonlar temiz kaynak bulma politikasını önemli hale getirir.
- `water_purifier` ve `charcoal_tablets` sadece medikal değil, ekonomik güçtür.

Lore karşılığı:

Hasat Hattı'nda sulama kanalı yalnızca tarım altyapısı değildir. Bir köyün hasta olup olmayacağını belirleyen siyasi damardır. Son Geçit'te satılan su şişesi sadece eşya değildir; güvenilirliği kanıtlanmamışsa kervanın tamamını düşürebilecek sessiz silahtır.

## Semptom Sistemi

Semptomlar hastalık türüne, evreye, şiddete, şansa ve bekleme süresine göre çalışır. Sistem AME/DO metinleri ve animasyonlarla oyuncunun durumunu görünür hale getirir.

Varsayılan semptom mantığı:

| Hastalık | Semptom Yönü | RP Sinyali |
| --- | --- | --- |
| Grip | Öksürük, ateş, zayıflık | Kalabalıkta panik ve karantina tartışması |
| Kan Enfeksiyonu | Yara kızarması, iltihap, ağrı | Kirli bandaj veya tedavi ihmali şüphesi |
| Mantar | Kaşıntı, deri tahrişi | Nemli bodrum, kapalı depo, toksik alan izi |
| Çürüme | Bulantı, çökme, kötüleşme | Ceset bölgesi veya karantina kalıntısı şüphesi |
| Su Kaynaklı | Karın ağrısı, kusma | Kirli kaynak, sabotaj veya ihmalkar su dağıtımı |

Semptomlar karakteri hemen "zombi" ilan etmek için kullanılmamalıdır. Semptomun gücü, karar belirsizliğinden gelir.

## Zombi Sistemiyle Bağlantı

Hastalık motoru ile zombi AI aynı şey değildir. Hastalık oyuncu bedenini yönetir; zombi sistemi çevre tehdidini yönetir. Ancak ikisi aynı dünya mantığında birleşir.

Zombi sistemi şu değerlerden beslenir:

- Bölge ekolojisi
- Karantina baskısı
- Hastalık profili
- Toksisite
- Nem ve iklim
- Oyuncu sesi
- Oyuncu kokusu
- Kan ve yara sinyali
- Görünürlük
- Bellek ve son temas noktası

Bu yüzden hasta veya yaralı bir karakter sadece kendi canı için riskte değildir. Koku, kan, yara ve enfeksiyon baskısı çevredeki tehdidi de etkileyebilir.

## Zombi Tipleri

Kodda tanımlı zombi tipleri şunlardır:

| Sistem Tipi | Lore Adı | Kullanım |
| --- | --- | --- |
| `walker` | Yürüyen | Ana sürü bedeni; yavaş ama kalabalıkta ölümcül. |
| `infected` | Enfekte | Hastalık profili veya nemli bölge etkisiyle öne çıkar. |
| `bloater` | Şişkin | Toksik ve çürümüş alanların ağır tehdidi. |
| `crawler` | Sürünen | Görüşü ve hareketi kıran yakın mesafe tehdidi. |
| `dormant` | Uykuda | Kapalı alan, arşiv, bodrum ve hastane korkusu. |
| `runner` | Koşucu | Kodda tanımlıdır ama mevcut ayarda kapalıdır. |
| `feral` | Yabanıl | Kodda tanımlıdır ama mevcut ayarda kapalıdır. |

Bu ayrım korunmalıdır. Mevcut oyun yapımında hızlı zombi türleri sistemde tanımlı olsa bile aktif değildir. Bu yüzden lore'da koşucu veya yabanıl türler standart tehdit gibi yazılmamalıdır. Kullanılacaksa sezonluk event, test alanı veya özel admin kararı olarak ele alınmalıdır.

## Zombi Davranışları

Zombi AI durumları sadece "görür ve saldırır" mantığında değildir. Kodda zombi davranışı şu hallerle düşünülür:

- Doğma
- Boşta bekleme
- Gezinme
- Araştırma
- Takip
- Kovalama
- Saldırı
- Yakalama
- Beslenme
- Sarsılma
- Bölgeye dönme
- Yok olma
- Ölme

Algı kaynakları:

- Görüş
- Ses
- Koku
- Kan
- Hafıza
- Yara
- Grup sinyali
- Yol kapanması

Lore karşılığı şudur: Enfekte sürüleri rastgele duvar gibi yazılmamalıdır. Ses çıkaran, kanayan, yaralı veya kötü korunan bir ekip daha çok dikkat çeker. Maskeli, kuru, sessiz ve düzenli hareket eden ekip daha uzun yaşar.

## Hareket Biçimleri

Zombi hareket stilleri:

| Sistem Stili | Lore Karşılığı |
| --- | --- |
| `shamble` | Sallanarak yürüme |
| `limp` | Aksayarak ilerleme |
| `drag` | Sürüklenme |
| `heavy` | Ağır ve baskılı hareket |
| `crawl` | Sürünme |
| `dormant` | Uykuda bekleme |

Bu stiller, bölge atmosferi için kullanılmalıdır. Veba Kenti'nde uykuda bekleyen eski hastalar, Hurda Harabesi'nde sürüklenen yarım bedenler, Sıfır Bölgesi'nde ağır ve toksik şişkinler aynı sistemin farklı yüzleridir.

## Bölgelere Göre Veba Dili

### Veba Kenti

Eski hastaneler, arşivler, sedye odaları, kapalı koridorlar ve başarısız karantina alanları Veba Kenti'nin ana tehditleridir. Burada çürüme hastalığı, kan enfeksiyonu ve kapalı alan mantarı öne çıkar.

Veba Kenti'nde loot almak, sadece eski dünyadan eşya çalmak değildir. Her dosya, her ilaç kutusu ve her kilitli koğuş bir karantina kararının kalıntısıdır.

### Hasat Hattı

Hasat Hattı'nın en büyük hastalık riski sudur. Sulama kanalı kirlenirse açlık değil, önce hastalık gelir. Temiz suyu yöneten kişi sadece tarlayı değil, köyün bedenini de yönetir.

Buradaki temel RP çatışması:

- Su arıtıcı kime verilecek?
- Kirli kanal kapatılırsa hasat düşecek mi?
- Mülteciler temiz kuyudan içebilecek mi?
- Hasta işçi tarladan uzaklaştırılacak mı?

### Hurda Harabesi

Hurda Harabesi paslı metal, açık yara, kesik, yağ, kimyasal ve toksik atölye alanıdır. Kan enfeksiyonu burada sıradan bir kaza değil, üretim bedelidir.

Bir jeneratör parçası kurtarmak, bazen üç işçinin kirli bandajla eve dönmesi demektir.

### Son Geçit

Son Geçit'te hastalık yolculukla yayılır. Yağmur, soğuk, yetersiz kıyafet, kirli matara ve kalabalık mola noktaları grip ile su kaynaklı hastalığı büyütür.

Bir kervan sadece mal taşımaz. Dedikodu, semptom, sahte ilaç ve kirli su da taşır.

### Sürgün Çukuru

Sürgün Çukuru'nda geçmiş sorulmaz; bandajın temiz olup olmadığı da çoğu zaman sorulmaz. Kaçak doktorlar, tarihi belirsiz antibiyotikler, kirli su arıtıcıları ve sahte respiratorler burada dolaşır.

Sürgün Çukuru'nun korkusu hastalığın kendisi değil, tedavinin pazarlığa dönüşmesidir.

### Sıfır Bölgesi

Sıfır Bölgesi, mevcut sistemde tek bir hastalık anahtarıyla açıklanmamalıdır. Burası karantina baskısı, toksisite, çürüme, kapalı tesisler ve eski emirlerin birleştiği endgame alanıdır.

Sıfır Bölgesi'nin gücü cevap vermesinde değil, doğru soruyu dayatmasındadır:

Karantina başarısız mı oldu, yoksa hiç bitmedi mi?

## Güç Odaklarının Hastalık Siyaseti

### Karakol-12

Hastalığı güvenlik meselesi olarak görür. Karantina, devriye, kayıt, giriş çıkış yasağı ve zorla izolasyon Karakol-12'nin refleksidir.

Güçlü yanı hızlı müdahaledir. Zayıf yanı, semptom ile suç arasındaki çizgiyi kolayca silmesidir.

### Beyaz Vadi

Hastalığı veri ve tedavi meselesi olarak görür. Numune, kayıt, semptom takibi, ilaç protokolü ve hasta geçmişi ister.

Güçlü yanı tedavi bilgisidir. Zayıf yanı, insanı dosyaya dönüştürme riskidir.

### Başak Surları

Hastalığı üretim ve toplum dengesiyle tartar. Hasta işçi, kirli kuyu, karantina altındaki tarla ve mülteci kampı doğrudan hasat meselesidir.

Güçlü yanı toplumsal dayanıklılıktır. Zayıf yanı, kaynak azaldığında merhametin hesap defterine dönüşmesidir.

### Tuz Pazarı

Hastalığı bilgi ve ticaret fırsatı olarak görür. Antibiyotik, maske, filtre, temiz bandaj, su arıtıcı ve hasta dedikodusu burada para eder.

Güçlü yanı her şeyi bulabilmesidir. Zayıf yanı, her şeyin bedelini yükseltmesidir.

### Koro Mahzenleri

Hastalığı sadece tıbbi olay olarak değil, eşik deneyimi olarak yorumlar. Semptomu kehanete, karantinayı ritüele, iyileşmeyi işarete dönüştürebilir.

Güçlü yanı korkuya anlam vermesidir. Zayıf yanı, anlam ararken tedaviyi geciktirmesidir.

### Kızıl Eşik

Hastalığı eski dünyanın çürümesinin kanıtı sayar. Tedaviyi bazen düzenin yalanı, karantinayı bazen temizlik fırsatı, hastayı bazen propaganda malzemesi olarak kullanır.

Güçlü yanı krizi politik dile çevirmesidir. Zayıf yanı, insan hayatını sembole indirgemesidir.

## Karantina Kültürü

Karantina LPZ'de sadece kapı kilitlemek değildir. Karantina şu soruları üretir:

- Kim içeri alınacak?
- Kim dışarıda bırakılacak?
- Hastayı kim muayene edecek?
- Temaslılar kim?
- Eşya yakılacak mı?
- Su kaynağı kapatılacak mı?
- Koloni üretimi duracak mı?
- Karar tıbbi mi, askeri mi, siyasi mi?

Karantina kararları her zaman bedel üretmelidir. Bedelsiz karantina, dramatik olarak zayıftır. Doğru karantina bile birini aç bırakabilir, bir kervanı geciktirebilir, bir aileyi bölebilir veya bir koloniyi savaşa sürükleyebilir.

## Sahte Vaka ve İhbar

Veba korkusu sosyal silahtır.

Bir kişiye "Vebalı" demek, bazı bölgelerde mahkeme kararı kadar ağırdır. Bu yüzden sahte ihbar lore'un doğal parçasıdır.

Sahte vaka suçlaması şu amaçlarla kullanılabilir:

- Rakibi koloniden attırmak
- Miras veya depo hakkını ele geçirmek
- Kervanı durdurmak
- Köy kuyusunu kapattırmak
- Doktoru siyasi baskı altına almak
- Karakol-12 müdahalesi çağırmak
- Tuz Pazarı'nda ilaç fiyatını yükseltmek
- Koro Mahzenleri için "işaret" üretmek

Sahte ihbar yakalanırsa yalnızca yalancı cezalandırılmamalıdır. Ona inanmak isteyen düzen de zarar görmelidir.

## Taşıyıcı Meselesi

Mevcut gtaserver hastalık sisteminde "taşıyıcı" ayrı ve kesin bir mekanik tür olarak kurulmamıştır. Bu yüzden taşıyıcı kavramı dikkatli kullanılmalıdır.

Doğru kullanım:

- Kuluçka evresindeki hasta
- Semptomu hafif ama riskli kişi
- Tedavisi yarım kalmış vaka
- Kirli su veya yara geçmişi saklanan karakter
- Politik olarak "Vebalı" ilan edilmiş masum kişi

Yanlış kullanım:

- Kesin bağışık seçilmiş kişi
- Enfekteleri kontrol eden insan
- Her hastalığı yayan özel sınıf
- Kolay tedavi anahtarı
- Sürekli kullanılan sezon hilesi

Taşıyıcı hikayesi cevap değil, soru üretmelidir.

## Sıfır Bölgesi Yorumu

Sıfır Bölgesi, enfeksiyon sisteminin üst lore düğümüdür. Fakat sistemsel olarak "Sıfır hastalığı" diye ayrı bir profil yoktur. Bu alan, mevcut profillerin en sert birleşimi olarak yazılmalıdır:

- Yüksek karantina baskısı
- Toksik iklim
- Çürüme hastalığı
- Kapalı tesis mantarı
- Kirli su
- Eski askeri emirler
- Eksik tıbbi kayıtlar
- Yanlış uygulanmış izolasyon protokolleri

Sıfır Bölgesi'nin mesajı net olmalıdır:

> Karantina başarısız olmadı.
> Karantina bitmedi.

Bu cümle kesin cevap değil, sezon motorudur. Bir grup bunu tedavi umudu olarak yorumlayabilir. Bir grup biyolojik silah kanıtı sayabilir. Bir grup eski dünyanın son yalanı diyebilir.

Hangisinin doğru olduğu hemen açıklanmamalıdır.

## Oyuncu Komutlarının Lore Karşılığı

Sistemde oyuncu tarafında hastalık ve hayatta kalma için kullanılan komutlar vardır. Bunlar RP'de görünmez UI işlemi gibi değil, karakter eylemi gibi yorumlanmalıdır.

| Komut | Lore Karşılığı |
| --- | --- |
| `/hastalik` | Kişinin kendi beden durumunu kontrol etmesi |
| `/semptomlar` | Görünür belirti ve hisleri takip etmesi |
| `/tedavi [item_uid]` | Belirli bir item ile müdahale |
| `/maruziyet` | Çevre ve beden riskini okuma |
| `/envanter` | Tıbbi ve hayatta kalma kaynaklarını kontrol |
| `/itemkullan` | İlaç, ekipman veya tüketilebilir kullanımı |
| `/siviic` | Sıvı tüketimi |
| `/nearitems` | Yakındaki kaynakları arama |

Bu komutlar karakterin dünyayla temasını güçlendirmek için kullanılmalıdır. Örneğin `/tedavi` sadece butona basmak değil, yaranın temizlenmesi, bandajın değişmesi, ilacın yutulması veya doktorun müdahalesidir.

## Admin ve Event Araçları

Admin komutları ceza aracı değil, hikaye motoru olarak kullanılmalıdır.

Öne çıkan sistem araçları:

| Komut | Kullanım |
| --- | --- |
| `/diseasepanel` | Hastalık profilleri, oyuncu durumları, tedavi ve audit takibi |
| `/diseasedebug` | Test ve hata ayıklama |
| `/diseasegive [flu|blood|fungal|corpse|water] [severity 1-4]` | Kontrollü event vakası |
| `/diseaseclear` | Hatalı veya bitmiş vaka temizliği |
| `/diseaseset` | Özel ayar |
| `/diseasereload` | Profil yenileme |
| `/exposuredebug` | Maruziyet sistemi kontrolü |
| `/protectiondebug` | Ekipman koruma kontrolü |
| `/exposureset` | Maruziyet ayarı |
| `/exposureclear` | Maruziyet temizliği |
| `/lootzonedisease` | Bölge hastalık profili |
| `/lootzoneclimate` | Bölge iklim profili |
| `/lootzonerad` | Bölge radyasyon değeri |
| `/lootzonepolicy` | Bölge davranış politikası |

Event tasarımında önce neden belirlenmelidir:

- Bu vaka hangi kaynaktan geldi?
- Hangi bölge veya item sorumlu?
- Hangi koloni karar vermek zorunda?
- Tedavi mümkün mü, pahalı mı, politik mi?
- Karantina kime yarıyor?
- Oyuncuların seçimi dünyada neyi değiştirecek?

## Audit ve Kayıt Kültürü

Sistemde hastalık olayları kayıt altına alınır. Bu teknik yapı lore'da önemli bir kültüre dönüşür:

- Beyaz Vadi kayıt ister.
- Karakol-12 temas zinciri çıkarır.
- Tuz Pazarı kayıtları satar veya değiştirir.
- Başak Surları iş gücü kaybını hesaplar.
- Kızıl Eşik kayıtları propaganda dosyasına çevirir.
- Koro Mahzenleri kayıtları kutsal işaret gibi yorumlar.

Hastalık kaydı sadece medikal belge değildir. Kimin içeri alınacağını, kimin sürüleceğini, kimin tedavi göreceğini ve kimin suçlanacağını belirleyen siyasi evraktır.

## RP Kullanım İlkeleri

Enfeksiyon olayları şu ilkelerle yazılmalıdır:

- Her hastalığın mekanik kaynağı olmalı.
- Semptom ile kesin suç aynı şey sayılmamalı.
- Tedavi mümkün olabilir ama bedelsiz olmamalı.
- Kirli su ve kirli bandaj hafife alınmamalı.
- Koruyucu ekipman sınıf farkı üretmeli.
- Karantina hem doğru hem acımasız olabilir.
- Zombi tehdidi hastalık motoruyla karıştırılmamalı, ama aynı ekosisteme bağlanmalı.
- Koşucu ve yabanıl türler mevcut ayarda standart düşman gibi yazılmamalı.
- Sıfır Bölgesi cevap deposu değil, sezon sorusu olmalı.

## Yasaklı Kolay Cevaplar

LPZ enfeksiyon kurgusunda şu kolay cevaplar kullanılmamalıdır:

- Her şeyi açıklayan tek virüs.
- Her hastalığı iyileştiren tek serum.
- Sürekli kullanılan seçilmiş taşıyıcı.
- Enfekteleri kontrol eden özel insan sınıfı.
- Hastalığı tamamen ortadan kaldıran kısa event.
- Koruyucu ekipmanı önemsizleştiren sahne.
- Kirli suyu sadece susuzluk mekaniği saymak.
- Karantina kararını sonuçsuz bırakmak.

Veba'nın gücü bilinmezlikte değil, sistemli belirsizliktedir. Oyuncu her şeyi bilmek zorunda değildir; ama admin ve yazar, her vakanın hangi mekanikten doğduğunu bilmelidir.

## Kısa Kanon Özeti

Veba, LPZ halkının çöküş sonrası hastalıklar için kullandığı ortak addır.

Gerçek sistem beş profile dayanır: grip, kan enfeksiyonu, mantar enfeksiyonu, çürüme hastalığı ve su kaynaklı hastalık.

Hastalık; bölge, iklim, yara, eşya, su ve beden direnciyle büyür.

Tedavi anlık mucize değil, maruziyet ve ilerlemeyi yöneten kaynak savaşıdır.

Zombi sistemi ayrı çalışır; ama hastalık, kan, yara, koku, toksisite ve bölge ekolojisi aynı dünyanın parçalarıdır.

Karantina tıbbi karar olduğu kadar siyasi karardır.

Sıfır Bölgesi, Veba'nın cevabı değil; dünyanın hala kapanmamış dosyasıdır.
