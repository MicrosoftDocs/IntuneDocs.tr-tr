---
title: Windows bilgisayarları koruma ilkeleri
titlesuffix: Microsoft Intune
description: Intune istemci yazılımı tarafından yönetilen Windows bilgisayarlarının güvenliğini sağlamaya yardımcı olmak için bu ilkeleri kullanın.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 10f19c0b9823adcd40ce38bae1c6cbaacd59c0db
ms.sourcegitcommit: 116be0eaa44fd5518ff34780d39569224ef4746b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36310496"
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a>Intune istemci yazılımını çalıştıran Windows bilgisayarlarını korumaya yardımcı olmak için ilkeleri kullanma

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Microsoft Intune, [Intune istemci yazılımı](manage-windows-pcs-with-microsoft-intune.md) tarafından yönetilen Windows bilgisayarlarının güvenliğini sağlamaya yardımcı olmak için kullanabileceğiniz üç ilke sunar.


## <a name="software-updates"></a>Yazılım güncelleştirmeleri

Intune, Microsoft’tan veya diğer şirketlerden önemli yazılım güncelleştirmeleri kullanıma sunulduğunda bunu size bildirerek, [yönettiğiniz Windows bilgisayarlarının güncelliğini korumanızı](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) kolaylaştırır. Bu güncelleştirmeleri onaylayabilir veya reddedebilirsiniz. Onaylanan güncelleştirmeler tüm uygun bilgisayarlara otomatik olarak yüklenir.

## <a name="windows-firewall"></a>Windows Güvenlik Duvarı

Windows Güvenlik Duvarı, bilgisayar korsanlarını, kötü amaçlı yazılımları ve diğer tehditleri Windows bilgisayarlarından uzak tutmaya yardımcı olur. Intune sayesinde, yönettiğiniz tüm bilgisayarlarda [Windows Güvenlik Duvarı için ayar ve özellikleri yönetme](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) imkanına sahip olursunuz.

## <a name="endpoint-protection"></a>Uç Nokta Koruma

Bir BT yöneticisi olarak en önemli önceliklerinizden biri, [yönettiğiniz Windows bilgisayarlarına kötü amaçlı yazılım ve virüs bulaşmasını engellemektir](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md). Intune, Endpoint Protection ile tümleşik çalışarak kötü amaçlı yazılım tehditlerine karşı gerçek zamanlı koruma sağlar, kötü amaçlı yazılım tanımlarını güncel tutar ve bilgisayarları otomatik olarak tarar. Endpoint Protection, kötü amaçlı yazılım saldırılarını yönetmek ve izlemek için yardımcı araçlar da sağlar.



### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)