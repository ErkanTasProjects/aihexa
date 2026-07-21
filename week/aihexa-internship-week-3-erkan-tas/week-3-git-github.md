
# Week 3 - Git / GitHub / README / Proje Dosya Disiplini

## Git nedir?
Git, bir projedeki dosyalarda yapılan değişiklikleri zaman içinde takip etmeyi sağlayan bir versiyon kontrol sistemidir. Kod üzerinde çalışırken her değişikliği kaydedebilir, istersen eski bir versiyona geri dönebilirsin. Bir nevi projenin geçmişini saklayan bir zaman makinesi gibidir.
**AIHEXA'da kullanımı:** Ekip içindeki geliştiriciler kod üzerinde çalışırken yaptıkları değişiklikleri kaybetmeden takip edebilir, hata durumunda eski versiyona dönebilir.

## GitHub nedir?
GitHub, Git ile takip edilen projelerin internet üzerinde saklandığı ve ekip halinde paylaşılabildiği bir platformdur. Git bilgisayarında çalışan sistemken, GitHub bu sistemi buluta taşıyıp ekip çalışmasını kolaylaştırır.
**AIHEXA'da kullanımı:** Farklı şehirlerde veya farklı saatlerde çalışan geliştiriciler aynı proje üzerinde GitHub sayesinde ortak çalışabilir.

## Repository (repo) nedir?
Bir projenin tüm dosyalarının ve geçmiş değişikliklerinin (commit'lerin) bir arada tutulduğu klasördür. Örneğin benim `aihexa-internship-week-3-4-erkan-tas` reposu, staj sürecindeki tüm dosyalarımı içinde barındırıyor.
**AIHEXA'da kullanımı:** Her proje veya modül için ayrı bir repository açılarak dosyalar düzenli tutulur.

## Commit nedir?
Yapılan bir değişikliği kaydetme işlemidir. Her commit, "bu an itibarıyla dosyalar böyleydi" diyen bir anlık kayıt gibidir. Örneğin `README.md` dosyasını oluşturduğumda attığım "Create README.md" işlemi bir committir.
**AIHEXA'da kullanımı:** Geliştiriciler yaptıkları her küçük değişikliği commit'leyerek projenin geçmişini adım adım takip edilebilir hale getirir.

## Branch nedir?
Ana koddan (genelde main olarak adlandırılır) ayrılan, üzerinde bağımsız çalışılabilen bir koldur. Yeni bir özellik denerken ana kodu bozmadan ayrı bir branch açılır, iş bitince ana koda birleştirilir.
**AIHEXA'da kullanımı:** Bir geliştirici yeni bir özellik eklerken diğer geliştiricilerin çalışmasını etkilemeden kendi branch'inde çalışabilir.

## Pull Request (PR) nedir?
Bir branch'te yapılan değişikliği ana koda eklemek için açılan istek/inceleme sürecidir. Ekip arkadaşları bu değişikliği inceler, uygun bulursa onaylayıp birleştirir (merge eder).
**AIHEXA'da kullanımı:** Bir geliştiricinin yazdığı kod, ana projeye eklenmeden önce başka bir geliştirici tarafından kontrol edilerek hataların önüne geçilir.

## Merge conflict nedir?
İki farklı değişiklik aynı dosyanın aynı satırını farklı şekilde değiştirdiğinde ortaya çıkan çakışma durumudur. Bu durumda hangi satırın kalacağına elle karar verilmesi gerekir.
**AIHEXA'da kullanımı:** Aynı dosya üzerinde birden fazla geliştirici çalıştığında ortaya çıkabilecek çakışmaların fark edilip düzgün şekilde çözülmesini sağlar.

## .gitignore nedir?
Git'in takip etmemesi istenen dosyaların listelendiği özel bir dosyadır. Şifre içeren dosyalar, geçici dosyalar veya `node_modules` gibi büyük klasörler buraya yazılarak yanlışlıkla GitHub'a yüklenmeleri engellenir.
**AIHEXA'da kullanımı:** Projedeki gizli bilgilerin (API anahtarları, şifreler) yanlışlıkla herkese açık şekilde paylaşılmasını önler.

## README.md dosyası neden önemlidir?
README, bir projeye ilk bakıldığında görülen dosyadır. Projenin ne olduğunu, amacını, kullanılan teknolojileri ve nasıl kullanılacağını anlatır. Düzgün bir README, projeyi tanımayan birinin bile projeyi hızlıca anlamasını sağlar.
**AIHEXA'da kullanımı:** Yeni bir geliştirici ekibe katıldığında, projeyi README sayesinde hızlıca anlayıp katkı vermeye başlayabilir.

## Issue nedir?
Bir görev, hata veya öneri için GitHub üzerinde açılan takip kaydıdır. Örneğin "Giriş sayfasında hata var" gibi bir sorun issue olarak açılır ve ilgili kişiye atanır.
**AIHEXA'da kullanımı:** Bulunan hatalar veya yapılacak işler issue olarak açılarak ekip içinde kimin ne yapacağı düzenli şekilde takip edilir.

## Bir yazılım ekibinde GitHub nasıl kullanılır?
Ekip üyeleri ortak bir repository üzerinde çalışır. Herkes kendi branch'inde geliştirme yapar, işini bitirince pull request açar, başka biri kontrol edip onaylar ve ana koda birleştirilir. Sorunlar issue olarak kaydedilir, ilerleme bu şekilde takip edilir.
**AIHEXA'da kullanımı:** Ekip üyeleri arasında kod karmaşası yaşanmadan, kimin ne üzerinde çalıştığı belli olacak şekilde düzenli bir iş akışı sağlanır.

## Commit mesajı nasıl yazılmalıdır?
Commit mesajı kısa, net ve neyin değiştiğini açıklayan şekilde yazılmalıdır. "Değişiklik yaptım" gibi belirsiz mesajlar yerine "README dosyasına günlük ilerleme tablosu eklendi" gibi açıklayıcı mesajlar tercih edilmelidir.

| Kötü Commit Mesajı | İyi Commit Mesajı |
|---|---|
| güncelleme | README dosyasına teslim edilecek dosyalar listesi eklendi |
| değişiklik | week-3-git-github.md dosyasına Git/GitHub araştırması eklendi |
| asdasd | .gitignore dosyası oluşturuldu |

**AIHEXA'da kullanımı:** Düzgün commit mesajları sayesinde ekip, projenin geçmişine bakarak hangi değişikliğin ne zaman ve neden yapıldığını kolayca anlayabilir.

## Proje klasör yapısı neden önemlidir?
Düzenli bir klasör yapısı, projeyi hem kendisi hem de başkaları için anlaşılır kılar. Dosyalar rastgele değil, mantıklı bir sıraya göre (örneğin haftaya göre, konuya göre) adlandırılırsa proje içinde kaybolmak yerine hızlıca istenen dosyaya ulaşılabilir.
**AIHEXA'da kullanımı:** Büyüyen bir projede düzenli klasör yapısı olmazsa geliştiriciler zamanla dosyaları bulamaz hale gelir; bu yüzden AIHEXA projelerinde de tutarlı isimlendirme önemlidir.

---

## Günlük Kısa Rapor

**Bugün ne öğrendim?**
Git ve GitHub'ın temel kavramlarını (repository, commit, branch, pull request, merge conflict, .gitignore) öğrendim ve bunların bir yazılım ekibinde nasıl kullanıldığını anladım.

**En çok zorlandığım konu neydi?**
Sıfırdan başladığım için zorlandım ama pes etmek yok. örn. "Merge conflict kavramını başta anlamakta zorlandım" veya "Branch mantığını kavramam biraz zaman aldı"

**GitHub'da ne oluşturdum?**
`aihexa-internship-week-3-4-erkan-tas` adlı repository'yi açtım, README.md ve week-3-git-github.md dahil 9 dosyayı oluşturdum.

**Yarın neye çalışacağım?**
Yarın Spring Boot temelleri ve backend mantığı konusuna çalışacağım.
