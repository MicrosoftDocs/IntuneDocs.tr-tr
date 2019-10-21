---
title: Cihaz yönetimi olmadan Exchange
titleSuffix: Microsoft Intune
description: Microsoft Intune'u kullanarak, bir cihaz yönetim sistemi ayarlamadan çalışanlara Office 365 Exchange Online e-postalarına erişim verin.
keywords: Office 365 Exchange e-posta erişimi
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/31/2017
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.topic: archived
ms.technology: ''
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ffcc4a7e48064e6a458126667cf6ab2c4e75777
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502264"
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Cihaz yönetimi gerektirmeden Office 365 Exchange Online’ı koruma

Bir cihaz yönetim sistemi ayarlama zahmetine katlanmaksızın çalışanların e-posta adreslerine erişimini sağlamak istiyorsanız, bu mümkündür. Intune aracılığıyla Office 365 Exchange Online’a erişim verebilirsiniz. Gerekli adımları tamamlamak için Microsoft 365 veya Azure Active Directory (premium) ve Intune lisanslarınızın olduğunu onaylayın. Çalışanların [desteklenen bir iOS veya Android cihazı](../fundamentals/supported-devices-browsers.md) olmalıdır. 

Bir cihaz yönetim sistemi ayarlamak istiyorsanız, bu da mümkündür. Bu tür bir uygulama koruması, cihaz yönetiminden bağımsız olarak çalışır. 

## <a name="action-plan"></a>Eylem planı

1. [Koşullu erişim hakkında bilgi edinin](conditional-access.md). 
2. [Uygulama tabanlı koşullu erişim hakkında bilgi edinin](app-based-conditional-access-intune.md).
3. [Exchange Online için uygulama tabanlı koşullu erişim Ilkeleri ayarlayın](app-based-conditional-access-intune-create.md).
4. [Yönetilemeyen uygulamaları engelleyin](app-modern-authentication-block.md), özellikle Azure Active Directory Authentication Library (ADAL) kullanmayanları.
5. Seçim [SharePoint Online için uygulama tabanlı koşullu erişim Ilkeleri ayarlayın](app-based-conditional-access-intune-create.md). Bu ilkeler, yönetilemeyen ve güvende olmayan uygulamalardan şirket verilerinize erişimi engeller. Ayrıca SharePoint Mobile’dan erişimi de sınırlar. 

## <a name="what-to-tell-employees-and-students"></a>Çalışanlara ve öğrencilere söylenecekler

* Çalışanlarınızdan ve öğrencilerinizden, iOS için Apple App Store veya Android için Google Play Store’dan Microsoft Outlook veya Microsoft SharePoint’i yüklemelerini isteyin. 
* Modern kimlik doğrulaması kullanmayan uygulamalara erişimi engellerseniz, çalışanlarınızı ve öğrencilerinizi bu kısıtlamadan haberdar edin. 

## <a name="next-steps"></a>Sonraki adımlar

Şirket verilerinin güvenliğini artırmak için uygulama tabanlı koşullu erişim kullandınız. Sonraki adımların parçası olarak, şirket verilerinizin güvenliğini arttırmak için aşağıdaki gibi diğer yollar hakkında bilgi edinebilirsiniz: 

* [Active Directory ve Azure Active Directory cihaz uyumluluğu, cihaz riski, konum ve Kullanıcı özniteliklerine dayalı koşullu erişimi](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)ayarlama.  
* Kasıtlı veya kasıtsız veri sızıntılarına karşı şirketinizi korumaya yardımcı olmak adına uygulama koruma ilkeleri ayarlamak. 
* Şirket verilerini ağınız dışında da korumak adına Azure Information Protection’dan yararlanmak. 

Bunu veya diğer EMS ya da Office 365 senaryolarını etkinleştirmek için yardıma mı ihtiyacınız var? Microsoft 365, Enterprise Mobility + Security veya Azure Active Directory Premium için en az 150 lisansınız varsa, [FastTrack avantajlarınızdan](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program) yararlanın. 