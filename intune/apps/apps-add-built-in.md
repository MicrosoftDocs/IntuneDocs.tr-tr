---
title: Microsoft Intune kullanarak mobil cihazlara yerleşik uygulamalar yükleme
titleSuffix: ''
description: Mobil cihazlarda yerleşik uygulamaları yüklemeyi kolaylaştırmak için Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e494f154c34a4e4866b9eb6980c713da8a7e23b6
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507327"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Microsoft Intune’a yerleşik uygulama ekleme

*Yerleşik* uygulama türü, iOS ve Android cihazlara Office 365 uygulamaları gibi seçkin yönetilen uygulamaları atamanızı kolaylaştırır. Bu uygulama türüne belirli uygulamaları atayabilirsiniz; örneğin Excel, OneDrive, Outlook, Skype ve diğerleri. Bir uygulamayı ekledikten sonra uygulama türü, *Yerleşik iOS uygulaması* veya *Yerleşik Android uygulaması* olarak görüntülenir. Yerleşik uygulama türünü kullanarak bu uygulamalardan hangilerini cihaz kullanıcılarına yayımlayacağınızı seçebilirsiniz.

Intune konsolunun önceki sürümlerinde Intune, Outlook ve OneDrive gibi varsayılan olarak yönetilen birkaç Office 365 uygulaması sağlar. Bu yönetilen uygulamalar için uygulama türü *Yönetilen iOS Mağaza Uygulaması* veya *Yönetilen Android Uygulaması* olarak etiketlenmiştir. Bu uygulama türlerini kullanmak yerine yerleşik uygulama türünü kullanmanızı öneririz. Yerleşik uygulama türünü kullanarak Office 365 uygulamalarını düzenleme ve silme konusunda daha fazla esneklik kazanırsınız.

>[!NOTE]
>*Yönetilen iOS Mağaza* veya *Yönetilen Android Uygulaması* olarak etiketli varsayılan Office 365 uygulamaları, tüm atamalar silindiğinde uygulama listesinden kaldırılır.

## <a name="add-a-built-in-app"></a>Yerleşik uygulama ekleme

Microsoft Intune’da mümkün olan uygulamalara yerleşik uygulama eklemek için şunları yapın:
1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçerek Microsoft Intune bölmesini görüntüleyin.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** bölmesinde **Yönet** altında **Uygulamalar**’ı seçin.
5. **Ekle**’yi seçin.
6. Uygulama **Ekle** bölmesindeki **Uygulama türü** listesinde **Yerleşik uygulama**’yı seçin.
7. **Uygulama seç**’e tıklayın.
8. **Yerleşik uygulama** bölmesinde dahil etmek istediğiniz uygulamaları seçin.
9. **Uygulama ekle** bölmesinde **Ekle**’yi seçin.


## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma

Yerleşik uygulama hakkındaki bilgileri değiştirebilirsiniz. Bu bilgiler, uygulamayı Intune’da bulmanıza yardımcı olur ve kullanıcıların uygulamayı Şirket Portalı’nda bulması kolaylaşır.
1. **İstemci uygulamalar - Uygulamalar** bölmesinde değiştirmek istediğiniz yerleşik uygulamayı seçin.  
    Yerleşik uygulamaya ait bir bölme görüntülenecektir.
2. **Yönet** altında **Özellikler** seçeneğine tıklayın.
3. Yerleşik uygulama bilgilerini değiştirmek için **Yapılandır** seçeneğine tıklayın.
4. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri değiştirebilirsiniz:
    - **Ad**: Yerleşik uygulamanın Şirket Portalı’nda görüntülenen adını girin. Kullandığınız tüm adların benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. 
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden birini seçin. Bu seçeneği ayarladığınızda, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin (örneğin *İK departmanı*).
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Simge Yükle**: Kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenecek bir simge yükleyin.
4. **Tamam**’ı seçin.
5. **Özellikler** bölmesinde **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Artık seçtiğiniz gruplara uygulamaları atayabilirsiniz. Daha fazla bilgi için bkz. [Uygulamaları gruplara atama](apps-deploy.md).