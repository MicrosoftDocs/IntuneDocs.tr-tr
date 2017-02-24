---
title: "macOS cihazları için Intune VPN ayarları | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: macOS cihazlarında VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: 6f7bcfaec34c4916f7c916210b00440062b83694


---

# <a name="vpn-settings-for-macos-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde macOS cihazları için VPN ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılabilir değildir.

## <a name="base-vpn-settings"></a>**Temel VPN ayarları**

**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - **Kimlik doğrulama sertifikası**’nın altında, bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](how-to-configure-certificates.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Özel VPN**
- **Bölünmüş tünel** - Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlayan bu seçeneği **etkinleştirin** veya **devre dışı bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, ama normal web’e göz atmak için otelin standart ağını kullanır.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or Mac OS X app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you deploy the software. For more information, see [How to deploy and monitor apps](/intune-azure/manage-apps/deploy-apps). --->

## <a name="custom-vpn-settings"></a>Özel VPN ayarları

**Özel VPN**’yi seçtiyseniz şu ek ayarları yapılandırın:

- **VPN tanımlayıcısı** Bu, kullandığınız VPN uygulamasının tanımlayıcısıdır ve VPN sağlayıcınız tarafından verilir.
- **Özel VPN öznitelikleri için anahtar ve değer çiftlerini girin** VPN bağlantınızı özelleştiren **Anahtarlar** ve **Değerler**’i ekleyin veya içeri aktarın. Yinelemek gerekirse, bu değerler normalde VPN sağlayıcınız tarafından verilir.


## <a name="proxy-settings"></a>Proxy ayarları

- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.
- **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
- **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.



<!--HONumber=Feb17_HO2-->

