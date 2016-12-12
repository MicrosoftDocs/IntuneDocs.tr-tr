---
title: "Cihazları kaydetme | Microsoft Intune"
description: "Mobil cihaz yönetimi (MDM), kaydı, cihazları yönetime getirmek ve kaynaklara erişim izni vermek için kullanır."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c59707ba2967b069dc30aee71d2642e91d71b23b
ms.openlocfilehash: a6e5148996b1010f0248f5b122246e38c3aa0464


---

# <a name="enroll-devices-for-management-in-intune"></a>Cihazları yönetim için Intune’a kaydetme
Microsoft Intune ile mobil cihaz yönetimini (MDM) etkinleştirmek için Windows bilgisayarları da dahil olmak üzere cihazları kaydedebilirsiniz. Bu konuda, Intune yönetiminde mobil cihazları kaydetmek için farklı yollar açıklanmaktadır. Cihazları kaydetme biçiminiz, cihaz türüne, sahipliğine ve gereken yönetim düzeyine bağlıdır. "Kendi cihazını getir" (KCG) kaydı, kullanıcıların kendi kişisel telefonlarını, tabletlerini veya bilgisayarlarını kaydetmesine izin verir. Şirkete ait cihaz (COD) kaydı uzaktan silme, paylaşılan cihazlar veya bir cihaz için kullanıcı benzeşimi gibi yönetim senaryolarına olanak sağlar.

Şirket içinde veya bulutta barındırılan [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) kullanırsanız, kayda gerek kalmadan basit Intune yönetimini etkinleştirebilirsiniz. Windows bilgisayarları, [Intune istemci yazılımı](#manage-windows-pcs-with-intune) kullanılarak da yönetilebilir.

## <a name="overview-of-device-enrollment-methods"></a>Cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tabloda Intune'a kayıt yöntemleri ve her yöntem için desteklenen özellikler ile gereksinimler gösterilmektedir. Özellik ve gereksinimleri açıklamaları aşağıda verilmiştir.

- **Temizle** - Kullanıcıların cihazı kaydedebilmesi için temizleme yapılıp yapılmaması gerektiğini belirtir. "Temizleme" terimi, cihazın fabrika verilerine döndürülerek tüm verilerin silinmesini ifade eder. Daha fazla bilgi için bkz. [Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md).
- **Benzeşim** - Cihazlarla kullanıcıları ilişkilendirir. Mobil uygulama yönetimi (MAM) ve şirket verilerine koşullu erişim için gereklidir. Daha fazla bilgi için bkz. [Kullanıcı benzeşimi](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices).
- **Kilitle** - Kullanıcıların cihazı yönetimden çıkarmasını engeller. iOS cihazlarında Kilitle eylemi için Denetimli mod gerekir. Daha fazla bilgi için bkz. [Uzaktan kilitleme](retire-devices-from-microsoft-intune-management.md#block-access-a-device).

**iOS kayıt yöntemleri**

| **Yöntem** |  **Temizleme gerekli mi?** |    **Benzeşim**    |   **Kilitle** | **Ayrıntılar** |
|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |   Hayır | [Daha fazla bilgi](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  | [Daha fazla bilgi](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Evet |   İsteğe bağlı |  İsteğe bağlı|[Daha fazla bilgi](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Evet |   İsteğe bağlı |  Hayır| [Daha fazla bilgi](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Hayır |    Hayır  | Hayır|[Daha fazla bilgi](ios-direct-enrollment-in-microsoft-intune.md)|

**Windows kayıt yöntemleri**

| **Yöntem** |  **Temizleme gerekli mi?** |    **Benzeşim**    |   **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Evet|   Evet |   Hayır | [Daha fazla bilgi](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[Daha fazla bilgi](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Android kayıt yöntemleri**

| **Yöntem** |  **Temizleme gerekli mi?** |    **Benzeşim**    |   **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |   Hayır | [Daha fazla bilgi](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[Daha fazla bilgi](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Doğru yöntemi bulmanıza yardımcı olmak üzere bir dizi soru için bkz. [Cihazların nasıl kaydedileceği seçin](/intune/get-started/choose-how-to-enroll-devices1).

## <a name="byod"></a>KCG
“Kendi cihazını getir” kullanıcıları Şirket Portalı uygulamasını yükler ve cihazlarını kaydeder. Bu, kullanıcıların şirket ağına bağlanarak etki alanına veya Azure Active Directory’ye katılmasına olanak tanır. Çoğu platformda, birçok COD senaryosu için KCG’yi etkinleştirmeniz gerekir. Daha fazla bilgi için bkz. [Cihaz kaydı için önkoşullar](prerequisites-for-enrollment.md). ([Tabloya dön](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Şirkete ait cihazlar
Şirkete ait cihazlar (COD) Intune konsolu kullanılarak yönetilebilir. iOS cihazları, Apple tarafından sağlanan araçlar üzerinden doğrudan kaydedilebilir. Tüm cihaz türleri, cihaz kayıt yöneticisini kullanan bir yönetici ya da müdür tarafından kaydedilebilir. IMEI numaralı cihazlar da, COD senaryolarını etkinleştirmek için şirkete ait olarak tanımlanabilir ve etiketlenebilir.

Daha fazla bilgi için bkz. [Şirkete ait cihazları kaydedin](manage-corporate-owned-devices.md).

### <a name="dem"></a>DEM
Cihaz kayıt yöneticisi şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir Intune hesabıdır. Yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Apple Aygıt Kayıt Programı (DEP) yönetimi, “havadan” ilke oluşturmanıza ve DEP ile satın alınan ve yönetilen iOS cihazlara dağıtmanıza olanak sağlar. Cihaz, kullanıcı cihazı ilk açtığında ve iOS Ayarlama Yardımcısı’nı çalıştırdığında kaydedilir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Kilitli kayıt
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[DEP](ios-device-enrollment-program-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
USB bağlantılı, şirkete ait cihazlar Intune ilkesiyle hazırlanır. Ayarlama Yardımcısı ile kayıt için yönetici, Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. Yöneticinin her cihazı el ile kaydetmesi gerekir. Kullanıcılar cihazlarını alır ve Kurulum Yardımcısını çalıştırarak cihazlarını kaydederler. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[Apple Configurator ile Kurulum Yardımcısı kaydı](ios-setup-assistant-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
Doğrudan kayıt için yönetici, bir Intune ilkesi oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı, şirkete ait cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Yöneticinin her cihazı el ile kaydetmesi gerekir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, jailbreak algılamasını ya da mobil uygulama yönetimini destekleyemez. [Apple Configurator ile doğrudan kayıt](ios-direct-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync ve Intune ile mobil cihaz yönetimi
Kaydedilmemiş ancak Exchange ActiveSync’e (EAS) bağlanan mobil cihazlar, EAS MDM ilkesi kullanılarak Intune tarafından yönetilebilir. Intune, şirket içinde veya bulutta barındırılan EAS ile iletişim kurmak için bir Exchange Connector kullanır.

Daha fazla bilgi için bkz. [Exchange ActiveSync ve Intune ile mobil cihaz yönetimi](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Intune ile Windows bilgisayarı yönetimini etkinleştirme  
Windows bilgisayarları, Intune istemci yazılımı ile yönetmek için Microsoft Intune da kullanabilirsiniz. Intune istemcisiyle yönetilen bilgisayarlar aşağıdakileri yapabilir:

 - Yazılım ve donanım envanterlerini raporlama
 - Masaüstü uygulamaları yükleme (örneğin, .exe ve .msi dosyaları)
 - Güvenlik Duvarı ayarlarını yönet

Intune istemci yazılımı ile yönetilen bilgisayarlar tamamen silinemese de, seçmeli silme kullanılabilir. Intune yazılım istemcisi ile yönetilen bilgisayarlar, koşullu erişim, VPN ve Wi-Fi ayarları ya da sertifika ve e-posta yapılandırmalarının dağıtımı gibi birçok Intune yönetimi özelliğinden yararlanamaz.

Daha fazla bilgi için bkz. [Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Desteklenen cihaz platformları

Intune aşağıdaki cihaz platformlarını yönetebilir:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Sonraki adımlar
- [Cihaz kaydı için önkoşullar](prerequisites-for-enrollment.md)
- [Şirkete ait cihazları yönetme](manage-corporate-owned-devices.md)
- [Desteklenen mobil cihazlar ve bilgisayarlar](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Dec16_HO2-->

