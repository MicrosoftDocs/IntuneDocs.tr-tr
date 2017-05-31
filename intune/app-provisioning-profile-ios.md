---
title: "Uygulama sağlama profilleri | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profilini önceden atamak için araçlar verir."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 966c097280ebebac68749e71c20381ee816360da
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profillerini kullanma

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="introduction"></a>Giriş

iPhone ve iPad’lere atanan Apple iOS iş kolu uygulamaları, dahili bir sağlama profili ve sertifikayla imzalanan bir kodla oluşturulur. Uygulama çalıştırıldığında iOS, uygulamanın bütünlüğünü onaylar ve sağlama profili tarafından tanımlanan ilkeleri zorunlu kılar. Aşağıdaki doğrulamalar yapılır:

- **Yükleme dosyası bütünlüğü** - iOS, uygulama ayrıntılarını kurumsal imzalama sertifikasının ortak anahtarıyla karşılaştırır. Bunlar farklıysa, uygulamanın içeriği değişmiş olabilir ve uygulamanın çalıştırılmasına izin verilmez.
- **Özellikleri zorunlu kılma** - iOS, uygulama yükleme (.ipa) dosyasındaki kurumsal sağlama profilinden (bireysel geliştirici sağlama profilleri değil) uygulama özelliklerini zorunlu kılma girişiminde bulunur.


Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi genellikle 3 yıldır. Öte yandan, bir yıl sonra sağlama profilinin süresi dolar. Sertifika hala geçerli durumdayken, Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profilini önceden atamak için araçlar verir.
Sertifikanın süresi dolduktan sonra, uygulamayı yeni bir sertifikayla tekrar imzalamanız ve yeni sertifikanın anahtarıyla yeni bir sağlama profili eklemeniz gerekir.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>iOS mobil uygulama sağlama profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
1.  **Mobil uygulamalar** iş yükünde **Yönet** > **iOS sağlama profilleri** seçeneğini belirleyin.
2.  Profil listesi dikey penceresinde **Profil oluştur**’u seçin.
3. **Profil oluştur** dikey penceresinde aşağıdakileri değerleri yapılandırın:
    - **Ad** - Bu mobil sağlama profiline bir ad verin.
    - **Açıklama** - İsteğe bağlı olarak, ilke için bir açıklama sağlayın.
    - **Profili dosyasını karşıya yükleme** - **İçeri Aktar**’ı seçin, sonra da Apple Developer web sitesinden indirdiğiniz bir Apple Mobil Yapılandırma Profili dosyasını (uzantısı **.mobileprovision** olmalı) seçin.
4. İşiniz bittiğinde **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

Profili gerekli iOS cihazlara atayın. Daha fazla bilgi için [Cihaz profillerini atama](device-profile-assign.md) kısmındaki adımları kullanın.
