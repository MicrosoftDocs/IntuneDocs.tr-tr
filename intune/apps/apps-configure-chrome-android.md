---
title: Intune kullanarak Android cihazları için Google Chrome 'U yapılandırma
titleSuffix: Microsoft Intune
description: Android cihazlar için Google Chrome ile Intune yapılandırma ilkelerini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b80b0dbd8128606db9220178baf0d05af1a3800
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72498788"
---
# <a name="configure-google-chrome-for-android-devices-using-intune"></a>Intune kullanarak Android cihazları için Google Chrome 'U yapılandırma 

Android cihazları için Google Chrome 'u yapılandırmak için bir Intune uygulama yapılandırma ilkesi kullanabilirsiniz. Uygulamanın ayarları otomatik olarak uygulanabilir. Örneğin, belirli bir yer işaretlerini ve engellemek veya izin vermek istediğiniz URL 'Leri ayarlayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- Kullanıcının Android kurumsal cihazının Intune 'A kayıtlı olması gerekir. Daha fazla bilgi için bkz. [Android kurumsal iş profili cihazlarının kaydını ayarlama](~/enrollment/android-work-profile-enroll.md).
- Google Chrome yönetilen bir Google Play uygulaması olarak eklenir. Yönetilen Google Play hakkında daha fazla bilgi için bkz. [Intune hesabınızı yönetilen Google Play hesabınıza bağlama](~/enrollment/connect-intune-android-enterprise.md).

## <a name="add-the-google-chrome-app-to-intune"></a>Google Chrome uygulamasını Intune 'a ekleme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde, **istemci uygulamaları** > **uygulama** >  ' ü seçin ve ardından **yönetilen Google Play** **uygulamasını ekleyin.**
3. Yönetilen Google Play gidin, **Google Chrome** ile arama yapın ve onaylayın.

    ![Google Chrome 'ı arama ve onaylama](~/apps/media/apps-configure-chrome-android/search.png)

4. Google Chrome 'ı gerekli uygulama türü olarak bir kullanıcı grubuna atayın. Cihaz Intune 'a kaydedildiğinde Google Chrome otomatik olarak dağıtılacaktır.

Intune 'a yönetilen Google Play uygulaması ekleme hakkında daha fazla bilgi için bkz. [yönetilen Google Play Mağazası uygulamaları](~/apps/apps-add-android-for-work.md#managed-google-play-store-apps).

## <a name="add-an-app-configuration-policy-for-managed-android-enterprise-devices"></a>Yönetilen Android Kurumsal cihazları için uygulama yapılandırma ilkesi ekleme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) bölmesinde, **uygulama yapılandırma ilkeleri** > **Ekle**' yi seçin.
2. İlke adınızı ekleyin, cihaz kayıt türü ve platform altında **Android** altında **yönetilen cihazlar** ' ı seçin.

    ![Google Chrome yapılandırma ilkesi Ekle](~/apps/media/apps-configure-chrome-android/add-policy.png)

3. **İlişkili uygulama** ' ya tıklayın ve **Google Chrome**' ı seçin.

    ![Ilişkili uygulama altında Google Chrome seçin](~/apps/media/apps-configure-chrome-android/associated-app.png)

4. Yapılandırma **ayarları**' na tıklayın, **yapılandırma tasarımcısını kullan**' ı seçin ve ardından **Ekle** ' ye tıklayarak yapılandırma anahtarlarını seçin.

    ![Yapılandırma tasarımcısını kullan Ekle](~/apps/media/apps-configure-chrome-android/configuration.png)

    Ortak ayarların örneği aşağıda verilmiştir:
    - **URL listesine erişimi engelleyin**: `["*"]`
    - **URL listesine erişime Izin ver**: `["baidu.com", "yahoo.com", "chrome://*"]`
    - **Yönetilen yer işaretleri**: `[{"toplevel_name": "My managed bookmarks folder"  },  {"url": "baidu.com",   "name": "Baidu"},  {"url": "youtube.com", "name": "Youtube"},  {"name": "Chrome links",  "children": [{"url": "chromium.org", "name": "Chromium"},    {"url": "dev.chromium.org", "name": "Chromium Developers"}]}]`
    - **Inbilito modu kullanılabilirliği**: `Incognito mode disabled`

    Yapılandırma ayarları, yapılandırma Tasarımcısı kullanılarak eklendikten sonra bir tabloda listelenecektir. 

    ![Ortak ayarlar](~/apps/media/apps-configure-chrome-android/common-settings.png)

    Yukarıdaki ayarlar yer işaretlerini oluşturur ve `baidu.com`, `yahoo.com` ve `chrome://` hariç tüm Web sitelerine erişime izin verir.

5. Yapılandırma ilkenizi Intune 'a eklemek için **Tamam** ve **Ekle** ' ye tıklayın.
6. Bu yapılandırma ilkesini bir kullanıcı grubuna atayın. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](~/apps/apps-deploy.md). 

## <a name="verify-the-device-settings"></a>Cihaz ayarlarını doğrulama

Android cihazı Android Enterprise 'a kaydedildikten sonra, Portföy simgesiyle yönetilen Google Chrome uygulaması otomatik olarak dağıtılacaktır.
 
   <img alt="Managed Google Chrome with the portfolio icon" src="~/apps/media/apps-configure-chrome-android/chrome-icon.png" width="350">

Google Chrome 'ı başlatın ve uygulanan ayarları görürsünüz.

   Leriniz<br>
   <img alt="Bookmarks" src="~/apps/media/apps-configure-chrome-android/bookmarks.png" width="350">

   Engellenen URL:<br>
   <img alt="Blocked URL" src="~/apps/media/apps-configure-chrome-android/blocked-url.png" width="350">

   URL 'ye izin ver:<br>
   <img alt="Allow URL" src="~/apps/media/apps-configure-chrome-android/allowed-url.png" width="350">

   Inbilito sekmesi:<br>
   <img alt="Incognito tab" src="~/apps/media/apps-configure-chrome-android/incognito-tab.png" width="350">

## <a name="troubleshooting"></a>Sorun giderme

1. İlke dağıtım durumunu izlemek için Intune portalını denetleyin.

    ![İlke dağıtım durumunu izleme](~/apps/media/apps-configure-chrome-android/monitor-status.png)

2. Google Chrome 'ı başlatın ve **Chrome://Policy**ziyaret edin. Ayarların başarıyla uygulandığını doğrulayabiliriz.

    ![Ayarların başarıyla uygulandığını doğrulayın](~/apps/media/apps-configure-chrome-android/confirm.png)

## <a name="additional-information"></a>Ek bilgiler

- [Yönetilen Android Kurumsal cihazları için uygulama yapılandırma ilkeleri ekleme](~/app-configuration-policies-use-android.md)
- [Chrome kurumsal ilke listesi](https://cloud.google.com/docs/chrome-enterprise/policies/)

## <a name="next-steps"></a>Sonraki adımlar

- Android kurumsal tam olarak yönetilen cihazlar hakkında daha fazla bilgi için bkz. [Intune 'Da Android Enterprise tam yönetme cihazlarını ayarlama](~/enrollment/android-fully-managed-enroll.md).