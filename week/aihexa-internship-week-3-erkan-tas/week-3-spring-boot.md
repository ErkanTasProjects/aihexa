# Week 3 - Spring Boot Temelleri ve Backend Mantığı

## Spring Boot nedir?
Spring Boot, Java programlama dili ile backend (sunucu tarafı) uygulamaları hızlı ve kolay şekilde geliştirmeyi sağlayan bir framework'tür (çatı yapı). Normalde Java ile bir sunucu uygulaması kurmak uzun ve karmaşık ayarlar gerektirirken, Spring Boot bu ayarların çoğunu otomatik hale getirerek geliştiriciyi doğrudan iş mantığına odaklanmaya bırakır.
**AIHEXA'da kullanımı:** AIHEXA'nın eğitim platformu, randevu sistemi gibi modüllerinin arka planda çalışan sunucu tarafı Spring Boot ile yazılabilir.

## Backend nedir?
Backend, kullanıcının doğrudan görmediği, verilerin işlendiği, saklandığı ve kurallara göre kontrol edildiği sunucu tarafıdır. Frontend (React gibi) kullanıcının gördüğü ekranları oluştururken, backend bu ekranların arkasındaki veri işlemlerini yürütür.
**AIHEXA'da kullanımı:** Bir kullanıcı eğitime başvurduğunda, bu başvurunun kaydedilmesi, kontrol edilmesi ve veritabanına yazılması backend tarafında gerçekleşir.

## REST API nedir?
REST API, frontend ile backend'in birbiriyle konuşabilmesi için belirlenmiş kurallar bütünüdür. Frontend, belirli bir adrese (endpoint) istek gönderir, backend bu isteği işleyip bir cevap (response) döner. Genelde JSON formatında veri alışverişi yapılır.
**AIHEXA'da kullanımı:** React ile yazılan başvuru formu, verileri REST API üzerinden Spring Boot backend'ine gönderir.

## Controller nedir?
Controller, frontend'den gelen istekleri (request) ilk karşılayan katmandır. Hangi adrese (endpoint) hangi işlemin yapılacağını belirler ve isteği ilgili Service katmanına yönlendirir.
**AIHEXA'da kullanımı:** Örneğin "/api/applications" adresine gelen bir başvuru isteğini Controller karşılar ve işleme sokar.

## Service nedir?
Service, iş mantığının (business logic) yazıldığı katmandır. Gelen verinin kurallara uygun olup olmadığını kontrol eder, gerekli işlemleri yapar ve Repository katmanına yönlendirir.
**AIHEXA'da kullanımı:** Bir başvurunun geçerli olup olmadığını (örneğin e-posta formatı doğru mu, zorunlu alanlar dolu mu) Service katmanı kontrol eder.

## Repository nedir?
Repository, veritabanı işlemlerinin yapıldığı katmandır. Veriyi veritabanına kaydetme, veritabanından okuma, güncelleme veya silme işlemleri burada gerçekleşir.
**AIHEXA'da kullanımı:** Kullanıcının başvuru bilgilerini veritabanına kaydetmek veya var olan başvuruları listelemek Repository katmanı üzerinden yapılır.

## Entity nedir?
Entity, veritabanındaki bir tabloyu temsil eden Java sınıfıdır. Örneğin bir "User" entity'si, veritabanındaki kullanıcılar tablosundaki her bir sütunu (ad, soyad, e-posta gibi) bir alan olarak tutar.
**AIHEXA'da kullanımı:** "Application" adlı bir entity, veritabanındaki başvurular tablosunu temsil edebilir.

## DTO nedir?
DTO (Data Transfer Object), frontend ile backend arasında veri taşımak için kullanılan basit bir nesnedir. Entity'nin tüm alanlarını değil, sadece dışarıya açılması gereken alanları içerir; bu sayede veritabanı yapısı doğrudan dışarıya sızdırılmaz.
**AIHEXA'da kullanımı:** Kullanıcıya sadece başvuru durumu ve adı gösterilmek isteniyorsa, hassas bilgiler (örneğin sistemsel ID'ler) DTO ile filtrelenip sadece gerekli veri gönderilir.

## JPA nedir?
JPA (Java Persistence API), Java nesneleri ile veritabanı tabloları arasında bağlantı kurmayı sağlayan bir standarttır. Entity sınıflarının veritabanı tablolarıyla eşleşmesini sağlar.
**AIHEXA'da kullanımı:** JPA sayesinde geliştirici SQL sorgusu yazmadan, Java kodu üzerinden veritabanı işlemlerini kolayca yapabilir.

## Hibernate nedir?
Hibernate, JPA standardını uygulayan popüler bir kütüphanedir. Java nesnelerini veritabanı tablolarına, veritabanı satırlarını da Java nesnelerine otomatik olarak dönüştürür.
**AIHEXA'da kullanımı:** Spring Boot projelerinde varsayılan olarak Hibernate kullanılarak veritabanı işlemleri kolaylaştırılır.

## Maven nedir?
Maven, Java projelerinde kullanılan kütüphanelerin (bağımlılıkların) yönetildiği ve projenin nasıl derleneceğinin tanımlandığı bir araçtır.
**AIHEXA'da kullanımı:** Projede Spring Boot, veritabanı bağlantısı gibi hangi kütüphanelerin kullanılacağı Maven ile yönetilir.

## pom.xml ne işe yarar?
pom.xml, Maven'in kullandığı yapılandırma dosyasıdır. Projede hangi kütüphanelerin (dependency) kullanılacağı, proje adı, versiyon bilgisi gibi ayarlar bu dosyada tutulur.
**AIHEXA'da kullanımı:** Spring Boot, veritabanı sürücüsü gibi ihtiyaç duyulan tüm kütüphaneler pom.xml içine eklenerek projeye dahil edilir.

## application.properties nedir?
Spring Boot projesinde veritabanı bağlantı bilgileri, sunucu portu gibi ayarların satır satır (key=value formatında) tutulduğu yapılandırma dosyasıdır.
**AIHEXA'da kullanımı:** Veritabanı adresi, kullanıcı adı, şifre gibi bilgiler bu dosyada tutularak proje başlatıldığında otomatik kullanılır.

## application.yml nedir?
application.properties ile aynı işi yapan, ancak girintili (YAML formatında) daha okunaklı bir yapı sunan alternatif yapılandırma dosyasıdır.
**AIHEXA'da kullanımı:** Proje büyüdükçe ayarların daha düzenli görünmesi istenirse application.yml tercih edilebilir.

## GET, POST, PUT, DELETE metotları ne işe yarar?
Bunlar HTTP metotlarıdır ve frontend'in backend'e ne tür bir istek yaptığını belirtir:
- **GET:** Veri okumak/listelemek için kullanılır.
- **POST:** Yeni bir veri oluşturmak için kullanılır.
- **PUT:** Var olan bir veriyi güncellemek için kullanılır.
- **DELETE:** Var olan bir veriyi silmek için kullanılır.
**AIHEXA'da kullanımı:** Bir başvuru oluşturmak POST, başvuruları listelemek GET, başvuru durumunu güncellemek PUT, başvuruyu silmek DELETE ile yapılır.

## HTTP status kodları nedir?
Backend'in frontend'e isteğin sonucunu bildirmek için gönderdiği sayısal kodlardır. İsteğin başarılı mı yoksa hatalı mı olduğunu anlamayı sağlar.

- **200:** İstek başarılı.
- **201:** Yeni bir kayıt başarıyla oluşturuldu.
- **400:** İstek hatalı/eksik (örneğin zorunlu alan boş bırakılmış).
- **401:** Yetkisiz erişim, giriş yapılmamış.
- **403:** Erişim yasak, yetki yok.
- **404:** İstenen kayıt/sayfa bulunamadı.
- **500:** Sunucu tarafında beklenmeyen bir hata oluştu.

**AIHEXA'da kullanımı:** Kullanıcı başvuru formunu gönderdiğinde başvuru başarıyla oluşturulursa 201, eksik bilgi varsa 400 dönülür.

## Backend hata mesajı nasıl okunur?
Backend bir hata verdiğinde genelde bir hata mesajı ve status kodu döner. Mesaj, hatanın hangi alanda veya hangi işlemde oluştuğunu açıklar; bu sayede sorunun kaynağı anlaşılabilir.
**AIHEXA'da kullanımı:** "E-posta formatı geçersiz" gibi net bir hata mesajı, hem geliştiricinin hem de kullanıcının sorunu hızlı anlamasını sağlar.

## Stack trace backend tarafında nasıl yorumlanır?
Stack trace, bir hata oluştuğunda kodun hangi satırda ve hangi sırayla çalışıp hataya ulaştığını gösteren bir hata izidir. Genelde en üstteki satır hatanın gerçekleştiği yeri gösterir, aşağıya doğru hangi fonksiyonların sırayla çağrıldığı görülür.
**AIHEXA'da kullanımı:** Bir modülde hata oluştuğunda geliştirici stack trace'e bakarak hatanın tam olarak hangi kod satırından kaynaklandığını bulup düzeltebilir.

---

## Kullanıcı Kayıt Akışı: React Form → JSON → Controller → Service → Repository → Database → Response → Frontend

1. **Kullanıcı hangi bilgileri girer?** Kullanıcı ad, soyad, e-posta, telefon ve şifre gibi bilgileri kayıt formuna girer.

2. **React bu bilgileri nasıl toplar?** React, formdaki her input alanının değerini state (useState) ile anlık olarak tutar. Kullanıcı "Kayıt Ol" butonuna bastığında bu state'teki veriler bir araya toplanır.

3. **Backend'e hangi formatta veri gönderilir?** Toplanan veriler JSON formatına çevrilerek, POST isteğiyle backend'in ilgili endpoint'ine (örneğin /api/users) gönderilir.

4. **Controller ne yapar?** Controller, gelen bu POST isteğini karşılar, JSON verisini alır ve işlenmesi için Service katmanına iletir.

5. **Service neyi kontrol eder?** Service katmanı, gelen bilgilerin kurallara uygun olup olmadığını kontrol eder: zorunlu alanlar dolu mu, e-posta formatı doğru mu, bu e-posta daha önce kayıtlı mı gibi kontroller yapılır.

6. **Repository ne işe yarar?** Kontroller başarılıysa Service, veriyi Repository katmanına iletir. Repository bu veriyi veritabanına kaydeder.

7. **Database'e hangi bilgiler kaydedilir?** Kullanıcının ad, soyad, e-posta, telefon bilgileri ve (şifrelenmiş hâlde) şifresi veritabanındaki kullanıcılar tablosuna kaydedilir.

8. **Backend başarılı olursa frontend ne gösterir?** Backend 201 (Created) status kodu ile "Kayıt başarılı" mesajı döner, React bu cevabı alıp kullanıcıya başarı mesajı veya yönlendirme (örneğin giriş sayfasına) gösterir.

9. **Backend hata verirse frontend ne gösterir?** Backend 400 gibi bir hata kodu ve açıklayıcı mesaj (örneğin "Bu e-posta zaten kayıtlı") dönerse, React bu mesajı kullanıcıya kırmızı bir uyarı olarak ekranda gösterir.

**AIHEXA'da kullanımı:** Bu akış, AIHEXA'nın eğitim başvuru sistemi, kullanıcı kayıt sistemi gibi tüm formlu modüllerinde aynı mantıkla çalışır; frontend veriyi toplar, backend kontrol edip veritabanına işler, sonucu tekrar frontend'e bildirir.

---

## Günlük Kısa Rapor

**Bugün ne öğrendim?**
Spring Boot'un temel yapı taşlarını (Controller, Service, Repository, Entity, DTO), REST API mantığını, HTTP metotlarını ve status kodlarını öğrendim. Ayrıca bir kullanıcı kayıt işleminin frontend'den veritabanına kadar hangi aşamalardan geçtiğini kavradım.

**En çok zorlandığım konu neydi?**
Yeni terimler olduğu için  bugun daha fazla zorlandım

**GitHub'da ne oluşturdum?**
week-3-spring-boot.md dosyasını doldurdum, Spring Boot kavramlarını ve kullanıcı kayıt akışını içeren içeriği repository'ye ekledim.

**Yarın neye çalışacağım?**
Yarın React temelleri ve frontend mantığı (component, props, state, useState, useEffect) konusuna çalışacağım.
