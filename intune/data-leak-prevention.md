---
title: "Yönetilmeyen cihazlarda veri sızıntılarını önleme"
description: "Cihazlardaki kurumsal verilere erişim izni verme ve verileri sızıntılardan koruma."
keywords: "veri koruma cihazı sızıntılara karşı korur O365 Office 365"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ae8702c51df1c3c2b8e6dd2a79bf4599e6b7677
ms.sourcegitcommit: 29ee35da2864b25f4432d2423b285014c77040af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2017
---
# <a name="prevent-data-leaks-on-non-managed-devices"></a>Yönetilmeyen cihazlarda veri sızıntılarını önleme

Office 365 tarafından barındırılan şirket verilerine erişim izni verirseniz kullanıcıların bilerek ya da bilmeyerek veri sızıntısına neden olmadan nasıl veri paylaşacağını ve kaydedeceğini denetleyebilirsiniz. Microsoft Intune, kullanıcılara ait cihazlarda şirket verilerinizin güvenliğini sağlamak için ayarlayabileceğiniz uygulama koruma ilkeleri sağlar. Cihazların Intune hizmetine kaydedilmesi gerekmez. 

Intune ile ayarlanan uygulama koruma ilkeleri, Microsoft olmayan bir cihaz yönetim çözümü ile yönetilen cihazlarda da çalışır. BT departmanı cihazlardaki kişisel verilere dokunmaz; yalnızca şirket verilerini yönetir. 

Windows, iOS veya Android çalıştıran cihazlarda şirket verilerini korumak için Office mobil uygulamalarına yönelik uygulama koruma ilkeleri ayarlayabilirsiniz. Bu ilkeler uygulama tabanlı PIN veya şirket veri şifrelemesi gibi ilkeler belirlemenize veya kullanıcıların yönetilen ve yönetilmeyen uygulamalar arasında kesme, kopyalama ve yapıştırma özelliklerini kullanmasını sınırlamak için daha gelişmiş ayarlar yapmanıza izin verir. Ayrıca, kullanıcıların cihazlarını kaydetmesi gerekmeden şirket verilerini uzaktan silebilirsiniz. 

Intune uygulama koruma ilkeleri, cihaz yönetiminden bağımsızdır. Uygulama koruma ilkeleri, Office mobil uygulamalarını gerek yönetilmeyen gerekse Intune tarafından yönetilen cihazların yanı sıra Microsoft olmayan MDM çözümleriyle yönetilen cihazlarda yönetmenize izin verir. 

## <a name="before-you-begin"></a>Başlamadan önce

Aşağıdaki koşulları yerine getirdiğinizde aşağıdaki eylem planı kullanılabilir:
* Şirketiniz buluta güvenli bir şekilde geçiş yapmaya hazırdır.
* Şirketiniz Office 365 Exchange Online, SharePoint Online, OneDrive İş veya Yammer kullanmaktadır.
* Şirketinizin Microsoft 365, Enterprise Mobility + Security (EMS) veya Azure Information Protection lisansları vardır.
* Şirketiniz, kullanıcıların şirkete ait veya kişisel Windows, iOS veya Android cihazlardan şirket verilerine erişmesine izin veriyordur. 
* Şirketiniz, kişisel cihazların bir cihaz yönetim hizmetine kaydedilmesini zorunlu kılmak istemiyordur. 

## <a name="action-plan"></a>Eylem planı

iOS ve Android cihazları için: 

1. [Uygulama koruma ilkelerinin](app-protection-policy.md) nasıl çalıştığını öğrenin.
2. Office mobil uygulamaları için nasıl [uygulama koruma ilkeleri oluşturulup dağıtılacağını](app-protection-policies.md) öğrenin. 
3. Oluşturup dağıttığınız [uygulama koruma ilkelerini izleyin](app-protection-policies-monitor.md). 

Windows 10 cihazları için: 

1. [Windows Bilgi Koruması’nın (WIP) nasıl çalıştığını](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) öğrenin. 
2. [Windows 10 için uygulama koruma ilkelerini](app-protection-policies-configure-windows-10.md) yapılandırmaya hazırlanın.
3. [Intune ile WIP uygulama koruma ilkeleri oluşturun ve dağıtın](windows-information-protection-policy-create.md).

## <a name="what-to-tell-employees-and-students"></a>Çalışanlara ve öğrencilere söylenecekler

Gerektiğinde, ek bilgi sağlamak için aşağıdaki bağlantıları paylaşın: 
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a>Sonraki adımlar

Bunu veya diğer EMS ya da Office 365 senaryolarını etkinleştirmek için yardıma mı ihtiyacınız var? Microsoft 365, Enterprise Mobility + Security veya Azure Active Directory Premium için en az 150 lisansınız varsa, [FastTrack avantajlarınızdan](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program) yararlanın. 