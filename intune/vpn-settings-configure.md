---
title: "Intune VPN ayarlarını yapılandırma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Yönettiğiniz cihazlarda VPN bağlantılarını yapılandırmak için Intune’u kullanmayı öğrenin."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8a8742d0b579fec734dd8335e2a610d126db21fa
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Microsoft Intune’da VPN ayarlarını yapılandırma

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir VPN bağlantısı profili kullanır. VPN ayarlarını kuruluşunuzdaki kullanıcılar ve cihazlara atamak için Microsoft Intune’da **VPN profilleri** kullanarak ağa kolay ve güvenli bir şekilde bağlanabilmelerini sağlayın.

Örneğin, tüm iOS cihazlara kurumsal ağ üzerindeki bir dosya paylaşımına bağlanmak için gereken ayarları sağlamak istediğinizi varsayın. Kurumsal ağa bağlanmak için gereken ayarları içeren bir VPN profili oluşturur ve ardından bu profili iOS cihazlarını kullanan tüm kullanıcılara atarsınız. Kullanıcılar VPN bağlantısını kullanılabilir ağlar listesinde görür ve ağa en az çaba ile bağlanabilir.

## <a name="vpn-connection-types"></a>VPN bağlantısı türleri

VPN profillerini oluştururken aşağıdaki bağlantı türlerini kullanabilirsiniz:

||||||||
|-|-|-|-|-|-|-|
|Bağlantı türü|Android|iOS|Mac OS|Windows Phone 8.1|Windows 8.1|Windows 10|
|Pulse Secure|Evet|Evet|Evet|Evet|Evet|Evet|
|Cisco (IPSec)|Hayır|Evet|Hayır|Hayır|Hayır|Hayır|
|Citrix|Evet|Evet|Hayır|Hayır|Hayır|Hayır|
|F5 Edge Client|Evet|Evet|Evet|Evet|Evet|Evet|
|Dell SonicWALL Mobile Connect|Evet|Evet|Evet|Evet|Evet|Evet|
|Check Point Capsule VPN|Evet|Evet|Evet|Evet|Evet|Evet|
|Cisco AnyConnect|Evet|Evet|Evet|Hayır|Hayır|Hayır|
|Otomatik|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|IKEv2|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|L2TP|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|PPTP|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|Özel|Hayır|Evet|Evet|Hayır|Hayır|Hayır|


> [!IMPORTANT]
> Bir cihaza atanan VPN profillerini kullanmadan önce profil için geçerli VPN uygulamasını yüklemeniz gerekir. Uygulamayı Intune kullanarak atamanıza yardımcı olması için [Microsoft Intune'da uygulama yönetimi nedir](app-management.md) konusunda verilen bilgileri kullanabilirsiniz.  

[Özel VPN profilleri oluşturma](custom-vpn-profiles-create.md) konu başlığı altında verilen URI ayarlarını kullanarak özel VPN profilleri oluşturmayı öğrenin.     

## <a name="create-a-device-profile-containing-vpn-settings"></a>VPN ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, VPN profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, VPN ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, VPN cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **VPN**’yi seçin.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ayarları](vpn-settings-android.md)
    - [iOS ayarları](vpn-settings-ios.md)
    - [macOS ayarları](vpn-settings-macos.md)
    - [Windows Phone 8.1 ayarları](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1 ayarları](vpn-settings-windows-8-1.md)
    - [Windows 10 ayarları](vpn-settings-windows-10.md)
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).


## <a name="methods-of-securing-vpn-profiles"></a>VPN profillerini güvenli hale getirme yöntemleri

VPN profilleri, farklı üreticilerden farklı bağlantı türleri ve farklı protokoller kullanabilir. Bu bağlantılar genellikle iki yöntemden biri kullanılarak güvenli hale getirilir.

### <a name="certificates"></a>Sertifikalar

VPN profilini oluştururken, Intune’da önceden oluşturduğunuz bir SCEP veya PKCS sertifika profilini seçersiniz. Bu kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin verildiğini belirtmek için oluşturduğunuz bir güvenilir sertifika profiline (veya *kök sertifikaya*) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, VPN bağlantısının kimliğini doğrulayan bilgisayara atanır. Bu, genellikle VPN sunucusudur.

Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune ile sertifikaları yapılandırma](certificates-configure.md).

### <a name="user-name-and-password"></a>Kullanıcı adı ve parola

Kullanıcı, kullanıcı adı ve parola girerek VPN sunucusunda kimliğini doğrular.
