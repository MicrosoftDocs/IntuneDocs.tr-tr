---
# required metadata

title: Exchange Online’a ve yeni Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama| Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune ile Exchange Online’a ve yeni Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama

Ayrılmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa, hesap yöneticinize başvurun.

Exchange Online’a veya yeni Ayrılmış Exchange Online ortamına e-posta erişimini denetlemek için, Intune’da Exchange Online’a koşullu erişim yapılandırın.
Koşullu erişimin nasıl çalıştığı hakkında daha fazla bilgi edinmek için, [E-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) makalesini okuyun.

>[!IMPORTANT]
>Modern kimlik doğrulamasının kullanıldığı uygulamalar bulunan bilgisayarlar ve Windows 10 Mobile cihazları için koşullu erişim özelliği, şu anda tüm Intune müşterilerine sağlanmaz. Bu özellikleri zaten kullanıyorsanız, herhangi bir işlem yapmanız gerekmez. Kullanmaya devam edebilirsiniz.

>Bilgisayarlarda veya Windows 10 Mobile cihazlarda modern kimlik doğrulamasının kullanıldığı uygulamalar için koşullu erişim ilkeleri oluşturmadıysanız ve bunu yapmak istiyorsanız, bir istek göndermeniz gerekir.  [Microsoft Connect sitesinde](http://go.microsoft.com/fwlink/?LinkId=761472), hem bilinen sorunlar hem de bu özelliği nasıl erişebileceğiniz hakkında daha fazla bilgi bulabilirsiniz.

Koşullu erişimi yapılandırabilmeniz için **önce**:

-   **Exchange Online içeren bir Office 365 aboneliğiniz (örneğin E3)** olmalı ve kullanıcılar Exchange Online lisansına sahip olmalıdır.

-  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’u Microsoft Exchange Online’a bağlayan ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsolu aracılığıyla cihaz bilgilerini yönetmenize yardımcı olan isteğe bağlı **Microsoft Intune hizmetten hizmete bağlayıcısını** yapılandırmayı göz önünde bulundurmalısınız. Uyumluluk ilkeleri veya koşullu erişim ilkelerini kullanmak için bağlayıcıyı kullanmanıza gerek yoktur, ancak koşullu erişimin etkisini değerlendirmeye yardımcı olan raporları çalıştırmak için bu gereklidir.

   > Koşullu erişimi hem Exchange Online hem de Şirket İçi Exchange için kullanmak istiyorsanız, hizmetten hizmete bağlayıcısını yapılandırmayın.

   Bağlayıcıyı yapılandırma yönergeleri için bkz. [Intune hizmetten hizmete bağlayıcısı](intune-service-to-service-exchange-connector.md)

Koşullu biçimlendirme ilkeleri yapılandırıldığında ve hedef kullanıcı belirlendiğinde, kullanıcının e-postasına bağlanabilmesi için önce **cihazın** şu özellikleri taşıması gerekir:

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a **kaydolmalı** veya etki alanına katılmış bir bilgisayar olmalıdır.

-  **Azure Active Directory’de kayıtlı olmalıdır**. Cihaz [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a kaydedildiğinde bu otomatik olarak gerçekleşir. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.

  AAD DRS, Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS Cihaz Kayıt Hizmeti'ni zaten dağıtan müşteriler, kayıtlı cihazlarını şirket içi Active Directory'lerinde görmez.

-   Söz konusu cihaza dağıtılmış tüm [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uyumluluk ilkeleriyle **uyumlu** olmalı veya şirket içi etki alanına katılmış olmalıdır.

Koşullu erişim ilkesine uyulmazsa, kullanıcı oturum açtığında şu iletilerden birini görür:

- Cihaz [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a kaydolmadıysa veya Azure Active Directory’de kayıtlı değilse, şirket portalı uygulamasını yükleme, cihazı kaydetme ve e-postayı etkinleştirme yönergelerinin bulunduğu bir ileti görüntülenir. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki kayıtla ilişkilendirir.

-   Cihazın değerlendirmesinde uyumluluk ilkesi kurallarına uygun olmadığı bulunursa, son kullanıcı sorunla ve bu sorunu nasıl çözebileceğiyle ilgili bilgilere ulaşabileceği [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Şirket Portalı web sitesine veya Şirket Portalı uygulamasına yönlendirilir.


Aşağıdaki diyagramda, Exchange Online için koşullu erişim ilkeleri tarafından kullanılan akış çizilmiştir.

![Cihazın erişimine izin verileceğini veya engelleneceğini belirleyen karar noktalarının çizildiği diyagram](../media/ConditionalAccess8-1.png)

## Mobil cihaz desteği
**Outlook**’tan ve **modern kimlik doğrulamasının kullanıldığı diğer uygulamalardan** Exchange Online e-postasına erişimi kısıtlayabilirsiniz:-

- Android 4.0 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri
- iOS 7.1 ve üzeri
- Windows Phone 8.1 ve üzeri

 **Modern k+imlik doğrulaması**, Active Directory Authentication Library (ADAL) tabanlı oturum açmayı Microsoft Office istemcilerine getirir.

> -   ADAL tabanlı kimlik doğrulaması, Office istemcilerinin tarayıcı tabanlı kimlik doğrulaması (pasif kimlik doğrulama olarak da bilinir) gerçekleştirmesine imkan sağlar.  Kullanıcı, kimlik doğrulamak için bir oturum açma web sayfasına yönlendirilir. Bu yeni oturum açma yöntemi, **çok faktörlü kimlik doğrulaması** ve **sertifika tabanlı kimlik doğrulaması** gibi daha iyi güvenlik önlemlerine olanak tanır.


Bu [makalede](https://support.office.com/en-US/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517), modern kimlik doğrulamasının nasıl çalıştığıyla ilgili daha ayrıntılı bilgi sağlanmıştır.

- Aşağıdaki platformlarda yerleşik **Exchange ActiveSync e-posta istemcisinden** Exchange e-postasına erişimi kısıtlayabilirsiniz:

- Android 4.0 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri

- iOS 7.1 ve üzeri

## Windows Phone 8.1 ve üzeri

Bilgisayarlar için destek

-   Aşağıdaki gereksinimleri karşılayan bilgisayarlar için **Exchange Online** ve **SharePoint Online** ’a erişmek amacıyla Office masaüstü uygulamalarını çalıştıran bilgisayarlara yönelik koşullu erişimi ayarlayabilirsiniz:

-   Bilgisayarın Windows 7.0 veya Windows 8.1 çalıştırıyor olması gerekir.

    Bilgisayar etki alanına katılmalı veya uyumluluk ilkesi kurallarına uygun olmalıdır.

    Uyumlu olarak kabul edilmesi için, bilgisayarın [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ’da kayıtlı olması ve ilkelere uyması gerekir.

-   Etki alanına katılmış bilgisayarları, Azure Active Directory ile [otomatik olarak kaydedilecek](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) şekilde ayarlamanız gerekir.

    [Office 365 modern kimlik doğrulamanın etkin olması](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) ve en son Office güncelleştirmelerine sahip olması gerekir.

-   Modern kimlik doğrulaması, Office 2013 Windows istemcileri için Active Directory Authentication Library (ADAL) tabanlı oturum açma özelliği sunar ve **çok faktörlü kimlik doğrulaması** ile **sertifika tabanlı kimlik doğrulaması** gibi daha üst düzey güvenlik sağlar. Modern olmayan kimlik doğrulama protokollerini engellemek için ADFS talep kurallarını ayarlayın.

## Ayrıntılı yönergeler 3. senaryoda ([O365’e tarayıcı tabanlı uygulamalar dışındaki tüm erişimi engelleme](https://technet.microsoft.com/library/dn592182.aspx)) sağlanmıştır.
### Koşullu erişimi yapılandırma
1. Adım: Uyumluluk ilkesi yapılandırma ve dağıtma


> Koşullu erişim ilkesini alacak olan kulanıcı grupları için de uyumluluk ilkesi [oluşturduğunuzdan](create-a-device-compliance-policy-in-microsoft-intune.md) ve [dağıttığınızdan](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) emin olun.

### Uyumluluk ilkesi dağıtmadıysanız, cihazlar uyumlu kabul edilir ve Exchange’e erişim izni alırlar.
2 Adım: Koşullu erişim ilkesinin etkisini değerlendirme

Koşullu erişim ilkesini yapılandırdıktan sonra Exchange’e erişimi engellenebilecek cihazları belirlemek üzere **Mobil Cihaz Envanter Raporları**’nı kullanabilirsiniz.
1.  Bunu yapmak için, [Microsoft Intune hizmetten hizmete bağlayıcısını](intune-service-to-service-exchange-connector.md) kullanarak [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile Exchange arasında bir bağlantı yapılandırabilirsiniz.
![**Raporlar -> Mobil Cihaz Envanter Raporları**’na gidin.](../media/IntuneSA2bMobileDeviceInventoryReport.png)

2.  Mobil cihaz envanter raporu sayfasının ekran görüntüsü
3.  Rapor parametrelerinde, değerlendirmek istediğiniz [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] grubunu ve gerekirse ilkenin geçerli olacağı cihaz platformlarını seçin.
Kuruluşunuzun gereksinimlerini karşılayan ölçütleri seçtikten sonra **Raporu Görüntüle**’yi seçin.
![Rapor Görüntüleyicisi yeni bir pencerede açılır.](../media/IntuneSA2cViewReport.PNG)

Örnek mobil cihaz envanter raporunun ekran görüntüsü

-   Raporu çalıştırdıktan sonra kullanıcının engellenip engellenmeyeceğini belirlemek için şu dört sütunu inceleyin:

-   **Yönetim Kanalı** – Cihazın Intune, Exchange ActiveSync veya her ikisi tarafından yönetilip yönetilmediğini belirtir.

-   **AAD Kayıtlı** – Cihazın Azure Active Directory’ye kayıtlı olup olmadığını belirtir (Çalışma Alanına Katılma olarak bilinir).

-   **Uyumlu** – Cihazın dağıttığınız herhangi bir uyumluluk ilkesiyle uyumlu olup olmadığını belirtir. **Exchange ActiveSync Kimliği** – iOS ve Android cihazların Exchange ActiveSync kimliklerinin Azure Active Directory'deki cihaz kaydı ile ilişkilendirilmiş olması gerekir.

    > Kullanıcı karantina e-postasında **E-postayı Etkinleştir** bağlantısını seçtiğinde bu durum ortaya çıkar.

Windows Phone cihazları her zaman bu sütunda bir değer görüntüler.

--------------------------
|Sütun değerleri aşağıdaki tabloda listelenenlerle eşleşmiyorsa, hedeflenen bir grubun parçası olan cihazların Exchange’e erişmesi engellenir:|Yönetim kanalı|AAD kayıtlı|Uyumlu|Exchange ActiveSync Kimliği|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Sonuçtaki eylem**|Microsoft Intune ve Exchange ActiveSync tarafından yönetilir|Evet|Evet|Bir değer görüntülenir|
|E-posta erişimine izin verilir|Başka bir değer|Hayır|Hayır|Bir değer görüntülenmez|
----------------------
E-posta erişimi engellenir

### Kullanıcılarınıza engelleneceklerini bildirmek için raporun içindekileri dışarı aktarabilir ve **E-posta Adresi** sütununu kullanabilirsiniz.
3. Adım: Koşullu erişim ilkesi için kullanıcı gruplarını yapılandırma Koşullu erişim ilkeleri farklı Azure Active Directory güvenlik kullanıcı gruplarını hedefler.  Ayrıca bazı kullanıcı gruplarını bu ilkeden muaf tutabilirsiniz.

Bir kullanıcı bir ilke tarafından hedeflendiğinde, e-postaya erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.

**Office 365 yönetim merkezinde** veya **Intune hesap portalında** bu grupları yapılandırabilirsiniz.

-   Her bir ilkede iki grup türü belirtebilirsiniz:

-   **Hedeflenen gruplar** – İlkenin geçerli olduğu kullanıcı grupları.

**Muaf tutulan gruplar** – İlkeden muaf tutulan kullanıcı grupları (isteğe bağlı)

Bir kullanıcı her iki gruptaysa ilkeden muaf tutulur.

### Yalnızca koşullu erişim ilkesi tarafından hedeflenen gruplar değerlendirmeye alınır.

1.  4. Adım: Koşullu erişim ilkesini yapılandırma
![[Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **Koşullu Erişim** > **Exchange Online İlkesi**’ni seçin.](../media/IntuneSA5dExchangeOnlinePolicy.png)

2.  Exchange Online koşullu erişim ilkesi sayfasının ekran görüntüsü

    > **Exchange Online İlkesi** sayfasında, **Exchange Online için koşullu erişim ilkesini etkinleştir**’i seçin.
    >
    > Uyumluluk İlkesi dağıtmadıysanız cihazlar uyumlu olarak kabul edilir.

3.  Uyumluluk durumuna bakılmaksızın, ilke tarafından hedeflenen tüm kullanıcıların cihazlarını Intune’a kaydetmeleri gerekir. **Uygulama erişimi**’nin altında, modern kimlik doğrulaması kullanan uygulamalar için ilkenin hangi platformlara uygulanacağını seçmenizin iki yolu vardır.

    -   **Desteklenen platformlar Android, iOS, Windows ve Windows Phone’dur.**

        Tüm platformlar  Bu seçenek **Exchange Online**’a erişmek için kullanılan tüm cihazların Intune’a kaydedilmesini ve ilkelerle uyumlu olmasını gerektirir.
        >[!TIP]
           **Modern kimlik doğrulaması** kullanan tüm istemci uygulamaları koşullu erişim ilkesine tabidir ve platform o sırada Intune tarafından desteklenmiyorsa **Exchange Online**’a erişim engellenir.  Bilgisayarlar için koşullu erişimi zaten kullanıyorsanız, bu seçeneği görmeyebilirsiniz. Bunun yerine **Belirli platformlar**’ı kullanın.   Bilgisayarlar için koşullu erişim şu anda tüm Intune müşterilerine sağlanmamaktadır.

    -   **[Microsoft Connect sitesinde](http://go.microsoft.com/fwlink/?LinkId=761472), hem bilinen sorunlar hem de bu özelliği nasıl erişebileceğiniz hakkında daha fazla bilgi bulabilirsiniz.**

         Belirli platformlar

4.  Koşullu erişim ilkesi, belirttiğiniz cihaz platformlarında **modern kimlik doğrulaması** kullanan tüm istemci uygulamaları için geçerlidir. **Exchange ActiveSync uygulamaları**’nın altında, uyumsuz cihazların Exchange Online’a erişmesini engellemeyi seçebilirsiniz. Cihaz desteklenen bir platformda çalıştırılmadığında e-posta erişimine izin vermeyi veya bu erişimi engellemeyi de seçebilirsiniz.


5.  Desteklenen platformlar Android, iOS, Windows ve Windows Phone’dur.  **Hedeflenen Gruplar**altında, ilkenin geçerli olacağı Active Directory güvenliği kullanıcı gruplarını seçin.
![Tüm kullanıcıları veya seçili bir kullanıcı grupları listesini hedeflemeyi seçebilirsiniz.](../media/IntuneSA5eTargetedExemptedGroups.PNG)
    > Hedeflenen ve Muaf Tutulan grup seçeneklerinin gösterildiği Exchange Online koşullu erişim ilkesi sayfasının ekran görüntüsü
    >
    > **Hedeflenen gruplar**’da bulunan kullanıcılar için Intune ilkeleri, Exchange kurallarının ve ilkelerinin yerini alır.
    >
    > -   Exchange, şu durumlarda yalnızca Exchange izin verme, engelleme ve karantinaya alma kurallarını ve Exchange ilkelerini uygular:
    > -   Kullanıcı Intune için lisanslı değilse.

6.  Kullanıcı Intune için lisanslıysa, ancak koşullu erişim ilkesinde hedeflenen güvenlik gruplarından birinde değilse.  **Muaf Tutulan Gruplar**altında, bu ilkeden muaf tutulan Active Directory güvenliği kullanıcı gruplarını seçin.

7.  Bir kullanıcı hem hedeflenen hem de muaf tutulan gruplardaysa, ilkeden muaf tutulur.

-   İşiniz bittiğinde **Kaydet**’i seçin.

-   Koşullu erişim ilkesini dağıtmanız gerekmez, hemen geçerli olur.

-   Kullanıcı bir e-posta hesabı oluşturduktan sonra cihaz hemen engellenir.

-   Engellenen bir kullanıcı, cihazı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a kaydeder ve uyumsuzluk sorunlarını çözerse, 2 dakika içinde e-posta erişiminin engeli kaldırılır.

**Kullanıcı cihazının kaydını kaldırırsa, yaklaşık 6 saat sonra e-posta engellenir.**

## Cihaz erişimini kısıtlamak üzere koşullu erişim ilkesini nasıl yapılandırabileceğinizi gösteren bazı örnek senaryolar görmek için, bkz. [E-posta erişimini kısıtlama örnek senaryoları](restrict-email-access-example-scenarios.md).

#### Uyumluluk ve koşullu erişim ilkeleri izleme

Exchange’e erişimi engellenmiş cihazları görüntülemek için
![[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] panosunda, engellenen cihazların sayısını ve daha fazla bilgiye ulaşmanızı sağlayan bağlantıları göstermek için **Exchange’e Erişimi Engellenmiş Cihazlar** kutucuğunu seçin.](../media/IntuneSA6BlockedDevices.PNG)

## Exchange’e erişimi engellenmiş cihazların sayısını gösteren Intune panosunun ekran görüntüsü
[Sonraki adımlar](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[SharePoint Online’a erişimi kısıtlama](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


<!--HONumber=May16_HO2-->

