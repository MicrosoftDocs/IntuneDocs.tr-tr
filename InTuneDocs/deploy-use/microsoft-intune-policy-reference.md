---
title: "Yapılandırma ilkesi başvurusu | Microsoft Docs"
description: "Cihazlarınızı yönetirken hangi Microsoft Intune ilkesine ihtiyaç duyduğunuza karar vermek için bu konu başlığı altındaki bilgileri kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: c7691f49fdbb63533d12ec64c49dfe6e8440e63a


---

# <a name="microsoft-intune-configuration-policy-reference"></a>Microsoft Intune yapılandırma ilkesi başvurusu

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cihazlarınızı yönetirken hangi Microsoft Intune yapılandırma ilkesine ihtiyaç duyduğunuza karar vermek için bu konu başlığı altındaki bilgileri kullanın.

> [!TIP]
> İlkeleri kullanma hakkında daha ayrıntılı bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).


## <a name="android-configuration-policies"></a>Android yapılandırma ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (Android 4 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri)**<br><br>**Özel Yapılandırma (Android for Work)**|Cihaz özelliklerini denetlemek için kullanılabilen Open Mobile Alliance Uniform Resource Identifier (OMA-URI) ayarları (Wi-Fi ayarları gibi) dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Android ilke ayarları](android-policy-settings-in-microsoft-intune.md).|
|**E-posta Profili (Samsung KNOX Standard 4.0 ve üzeri)**<br><br>**E-posta Profili (Android for Work - Gmail)**<br><br>**E-posta Profili (Android for Work - Nine Work)**|Yönetilen cihazlarda Exchange ActiveSync e-posta ayarları oluşturun, dağıtın ve izleyin. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.<br /><br />Ayrıntılar için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Genel Yapılandırma (Android 4 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri)**<br><br>**Genel Yapılandırma (Android for Work)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Uyumlu veya uyumsuz olan uygulamaları belirtin ve bunların ne zaman kullanıldığını bildirin.<br />Cihazı yalnızca belirli özellikleri çalışacak şekilde kilitleyen (örneğin, cihazın yalnızca bir uygulama çalıştırmasına izin vermek veya ses düğmelerini devre dışı bırakmak) bilgi noktası modunu yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Android ilke ayarları](android-policy-settings-in-microsoft-intune.md).|
|**PKCS #12 (.PFX) Sertifika Profili (Android 4 ve üzeri)**<br><br>**PKCS #12 (.PFX) Sertifika Profili (Android for Work)**|Cihaz sertifika istekleri için .PFX ayarları oluşturmak ve dağıtmak istiyorsanız bu profili kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**SCEP Sertifika Profili (Android 4 ve üzeri)**<br><br>**SCEP Sertifika Profili (Android for Work)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilen Sertifika Profili (Android 4 ve üzeri)**<br><br>**Güvenilen Sertifika Profili (Android for Work)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (Android 4 ve üzeri)**<br><br>**VPN Profili (Android for Work)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak son kullanıcılar ile işleri arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Profili (Android 4 ve üzeri)**<br><br>**Wi-Fi Profili (Android for Work)**|Kablosuz ağ ayarlarını yapılandırın ve kuruluşunuzdaki kullanıcılara dağıtın. Bu ayarları dağıtarak son kullanıcılarla kablosuz ağ arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|
|**Mobil Uygulama Yapılandırma İlkesi (Android for Work)**|Kullanıcı bir Android for Work uygulaması çalıştırdığında gerekebilecek ayarları otomatik olarak sağlamak için mobil uygulama yapılandırma ilkelerini kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Android for Work uygulamalarını mobil uygulama yapılandırma ilkeleri ile yapılandırma](afw-app-configuration-policy.md).

## <a name="ios-configuration-policies"></a>iOS yapılandırma ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (iOS 8.0 ve üzeri)**|Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profillerini iOS cihazlara dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları](ios-policy-settings-in-microsoft-intune.md).|
|**E-posta Profili (iOS 8.0 ve üzeri)**|Yönetilen cihazlarda Exchange ActiveSync e-posta ayarları oluşturun, dağıtın ve izleyin. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.<br /><br />Ayrıntılar için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Genel Yapılandırma (iOS 8.0 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Uyumlu veya uyumsuz olan uygulamaları belirtin ve bunların ne zaman kullanıldığını bildirin.<br />Cihazı yalnızca belirli özellikleri çalışacak şekilde kilitleyen (örneğin, cihazın yalnızca bir uygulama çalıştırmasına izin vermek veya ses düğmelerini devre dışı bırakmak) bilgi noktası modunu yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları](ios-policy-settings-in-microsoft-intune.md).|
|**Mobil Uygulama Yapılandırma İlkesi (iOS 8.0 ve üzeri)**|Kullanıcı bir iOS uygulaması çalıştırdığında gerekebilecek ayarları otomatik olarak sağlamak için mobil uygulama yapılandırma ilkelerini kullanın.<br /><br />Ayrıntılar için bkz. [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).|
|**Mobil Sağlama Profili İlkesi (iOS 8.0 ve üzeri)**|Apple iOS iş kolu mobil uygulamaları, eklenen ve sertifika kullanılarak kodla imzalanan bir sağlama profiliyle oluşturulur. Uygulama iOS cihazında çalıştırıldığında, iOS uygulamanın bütünlüğünü onaylar ve sağlama profilinin tanımladığı ilkeleri zorunlu tutar.<br><br>Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi genellikle 3 yıldır. Öte yandan, bir yıl sonra sağlama profilinin süresi dolar. Sertifikası hala geçerli olduğu halde süresi dolmak üzere olan uygulamaların bulunduğu cihazlara, yeni sağlama profili ilkesini önceden dağıtmak için bu ilkeyi kullanın.<br><br>Ayrıntılar için bkz. [Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanma](ios-mobile-app-provisioning-profiles.md).|
|**PKCS #12 (.PFX) Sertifika Profili (iOS 8.0 ve üzeri)**|Cihaz sertifika istekleri için .PFX ayarları oluşturmak ve dağıtmak istiyorsanız bu profili kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**SCEP Sertifika Profili (iOS 8.0 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilir Sertifika Profili (iOS 8.0 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (iOS 8.0 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak son kullanıcılar ile işleri arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Profili (iOS 8.0 ve üzeri)**|Kablosuz ağ ayarlarını yapılandırın ve kuruluşunuzdaki kullanıcılara dağıtın. Bu ayarları dağıtarak son kullanıcılarla kablosuz ağ arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|


## <a name="mac-os-x-configuration-policies"></a>Mac OS X yapılandırma ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (Mac OS X 10.9 ve üzeri)**|Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profillerini Mac bilgisayarlara dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Mac OS X ilke ayarları](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Mac OS X 10.9 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Uyumlu veya uyumsuz olan uygulamaları belirtin ve bunların ne zaman kullanıldığını bildirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Mac OS X ilke ayarları](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**SCEP Sertifika Profili (Mac OS X 10.9 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilen Sertifika Profili (Mac OS X 10.9 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (Mac OS X 10.9 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak son kullanıcılar ile işleri arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Profili (Mac OS X 10.9 ve üzeri)**|Kablosuz ağ ayarlarını yapılandırın ve kuruluşunuzdaki kullanıcılara dağıtın. Bu ayarları dağıtarak son kullanıcılarla kablosuz ağ arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|

## <a name="windows-configuration-policies"></a>Windows yapılandırma ilkeleri
Yalnızca Windows Phone ve kayıtlı Windows cihazlar için geçerlidir.

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (Windows 10 Masaüstü ile Mobile ve üzeri)**|Cihaz özelliklerini denetlemek için kullanılabilen OMA-URI ayarlarını dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br />    Ayrıntılar için bkz. [Microsoft Intune’da Windows 10 ilke ayarları](windows-10-policy-settings-in-microsoft-intune.md).|
|**Özel Yapılandırma (Windows Phone 8.1 ve üzeri)**|Cihaz özelliklerini denetlemek için kullanılabilen OMA-URI ayarlarını dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows Phone 8.1 ayarları](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Sürüm Yükseltme İlkesi (Windows 10 Masaüstü ve sonrası)**<br><br>**Sürüm Yükseltme İlkesi (Windows 10 Holographic ve sonrası)**<br><br>**Sürüm Yükseltme İlkesi (Windows 10 Mobile ve üzeri)**|Windows 10 cihazlarını daha yeni bir sürüme güncelleştirmek için kullanılan lisans veya ürün anahtarı bilgilerini içeren ilkeler yapılandırın ve dağıtın.<br><br>Ayrıntılar için bkz. [Microsoft Intune’da sürüm yükseltme ilkesi ayarları](edition-upgrade-policy-settings-in-microsoft-intune.md).|  
|**E-posta Profili (Windows Phone 8.1 ve üzeri)**<br /><br />**E-posta Profili (Windows 10 Masaüstü ile Mobile ve üzeri)**|Yönetilen cihazlarda Exchange ActiveSync e-posta ayarları oluşturun, dağıtın ve izleyin. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.<br /><br />Ayrıntılar için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Genel Yapılandırma (Windows 10 Masaüstü ile Mobile ve üzeri)**|Kayıtlı Windows 10 masaüstü ve Mobile cihazları için mobil cihaz güvenliğini ve işlev ayarlarını yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows 10 ilke ayarları](windows-10-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Windows 10 Team ve üzeri)**|Kayıtlı Windows 10 Team cihazları (örneğin, Surface Hub cihazı) için cihaz güvenliğini ve işlevsel ayarları yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows Team yapılandırma ilkesi ayarları](windows-team-configuration-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Windows 8.1 ve üzeri)**|Kayıtlı Windows cihazları için mobil cihaz güvenliğini ve işlev ayarlarını yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows ilke ayarları](windows-configuration-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Windows Phone 8.1 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Kullanıcıların kullanabileceği ve kullanamayacağı uygulamaları belirtin ve uyumsuz uygulamaların yüklenmesini veya kullanılmasını engelleyin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows Phone 8.1 ayarları](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**PKCS #12 (.PFX) Sertifika Profili (Windows 10 Masaüstü ve Mobile ve üzeri)**|Cihaz sertifika istekleri için .PFX ayarları oluşturmak ve dağıtmak istiyorsanız bu profili kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**SCEP Sertifika Profili (Windows 8.1 ve üzeri)**<br /><br />**SCEP Sertifikası Profili (Windows Phone 8.1 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilir Sertifika Profili (Windows 8.1 ve üzeri)**<br /><br />**Güvenilir Sertifika Profili (Windows Phone 8.1 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (Windows 10 Masaüstü ve Mobile ile üzeri)**<br /><br />**VPN Profili (Windows 8.1 ve üzeri)**<br /><br />**VPN Profili (Windows Phone 8.1 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak son kullanıcılar ile işleri arasındaki bağlantıları basitleştirirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Üzerinden İçeri Aktarma**|Önceden bir dosyaya aktardığınız Windows Wi-Fi yapılandırmalarını içeri aktarın ve dağıtın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|
|**Windows Bilgi Koruması**<br>(eski adı kurumsal veri koruma)|Kuruluşta çalışanlara ait cihazlar arttıkça, kuruluşun denetimi dışında kalan e-posta, sosyal medya ve genel bulut gibi uygulamalar ve hizmetler aracılığıyla yanlışlıkla veri sızıntıları yaşama riski de artar. Örneğin, bir çalışan en son mühendislik çalışmalarının resimlerini kişisel bir e-posta hesabından gönderebilir, ürün bilgilerini bir tweet’e kopyalayıp yapıştırabilir veya hazırlanması devam eden satış raporunu genel bulut depolama alanına kaydedebilir.<br><br>Windows Bilgi Koruması, çalışanın deneyimine başka hiçbir şekilde müdahale etmeden bu olası veri sıkıntılarına karşı korumaya yardımcı olur. Ayrıca, ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan, kuruluşa ait cihazlarda ve çalışanların iş yerine getirdiği kişisel cihazlarda yanlışlıkla ortaya çıkabilecek veri sızıntılarına karşı kurumsal uygulamaları ve verileri korumaya da yardımcı olur.<br><br>Bu Intune ilkesi, Windows Information Protection tarafından korunan uygulamalar listesini, kurumsal ağ konumlarını, koruma düzeyini ve şifreleme ayarlarını yönetir.<br><br>Daha fazla bilgi için bkz. [Windows Bilgi Koruması’nı kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-edp).|


## <a name="software-policies"></a>Yazılım ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Yönetilen Tarayıcı İlkesi (Android 4 ve üzeri)**<br /><br />**Managed Browser İlkesi (iOS 8.0 ve üzeri)**|Kullanıcıların yönetilen tarayıcı uygulamasını kullanırken erişebileceği ve erişemeyeceği web sitelerini belirtin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).|
|**Mobil Uygulama Yönetimi (Android 4 ve üzeri)**<br /><br />**Mobil Uygulama Yönetimi İlkesi (iOS 8.0 ve üzeri)**|Dağıttığınız uygulamaları şirket uyumluluk ve güvenlik ilkeleriyle uyumlu hale getirmeye yardımcı olmak için uygulamaların işlevlerini değiştirin. Örneğin, yönetilen bir uygulama içinde kesme, kopyalama ve yapıştırma işlemlerini kısıtlayabilir veya bir uygulamayı tüm web bağlantılarını yönetilen tarayıcıda açmak için yapılandırabilirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).|

## <a name="common-mobile-device-settings"></a>Ortak Mobil Cihaz Ayarları

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Exchange ActiveSync İlkesi**|Exchange ActiveSync tarafından yönetilen cihazlar için mobil cihaz güvenliğini ve işlev ayarlarını yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Exchange ActiveSync ilkesi ayarları](exchange-activesync-policy-settings-in-microsoft-intune.md).|
|**Mobil Cihaz Güvenlik İlkesi**|<ul><li>Şunları içeren mobil cihaz ayarlarını (tüm platformlar) yapılandırır:<br /><br /><ul><li>Güvenlik</li><li>Şifreleme</li><li>Sistem</li><li>E-posta</li><li>Uygulamalar</li></ul></li></ul>
> [!IMPORTANT]
Microsoft Intune’da artık her cihaz platformu için ayrı **yapılandırma ilkeleri** vardır ve bu ilkeler kullanabileceğiniz en güncel ayarları içerir. Mobil cihaz güvenlik ilkesini kullanmaya devam edebilirsiniz ve var olan tüm dağıtımlar çalışmaya devam eder, ancak yeni yapılandırma ilkelerine geçmeyi en kısa sürede planlamanız gerekmektedir.<br />Ayrıntılar için bkz. [Microsoft Intune’da mobil cihaz güvenliği ilke ayarları](mobile-device-security-policy-settings-in-microsoft-intune.md).

## <a name="policies-for-windows-pcs-managed-by-the-intune-software-client"></a>Windows bilgisayarlar için ilkeler Intune yazılım istemcisi tarafından yönetilir

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Microsoft Intune Aracısı Ayarları**|Aşağıdakilerle ilgili ayarlar dahil olmak üzere bilgisayarlarda Intune bilgisayar istemcisini yapılandırın:<br /><br />-   Endpoint Protection<br />-   Yazılım güncelleştirmeleri<br />-   İlke denetimi zamanlaması<br /><br />Bu tür bir ilke yalnızca cihaz gruplarına dağıtılabilir.<br /><br />Intune istemcileri yeni ve güncelleştirilmiş ilkeyi varsayılan olarak sekiz saatlik **Güncelleştirme ve uygulama algılama sıklığı** ayarına göre indirir. Ancak, istediğiniz zaman bilgisayarlarda ilke yenileme uygulayabilirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune'da yazılım güncelleştirmeleriyle Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Microsoft Intune Center Ayarları**|Yönetilen bilgisayarlarda, Microsoft Intune Merkezi'nde gösterilen ayrıntıları yapılandırın.<br /><br />Bu tür bir ilke yalnızca cihaz gruplarına dağıtılabilir.<br /><br />Ayrıntılar için bkz. [Microsoft Intune bilgisayar istemcisiyle ortak Windows bilgisayarı yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).|
|**Windows Güvenlik Duvarı Ayarları**|Bilgisayarlarda aşağıdakiler dahil Windows Güvenlik Duvarı ayarları ve ortak ağ iletişimi için özel durumları yapılandırır:<br /><br />-   BranchCache<br />-   Uzaktan yardım<br />-   Medya paylaşımı<br /><br />Bu tür bir ilke yalnızca cihaz gruplarına dağıtılabilir.<br /><br />Ayrıntılar için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).|

### <a name="see-also"></a>Ayrıca bkz.

[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->

