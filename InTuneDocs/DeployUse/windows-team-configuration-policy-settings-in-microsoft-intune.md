---
# required metadata

title: Microsoft Intune’da Windows Team yapılandırma ilkesi ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Windows Team yapılandırma ilkesi ayarları
Microsoft Surface Hub gibi kayıtlı Windows 10 Team cihazlarının ayarlarını yapılandırmak için Microsoft Intune **Windows 10 Team genel yapılandırma ilkesini** kullanın.

|Ayar adı|Ayrıntılar|
|----------------|-----------|
|**Odada birisi olduğunda ekranın otomatik olarak uyanmasına izin ver**|Algılayıcı, odada birisini algıladığında cihazın otomatik olarak uyanmasına izin verir.|
|**Kablosuz projeksiyon için PIN iste**|Cihazın kablosuz projeksiyon özelliklerini kullanabilmek için PIN girmenin gerekli olup olmadığını belirtir.|
|**Cihaz güncelleştirmeleri için bir bakım penceresi ayarlama**|Cihazda güncelleştirme gerçekleştirilebildiği zaman pencereyi yapılandırır. Pencerenin başlangıç saatini ve süresini (1-5 saat) yapılandırabilirsiniz.|
|**Azure Operasyonel Öngörüler'i etkinleştirme**|Microsoft Operations Manager’ın bir parçası olan Azure Operasyonel Öngörüler, Windows 10 Team cihazlarından günlük dosyası verilerini toplar, depolar ve analiz eder.<br /><br />Azure Operasyonel Öngörüler'e bağlanmak için **Çalışma Alanı Kimliği** ve **Çalışma Alanı Anahtarı** belirtmeniz gerekir..|
|**Miracast kablosuz projektörü etkinleştirme**|Windows 10 Team cihazlarının yansıtmak için Miracast özellikli cihazları kullanmasına izin vermek istiyorsanız bu seçeneği etkinleştirin.<br /><br />Bu seçeneği etkinleştirirseniz **Miracast kanalı seçin** menüsünden içeriği yansıtmak için kullanılan Miracast kanalını seçin.|
|**Karşılama ekranında görüntülenen toplantı bilgilerini seçin**|Bu seçeneği etkinleştirirseniz, **Hoş Geldiniz** ekranının **Toplantılar** kutucuğunda gösterilecek bilgileri seçebilirsiniz. Şunları yapabilirsiniz:<br /><br />-   **Yalnızca düzenleyeni ve saati göster**<br />-   **Düzenleyeni, saati ve konuyu göster (özel toplantılar için konu gizlidir)**|
|**Kilit ekranı arka plan görüntüsü URL'si**|Windows 10 Team cihazlarının **Hoş Geldiniz** ekranında belirttiğiniz URL’den özel bir arka plan görüntülemek için bu ayarı etkinleştirin.<br /><br />Resim PNG biçiminde olmalı ve URL **https://** ile başlamalıdır..|


### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->

