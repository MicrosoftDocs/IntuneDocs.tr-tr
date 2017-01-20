---
title: "Intune tasarımı oluşturma | Microsoft Docs"
description: "Bu makale, Microsoft Intune yalnızca bulut tasarımı ve uygulaması için bir tasarım oluşturmanıza yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fa33bd3833f7f7198eed3f4f486c27bae3ba47d7
ms.openlocfilehash: 5f05aa4a27be14a05663aa9de82af63291699403


---

# <a name="create-an-intune-design"></a>Intune tasarımı oluşturma

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Kılavuzun bu bölümü, Bölüm 2'deki diğer konular ile paralel olarak kullanılmalıdır. Bu tasarım, bu kılavuzun önceki bölümlerini tamamlarken topladığınız bilgileri ve vereceğiniz kararları temel alacaktır. Bu tasarım bölümünde, bulutta yer alan ve Microsoft bulut tabanlı bir hizmet olan tek başına Intune’a odaklanacağız.

Şirket içi altyapı gereksinimleri minimal olsa da, hedeflerinizi, amaçlarınızı ve gereksinimlerinizi karşılayan doğru mobil cihaz yönetimi çözümüne sahip olduğunuzdan emin olmak için bir tasarım planı üzerinde çalışmanız önerilir.

Ayrıca, uygulama ve sınama aşamaları sırasında sıkça tasarım değişikliği gerçekleştiğinden, bu değişiklikleri ve arkasındaki nedeni meydana geldikleri anda belgelediğinizden emin olun. Aşağıdaki alanlardan bahsedeceğiz:

-   Mevcut ortam

-   Intune dağıtım seçenekleri

-   Dış bağımlılıklar için kimlik gereksinimleri

-   Cihaz platformunda dikkat edilecek noktalar

-   Sağlanacak gereksinimler  

Bu alanların her birini daha ayrıntılı bir şekilde gözden geçirelim. 

## <a name="record-your-environment"></a>Ortamınızı kaydetme

Tasarımınızı oluşturmadan önce ilk olarak mevcut ortamınızı kaydetmeniz gerekir. Mevcut ortam, tasarım kararlarını etkileyebilir ve diğer Intune tasarım kararları verilirken mevcut ortam belgelenmeli ve buna başvurulmalıdır. Aşağıda mevcut ortamın nasıl kaydedileceğine ilişkin birkaç örnek verilmiştir:

-   **Buluttaki kimlik**

    -   DirSync veya Azure Active Directory (AAD) Connect kullanıyor musunuz?

    -   Ortamınız şirket dışında mı?

    -   Çok faktörlü kimlik doğrulaması etkin mi?

-   **E-posta ortamı**

    -   Exchange kullanılıyor mu ve kullanılıyorsa şirket içinde mi yoksa bulutta mı kullanılıyor?

    -   Exchange’i buluta geçirme projesinin ortasında mısınız?

-   **Geçerli MDM çözümü**

    -   Şu anda diğer MDM çözümlerini kullanıyor musunuz?

    -   Şirket ve KCG kullanım örneği senaryoları için hangi MDM çözümlerini kullanıyorsunuz?

    -   Hangi özellikleri kullanıyorsunuz (örneğin uygulama cihaz ayarları, Wi-Fi yapılandırmaları vb.)?

    -   Hangi cihaz platformları destekleniyor?

    -   MDM çözümü hangi gruplar ve kaç kullanıcı tarafından kullanılıyor?

-   **Sertifika Çözümü**

    -   Bir Sertifika çözümü uyguladınız mı?

    -   Hangi sertifika türlerini kullanıyorsunuz?

-   **Sistem Yönetimi**

    -   PC ve sunucu ortamınızı nasıl yönetiyorsunuz?

    -   System Center Configuration Manager kullanılıyor mu? Bir üçüncü taraf sistem yönetimi platformu kullanıyor musunuz?

-   **VPN Çözümü**

    -   VPN çözümünüz nedir?

    -   Hem şirket hem de KCG örneği senaryolarında kullanılıyor mu?

Mevcut MDM ortamını kaydederken ortamınızda değişiklik yapabilmek için hazırlanan tüm projeleri ve planları not aldığınızdan emin olun. Intune tasarımınızı oluştururken yardımcı olmak üzere mevcut ortamı kaydetme yoluna ilişkin bir örnek aşağıda verilmiştir:

| **Çözüm alanı** | **Mevcut ortam** | **Yorumlar** |
|:---:|:---:|:---:|
| **Kimlik** | Azure AD, Azure AD Connect, şirket dışında değil, MFA yok | Yıl sonundan itibaren MFA’yı etkinleştirme projesi geçerli |                 
| **E-posta ortamı** | Şirket İçi Exchange, Exchange Online | Şu anda Şirket İçi Exchange sürümünden Exchange Online sürümüne geçiriliyor. Posta kutularının % 75’i geçirildi. Kalan %25 Intune Pilot başlamadan önce geçirilecektir. |                
| **SharePoint** | Şirket İçi SharePoint | SharePoint Online sürümüne geçirme planı yok |  
| **Geçerli MDM** | Exchange ActiveSync |  |
| **Sertifika çözümü** | Microsoft Server 2012 R2, AD Sertifika Hizmetleri | Web Sitesi Sunucuları için yalnızca PKI kullanın |
| **Sistem Yönetimi** | System Center Configuration Manager CB 1606 | Intune karma çözümün araştırılması isteniyor |
| **VPN çözümü** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Bir Intune dağıtım seçeneği belirleyin

Intune iki dağıtım seçeneği sunar: Tek başına ve karma. Hangisinin iş gereksinimlerinize uyduğuna karar vermeniz gerekir. Tek başına, bulut ortamında çalışan Intune hizmeti anlamına gelirken karma, Intune'un System Center Configuration Manager ile tümleştirilmesini belirtir.

- [Tek başına Microsoft Intune ve System Center Configuration Manager ile karma mobil cihaz yönetimi (MDM) arasında seçim yapma](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management) hakkında daha fazla bilgi edinin

## <a name="intune-tenant-location"></a>Intune kiracı konumu

Kuruluşunuz küresel olarak faaliyet gösteriyorsa hizmete abone olurken kiracının nerede yer alacağını planladığınızdan emin olun. Ülke, bir Intune aboneliğine ilk kez kaydolduğunuzda tanımlanır ve aşağıda listelenen dünya genelindeki bölgelerle eşlenir:

-   Kuzey Amerika

-   Avrupa, Orta Doğu ve Afrika

-   Asya ve Pasifik

>[!IMPORTANT]
> Ülke/kiracı konumunu sonradan değiştirmek mümkün değildir.

## <a name="external-dependencies"></a>Dış bağımlılıklar

Dış bağımlılıklar Intune’dan ayrı ancak aynı zamanda Intune gereksinimi olan veya Intune ile tümleşebilen hizmet ve ürünlerdir. Herhangi bir dış bağımlılığın gereksinimlerini ve nasıl yapılandırılacağını belirlemek önemlidir. Yaygın dış bağımlılıklara bazı örnekler aşağıda listelenmiştir.

-   Kimlik

-   Kullanıcı ve cihaz grupları

-   PKI

Bu yaygın dış bağımlılıkları aşağıda daha ayrıntılı bir şekilde inceleyeceğiz

### <a name="identity"></a>Kimlik

Kimlik, kuruluşunuzda bulunan ve cihaz kaydeden kullanıcıları nasıl tanımladığımızdır. Intune, kullanıcı kimlik sağlayıcısı olarak Azure Active Directory (Azure AD) gerektirir. Bu hizmeti zaten kullanıyorsanız bulutta varolan kimliğinizden yararlanmanız mümkün olacaktır. Ayrıca Azure AD Connect, şirket içi kullanıcı kimliklerinizi Microsoft bulut hizmetleri ile eşitlemek için önerilen araçtır. Kuruluşunuzda zaten Office 365 kullanılıyorsa Intune’un aynı Azure Active Directory ortamını kullanması önemlidir.

Intune'un Kimlik gereksinimleri hakkında daha fazla bilgiyi aşağıda bulabilirsiniz.

-   [Kimlik gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview) hakkında daha fazla bilgi edinin.

-   [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements) hakkında daha fazla bilgi edinin.

-   [Çok faktörlü kimlik doğrulaması gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements) hakkında daha fazla bilgi edinin.

### <a name="user-and-device-groups"></a>Kullanıcı ve cihaz grupları

Kullanıcı ve cihaz grupları bir dağıtımın hedefini belirler. İlkeler, uygulamalar ve profiller için dağıtım hedeflemesi içerebilir. Intune bulut yalnızca kullanıcı ve cihaz gruplarını destekler; hangi kullanıcı ve cihaz gruplarının gerekli olacağını belirlemeniz gerekir. Tüm grupların şirket içi Active Directory'de oluşturulması, sonra Azure Active Directory ile eşitlenmesi önerilir. Aşağıda kullanıcı ve cihaz grubu planlama ve oluşturma hakkında daha fazla bilgi bulabilirsiniz.

-   [Kullanıcı ve cihaz gruplarınızı planlama](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups) hakkında daha fazla bilgi edinin.

-   [Kullanıcı ve cihaz gruplarının nasıl oluşturulacağını](https://docs.microsoft.com/en-us/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) öğrenin.

### <a name="public-key-infrastructure-pki"></a>Ortak Anahtar Altyapısı (PKI)

Ortak Anahtar Altyapısı, bir hizmette güvenli kimlik doğrulaması yapabilmek için cihazlara veya kullanıcılara sertifika sağlar. Intune, Microsoft PKI altyapısını destekler. Sertifika tabanlı kimlik doğrulama gereksinimlerini karşılamak için cihaz ve kullanıcı sertifikaları bir mobil cihaza sağlanabilir. Sertifikaları uygulamadan önce, sertifikaların gerekli olup olmadığını, ağ altyapısının sertifika tabanlı kimlik doğrulamasını destekleyip desteklemediğini ve sertifikaların şu anda mevcut ortamda kullanılıp kullanılmadığını belirlemeniz gerekir.

Sertifikaları VPN, Wi-Fi veya Intune ile e-posta profilleriyle kullanmayı planlıyorsanız sertifika ilkeleri oluşturmaya ve dağıtmaya hazır, desteklenen bir [PKI altyapısına sahip olduğunuzdan](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) emin olmanız gerekir.

Ayrıca, SCEP sertifikaları sağlanacaksa hangi sunucunun Ağ Cihazı Kayıt Hizmeti (NDES) özelliğini barındıracağını ve iletişimin nasıl olacağını belirlemeniz gerekir.

Intune’da sertifikaları yapılandırma hakkında daha fazla bilgi için aşağıdakilere bakın:

-   [SCEP için sertifika altyapısını yapılandırma](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [PFX için sertifika altyapısını yapılandırma](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Intune sertifika profillerini yapılandırma](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Kaynak erişim ilkelerini yapılandırma](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="device-platform-considerations"></a>Cihaz Platformunda Dikkat Edilecek Noktalar

Cihazlarınızı doğru şekilde anlamak için daha yakından incelemeniz gerekir.

-   Desteklenen cihaz platformlarını belirleme

-   Cihazlar

-   Cihaz sahipliği

-   Toplu kayıt

Bu alanları daha ayrıntılı bir şekilde gözden geçirelim.

### <a name="determine-supported-device-platforms"></a>Desteklenen cihaz platformlarını belirleme

Ortamda hangi cihazların olacağını bilmeniz ve tasarımınızı oluştururken bunların Intune tarafından desteklenip desteklenmediğini doğrulamanız gerekir. Intune; iOS, Android ve Windows platformlarını destekler.

-   [Intune Tarafından Desteklenen Cihazlar](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers) hakkında daha fazla bilgi edinin.

### <a name="devices"></a>Cihazlar

Intune, kurumsal verilerin güvenliğini sağlamak ve son kullanıcılara daha fazla konumda çalışma olanağı sunmak için mobil cihazları yönetir. Intune birden çok cihaz platformunu desteklediğinden, kuruluşunuzun tasarımında desteklenecek cihazların ve işletim sistemi platformlarının belgelenmesi önerilir. Bu, bölümde oluşturulan cihazları ve platformları (durum gereksinimlerini kullanın) genişletir.

Ayrıca, cihaz özelliklerini işletim sistemi platformu ve sürümüne göre denetlerken listeye başvurmak için sürümleri bilmeniz de önerilir. Örnek aşağıda verilmiştir:

| **Cihaz platformu** | **İşletim Sistemi Sürümleri** |
|:---:|:---:|
| iOS - iPhone | 9.0+ |                
| iOS - iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10 tablet | 10+ |

### <a name="device-ownership"></a>Cihaz sahipliği

Intune, şirket ve KCG sahipliğini destekler. Bir Cihaz, cihaz kayıt yöneticisi tarafından veya cihaz kayıt programı ile kaydedilmişse şirkete ait olarak kabul edilir. Örneğin bir cihaz Apple DEP aracılığıyla kaydedilmiş, şirkete ait olarak işaretlenmiş ve hedeflenen şirket ilkelerini ve uygulamalarını alan bir cihaz grubuna yerleştirilmiş olabilir.

Şirket ve KCG kullanım örnekleri hakkında daha fazla bilgi için [Bölüm 3: Kullanım örneği senaryosu gereksinimleri](section-3-determine-use-case-requirements.md) bölümüne başvurun.

### <a name="bulk-enrollment"></a>Toplu kayıt

Şirket portalı üzerinden kendi kendine kayıt işlemini tamamlamak için Intune’a cihaz kaydetmeye yönelik birden çok kayıt seçeneği vardır. Toplu kayıt, platforma bağlı olarak farklı yollarla gerçekleştirilebilir. Toplu kayıt gerekli olursa önce toplu kayıt yöntemini belirleyin ve tasarımınıza dahil edin. Farklı toplu kayıt yöntemleri hakkında daha fazla bilgiyi aşağıda bulabilirsiniz.

-   [Toplu kayıt](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune) hakkında daha fazla bilgi edinin.

## <a name="feature-requirements"></a>Özellik gereksinimleri

Bu bölümlerde, kullanım örneği senaryo gereksinimlerinize uygun aşağıdaki özellikleri ve yetenekleri inceleyeceğiz:

-   Hüküm ve Koşullar İlkeleri

-   İlke

-   Kaynak Profilleri

-   Uygulamalar

-   Uyumluluk İlkesi

-   Koşullu Erişim

Bu alanların her birini daha ayrıntılı bir şekilde gözden geçirelim.

### <a name="terms-and-conditions-policies"></a>Hüküm ve Koşullar ilkeleri

Hüküm ve Koşullar, bir son kullanıcının kayıt öncesi kabul etmesi gereken ilkeleri veya koşulları açıklamak için kullanılabilir. Intune, kullanıcı gruplarına birden çok hüküm ve koşullar ilkesi ekleme ve dağıtma yeteneğini destekler. Hüküm ve koşul ilkelerinin gerekli olup olmadığını belirlemeniz gerekir. Gerekliyse kuruluşta bu bilgiyi sağlamaktan kimin sorumlu olacağını belirlemelisiniz.

-   Intune’da [hüküm ve koşul ilkeleri oluşturma](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) hakkında bilgi edinin. Hüküm ve koşullar ilkesinin nasıl belgeleneceğine ilişkin bir örnek aşağıda verilmiştir.

| **Hüküm ve Koşullar adı** | **Kullanım örneği** | **Hedeflenen grup** |
|:---:|:---:|:---:|
| Kurumsal Hüküm ve Koşullar | Kurumsal | Kurumsal kullanıcılar |                 
| KCG Hüküm ve Koşulları | KCG | KCG kullanıcıları |                

### <a name="configuration-policies"></a>Yapılandırma ilkeleri

Yapılandırma ilkeleri bir cihazdaki güvenlik ayarlarını ve özelliklerini yönetmek için kullanılır. Yapılandırma ilkelerinizi tasarlarken, Intune cihazları için gerekli yapılandırmaları belirlemek için kullanım örneği gereksinimleri bölümüne bakın. Hangi ayarların ve bunların nasıl yapılandırılacağını ve ayrıca hangi kullanıcıya veya cihaz gruplarına hedefleneceğini belgeleyin.

Platform başına en az bir Yapılandırma İlkesi oluşturmanız gerekir. Gerekirse her platform için birden çok Yapılandırma İlkesi oluşturabilirsiniz. Aşağıda farklı platformlar ve kullanım örneği senaryoları için dört farklı yapılandırma ilkesi tasarlamaya örnek verilmiştir.

| **İlke adı** | **Cihaz platformu** | **Ayarlar** | **Hedef grup** |   
|:---:|:---:|:---:|:---:|
| Kurumsal - iOS | iOS | PIN gereklidir, Uzunluğu: 6, Bulut Yedeklemeyi Kısıtla | Kurumsal Cihazlar |                                                           
| Kurumsal - Android | Android | PIN gereklidir, Uzunluğu: 6, Bulut Yedeklemeyi Kısıtla | Kurumsal Cihazlar |                                                           
| KCG – iOS  | iOS | PIN gereklidir, Uzunluğu: 4 | KCG cihazlar |
| KCG – Android  | Android | PIN gereklidir, Uzunluğu: 4 | KCG cihazlar |

### <a name="profiles"></a>Profiller

Profiller, son kullanıcının şirket verilerine bağlanmasına yardımcı olmak için kullanılır. Intune birçok profil türünü destekler. [Profillerin](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) ne zaman yapılandırılacağını belirlemek için kullanım örneklerine ve gereksinimlerine başvurun. Tüm cihaz profilleri platform türüne göre kategorize edilir ve tasarım belgelerine eklenmelidir.

-   Sertifika profilleri

-   Wi-Fi profili

-   VPN profili

-   E-posta profili

Her profil türünü daha ayrıntılı bir şekilde inceleyelim.

##### <a name="certificate-profiles"></a>Sertifika profilleri

Sertifika profilleri Intune’un bir kullanıcı veya cihaza sertifika vermesine olanak tanır. Intune aşağıdakileri destekler:

-   Basit Sertifika Kayıt Protokolü (SCEP)

-   Güvenilen Kök Sertifika

-   PFX sertifikası.

Hangi kullanıcı grubunun sertifikaya ihtiyacı olduğu, kaç sertifika profili gerekeceği ve bunların hangi kullanıcı gruplarına dağıtılacağının belgelenmesi önerilir.

>[!NOTE]
> Güvenilen kök sertifikanın SCEP sertifikası için gerekli olduğunu unutmayın ve SCEP sertifikası için hedeflenen tüm kullanıcıların aynı zamanda güvenilen kök sertifika alacağından emin olun. SCEP sertifikaları gerekiyorsa hangi SCEP sertifika şablonlarının gerekli olacağını tasarlayın ve belgeleyin.

Tasarım sırasında sertifikaları belgelemeye dair bir örnek aşağıda verilmiştir:

| **Tür** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| Kök CA | Kurumsal Kök CA | Android, iOS, Windows mobile | Kurumsal, KCG  |                                                           
| SCEP | Kullanıcı Sertifikası | Android, iOS, Windows mobile | Kurumsal, KCG |                                                           

##### <a name="wi-fi-profile"></a>Wi-Fi profili

Wi-Fi profilleri, bir mobil cihazı otomatik olarak kablosuz ağa bağlamak için kullanılır. Intune, Wi-Fi profillerinin desteklenen tüm platformlara dağıtılmasını destekler.

-   [Intune’un Wi-Fi profillerini nasıl desteklediği](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune) hakkında daha fazla bilgi edinin.

Bir Wi-Fi profili için bir tasarım örneği aşağıda verilmiştir:

| **Tür** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Asya Wi-Fi profili | Android | Kurumsal, KCG Asya bölgesi|                                                           
| Wi-Fi | Kuzey Amerika Wi-Fi profili | Android, iOS, Windows 10 Mobile | Kurumsal, KCG Kuzey Amerika bölgesi |                                                           

##### <a name="vpn-profile"></a>VPN profili

VPN profilleri, kullanıcıların ağınıza uzak konumlardan güvenli bir şekilde erişmesini sağlar. Intune, yerel mobil VPN bağlantıları ve üçüncü taraf satıcılarından VPN profillerini destekler.

-   [Intune tarafından desteklenen VPN profilleri ve satıcıları](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune) hakkında daha fazla bilgi edinin.

Bir VPN profili tasarımının belgelenmesine ilişkin bir örnek aşağıda verilmiştir.

| **Tür** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN Cisco herhangi bir bağlantı Profili | Android, iOS, Windows 10 Mobile | Kurumsal, KCG Kuzey Amerika ve Almanya|                                                           
| VPN | Pulse Secure | Android | Kurumsal, KCG Asya bölgesi |                                                           

##### <a name="email-profile"></a>E-posta profili

E-posta profilleri, bir e-posta istemcisinin bağlantı bilgileriyle otomatik olarak kurulmasına ve e-posta yapılandırmasını ayarlamasına olanak tanır. Intune, bazı cihazlarda e-posta profillerini destekler.

-   [E-posta profilleri](https://docs.microsoft.com/en-us/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) ve hangi platformların desteklendiği hakkında daha fazla bilgi edinin.

E-posta profillerinin tasarımının belgelenmesine dair bir örnek aşağıda verilmiştir:

| **Tür** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| E-posta profili | iOS e-posta profili | iOS | Kurumsal – KCG bilgi çalışanı |                                                           
| E-posta profili | Android Knox e-posta profili | Android Knox | KCG |

### <a name="apps"></a>Uygulamalar

Intune, kullanıcılara veya cihazlara uygulama sağlamayı birden çok yolla destekler. Sağlanan uygulama türü; yazılım yükleme uygulamaları, genel uygulama mağazasından uygulamalar, dış bağlantılar veya yönetilen iOS uygulamaları olabilir. Tek tek uygulama dağıtımlarına ek olarak toplu satın alınan uygulamalar, iOS ve Windows için toplu satın alma programları aracılığıyla yönetilebilir ve dağıtılabilir. Intune’un uygulamaları ve toplu satın alma programlarını nasıl desteklediği hakkında daha fazla bilgi aşağıda verilmiştir.

-   [Uygulama türleri](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune) hakkında daha fazla bilgi edinin

-   [iOS İş için Toplu Satın Alma Programı (VPP](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) hakkında daha fazla bilgi edinin.

-   [İş için Windows Mağazası](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune) hakkında daha fazla bilgi edinin.

#### <a name="app-type-requirements"></a>Uygulama türü gereksinimleri

Uygulamalar kullanıcılara ve cihazlara dağıtılabildiği için hangi uygulamaların Intune tarafından yönetileceğine karar vermeniz önerilir. Listeyi oluştururken aşağıdaki soruları yanıtlamayı deneyin:

-   Uygulamalar bulut hizmetleriyle tümleştirme gerektiriyor mu?

-   KCG kullanıcılarına tüm uygulamalar sağlanacak mı?

-   Bu uygulamalar için kullanılabilen dağıtım seçenekleri nelerdir?

-   Şirketinizin, iş ortaklarına Hizmet olarak yazılım (SaaS) uygulama verilerine erişim sağlaması gerekiyor mu?

-   Uygulamalar kullanıcının cihazlarından İnternet erişimini gerektiriyor mu?

-   Uygulamalar bir uygulama mağazasında genel olarak kullanılabilir mi ya da özel İş Kolu Uygulamaları mı?


>[!TIP]
> [Intune’un desteklediği farklı türde uygulamalara](https://docs.microsoft.com/intune/deploy-use/add-apps) göz atın.

#### <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

Uygulama koruma ilkeleri, uygulamanın kurumsal verileri nasıl yönettiğini tanımlayarak veri kaybını en aza indirir. Intune, mobil uygulama yönetimi ile çalışması için oluşturulan tüm uygulamalarda uygulama koruma ilkelerini destekler. Uygulama koruma ilkesi tasarlarken, belirli bir uygulamada şirket verilerine hangi kısıtlamaları getireceğinizi belirlemeniz gerekir. [Uygulama koruma ilkelerinin](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) nasıl çalıştığını gözden geçirmeniz önerilir. Aşağıda mevcut uygulamaların nasıl belgeleneceği ve hangi korumanın gerektiğine ilişkin bir örnek verilmiştir.

| **Uygulama** | **Amaç** | **Platformlar** | **Kullanım örneği** | **Uygulama koruma ilkesi** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook mobile  | Kullanılabilir | iOS | Kurumsal - Yöneticiler | Jailbreak uygulanmış olamaz, dosyaları şifreleyin |                                                         
| Word | Kullanılabilir | iOS, Android - Samsung Knox, Knox harici, Windows 10 mobile | Kurumsal, KCG | Jailbreak uygulanmış olamaz, dosyaları şifreleyin |                                                         

#### <a name="compliance-policies"></a>Uyumluluk ilkeleri

Uyumluluk ilkeleri, bir cihazın belirli gereksinimlere uygun olup olmadığını belirler. Intune, bir cihazın uyumlu veya uyumsuz olarak kabul edileceğini belirlemek için uyumluluk ilkeleri kullanır. Bundan sonra, şirket kaynaklarına erişimi kısıtlamak için uyumluluk durumu kullanılabilir. Koşullu erişim gerekiyorsa bir [cihaz uyumluluk ilkesi](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) tasarlamanız önerilir. Kaç cihaz uyumluluk ilkesi gerektiğini ve hangi kullanıcı gruplarının hedef kullanıcı grupları olduğunu belirlemek için gereksinimlere ve kullanım örneklerine başvurun. Ek olarak, bir cihazın uyumsuz olarak kabul edilmesi için oturum açmadan önce ne kadar süre çevrimdışı kalabileceğini de belirlemeniz gerekir.

Bir uyumluluk ilkesi tasarlamaya ilişkin bir örnek aşağıda verilmiştir:

| **İlke adı** | **Cihaz platformu** | **Ayarlar** | **Hedef grup** |   
|:---:|:---:|:---:|:---:|
| Uyumluluk ilkesi | iOS, Android - Samsung Knox, Knox harici, Windows 10 mobile | PIN - gerekli, jailbreak uygulanmış olamaz | Kurumsal, KCG |

#### <a name="conditional-access-policies"></a>Koşullu erişim ilkeleri

Koşullu Erişim yalnızca uyumlu cihazların şirket kaynaklarına erişmesine izin vermek için kullanılır. Intune şirket kaynaklarına erişimi denetlemek için tüm Enterprise Mobility + Security (EMS) ile birlikte çalışır. Koşullu erişimin gerekli olup olmadığını ve neyin korunması gerektiğini belirlemeniz gerekir.

-   [Koşullu Erişim](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) hakkında daha fazla bilgi edinin.

Çevrimiçi erişim için hangi platformların ve kullanıcı gruplarının koşullu erişim ilkeleri tarafından hedefleneceğini belirleyin.

Ek olarak, Exchange Online veya Şirket İçi Exchange için Intune hizmetten hizmete bağlayıcısını yüklemeniz/yapılandırmanızın gerekli olup olmadığını belirlemeniz gerekir.

Intune hizmetten hizmete bağlayıcılarının nasıl yükleneceği ve yapılandırılacağı hakkında daha fazla bilgi edinin:

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Exchange Şirket İçi](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Aşağıda, koşullu erişim ilkelerinin belgelenmesine dair bir örnek verilmiştir:

| **Hizmet** | **Modern Kimlik Doğrulaması Platformları** | **Temel Kimlik Doğrulaması** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Intune’un desteklediği platformlarda uyumlu olmayan cihazları engelle | Kurumsal, KCG |
| SharePoint Online | iOS, Android |  | Kurumsal, KCG |

## <a name="next-section"></a>Sonraki Bölüm

Sonraki bölümde [Intune uygulama süreci](section-8-onboarding-process.md) hakkında yönergeler sağlanır.



<!--HONumber=Dec16_HO5-->

