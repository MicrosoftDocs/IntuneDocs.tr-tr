---
title: "Windows Bilgi Koruması’nı yapılandırma - Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows Bilgi Koruması’nı yönetmek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: fc58b07fe33ff6223dfa182fb4f81f15379295fa
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Microsoft Intune’da Windows Bilgi Koruması’nı yapılandırma

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Kuruluşta çalışanlara ait cihazlar arttıkça, kuruluşun denetimi dışında kalan e-posta, sosyal medya ve genel bulut gibi uygulamalar ve hizmetler aracılığıyla yanlışlıkla veri sızıntıları yaşama riski de artar. Örneğin, bir çalışan en son mühendislik çalışmalarının resimlerini kişisel bir e-posta hesabından gönderebilir, ürün bilgilerini bir tweet’e kopyalayıp yapıştırabilir veya hazırlanması devam eden satış raporunu genel bulut depolama alanına kaydedebilir.

**Windows Bilgi Koruması**, çalışanın deneyimine başka hiçbir şekilde müdahale etmeden bu olası veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan, kuruluşa ait cihazlarda ve çalışanların iş yerine getirdiği kişisel cihazlarda yanlışlıkla ortaya çıkabilecek veri sızıntılarına karşı kurumsal uygulamaları ve verileri korumaya da yardımcı olur.

Bu Intune ilkesi, Windows Information Protection tarafından korunan uygulamalar listesini, kurumsal ağ konumlarını, koruma düzeyini ve şifreleme ayarlarını yönetir.

>[!NOTE]
> Windows 10 Şirket Portalı uygulamasını Windows Bilgi Koruması ile kullanmak için Şirket Portalı uygulamasını Windows Bilgi Koruması’nın **Muaf** modu altına eklemeniz gerekir. 

### <a name="next-steps"></a>Sonraki adımlar
Daha fazla bilgi için bkz. [Windows Bilgi Koruması’nı kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
