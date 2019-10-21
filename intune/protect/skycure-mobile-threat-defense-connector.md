---
title: Microsoft Intune ile Symantec bağlayıcısı
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Symantec Endpoint Protection Mobile’ı Intune ile tümleştirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/09/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be8fbb0bd96891eb3af3157deddfc325ebc5f2b9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508933"
---
# <a name="symantec-endpoint-protection-mobile-connector"></a>Symantec Endpoint Protection Mobile bağlayıcısı

Microsoft Intune ile tümleştirilen bir mobil tehdit savunması çözümü olan Symantec Endpoint Protection Mobile (SEP Mobile) tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, SEP Mobile çalıştıran cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:

- Fiziksel savunma

- Ağ savunması

- Uygulama savunması

- Güvenlik açıkları savunması

Intune cihaz uyumluluk ilkeleri aracılığıyla merkezi mobil risk değerlendirmesi etkinleştirebilir ve ardından, algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişimine izin vermek veya erişimi engellemek için koşullu erişim ilkeleri kullanabilirsiniz.

## <a name="how-do-intune-and-sep-mobile-help-protect-your-company-resources"></a>Intune ve SEP Mobile şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android veya iOS için SEP Mobile uygulaması dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini (varsa) yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için bunları Symantec bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, SEP Mobile risk değerlendirmesini temel alan bir SEP Mobile’a yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihaz uyumsuz bulunursa Exchange Online ve SharePoint Online gibi kaynaklara erişimi engellenir. Engellenen cihazlardaki kullanıcılar SEP Mobile uygulamasından sorunu çözmek ve şirket kaynaklarına yeniden erişim kazanmak için yol gösteren yönergeler alır.

Intune, SEP Mobile ile iki tümleştirme modunu destekler:

- **Temel kurulum**, Intune’daki cihazlar için SEP Mobile görünürlüğüne olanak tanıyan salt okunur modudur.

- **Tam tümleştirme**, SEP Mobile’ın Intune’a cihazın risk ve güvenlik olayı ayrıntılarını raporlamasına olanak tanır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Burada sık karşılaşılan bazı senaryolar verilmiştir:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazları engelleyebilirsiniz:

- Şirket e-postasına bağlanma

- OneDrive İş uygulaması ile şirket dosyalarını eşitleme

- Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Algılanan kötü amaçlı uygulamaların kavramsal görüntüsü](./media/skycure-mobile-threat-defense-connector/symantec-arch-1.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandıktan sonra düzeltmeye verilen erişim görüntüsü](./media/skycure-mobile-threat-defense-connector/symantec-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Ağda **bağlantıyı izinsiz izleme** gibi tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/skycure-mobile-threat-defense-connector/symantec-arch-3.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](./media/skycure-mobile-threat-defense-connector/symantec-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Ağda **Bağlantıyı izinsiz izleme** gibi tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/skycure-mobile-threat-defense-connector/symantec-arch-5.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](./media/skycure-mobile-threat-defense-connector/symantec-arch-6.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

- **Android 4.1 ve üzeri**

- **iOS 8 ve üzeri**

## <a name="pre-requisites"></a>Ön koşullar

- Azure Active Directory Premium

- Microsoft Intune aboneliği

- Symantec Endpoint Protection Mobile aboneliği

Daha fazla bilgi için [Symantec web sitesini](https://www.skycure.com/skycure-microsoft-integration/) gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar

Burada, Intune’u SEP Mobile ile tümleştirme işlemini tamamlamak için gereken adımlar verilmiştir:

- [Intune ile SEP Mobile tümleştirmesini ayarlama](skycure-mtd-connector-integration.md)

- [ uygulamaları, Microsoft Authenticator ve iOS uygulama yapılandırma ilkesi ekleme ve atama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Intune ile SEP Mobile cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Intune’da SEP Mobile MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)