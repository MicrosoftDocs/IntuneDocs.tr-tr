---
title: "Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme | Microsoft Docs"
description: "Bu konu başlığı altındaki bilgiler, özel iş kolu uygulamalarınızın mobil uygulama yönetimi ilkelerini kullanabilmesini sağlamak için, Uygulama sarmalama aracını ve Uygulama SDK&quot;sını ne zaman kullanmanız gerektiğine karar vermenize yardımcı olur."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8ee746ec2ccd9b924c242e956a8c89fba248ca96
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="prepare-line-of-business-apps-for-mam"></a>İş kolu uygulamalarını MAM için hazırlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune Uygulaması Sarmalama Aracı’nı veya Intune Uygulama SDK’sını kullanarak uygulamalarınızın mobil uygulama yönetim (MAM) ilkelerini kullanmasını sağlayabilirsiniz. Bu iki yöntem ve ne zaman kullanılacakları hakkında bilgi edinmek için bu bilgileri kullanın.

## <a name="intune-app-wrapping-tool"></a>Intune Uygulaması Sarmalama Aracı
Uygulama Sarmalama Aracı öncelikle iç iş kolu (LOB) uygulamaları için kullanılır. Araç, uygulamanın çevresinde sarmalayıcı oluşturan ve sonra uygulamanın bir Intune MAM ilkesiyle yönetilmesine izin veren bir komut satırı uygulamasıdır.

Aracı kullanmak için kaynak kodu gerekli değildir, ancak imzalama kimlik bilgileri gereklidir.  İmzalama kimlik bilgileri hakkında daha fazla bilgi için bkz. [Intune blogu](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Uygulama Sarmalama Aracı belgeleri için bkz. [Android Uygulaması Sarmalama Aracı](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) ve [iOS Uygulaması Sarmalama Aracı](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Uygulama Sarmalama Aracı, Apple App Store veya Google Play Store'daki uygulamaları **desteklemez**. Ayrıca geliştirici tümleştirmesi gerektiren bazı özellikler için de destek sunmaz (aşağıdaki özellik karşılaştırma tablosuna bakın).


Intune’da kayıtlı olmayan cihazlarda MAM için Uygulama Sarmalama Aracı hakkında daha fazla bilgi edinmek üzere bkz. [Microsoft Intune’da kayıtlı olmayan cihazlarda iş kolu uygulamalarını ve verileri koruma](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını kullanma nedenleri:
* Uygulamanız yerleşik veri koruma özelliklerine sahip değil.
* Uygulamanız basit.
* Uygulamanız dahili olarak dağıtılmış.
* Uygulamanın kaynak koduna erişiminiz yok
* Uygulamayı siz geliştirmediniz.
* Uygulamanızda en düşük kullanıcı kimlik doğrulama deneyimleri bulunuyor.


### <a name="supported-app-development-platforms"></a>Desteklenen uygulama geliştirme platformları

|**Uygulama Sarmalama Aracı** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Evet|Evet|
|**Android**| Hayır |Evet|

## <a name="intune-app-sdk"></a>Intune Uygulama SDK'sı
Uygulama SDK'sı temel olarak App Store veya Google Play Store’da uygulamaları olan ve uygulamaları Intune ile yönetebilmek isteyen müşteriler için tasarlanmıştır. Ancak, bir iş kolu uygulaması olsa bile SDK’yı tümleştirme özelliğinden her uygulama yararlanabilir.

SDK hakkında daha fazla bilgi edinmek için bkz. [Genel bakış](../develop/intune-app-sdk.md). SDK’yı kullanmaya başlamak için bkz. [Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama](../develop/intune-app-sdk-get-started.md).

### <a name="reasons-to-use-the-sdk"></a>SDK kullanma nedenleri
* Uygulamanız yerleşik veri koruma özelliklerine sahip değil.
* Uygulamanız karmaşık ve birçok deneyim içeriyor.
* Uygulamanız Google Play veya Apple App Store gibi genel bir uygulama mağazasında dağıtılmıştır.
* Bir uygulama geliştiricisisiniz ve SDK kullanabilecek teknik bilgiye sahipsiniz.
* Uygulamanız diğer SDK tümleştirmelerine sahip.
* Uygulamanız sıkça güncelleştiriliyor.

### <a name="supported-app-development-platforms"></a>Desteklenen uygulama geliştirme platformları

|**Intune Uygulama SDK'sı** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Evet – [Intune Uygulaması SDK Xamarin Bileşenini](../develop/intune-app-sdk-xamarin.md) kullan.|Evet – [Intune Uygulaması SDK Cordova Eklentisini](../develop/intune-app-sdk-cordova.md) kullan.|
|**Android**| Evet – [Intune Uygulaması SDK Xamarin Bileşenini](../develop/intune-app-sdk-xamarin.md) kullan.|Evet – [Intune Uygulaması SDK Cordova Eklentisini](../develop/intune-app-sdk-cordova.md) kullan.|

## <a name="feature-comparison"></a>Özellik karşılaştırması
Bu tabloda Uygulama SDK'si ve Uygulama Sarmalama Aracı için kullanabileceğiniz ayarlar listelenmektedir.

> [!NOTE]
> Uygulama Sarmalama Aracı, tek başına Intune veya Configuration Manager ile Intune ile kullanılabilir.

|Özellik|Uygulama SDK'sı|Uygulama Sarmalama Aracı|
|-----------|---------------------|-----------|
|Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın|X|X|
|Android, iTunes veya iCloud yedeklemelerini engelle|X|X|
|Uygulamanın diğer uygulamalara veri aktarmasına izin ver|X|X|
|Uygulamanın diğer uygulamalardan veri almasına izin ver|X|X|
|Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama|X|X|
|Erişim için basit PIN gerektir|X|X|
|Intune PIN ile yerleşik uygulama PIN kodunu değiştir|X||
|PIN sıfırlanmadan önceki deneme sayısını belirtin|X|X|
|PIN yerine parmak izine izin ver |X|X|
|Erişim için kurumsal kimlik bilgileri gerektir|X|X|
|Yönetilen cihazların, jailbreak uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelle|X|X|
|Uygulama verilerini şifreleme|X|X|
|Belirtilen sayıda dakika sonrasında erişim gereksinimlerini yeniden denetle|X|X|
|Çevrimdışı kullanım süresini belirtin|X|X|
|Ekran yakalamayı engelle (yalnızca Android)|X|X|
|Tam Temizleme|X|X|
|Seçmeli Silme <br></br>**Not:** iOS için yönetim profili kaldırıldığında uygulama da kaldırılır.|X||
|“Farklı Kaydet”i önleme |X||
|Çoklu Kimlik Desteği|X||
|Cihaz kaydı olmadan MAM desteği|X|X|
|Özelleştirilebilir Stil |X|||
### <a name="see-also"></a>Ayrıca bkz.

[Android uygulama sarmalama aracı](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS uygulama sarmalama aracı](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)
