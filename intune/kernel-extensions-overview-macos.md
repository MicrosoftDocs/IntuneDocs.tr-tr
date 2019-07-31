---
title: Microsoft Intune-Azure ile macOS çekirdek uzantıları cihaz profili oluşturma | Microsoft Docs
titleSuffix: ''
description: Bir macOS cihaz profili ekleyin veya oluşturun ve ardından Kullanıcı geçersiz kılması, takım tanımlayıcısı eklemek ve Microsoft Intune bir paket ve takım tanımlayıcısı sağlamak için çekirdek uzantıları yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eca4692189af9272d3d1fc427b4eba638d8b5b27
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882978"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Intune 'A macOS çekirdek uzantıları ekleme

MacOS cihazlarında, çekirdek düzeyinde özellikler ekleyebilirsiniz. Bu özellikler, işletim sisteminin normal programların erişememe bölümlerine erişir. Kuruluşunuz, bir uygulamada ve bir cihaz özelliğinde bulunmayan belirli gereksinimlere veya gereksinimlere sahip olabilir. 

Cihazlarınızda her zaman yüklenmesine izin verilen çekirdek uzantıları eklemek için, Microsoft Intune ' de "çekirdek uzantıları" (KEXT) ekleyin ve ardından bu uzantıları cihazlarınıza dağıtın.

Örneğin, cihazınızı kötü amaçlı içeriğe karşı tarayan bir virüs tarama programı vardır. Bu virüs tarama programının çekirdek uzantısını Intune 'da izin verilen bir çekirdek uzantısı olarak ekleyebilirsiniz. Ardından, uzantıyı macOS cihazlarınıza "atayın".

Yöneticiler, bu özellik ile kullanıcıların çekirdek uzantılarını geçersiz kılmasına, takım tanımlayıcıları eklemesine ve Intune 'A belirli çekirdek uzantıları eklemesine izin verebilir.

Bu özellik şu platformlarda geçerlidir:

- macOS 10.13.2 ve üzeri

Bu özelliği kullanmak için cihazların şu olması gerekir:

- Apple 'ın Aygıt Kayıt Programı (DEP) kullanılarak Intune 'A kayıtlı. [MacOS cihazlarının otomatik olarak kaydedilmesi](device-enrollment-program-enroll-macos.md) daha fazla bilgi içerir.

  OR

- "Kullanıcı onaylı kayıt" (Apple 'ın dönemi) ile Intune 'A kaydolmuş. [MacOS High Sierra içindeki çekirdek uzantılarında değişiklikler Için hazırlanma](https://support.apple.com/en-us/HT208019) (Apple 'ın Web sitesini açar) daha fazla bilgi içerir.

Intune, kuruluşunuzun ihtiyaçlarına göre bu ayarları oluşturmak ve özelleştirmek için "yapılandırma profillerini" kullanır. Bu özellikleri bir profile ekledikten sonra, profili kuruluşunuzdaki macOS cihazlarına gönderebilir veya dağıtabilirsiniz.

Bu makalede, Intune 'da çekirdek uzantıları kullanılarak bir cihaz yapılandırma profili oluşturma konusu gösterilmektedir.

> [!TIP]
> Çekirdek uzantıları hakkında daha fazla bilgi için bkz. [çekirdek uzantısına genel bakış](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (Apple 'ın Web sitesini açar).

## <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- İmzasız eski çekirdek uzantıları eklenebilir.
- Çekirdek uzantısının doğru takım tanımlayıcısını ve paket KIMLIĞINI girdiğinizden emin olun. Intune girdiğiniz değerleri doğrulamaz. Yanlış bilgi girerseniz, uzantı cihazda çalışmaz.

> [!NOTE]
> Apple tüm yazılımlar için imzalama ve imza hakkında bilgi yayımladı. MacOS 10.14.5 ve daha yeni sürümlerde, Intune aracılığıyla dağıtılan çekirdek uzantıları Apple 'ın önemli ilkesini karşılamak zorunda kalmaz.
>
> Bu ilke ve tüm güncelleştirmeler veya değişiklikler hakkında bilgi için aşağıdaki kaynaklara bakın:
>
> - [Dağıtıma başlamadan önce uygulamanızı önemli](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) bir hale getirme (Apple 'ın Web sitesini açar) 
> - [MacOS High Sierra içindeki çekirdek uzantılarında değişiklikler Için hazırlanma](https://support.apple.com/en-us/HT208019) (Apple 'ın Web sitesini açar)

## <a name="create-the-profile"></a>Profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **MacOS** seçin
    - **Profil türü**: **Uzantıları**seçin.
    - **Ayarları**: Yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yapacaklarınız için, bkz.:

        - [macOS](kernel-extensions-settings-macos.md)

4. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profil oluşturulur ve listede gösterilir. [Profili atayıp](device-profile-assign.md) [durumunu izlemeyi](device-profile-monitor.md)unutmayın.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak için hazırlanın. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).