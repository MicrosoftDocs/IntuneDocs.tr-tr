---
title: "Şirket Portalı’nı özelleştirme | Microsoft Intune"
description: "Intune Şirket Portalı kullanıcıların cihaz kaydetme, uygulama yükleme ve BT departmanı bilgilerine ulaşma gibi sık kullanılan görevleri gerçekleştirmesini sağlar."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 04cccd410417dca4477c0d6cd61b0940dda8c389


---

# <a name="customize-the-company-portal"></a>Şirket Portalı'nı özelleştirme
Intune Şirket Portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.

Intune Şirket Portalı, kullanıcıların şirket verilerine ve uygulamalarına erişmesini sağlar. Şirket Portalı iki biçimde sağlanır:

-   **Şirket portalı uygulaması**: Intune ile yönettiğiniz cihazlarda kullanılabilen bir uygulama. [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-ios-or-mac-os-x-device-with-intune) ve [Windows](/Intune/EndUser/using-your-windows-device-with-intune) için Şirket Portalı uygulamaları hakkında daha fazla bilgi edinin.


- **Şirket Portalı web sitesi**: Son kullanıcıların Şirket Portalı uygulamasından yapacağı görevlerin çoğunu yapmasını sağlayan web sitesi. Intune Şirket Portalının URL'si: [http://portal.manage.microsoft.com](http://portal.manage.microsoft.com). [Intune Şirket Portalı web sitesini kullanma](/Intune/EndUser/using-the-intune-company-portal-website) konusu, bu web sitesi hakkında daha fazla bilgi sağlar.

> [!TIP]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.

Kullanıcıların Şirket Portalı’nda yerine getirebilecekleri görevlerden bazıları:

-   Cihazları kaydetme
-   Cihazlarının durumunu görüntüleme
-   Cihazlarını sıfırlama
-   Parolalarını sıfırlama
-   Cihazlarını uzaktan kilitleme
-   Kuruluşunuz tarafından dağıtılan yazılımları indirme
-   Destek için BT bölümüne başvurun

> [!NOTE]
> Şirket Portalı uygulaması belirli ülkelerde henüz kullanılmamaktadır.
> __iOS__: iOS için Şirket Portalı uygulaması Apple iOS App Store’da [tüm kullanılabilir bölgelerde](https://go.microsoft.com/fwlink/?linkid=831284) yayınlanmıştır.
> __Android__: Android için Şirket Portalı uygulaması şu anda Çin'de kullanılmamaktadır. Bu ülkelerde, [Şirket Portalı uygulamasının Android sürümünü dışarıdan yüklemek](https://www.microsoft.com/en-us/download/details.aspx?id=49140) alternatif bir çözümdür.  

## <a name="customize-company-portal-settings"></a>Şirket Portalı ayarlarını özelleştirme
Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bir kiracı veya hizmet yöneticisi olarak [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) oturum açmanız, **Yönetici** &gt; **Şirket Portalı**'nı seçmeniz ve Şirket Portalı ayarlarını yapılandırmanız yeterli olur.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## <a name="company-contact-information-and-privacy-statement"></a>Şirket iletişim bilgileri ve gizlilik bildirimi
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Kullanıcılara kişi bilgileri ve ayrıntıları Şirket Portalı’nın BT’ye Başvur ekranında görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
    |----------|------------------------|----------------|
    |Şirket adı|40|Bu ad Şirket Portalı’nın başlığı olarak gösterilir.|
    |BT departmanı ilgili kişi adı|40|Bu ad **BT’ye Başvur**sayfasında gösterilir.|
    |BT departmanı telefon numarası|20|Bu iletişim numarası **BT'ye Başvur** sayfasında gösterilir.|
    |BT departmanı e-posta adresi|40|Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. **alias@domainname.com** biçiminde geçerli bir e-posta adresi girmeniz gerekir.|
    |Ek bilgiler|120|**BT'ye Başvur** sayfasında gösterilir.|
    |Şirket gizlilik bildirimi URL'si|79|Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. https://www.contoso.com biçiminde geçerli bir URL girmelisiniz.|

## <a name="support-contacts"></a>Destek kişileri
Şirket Portalı’nda kullanıcılara, çevrimiçi desteğe erişebilmeleri için destek web sitesi gösterilir.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
    |----------|------------------------|----------------|
    |Destek web sitesi URL'si|150|Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, https://www.contoso.com biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez.|
    |Web sitesinin adı|40|Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında **BT web sitesine gidin** ifadesi gösterilir.|

## <a name="company-branding-customization"></a>Şirket markasıyla özelleştirme
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.

|Alan adı|Daha fazla bilgi|
    |----------|----------------|
    |Tema rengi|Şirket Portalı’na uygulamak için bir tema rengi seçin.|
    |Şirket logosunu ekle|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. Her logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 100 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır.|
    |[!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Şirket Portalı uygulaması için bir arka plan seçin|Bu ayar yalnızca [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Şirket Portalı uygulamasını etkiler.|


Değişiklikleri kaydettikten sonra, Şirket Portalı web sitesini görüntülemek için yönetici konsolunun **Şirket Portalı** sayfasının sonunda sağlanan bağlantıları kullanabilirsiniz. Bu bağlantılar değiştirilemez. Bir kullanıcı oturum açtığında bu bağlantılar Şirket Portalı’ndaki aboneliklerinizi görüntüler.

>[!div class="step-by-step"]

>[&larr; **İlkeler ve uygulamalar oluşturma**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Cihazları kaydetme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Dec16_HO2-->

