---
title: "macOS cihazları için Intune özel ayarları"
titleSuffix: Intune on Azure
description: "Bir macOS özel profilinde kullanabileceğiniz ayarları öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57c4ec3621ffaef5c1aaffd55c87baac91e50154
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Microsoft Intune’da macOS cihazları için özel ayarlar

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[Apple Configurator aracını](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) kullanarak oluşturduğunuz ayarları macOS cihazlarına atamak için Microsoft Intune macOS özel profilini kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune macOS özel profiline aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara atayabilirsiniz.

Bu özellik, diğer Intune profil türleriyle yapılandırılamayan macOS ayarlarını atamanıza olanak tanır.


1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. **Profil Oluştur** dikey penceresinde aşağıdakileri belirtin:

- **Özel yapılandırma profili adı** - Cihazda ve Intune durum bilgisinde gösterileceği haliyle ilke için bir ad girin.
- **Yapılandırma profili dosyası** - Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin.
Apple Configurator aracından dışarı aktardığınız ayarların, macOS özel ilkesini atadığınız cihazlardaki macOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların nasıl çözümleneceği hakkında bilgi için, [Apple Developer](https://developer.apple.com/) web sitesinde **Yapılandırma Profili Başvurusu** ve **Mobil Cihaz Yönetim Protokolü Başvurusu** öğelerini arayın.

İçeri aktardığınız dosya, dikey pencerenin **Dosya içeriği** alanında görüntülenir.