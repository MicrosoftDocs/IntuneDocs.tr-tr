---
title: "Android cihazları için Intune VPN ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Android cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8c8690b191c7358c8fd60c241177aca1372a8f54
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazları için VPN ayarları

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılabilir değildir.

**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - Bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](certificates-configure.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Parmak izi** (yalnızca Check Point Capsule VPN) - VPN sunucusunun güvenilir olduğunu doğrulamak için kullanılacak bir dize (örneğin "Contoso Parmak İzi Kodu") belirtin. Parmak izi, bağlanırken aynı parmak izini sunan herhangi bir sunucuya güvenmesi için istemciye gönderilebilir. Cihazda henüz parmak izi yoksa, parmak izini gösterirken kullanıcıdan bağlandığı VPN sunucusuna güvenmesini ister (kullanıcı parmak izini el ile doğrular ve bağlanmak için güven’i seçer).
- **Citrix VPN öznitelikleri için anahtar ve değer çiftleri girin** (yalnızca Citrix) - VPN bağlantısının özelliklerini yapılandırmak için, Citrix tarafından sağlanan anahtar ve değer çiftlerini girin.
