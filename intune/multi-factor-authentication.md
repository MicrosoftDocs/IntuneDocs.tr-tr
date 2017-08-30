---
title: "Intune cihaz kaydı için çok faktörlü kimlik doğrulaması"
titleSuffix: Intune on Azure
description: "Azure AD’de cihaz kaydı için çok faktörlü kimlik doğrulaması isteme."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: 4789f94d06f61219dea3faa64a4ed0c59afcd56b
ms.sourcegitcommit: af013af8d9a63c9aa16e5e9eddf38ad9c5a77898
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Intune cihaz kayıtları için çok faktörlü kimlik doğrulaması

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak üzere cihaz kaydı için Azure Active Directory (AD) çok faktörlü kimlik doğrulamasını (MFA) kullanabilir.

MFA, aşağıdaki doğrulama yöntemlerinden herhangi ikisini veya daha fazlasını zorunlu tutar:

- Bildiğiniz bir şey (genellikle parola veya PIN).
- Sahip olduğunu bir şey (telefon gibi kopyalaması kolay olmayan güvenilir bir cihaz).
- Sahip olduğunuz bir özellik (parmak izi gibi biyometrik bilgiler).

MFA; iOS, Android, Windows 8.1 veya üzeri, Windows Phone 8.1 ya da Windows 10 Mobile veya üzeri cihazlar için desteklenir.

MFA’yı etkinleştirdiğinizde, son kullanıcıların bir cihazı kaydetmek için kimlik bilgilerini iki şekilde sağlamaları gerekir.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune'u cihaz kaydında çok faktörlü kimlik doğrulama isteyecek şekilde yapılandırma

Bir cihaz kaydedildiğinde MFA istemek için şu adımları izleyin:

>[!Important]
>Microsoft Intune kaydı için **Cihaz tabanlı erişim kuralları** yapılandırmayın.

1. Kimlik bilgilerinizle [Microsoft Azure portalında](https://portal.azure.com) oturum açın.
2. Portalda **Azure Active Directory**’yi seçin.
2. **Azure Active Directory**’de **Yönet** > **Kuruluş uygulamaları**’nı seçin.
3. **Kuruluş uygulamaları**’nda **Yönet** > **Tüm uygulamalar**’ı seçin. Yönettiğiniz tüm Azure uygulamalarının listesini görürsünüz.
3. Listeden **Microsoft Intune kaydı**’nı seçin.
4. **Microsoft Intune kaydı**’nda **Güvenlik** > **Koşullu erişim**’i seçin.
5. **Yeni ilke**’yi seçin.
6. **Yeni** ilkede, ilke için açıklayıcı bir ad yazın.
7. **Atamalar** kısmında **Kullanıcılar ve gruplar**’ı seçin.
8. **Kullanıcılar ve gruplar**’da, ilkeyi alacak kullanıcı ve grupları seçin ve daha sonra **Bitti**’yi seçin.
9. **Atamalar** kısmında **Bulut uygulamaları**’nı seçin.
10. **Bulut uygulamaları**‘nın **Ekleme** sekmesinde, **Uygulama seç**’i, daha sonra **Seçin** > **Microsoft Intune Kaydı**’nı ve son olarak **Bitti**’yi seçin.
11. **Atamalar** kısmında **Koşullar**’ı seçin.
12. **Koşullar**’da MFA için hiçbir ayar yapılandırmanız gerekmez.
13. **Erişim denetimleri** kısmında **Ver**’i seçin.
14. **Ver** kısmında **Erişim ver**’i ve daha sonra **Çok faktörlü kimlik doğrulamasını gerektir**’i seçin.
    **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçmeyin çünkü bir cihaz kaydedilene kadar cihazın uyumluluğu değerlendirilemez.
15. **Seçin** öğesini belirleyin.
16. **Yeni ilke**’de **İlkeyi etkinleştir** > **Açık**’ı ve daha sonra **Oluştur**’u seçin.



## <a name="next-steps"></a>Sonraki adımlar

Artık kullanıcılar bir cihaz kaydettiğinde; PIN, telefon veya biyometrik bilgiler gibi ikinci bir kimlik tanımlama şekli ile kimlik doğrulamaları gerekecektir.