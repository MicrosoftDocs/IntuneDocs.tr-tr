---
title: "Windows Team yapılandırma ilkesi ayarları | Microsoft Docs"
description: "Microsoft Surface Hub gibi kayıtlı Windows 10 Team cihazlarının ayarlarını yapılandırmak için Microsoft Intune **Windows 10 Team genel yapılandırma ilkesini** kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 136f83a7340424b420e4a487a0758992a802ece3


---

# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows Team yapılandırma ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Surface Hub gibi kayıtlı Windows 10 Team cihazlarının ayarlarını yapılandırmak için Microsoft Intune **Windows 10 Team genel yapılandırma ilkesini** kullanın.

|Ayar adı|Ayrıntılar|
|----------------|-----------|
|**Odada birisi olduğunda ekranın otomatik olarak uyanmasına izin ver**|Algılayıcı, odada birisini algıladığında cihazın otomatik olarak uyanmasına izin verir.|
|**Kablosuz projeksiyon için PIN iste**|Cihazın kablosuz projeksiyon özelliklerini kullanabilmek için PIN girmenin gerekli olup olmadığını belirtir.|
|**Cihaz güncelleştirmeleri için bir bakım penceresi ayarla**|Cihazda güncelleştirme gerçekleştirilebildiği zaman pencereyi yapılandırır. Pencerenin başlangıç saatini ve süresini (1-5 saat) yapılandırabilirsiniz.|
|**Azure Operasyonel Öngörüler'i etkinleştir**|Microsoft Operations Manager’ın bir parçası olan Azure Operasyonel Öngörüler, Windows 10 Team cihazlarından günlük dosyası verilerini toplar, depolar ve analiz eder.<br /><br />Azure Operasyonel Öngörüler'e bağlanmak için bir **Çalışma Alanı Kimliği** ve bir **Çalışma Alanı Anahtarı** belirtmeniz gerekir.|
|**Miracast kablosuz projektörü etkinleştir**|Windows 10 Team cihazlarının yansıtmak için Miracast özellikli cihazları kullanmasına izin vermek istiyorsanız bu seçeneği etkinleştirin.<br /><br />Bu seçeneği etkinleştirirseniz **Miracast kanalı seçin** menüsünden içeriği yansıtmak için kullanılan Miracast kanalını seçin.|
|**Karşılama ekranında görüntülenen toplantı bilgilerini seçin**|Bu seçeneği etkinleştirirseniz, **Hoş Geldiniz** ekranının **Toplantılar** kutucuğunda gösterilecek bilgileri seçebilirsiniz. Şunları yapabilirsiniz:<br /><br />-   **Yalnızca düzenleyeni ve saati göster**<br />-   **Düzenleyeni, saati ve konuyu göster (özel toplantılar için konu gizlidir)**|
|**Kilit ekranı arka plan görüntüsü URL'si**|Windows 10 Team cihazlarının **Hoş Geldiniz** ekranında belirttiğiniz URL’den özel bir arka plan görüntülemek için bu ayarı etkinleştirin.<br /><br />Görüntü PNG biçiminde olmalıdır ve URL **https://** ile başlamalıdır.|


### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Dec16_HO5-->

