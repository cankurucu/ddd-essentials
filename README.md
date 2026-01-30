Domain Driven Design (DDD) Nedir?
===============================
DDD, hem stratejik hem de taktiksel olarak yüksek değer sunan yazılım geliştirmek ve işletmelerin rekabet güçlerini artırabilmeleri için gereklidir. Kurumların her konuda en iyisi olmaları mümkün değildir. Bunun temel nedeni, kaynakların, zamanın ve odak noktasının sınırlı olmasıdır. Bir organizasyonun her alanda mükemmel olmaya çalışması yerine hangi alanda fark yaratması ve uzmanlaşması gerektiğini (çekirdek yetkinlikler) dikkatle seçmesi stratejik bir zorunluluktur. Bu nedenle DDD, bir organizasyonun hangi alanlarda uzmanlaşması gerektiğini (çekirdek yetkinlikler) anlamasına ve kaynaklarını bu alanlarda kullanmasına yardımcı olur.
İşte tam bu noktada DDD, “her şeyi iyi yapmaya çalışmak” yerine “doğru şeyi çok iyi yapmak” fikrini merkeze alır. Organizasyonların hangi alanlarda odaklanması, nerelerde derinleşmesi ve hangi alanlara nasıl yatırım yapması gerektiğini netleştirir. Bu yaklaşımı daha somut hale getirmek için aşağıdaki başlıklara bakmak gerekir:

* **Stratejik Odaklanma ve Rekabet Avantajı:** Bir kurumun rakiplerinden ayrışmasını sağlayan şey, her işi yapması değil, Core Domain olarak belirlenen ve kuruma en yüksek stratejik değeri katan alanda mükemmelleşmesidir. Kurumlar en iyi kaynaklarını bu stratejik alanda kullanmalıdır.
* **Derin Öğrenme ve Uzmanlık Gereksinimi:** Bir alanda gerçekten başarılı olmak için ciddi şekilde derinlemesine öğrenme, iş birliği ve deney süreci gerekir. Hızlı ilerleyen bir sektörde kurumun her konuda bu seviyede bir uzmanlığa ulaşmak için yeterli zamanı ve bütçesi bulunmaz. Bu nedenle zamanbox (zaman sınırı) içinde en değerli alanlara odaklanmak zorundadır.
* **Farklı Yatırım Gereksinimleri:** İş süreçlerinin her biri aynı öneme sahip değildir. Kurumlar, core domain'lerin yanı sıra Supporting (Destekleyici) ve Generic (Genel) subdomain'lerle de ilgilenmek zorundadır. Ancak kurumun tüm alanlara eşit şekilde yatırım yapması verimsizdir. Bu yüzden stratejik olmayan alanlarda hazır çözümler kullanmak ya da daha az yatırım yapmak daha mantıklıdır.
* **Karmaşıklığın Yönetimi:** Bütün iş modellerini tek bir büyük yapı gibi yönetmeye çalışmak "Big Ball of Mud" (Büyük Çamur Yığını) adı verilen karmaşık ve yönetilemez sistemlere yol açar. Kurumlar, odaklarını bölerek, sınırları net belirlenmiş alanlarda (Bounded Contexts) çalışarak bu karmaşıklığı yönetebilirler.

Özetle her konuda iyi olmak kurumun enerjisini tüketir ve gerçek stratejik avantajını gölgeler. Bu yüzden en büyük yatırımın nereye yapılacağı konusunda bilinçli seçim yapılmalıdır.

## DDD'nin Çözdüğü Temel Problemler ve Sağladığı Faydalar

### Karmaşıklıkla Mücadele ve Etkin Tasarım
Yazılım projelerinde tasarımın "pahalı" olduğu düşüncesinden dolayı kervan yolda düzülür düşüncesinde çok fazla proje geliştirilmektedir. Tasarımı olmayan ya da kötü tasarlanmış bir yazılımın maliyeti ise başlangıçta yapılan etkili bir tasarımın maliyetinden çok daha yüksektir. Ancak tasarım kaçınılmazdır ve eninde sonunda tasarıma vakit ve kaynak ayırmak gerekecektir. DDD, karmaşık hale gelmiş projelerde çekilen acıyı azaltarak yazılımın business ihtiyaçlarını scale edilebilir bir mimariyle doğru bir şekilde modellenmesini sağlar.

### "Big Ball of Mud" (Büyük Çamur Yığını) Problemi
DDD uygulanmayan projelerde sınırları belirsiz ve birbirleriyle iç içe geçmiş birden fazla karmaşık modeller bir araya geldiğinde "Big Ball of Mud" (Büyük Çamur Yığını) oluşur. Bu durum sistemin bakım maliyetini artırır ve hatta imkansız hale getirebilir. DDD, Bounded Contexts kullanarak karmaşık modeller sınırları iyi bir şekilde çizilerek birbirinden ayırır ve kaosu engeller.

### Product ve Developer Arasındaki İletişim Kopukluğu
Yazılımcılar olarak genellikle teknolojiye aşırı odaklanarak asıl business operasyonlarını gözden kaçırabiliyoruz. Bu da işletmenin zihinsel modeli ile teslim edilen yazılım arasında büyük kopukluklara neden oluyor. DDD, Ubiquitous Language (Ortak Dil) aracılığıyla developer'lar ve domain expert'lerin aynı dili konuşmasını sağlar, yazılımın bu dili kod seviyesinde de yansıtmasını sağlayarak bu kopukluğu giderir.

### Teknik ve Mimari Problemler
DDD, yazılım ekiplerinin sıkça düştüğü tuzakları çözmeye yardımcı olur.

* **Teknoloji Odaklılık:** Problemleri iş mantığı yerine sadece yeni teknoloji trendleriyle çözmeye çalışmak.
* **Veritabanı Önceliği:** İş süreçlerini tartışmak yerine tartışmaların veritabanı şemaları üzerinden yapılması.
* **Yanlış Soyutlamalar:** Gelecekteki hayali ihtiyaçları karşılamak için feature-proofing yaparak gerçek iş ihtiyaçlarını ıskalamak.
* **Tightly Couple (Sıkı Bağlı) Servisler:** Servislerin doğrudan birbirine bağımlı olması sonucu bakım zorluklarının yaşanması.
* **Business Kurallarının Yanlış Yere Konumlandırılması:** Middleware, UI ve hatta veritabanı katmanlarına sızması.

## Stratejik Tasarım (Strategic Design)
DDD'nin en kritik aşamasıdır. Koda girmeden önce yapılan "geniş fırça darbelerine" benzetilir. Taktiksel tasarımın (aggregate'ler, domain event'ler vb.) etkili bir şekilde uygulanabilmesi için öncelikle stratejik tasarımın sağlan bir temel oluşturması gerekir.
Stratejik tasarım bir organizasyonun neyin stratejik olarak önemli olduğunu anlamasını sağlar. Önceki başlıklarda kurumların her konuda iyi olamayacağını ve kendini rakiplerden ayıracağı alanı seçmesi gerektiğinin önemini bahsetmiştim. Bu en önemli alana Core Domain denir.

![Insurance Domain](images/insurance-domain.png)

### Bounded Contexts
Modellerin birbirinden ayrıldığı anlamsal sınırlardır. DDD'de merkezi bir desendir. Bu sınırlar içerisinde her bileşenin belirli bir anlamı vardır ve bu anlam o bağlama özeldir. Modellerin sınırlarını net olarak çizmek Big Ball of Mud'ı (Büyük Çamur Yığını) engeller.

**Sigorta Domain'i Örneği:**
Yukarıdaki diyagramda DDD - Stratejik Tasarım bakış açısıyla çizilmiş sigortacılık sektörüne ait Bounded Context haritasını inceleyelim:
* **En dış çerçeve: Insurance Domain:** En üst seviye yani Problem Space'dir. "Biz sigortacılık işini yapıyoruz" mesajını verir.
* **Bir alt seviye: Subdomain'ler:** Insurance Domain üç ana business'a ayrılmış: Vehicle Insurance Domain, Home Insurance Domain, Life Insurance Domain.
* **Her Subdomain'in içi: Bounded Context'ler:** Her bir sigorta türünün içinde aynı isimli ama farklı anlamlara sahip bounded context'ler var: Claim Domain, Policy Domain, Customer Domain, Document Domain, Identity Domain. İsimler aynı olmasına rağmen birbirinden farklı bounded context'lerde farklı amaçlara hizmet etmektedirler. Bunların invariantları, veri yapıları ve süreçleri birbirinden farklıdır.
* **Claim Domain'in içindeki daha küçük ayrımlar:** Özellikle Vehicle ve Life arasında Motor Domain ve Boat Domain'e odaklanırsak Claim domain kendi içinde tek tip olmadığını, bazı varyasyonların ayrı modeller gerektirdiğini görüyoruz.

Bu diyagramda yeşil ile işaretlenmiş olanların Core Domain olduğunu yani kurumun rakiplerinden ayıran, en kritik business ve en çok yatırım yapılması gereken alan olduğunu görüyoruz. Buna göre Claim ve Policy Domain kurumun core domain'leri olduğunu görüyoruz.
Sarı ile işaretlenmiş olanları da business için gerekli olduğunu ancak kurumun rakiplerine karşı rekabet avantajı yaratmadığını görüyoruz. Bu domainler kolay şekilde outsource edilebilir ya da dışarıdan hazır çözümler (generic) alınarak çözüm bulunabilir.

### Ubiquitous Language (UL) (Ortak Dil)
Belirli bir Bounded Context içerisinde hem yazılımcıların hem de domain expert'lerin konuştuğu, aynı zamanda kodun içinde de kullanılan dildir.
Bounded Context başlığında bahsettiğim örneğe geri dönecek olursak, bu örnekte tek bir ubiquitous language (UL) olmadığını göreceiz.
UL sadece ilgili Bounded Context sınırları içinde geçerlidir. Örnekte aynı kelimeler farklı UL'leri temsil etmektedir.

**Vehicle Insurance Domain - Claim UL:**
* Claim
* MotorClaim
* BoatClaim
* DamageAssessment
* RepairShop
* ..
  (Burada Claim ifadesi araç hasarını temsil etmektedir.)

**Home Insurance Domain - Claim UL:**
* Claim
* PropertyDamage
* FireIncident
* FloodRisk
* LocatiomRiskZone
* ..
  (Burada ise Claim konutla ilgili riskleri temsil etmektedir.)

### Subdomains
Karmaşık business'ları mantıksal parçalara bölünmesidir. Core Domain (stratejik rekabet alanı), Supporting Subdomain (destekleyici ama çekirdek olmayan) ve Generic Subdomain (hazır çözümlerle halledilebilen) olarak üçe ayrılır.
Yukarıdaki diyagramda Insurance Domain altında bulunan Vehicle, Home ve Life Domain'lerin her biri subdomain'dir.

**Subdomain ≠ Bounded Context**
Yukarıdaki diyagrama göre subdomain ve bounded context'lerinin ayrımı şu şekilde oluyor:
* **Subdomain:** "ne iş yapıyoruz?" sorusunun cevabıdır. (Vehicle, Home, Life)
* **Bounded Context:** "bu işi hangi dil ve modelle yapıyoruz?" sorusunun cevabıdır. (Claim, Policy, Customer)

| Subdomain Türü | Diyagramdaki Karşılığı | İşteki Rolü | Neden Bu Sınıfta? | Outsource/Hazır Çözüm Uygulanabilir mi? |
| :--- | :--- | :--- | :--- | :--- |
| **Core Domain** | Claim Domain (Vehicle/Home/Life), Policy Domain | Şirketin rekabet avantajı yarattığı alan. | En karmaşık iş kurallarına sahip. Şirketi farklılaştırır. Sürekli gelişir. | Outsource edilemez. Hazır paket uygun değil. Şirket içi senior ekip gerektirir. |
| **Supporting Subdomain** | Document Domain, Customer Domain, Care Domain | Core Domain'i çalışmasını destekler. | İş için gereklidir. Rekabette fark yarattırmaz. | Kısmen outsource edilebilir. |
| **Generic Subdomain** | Identity Domain, Implicit: Notification, Logging, Auth | Her şirkette benzer yapılar vardır. | Domain bilgisi gerektirmez. | Kullanıcı yönetimi ve auth mekanizması için Keycloak/Auth0 kullanılabilir. Müşteri iletişimleri için hazır Email/SMS servisleri kullanılabilir. |

### Context Mapping
DDD'de stratejik tasarım aşamasında farklı Bounded Context'ler arasında hem ekipler arasındaki ilişkilerinin hem de teknik entegrasyon yöntemlerininin tanımlandığı yöntemdir.
Her Bounded Context'in kendine has bir ubiquitous langauge'i vardır. Context Mapping bu diller arasında tercümeyi ve etkileşim biçimini temsil eder.
Context Mapping türleri şunlardır:

#### Ekip İlişkileri ve Stratejik Yaklaşımlar
* **Partnership:** İki ekip arasındaki hedefler birbirine bağımlıdır. Ekipler ya birlikte başarılı olur ya da birlikte başarısız olurlar. Sürekli entegrasyon ve dirsek temaslı çalıştırma gerektirir. Sigorta Domaini örneğinde; Vehicle Insurance içinde Claim ile Policy domain'leri birbirlerine partnership olarak bağlıdır. Çünkü; Claim poliçe olmadan anlamsızdır, poliçe claim kuralları olmadan eksiktir.
* **Shared Kernel:** İki veya daha fazla ekibin modelin küçük ama ortak bir parçasını paylaştığı durumdur. İki bounded context'in sadece %100 ortak, davranış içermeyen ve küçük bir model parçası varsa (Örn: Money, Currency) shared kernel olarak paylaştırılabilir.
* **Customer-Supplier (Müşteri-Tedarikçi):** Supplier'ın üst akış (Upstream-U), müşterinin ise alt akış (Downstream-D) olduğu ilişkidir. Supplier değişim önceliğine sahiptir. Sigorta örneğinde; Claim Domain -> Customer, Document Domain -> Supplier'dır. 
* ![Customer-Supplier](images/customer-supplier.png)
* **Conformist (Uyumcu):** Üst akış ekibinin alt akış ekibinin ihtiyaçlarını karşılamak konusunda bir motivasyonu olmadığı durumlarda, alt akış ekibinin üst akış modelini olduğu gibi kabul ettiği durumdur. (Örn: Dışarıdan hazır alınan bir Document Management System).
* **Separate Ways (Ayrı Yollar):** Bounded Context'ler arasında entegrasyonun anlamlı bir kazanç sağlamayacağı anlaşıldığında her ekibin kendi özel çözümlerini üretmesidir.
* **Big Ball of Mud (Büyük Çamur Yığını):** Karmaşık ve sınırları belirsiz sistemlerle (legacy sistemler gibi) karşılaşıldığında, bu karmaşanın kendi modelinizi kirletmesine izin verilmemelidir.

#### Teknik Entegrasyon ve Korunma Mekanizmaları
* **Anticorruption Layer (ACL):** En savunmacı yaklaşımdır. Alt akış ekibi, dışarıdan gelen yabancı kavramların kendi modelini etkilememesi için izolasyon katmanı oluşturur. ![Anticorruption Layer](images/acl.png)
* **Open Host Service (OHS):** Bir Bounded Context'e erişimi kolaylaştırmak için tanımlanmış, dökümante edilmiş bir protokol veya API'dir. (REST, gRPC, Kafka vb.)
* **Published Language (PL):** OHS'nin konuştuğu resmi dildir. Servisi dış dünyaya açarken sahip olduğu kurallardır (JSON DTO'lar, event schema vb.).

| Kavram | Kimin için? | Amaç |
| :--- | :--- | :--- |
| **ACL** | Consumer'ı korur | Legacy kirliliğini engeller. Domain Model'e sızmayı önler. |
| **OHS** | Provider'ı korur | Entegrasyonu merkezileştirir. Açık bir kapı sunar. |
| **PL** | Client <-> Domain Model | İletişimde kullanılacak dili tanımlar (Sade tutulmalıdır). |

![Vehicle Insurance Domain Context Mapping](images/vehicle-insurance-context-mapping.png)

Kaynaklar:
* DDD Distilled Vaughn Vernon
* https://alok-mishra.com/2020/08/17/ddd-domains-bounded-contexts/
* https://www.martinfowler.com/bliki/BoundedContext.html