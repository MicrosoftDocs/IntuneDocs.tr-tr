---
title: "Microsoft Intune’da KCG’yi etkinleştirme"
description: 
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 880b83a63eefe13a96ab8838c7092c185aa32cd0
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2017
---
# <a name="enable-byod-with-intune"></a>Intune ile KCG'yi Etkinleştirme

Bu konu, kuruluşunuzda Kendi cihazını Getir (KCG) çözümünü etkinleştirmek üzere Intune’u ayarlamanız için yüksek düzey bir iş akışı sağlar. Görev, üç işleme ayrılır ve “Nasıl Yapılır?” konularına giden destekleyici bağlantılar sağlanır.

İş akışı aşağıdaki gibi üç işleme ayrılmıştır. Kuruluşunuzun gereksinimlerine göre süreçlerde değişiklik yapabilirsiniz.

-   **[Cihazları kaydetme ve uyumluluğu denetleme](#enroll-devices-and-check-for-compliance)**, kullanıcıların kişisel cihazlarını Intune yönetimine nasıl kaydedeceğini açıklar. Intune; iOS, macOS, Android ve Windows cihazları yönetebilir. Bu bölüm ayrıca, cihazlara nasıl ilke dağıtılacağını açıklar ve cihazların temel güvenlik gereksinimlerini karşıladığından emin olmanıza yardımcı olur.

- **[Şirket kaynaklarına erişim sağlama](#provide-access-to-company-resources)** işlemi, BT ekibi tarafından kullanıcıların şirket kaynaklarına kolay ve güvenli erişiminin nasıl sağlanacağını gösterir. Bunu, yönetilen cihazlara erişim profilleri dağıtarak yaparsınız. Bu bölüm ayrıca toplu satın alınan uygulama dağıtımlarını Intune’da nasıl yöneteceğinizi açıklar.

-   **[Şirket verilerini koruma](#protect-company-data)**, şirket kaynaklarına koşullu erişim sağlamayı, veri kaybını önlemeyi ve şirket uygulama ve verileri, iş için artık gerekli olmadığında veya kaybedildiğinde/çalındığında bunların nasıl kaldırılacağını öğrenmenize yardımcı olur.

[![Microsoft Intune’da KCG’yi etkinleştirmek için yüksek düzey iş akışı diyagramı](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Başlamadan önce
Kullanıcıların cihazlarını kaydetmesi için önce Intune hizmetini hazırlamanız gerekir. Bunu yapmak için [kullanıcılara lisans atayın](licenses-assign.md) ve [mobil cihaz yönetim yetkilisini ayarlayın](mdm-authority-set.md).

Başlamışken [şirket portalını da özelleştirebilirsiniz](company-portal-customize.md). Şirket markasını ekleyin ve kullanıcılar için destek bilgileri sağlayın. Böylece kullanıcılarınıza güvenilir bir kayıt ve destek deneyimi sunabilirsiniz.

## <a name="enroll-devices-and-check-for-compliance"></a>Cihazları kaydetme ve uyumluluk denetimi yapma

Intune hizmetini hazırladıktan sonra, yönetmek istediğiniz cihaz türleri için çeşitli kayıt gereksinimlerini karşılamanız gerekir. Cihazları yönetime kaydetme işlemi oldukça basittir ancak çeşitli cihaz türlerine göre biraz farklılık gösterir.

-   **iOS ve Mac cihazlar** iPad, iPhone veya MacOS cihazları kaydetmek için bir [Apple Anında İletilen Bildirim servisi (APNs) sertifikası](apple-mdm-push-certificate-get.md) almanız gerekir. APNs sertifikanızı Intune’a yükledikten sonra kullanıcılar, [iOS cihazlarını kaydetmek](/intune-user-help/enroll-your-device-in-intune-ios) için Şirket Portalı uygulamasını, [MacOS cihazlarını kaydetmek](/intune-user-help/enroll-your-device-in-intune-macos) içinse Şirket Portalı web sitesini kullanabilir.

-   **Android cihazlar** Intune hizmetini Android cihazların kaydına hazır hale getirmek için yapmanız gereken bir şey yoktur. Kullanıcılar Google Play’den edinilebilecek Şirket Portalı uygulamasını kullanarak [Android cihazlarını yönetime kaydedebilir](/intune-user-help/enroll-your-device-in-intune-android.md).

-   **Windows Phone ve bilgisayarlar** Windows cihazların kaydını kolaylaştırmak amacıyla [kayıt sunucusu için bir DNS diğer adı ayarlamalısınız](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium). Bunu yapmadığınız takdirde kullanıcılar, [Windows cihazlarını kaydetmek](/intune-user-help/enroll-your-w10-phone-or-w10-pc-windows) için bir iş veya okul hesabı ekleyebilir.

  - Azure AD Premium’unuz varsa [otomatik kaydı etkinleştirerek](windows-enroll.md) kullanıcılarınızın Windows cihazları kaydetmelerini kolaylaştırabilirsiniz. Bu özellik, bir kullanıcı kişisel cihazını kaydetmek için iş veya okul hesabı eklediğinde cihazı otomatik olarak kaydeder. Ayrıca kuruluşunuzun Azure AD’sine katılan şirkete ait cihazlarda da çalışır.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Yönetilen cihazların, temel güvenlik gereksinimlerini karşıladığından emin olma

Kullanıcılar cihazlarını yönetime kaydettikten sonra BT çalışanlarının, şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların temel güvenlik gereksinimlerini karşıladığından emin olmaları gerekir. Bu kurallar, cihazlara ve cihazlarda depolanan şifreleme verilerine erişmek için bir PIN kullanmayı içerebilir. Bu tür bir kurallar kümesine [uyumluluk ilkesi](device-compliance.md) adı verilir.

Bir kullanıcıya [uyumluluk ilkesi dağıttığınızda](device-compliance-get-started.md) Intune, KCG ilkenizin bir parçası olarak tanımladığınız temel güvenlik gereksinimlerine uyup uymadıklarını görmek için kullanıcının Intune tarafından yönetilen tüm cihazlarını kontrol eder. İlke uyumluluk değerlendirmesi yapılan cihazın durumu, Intune hizmetine bildirilir. Bazen kullanıcıların, PIN veya cihaz şifreleme gibi ayarları düzeltmeleri istenebilir. Bunun dışında şirket portalı uygulaması, ilkenize uymayan herhangi bir ayarı yalnızca kullanıcıya bildirir.

## <a name="provide-access-to-company-resources"></a>Şirket kaynaklarına erişim sağlama

Çalışanlarınızın çoğu, mobil cihazlarından şirket e-posta ve belgelerine erişmek ister. Bunun, karmaşık adımlarla uğraşmadan veya yardım masasını aramadan ayarlanmasını beklerler. Intune, mobil cihazlara önceden yüklenen yerel e-posta uygulamaları için [e-posta ayarları oluşturup dağıtmanızı](conditional-access-intune-common-ways-use.md) kolaylaştırır.
<!--- this was old link: (https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune). check with Andre--->

> [!NOTE]
> Intune, Google Play mağazasında bulunan Gmail ve Nine Work e-posta uygulamaları için İş için Android e-posta profili yapılandırmasını destekler.

Intune ayrıca, kullanıcılar dışarıda çalıştığında şirket içi şirket verilerine erişimi denetlemenize ve korumanıza yardımcı olur. Intune [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) ve e-posta profilleri birlikte çalışarak kullanıcılarınızın, işlerini nerede olursa olsun gerçekleştirmek için ihtiyaç duydukları dosyalara ve kaynaklara erişim kazanmalarına yardımcı olur. Azure Active Directory Uygulama Proxy'si ve koşullu erişim kullanarak şirketinizin şirket içinde barındırılan web uygulamaları ve hizmetlerinin de erişim güvenliği ve koruması sağlanabilir.

### <a name="manage-volume-purchased-apps"></a>Toplu satın alınan uygulamaları yönetme
Intune ile şunları kolayca yapabilirsiniz:
* Herhangi bir uygulama mağazasından toplu lisans bilgisini içeri aktarma
* Kaç lisans kullandığınızı takip etme
* Kullanıcılarınızın, sahip olduğunuz uygulamanın birden fazla kopyasını indirmelerini önleme
* [Mağaza uygulamalarını yönetilen cihazlara gönderme](apps-deploy.md)
* Şirket portalı web sitesini kullanarak uygulamaları, yönetilmeyen cihazlara gönderme

Ayrıca, iOS uygulama mağazasından ve İş İçin Windows Mağazası’ndan toplu olarak satın aldığınız uygulamaları Intune ile yönetebilirsiniz. Bu durum, toplu satın alınan uygulamaları izlemeye yönelik yönetim yükünü azaltmanıza yardımcı olabilir.

> [!TIP]
> [Azure AD Connect ile Çoklu Oturum Açma’yı (SSO) yapılandırabilirsiniz](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). SSO ile kullanıcılar, şirkette kullandıkları etki alanı kullanıcı adı ve parolaları ile uygulamalarda oturum açabilir. Ayrıca Azure Active Directory Uygulama Proxy’si ile [şirket içinde barındırılan web uygulamalarına İnternet üzerinden erişim sağlayabilirsiniz](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [iOS cihazları için toplu satın alınan uygulamaları yönetme](vpp-apps-ios.md). [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ile iOS için birden çok lisans satın alabilirsiniz. Apple web sitesinden bir Apple VPP hesabı ayarlamanız ve Apple VPP belirtecini Intune’a yüklemeniz gerekir. Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

-   [İş İçin Windows Mağazası’ndan satın alınan uygulamaları yönetme](windows-store-for-business.md). [İş İçin Windows Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için uygulamaları tek tek veya toplu olarak bulabileceğiniz ve satın alabileceğiniz bir yerdir. Mağazayı Intune’a bağlayarak, toplu satın alınan uygulamaları Intune portalından yönetebilirsiniz.

## <a name="protect-company-data"></a>Şirket verilerini koruma

Intune, şirket verilerini pek çok teknoloji katmanıyla korur. Kimlik katmanında koşullu erişim, hizmetlere erişimi korur. Koşullu erişim, yalnızca yönetilen ve uyumlu cihazların şirket kaynaklarına erişmesine izin verir. İstemci uygulama katmanında mobil uygulama yönetimi (MAM), veri kaybını önler.  Uygulama koruma ilkeleri, verilerin korunmayan uygulamalara veya depolama konumlarına taşınmasını engeller. Bu ilkeler ayrıca, bir cihaz kaybolduğunda veya çalındığında tüm şirket verilerini silmenize imkan tanır.

### <a name="enforce-conditional-access-to-company-resources"></a>Şirket kaynaklarına koşullu erişimi zorunlu kılma

Uyumluluk ilkelerini [koşullu erişim ilkeleriyle](device-compliance.md) birlikte kullanarak cihazların KCG ilkenizle belirlenen temel güvenlik gereksinimlerini karşılayıp karşılamadığını denetleyebilirsiniz. Bir cihaz bu gereksinimleri karşılamıyorsa kurallar uygulamaya girer ve cihaz, ilke gereksinimlerine uyum sağlayana kadar erişim engellenir. Bu seçenek, yalnızca yönetilen ve uyumlu cihazların Exchange ([Şirket içi Exchange](exchange-connector-install.md) veya [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype Kurumsal Çevrimiçi Sürüm gibi hizmetlerden şirket verilerine erişmesini sağlar.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Uyumluluğu doğrulayacak herhangi bir uyumluluk ilkesi yoksa koşullu erişim ilkeleri çalışmaz.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Uygulama koruma ilkeleriyle şirket verilerinin kaybını önleme

Intune’un uygulama koruma ilkelerini kullanarak, verilerinize erişim için cihazların kayıtlı olmasını gerektirmeyi seçebilirsiniz. Bu seçim, şirket verilerini korumanıza yardımcı olur ve bir kullanıcı, cihazını Intune’a kaydetmese bile şirket verilerine güvenli bir şekilde erişebilir.

Kullanıcılarınızın iOS ve Android cihazları tarafından erişilen şirket verilerini korumaya yardımcı olmak için [Intune uygulama koruma ilkelerini](app-protection-policies.md) kullanabilirsiniz. Bu uygulama düzeyinde ilkeleri uyguladığınızda, cihazın Intune tarafından yönetilmediği durumlarda dahi şirket verilerinin çalışanlar tarafından nasıl kullanıldığını ve paylaşıldığını denetleyebilirsiniz

Bu işlemi yönetilen Windows 10 cihazlarda yapmak için [Windows Bilgi Koruması (WIP) ilkelerini](app-protection-policies-configure-windows-10.md) kullanın. Bu ilkeler, çalışanların deneyimini etkilemeden çalışır. Ağ ortamınız veya diğer uygulamalarınızda değişiklik gerektirmez.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Kişisel verileri korurken şirket verilerini silme

Bir cihazın iş için artık gerekli olmadığı, kullanım amacının değiştirildiği veya kaybolduğu durumlarda bu cihazdan şirket uygulamalarını ve verilerini kaldırabiliyor olmanız gerekir. Bunu yapmak için Intune’un seçmeli silme ve tam silme özelliklerini kullanabilirsiniz. Kullanıcılarınız, Intune yönetimine kaydettikleri kişisel cihazlarını Intune Şirket Portalı aracılığıyla uzaktan da silebilir.

[Tam temizleme](devices-wipe.md), cihazı fabrika varsayılan ayarlarına geri yükler ve tüm şirket ve kullanıcı verileriyle ayarlarını kaldırır. [Seçmeli silme](devices-wipe.md#selective-wipe), cihazdan yalnızca şirket verilerini siler ve kullanıcının kişisel verilerine dokunmaz.

Seçmeli silme başlatıldıktan sonra cihaz, yönetimden kaldırmak için anında işlemi başlatır. İşlem tamamlandığında, tüm şirket verileri silinir ve cihaz adı Intune yönetici konsolundan kaldırılır. Böylece cihaz yönetimi yaşam döngüsü sonlanır.