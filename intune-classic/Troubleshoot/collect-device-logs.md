---
title: "Cihaz günlüklerini toplama| Microsoft Docs"
description: "Yönetilen cihazlarınızdan günlük toplamayı öğrenin."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f75719a02e37f6285fb1d7c5de32bb7eb4b3a1ed
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="device-logs"></a>Cihaz günlükleri

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Sorun giderme çalışmalarınız kapsamında, kullanıcı cihazlarından günlükleri toplamak isteyebilirsiniz. Günlükleri toplama yönergeleri burada açıklanmaktadır. Normalde cihaza erişmeniz, bu günlükleri almanız veya kullanıcıdan günlükleri toplayıp size göndermesini istemeniz gerekebilir.

### <a name="android-logs"></a>Android günlükleri
Android günlükleri *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files* yolunda yer alır.

Bazen, özellikle de yeni Android cihazlarında dosyalar görünmez. Bu durumda kullanıcılarınıza Android için Şirket Portalı'nı açtırın. Sonra **Ayarlar**>**Günlükleri Kopyala**'yı seçmeleri ve cihazlarını yeniden başlatmaları gerekir.

Kullanıcılarınızın veri günlüklerini size nasıl gönderebileceği hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [BT yöneticinizin cihaz sorunlarını düzeltmesine yardımcı olmak için Ayrıntılı Günlük Kaydı'nı kullanın](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Kullanıcıların size tüm veri günlüklerini otomatik gönderen Ayrıntılı Günlük Kaydı'nı nasıl açacağını anlatır. Ayrıntılı Günlük Kaydı, varsayılan olarak açıktır.

- [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [Tanılama veri günlüklerini USB kablosu kullanarak BT yöneticinize gönderme](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>iOS günlükleri

Kullanıcılar, [BT yöneticinize iOS kayıt hatalarını gönderme](/intune-user-help/send-errors-to-your-it-admin-ios) konu başlığı altında açıklandığı gibi kayıt hatalarını size gönderebilir.

Kullanıcılar, [iOS Cihaz Günlükleri Gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-ios) konusunda açıklandığı gibi cihaz günlükleri gönderebilirler.

### <a name="mac-os-x-logs"></a>Mac OS X günlükleri

1. **Console** uygulamasını açın.
2. **FILES** altından **system.log** dosyasını seçin.
3. En üstteki menü çubuğunda **Dosya** > **Kopyayı Farklı Kaydet**'i seçin. Sonra dosyayı kaydedin.

### <a name="windows-phone"></a>Windows Phone

Windows Phone Şirket Portalı uygulamasında kullanıcılar, menüye erişmek için üç noktayı (**…**), sonra **Günlükleri Gönder**'i seçer. Bu seçenek Şirket Portalı'nda hem oturum açmadan önce hem de oturum açtıktan sonra kullanılabilir.

### <a name="windows"></a>Windows

Windows Şirket Portalı'nda günlükler, *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState* konumunda bulunur.
