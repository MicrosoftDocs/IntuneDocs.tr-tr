---
title: "iOS ilke ayarları | Microsoft Intune"
description: "Intune ile yönettiğiniz iOS cihazlarında ayarları ve özellikleri denetleyen ilkeler oluşturun."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bc5ff023b5d29ded999c7e49c5e7c2aee8a23bba
ms.openlocfilehash: e71cc1e8e2cb0f46507ff63d962f3d477acfb72e


---

# Microsoft Intune’da iOS ilke ayarları

Intune, iOS cihazlarda yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. Ayrıca, Intune'dan kullanılamayan özel ayarları oluşturmak için Apple Configurator aracını kullanabilirsiniz.

## Genel yapılandırma ilkesi ayarları

Microsoft Intune **iOS genel yapılandırma ilkesini** kullanarak aşağıdaki ayarları yapılandırabilirsiniz:

-   **Genel cihaz ve güvenlik ayarları**. Cihazda bir dizi özelliği ve işlevi denetlemenize olanak sağlayan, önceden tanımlı ayarlar listesinden seçim yapın.

-   **Bilgi noktası modu**. Bir cihazı, yalnızca belirli özellikleri çalışacak şekilde kilitler. Örneğin, cihazın yalnızca belirttiğiniz bir yönetilen uygulamayı çalıştırmasına izin verebilir veya cihazdaki ses düğmelerini devre dışı bırakabilirsiniz. Bu ayarlar, bir cihazın tanıtım modeli için veya yalnızca tek bir işlevi (satış noktası cihazı gibi) gerçekleştirmeye ayrılmış bir cihaz için kullanılabilir.

-   **Uyumlu ve uyumsuz uygulamalar**. Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini belirtin. Android ve iOS cihazlarında **Uyumlu Olmayan Uygulamalar Raporu**’nu kullanarak, listede belirttiğiniz uygulamaları kullanıcıların yüklemiş olduğu uygulamalarla karşılaştırılabilir ve uyumlu olup olmadıklarını görüntüleyebilirsiniz (ancak uygulamanın yüklenmesi engellenemez).

> [!TIP]
> Kullanıcılarınızın, cihazlarındaki uygulamaların (kişisel uygulamalar dahil) değerlendirileceğini ve uyumsuz uygulamaların engelleneceğini ya da uyumsuz olarak bildirileceğini anladığından emin olmak amacıyla, kullanıcılara yönelik hüküm ve koşullar yapılandırabilirsiniz. Kullanıcılar, uygulamalara erişmek üzere cihazlarını kaydedip şirket portalını kullanmadan önce bu hüküm ve koşulları kabul etmelidir. Hüküm ve koşulları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da hüküm ve koşullar ilkesi ayarları](terms-and-condition-policy-settings-in-microsoft-intune.md).

Aradığınız özellik bu konu başlığı altında görünmüyorsa, [Apple Configurator aracı](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) ile oluşturduğunuz ayarları içeri aktarmanızı sağlayan bir iOS özel ilkesi kullanarak bu özelliği oluşturabilirsiniz. Daha fazla bilgi için, bu konunun devamındaki “Özel ilke ayarları” bölümüne bakın.

### Güvenlik ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Kullanıcının cihazına erişmek için parola girmesinin gerekip gerekmediğini belirtin.|
|**Gerekli parola türü**|Gerekli parola türünü belirtin (yalnızca sayısal veya alfasayısal gibi).|
|**Parolada gerekli karmaşık karakter sayısı**|Parolada bulunması gereken simge karakterlerinin sayısını belirtin (**#** veya **@** gibi).|
|**Minimum parola uzunluğu**|Parolada bulunacak karakter sayısı için alt sınır belirtin.|
|**Basit parolalara izin ver**|**0000** ve **1234** gibi basit parolalara izin verin.|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu ayar cihazı temizlemeden önce gerçekleşebilecek başarısız oturum açma girişimlerinin sayısını belirtin.|
|**Parola istenmeden önce geçen işlem yapılmayan dakika sayısı**<sup>1</sup>|Kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalabileceğini belirtin.|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtin.|
|**Parola geçmişini anımsa**|Kullanıcının önceden kullanmış olduğu parolaları kullanıp kullanamayacağını belirtin.|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtin.|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**<sup>1</sup>|Cihazın ekranı kapatılmadan önce beklenecek dakika sayısını belirtin.|
|**Parmak izi ile kilit açmaya izin ver**|Parmak izi kullanarak cihaz kilidini açmaya izin verin.|
<sup>1</sup> iOS cihazlarında **Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı** ve **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarlarını sırayla uygulayarak yapılandırın. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran 5 dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için 5 dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki 5 dakikanın sonunda cihaz kilitlenir.

### Sistem ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Ekran görüntüsüne izin ver**|Kullanıcının ekran içeriğini resim olarak yakalamasına izin verin.|
|**Kilit ekranında denetim merkezine izin ver**|Cihaz kilitliyken kullanıcının denetim merkezi uygulamasına erişmesine izin verin.|
|**Kilit ekranında bildirim görünümüne izin ver**|Kullanıcının, cihazın kilidini açmadan bildirimler görünümüne erişime izin verin.|
|**Kilit ekranında bugün görünümüne izin ver**|Cihaz kilitliyken kullanıcının bildirimleri görüntülemesine izin verin.|
|**Güvenilmeyen TLS sertifikalarına izin ver**|Cihazda güvenilmeyen Aktarım Katmanı Güvenliği sertifikalarına izin verin.|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Apple’a tanılama verileri göndermesine izin verin veya bunu engelleyin.|
|**Kilitliyken passbook kullanımına izin ver**|Cihaz kilitliyken kullanıcının Passbook uygulamasına erişmesine izin verin.|

### Belgeler ve veriler için bulut ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**iCloud'a yedeklemeye izin ver**|Kullanıcının cihazı iCloud’a yedeklemesine izin verin.|
|**iCloud'a belge eşitlemeye izin ver**|iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verin.|
|**iCloud'a Fotoğraf Akışını eşitlemeye izin ver**|Cihazdaki fotoğrafların iCloud’a eşitlenmesine izin verin.|
|**Şifreli yedekleme iste**|Tüm cihaz yedeklemelerinin şifrelenmesini zorunlu tutar.|
|**Yönetilen uygulamaların iCloud ile veri eşitlemesine izin verme**|Intune ile yönettiğiniz uygulamaların, kullanıcının iCloud hesabıyla veri eşitlemesine izin verin.|
|**İletim’in başka bir cihazda etkinliklerini sürdürmesine izin verme**|Kullanıcının bir iOS cihazında başladığı çalışmayı başka bir iOS veya Mac OS X cihazında sürdürmesine izin verin.|

### Tarayıcı için uygulama ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Safari'ye izin ver**|Cihazda Safari tarayıcısının kullanılıp kullanılamayacağını belirtin.|
|**Otomatik doldurmaya izin ver**|Kullanıcının tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.|
|**Açılır pencere engelleyicisine izin ver**|Tarayıcı açılır pencere engelleyicisini etkinleştirin veya devre dışı bırakın.|
|**Tanımlama bilgilerine izin ver**|Tarayıcının tanımlama bilgilerini kullanmasına izin verin.|
|**Java betiği oluşturmaya izin ver**|Tarayıcıda Java betiğinin çalıştırılmasına izin verin.|
|**Sahtekarlık uyarısına izin ver**|Tarayıcıda sahtekarlık uyarılarına izin verin.|

### Uygulamalara yönelik uygulama ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Uygulama depolamaya izin ver**|Cihazların uygulama mağazasına erişmesine izin verin.|
|**Uygulama deposuna erişim için parola iste**|Kullanıcının uygulama mağazasını ziyaret etmeden önce parola girmesini isteyin.|
|**Uygulama içi satın almalara izin ver**|Çalışan bir uygulamanın içinden mağazada alışveriş yapılmasına izin verir.|
|**Diğer yönetilmeyen uygulamalardaki yönetilen belgelere izin ver**|Kurumsal belgelerin tüm uygulamalarda görüntülenmesine izin verin.<br>**Örnek:** Kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı hayır olarak yapılandırın. Cihaz, ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermeyecektir.|
|**Diğer yönetilen uygulamalardaki yönetilmeyen belgelere izin ver**|Tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verin.|
|**Görüntülü konferansa izin ver**|Cihazda Facetime gibi görüntülü konferans uygulamalarına izin verin.|
|**Medya mağazasında yetişkinlere yönelik içeriğe izin ver**|Cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verin.|
|**Kullanıcının iBook mağazasından 'Erotika' olarak işaretlenmiş içerik indirmesine izin verme**|Kullanıcının “Erotik” kategorisindeki kitapları indirmesine izin verin.|

### Oyunlar için uygulama ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Game Center arkadaşlarını eklemeye izin ver**|Kullanıcının Game Center'da arkadaş eklemesine izin verin.|
|**Çok oyunculu oyunlara izin ver**|Kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verin.|

### Donanım için cihaz özellikleri ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Kameraya izin ver**|Cihazdaki kameranın kullanılıp kullanılamayacağını belirtin.|
|**Giden AirPlay istekleri için bir eşleştirme parolası gerektirme**|Kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere AirPlay’i kullanması için, eşleştirilen parola isteyin.|

### Hücresel veri için cihaz özellikleri ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Sesli dolaşıma izin ver**|Cihaz cep telefonu şebekesindeyken sesli dolaşıma izin verin.|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verin.|
|**Dolaşımdayken genel arka plan almaya izin ver**|Cihazın, cep telefonu şebekesinde dolaşımdayken e-posta gibi verileri almasına izin verir.|

### Özellikler için cihaz özellikleri ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Siri'ye izin ver**|Cihazda Siri ses yardımcısının kullanımına izin verin.|
|**Cihaz kilitliyken Siri'ye izin ver**|Cihaz kilitliyken cihazda Siri ses yardımcısının kullanımına izin verin.|
|**Sesli aramaya izin ver**|Cihazda sesli arama özelliğinin kullanımına izin verin.|


### Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Uyumlu ve Uyumsuz Uygulamalar** listesinde, aşağıdaki bilgileri kullanarak bir uyumlu veya uyumsuz uygulamalar listesi belirleyin.

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların bir listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.|
|**Kullanıcılar listelenmeyen uygulamaları yüklediğinde uyumsuzluğu bildir**|Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Uyumluluğun korunması için kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekleyin. Tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin. Daha fazla yardım için, bu konunun devamındaki “Uygulama mağazalarının URL’lerini belirtme” bölümünü okuyun.|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarın. Dosyada şu biçimi kullanın: uygulama adı, yayımcı, uygulama URL’si.|
|**Düzenle**|Seçili uygulamanın adını, yayımcısını ve URL'sini düzenleyin.|
|**Sil**|Seçili uygulamayı listeden silin.|

### Bilgi noktası modu ayarları

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz bilgi noktası modundayken çalışmasına izin verilecek yönetilen bir uygulama seçin**|**Gözat**’ı seçin ve sonra, yönetilen uygulamayı veya cihaz bilgi noktası modundayken çalışmasına izin verilecek mağaza uygulamasını belirtin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez. Daha fazla yardım için, bu konunun devamındaki “Uygulama mağazalarının URL’lerini belirtme” bölümüne bakın.|
|**Dokunmatik ekrana izin ver**|Cihazda dokunmatik ekranı etkinleştirin veya devre dışı bırakın.|
|**Ekran döndürmeye izin ver**|Kullanıcı, cihazı döndürdüğünde ekran yönünü değiştirmeyi etkinleştirin veya devre dışı bırakın.|
|**Ses düğmelerine izin ver**|Cihazdaki ses düğmelerinin kullanımını etkinleştirin veya devre dışı bırakın.|
|**Ses açma/kapama düğmesine izin ver**|Cihazda ses açma/kapama (sessiz) düğmesini etkinleştirin veya devre dışı bırakın.|
|**Açma/kapatma düğmesine izin ver**|Ekranda uykuya geçme ve uyandırma düğmesini etkinleştirin veya devre dışı bırakın.|
|**Otomatik kilide izin ver**|Cihazın otomatik olarak kilitlenmesini etkinleştirin veya devre dışı bırakın.|
|**Mono sesi etkinleştir**|**Mono ses**erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Seslendirmeyi etkinleştir**|Cihazın ekranındaki metinleri sesli olarak okuyan **VoiceOver** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Seslendirme ayarlarını etkinleştir**|Kullanıcının VoiceOver işlevini ayarlamasına izin veren seslendirme ayarlarını (örneğin, ekran üzerindeki metnin ne kadar hızlı okunacağı) etkinleştirin veya devre dışı bırakın.|
|**Yakınlaştırmayı etkinleştir**|Kullanıcının cihazın ekranını dokunarak yakınlaştırmasına olanak sağlayan **Yakınlaştırma** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Yakınlaştırma ayarlarını etkinleştir**|Kullanıcının yakınlaştırma işlevini ayarlamasını sağlayan yakınlaştırma ayarlarını etkinleştirin veya devre dışı bırakın.|
|**Renkleri ters çevirmeyi etkinleştir**|Görme bozukluğu olan kullanıcılara yardımcı olmak için ekranı ayarlayan **Renkleri ters çevir** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Renkleri ters çevir ayarlarını etkinleştir**|Kullanıcının renkleri ters çevirme işlevini ayarlamasına olanak sağlayan renkleri ters çevirme ayarlarını etkinleştirin veya devre dışı bırakın.|
|**Yardımcı dokunmayı etkinleştir**|Ekran hareketlerini gerçekleştirmekte zorlanabilecek kullanıcıların bunları yapmasına yardımcı olan **Yardımcı Dokunma** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Yardımcı dokunma ayarlarını etkinleştir**|Kullanıcının yardımcı dokunma işlevini ayarlamasına olanak sağlayan yardımcı dokunma ayarlarını etkinleştirin veya devre dışı bırakın.|
|**Seçimi seslendirmeyi etkinleştir**|Kullanıcının seçtiği metni sesli okuyabilen **Seçimi Seslendir** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
> [!NOTE]
> aşağıdaki notlar, iOS cihazlarda bilgi noktası modu ayarları için geçerlidir:
>
> -   Bir iOS cihazını bilgi noktası modu için yapılandırmadan önce, [Apple Configurator aracı](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)nı veya cihaz kayıt yöneticisini kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracı hakkında daha fazla bilgi için Apple belgelerinize bakın.
> -   Belirttiğiniz iOS uygulaması siz yapılandırma ilkesini dağıttıktan sonra yüklendiyse, cihaz, yeniden başlatılana kadar bilgi noktası moduna girmez.

### Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

 **Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak izin verilen ve engellenen uygulamaların uyumluluğunu görüntüleyin.

##### Uyumlu Olmayan Uygulamalar Raporu'nu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Raporlar** &gt; **Uyumsuz Uygulamalar Raporu**’nu seçin.

2.  Denetlemek istediğiniz cihaz gruplarını seçin, sonra uyumlu uygulamaları, uyumsuz uygulamaları ya da her ikisini de denetlemek istediğinizi belirtin ve sonra **Raporu Görüntüle**’yi seçin.

#### Uygulama mağazalarının URL'lerini belirtme
Uyumlu ve uyumsuz uygulamalar listesinde veya **Cihaz bilgi noktası modundayken çalışmasına izin verilecek bir yönetilen uygulama seçin** seçeneğinde (yalnızca iOS) bir uygulamanın URL'sini belirtmek için aşağıdaki biçimi kullanın:

1. Bir arama motoru kullanarak, iTunes App Store'dan kullanmak istediğiniz uygulamayı bulun ve uygulamanın sayfasını açın.

2. Sayfanın URL'sini kopyalayın ve bunu, uyumlu veya uyumsuz uygulamalar listesini ya da bilgi noktası modunda çalıştırmak istediğiniz uygulamayı yapılandırmak için gereken URL olarak kullanın.

**Örnek:**  **iPad için Microsoft Word**ifadesini aratın. Kullandığınız URL **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8** olacaktır.

> [!NOTE]
> iTunes yazılımını kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** komutuyla uygulama URL'sini alabilirsiniz.

### Kayıt ayarları
Tüm ayarlar iOS 7.1 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz denetimli moddayken Etkinleştirme Kilidi’ne izin verme**|Denetimli iOS cihazlarında Etkinleştirme Kilidi’ni etkinleştirin.|

### Denetim
iOS 7.1 ve üstünü çalıştıran denetimli moddaki cihazlarda aşağıdaki ayarları yapılandırabilirsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Hesapta değişikliğe izin verme**|Kullanıcının e-posta yapılandırması gibi hesap ayarlarını değiştirmesine izin verin.|
|**AirDrop’a izin verme**|Yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verin.|
|**Uygulama hücresel veri kullanım ayarlarında değişikliğe izin verme**|Kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verme.|
|**Siri’nin kullanıcı tarafından oluşturulan içeriği İnternet’ten sorgulamasına izin verme**|Siri’nin soruları yanıtlamak için web sitelerine erişmesine izin verin.|
|**iBooks mağazası erişimine izin verme**|Kullanıcının iBooks mağazasındaki kitaplara göz atmasına ve bunları satın almasına izin verin.|
|**Find My Friends uygulamasının ayarlarında değişikliğe izin verme**|Kullanıcının Find My Friends uygulamasının ayarlarını değiştirmesine izin verin.|
|**Cihazda tüm içeriği ve ayarları silme seçeneğinin kullanılmasına izin verme**|Kullanıcının, cihazda tüm içeriği ve ayarları silme seçeneğini kullanmasına izin verin.|
|**Kullanıcının cihaz ayarlarında kısıtlamaları etkinleştirmesine izin verme**|Kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri) yapılandırmasına izin verin.|
|**Spotlight aramanın İnternet’ten sonuç döndürmesine izin verme**|Spotlight aramasının daha fazla sonuç sağlamak için İnternet’e bağlanmasına izin verin.|
|**Game Center uygulamasının kullanılmasına izin verme**|Game Center uygulamasının kullanımına izin verin.|
|**Bir iOS cihazının eşleşebileceği cihazları denetlemek için konak eşleştirmesine izin verme**|Bir iOS 7 cihazının hangi cihazlarla eşleşebileceğini yöneticinin denetlemesi için konak eşleştirmeye izin verin.|
|**Kullanıcının yapılandırma profilleri ve sertifikaları yüklemesine izin verme**|Kullanıcının yapılandırma profilleri ve sertifikaları yüklemesine izin verin.|
|**Cihazda Messages uygulamasının kullanılmasına izin verme**|Kısa mesaj göndermek için Messages uygulamasının kullanılmasına izin verin.|


## Özel ilke ayarları

[Apple Configurator aracını](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) kullanarak oluşturduğunuz ayarları iOS cihazlarına dağıtmak için Microsoft Intune **iOS özel ilkesini** kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune iOS özel ilkesine içeri aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara dağıtabilirsiniz.

Bu özellik, Intune genel yapılandırma ilkeleriyle yapılandırılamayan iOS ayarlarını dağıtmanıza olanak sağlar.

### Önkoşullar
Başlamadan önce, Apple Configurator’ı yüklemiş ve kullanıcılara veya cihazlara dağıtmak istediğiniz ayarları içeren bir yapılandırma dosyası oluşturmuş olmanız gerekir. [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)‘dan Apple Configurator’ı indirebilir ve Apple Configurator hakkında bilgi edinebilirsiniz.

> [!NOTE]
> Intune, bir iOS özel ilkesindeki tek tek ayarların uyumluluğunu raporlamaz. Ancak, ilkenin genel uyumluluğu raporlanır.

### Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için iOS özel ilkesine benzersiz bir ad girin.|
    |**Açıklama**|iOS özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### Özel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
|**Özel yapılandırma profili adı (kullanıcılara gösterilir)**|Cihazda ve Intune ilke raporlarında görüntülenecek şekilde ilke için bir ad sağlayın.|
|**Yapılandırma profili dosyası**|**İçeri Aktar**’ı seçin ve sonra Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin. **Not:** Apple Configurator aracından dışarı aktardığınız ayarların, iOS özel ilkesini dağıttığınız cihazlardaki iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların nasıl çözümleneceği hakkında bilgi için, [Apple Developer](https://developer.apple.com/) web sitesinde **Yapılandırma Profili Başvurusu** ve **Mobil Cihaz Yönetim Protokolü Başvurusu** öğelerini arayın.|
    |**Yapılandırma profili ayrıntıları**|İçeri aktardığınız yapılandırma profili için XML kodunu görüntüleyin.|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO1-->

