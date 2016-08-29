---
title: "Pulse Secure kullanılarak Android için uygulama başına VPN | Microsoft Intune"
description: "Intune tarafından yönetilen Android cihazları için uygulama başına VPN profili oluşturabilirsiniz."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87aea89a323fb05087322fb117d0be2e579a06ff
ms.openlocfilehash: 6eda2828a801700e885d1bed667f9260f325e175


---

# Özel ilke kullanarak Android cihazları için uygulama başına VPN profili oluşturma

Intune tarafından yönetilen Android cihazları için uygulama başına VPN profili oluşturabilirsiniz. Öncelikle, Pulse Secure bağlantı türünü kullanan bir VPN profili oluşturursunuz ve sonra da bu profili belirli uygulamalarla ilişkilendiren özel bir yapılandırma ilkesi oluşturursunuz. Bu ilkeleri Android cihaz veya kullanıcı gruplarınıza dağıttıktan sonra, belirtilen uygulamalardan birinin söz konusu cihazlarda açılması, bu uygulama için VPN bağlantısını açar.

> [!NOTE]
> 
> Bu profil için yalnızca Pulse Secure bağlantı türü desteklenir.


### 1. Adım: VPN profili oluşturma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **İlke Ekle**’ye tıklayın.
2. **Android**’i genişleterek yeni ilke için bir şablon seçin ve sonra da **VPN Profili (Android 4 ve üstü)** öğesini seçin.

3. Şablonda, **Bağlantı türü** olarak **Pulse Secure** seçin.
4. VPN profilini tamamlayın ve kaydedin. VPN profilleri hakkında daha fazla bilgi için bkz. [VPN bağlantıları](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
> 
> Sonraki adımda kullanmak üzere VPN profili adını not edin.   Örneğin, **UygulamaVpnProfilim**.

### 2. Adım: Özel yapılandırma ilkesi oluşturma

   1. Intune yönetim konsolunda **İlke** -> **İlke Ekle** -> **Android** -> **Özel yapılandırma** -> **İlke Oluştur**’a tıklayın.
   2. İlke için bir ad sağlayın.
   3. **OMA-URI ayarları**’nın altında **Ekle**’ye tıklayın.
   4. Bir ayar adı sağlayın.
   5. **Veri türü** olarak **Dize** belirtin.
   6. **OMA-URI** için şu dizeyi belirtin: **./Vendor/MSFT/VPN/Profile/*Ad*/PackageList**; burada *Ad*, 1. Adım’da not ettiğiniz VPN profili adıdır. Bizim örneğimizde, dize şöyle olabilir: **./Vendor/MSFT/VPN/Profile/UygulamaVpnProfilim/PakatListesi**.
   7.   **Değer** alanında, profille ilişkilendirilecek paketlerin noktalı virgülle ayrılmış listesini sağlayın.  Örneğin, Excel’in ve Google Chrome tarayıcısının VPN bağlantısını kullanmasını istiyorsanız, şunu girebilirsiniz: **com.microsoft.office.excel;com.android.chrome**.


   ![Örnek Android uygulama başına VPN özel ilkesi](..\media\android_per_app_vpn_oma_uri.png)
#### Uygulama listenizi Kara Liste veya Beyaz Liste olarak ayarlama (isteğe bağlı)
**KARA LİSTE** değerini kullanarak, uygulama listenizin VPN bağlantısını kullanmasına izin *verilmeyeceğini* belirtebilirsiniz.  Diğer tüm uygulamalar VPN üzerinden bağlanır.

Alternatif olarak, **BEYAZ LİSTE** değerini kullanabilir ve *yalnızca* belirtilen uygulamaların VPN bağlantısını kullanabileceğini belirtebilirsiniz.


1.  OMA-URI ayarlarının altında **Ekle**’ye tıklayın.
2.  Bir ayar adı sağlayın.
3.  **Veri türü** olarak **Dize** belirtin.
4.  **OMA-URI** için şu dizeyi belirtin: **./Vendor/MSFT/VPN/Profile/*Ad*/Mode**; burada *Ad*, 1. Adım’da not ettiğiniz VPN profili adıdır. Bizim örneğimizde, dize şöyle olabilir: **./Vendor/MSFT/VPN/Profile/UygulamamVpnProfili/Mode**.
5.  **Değer** alanına **KARA LİSTE** veya **BEYAZ LİSTE** girin.



### 3. Adım: Her iki ilkeyi de dağıtma

*Her iki* ilkeyi de *aynı* Intune gruplarına dağıtmalısınız.

   1.   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

 **İlke** çalışma alanının **Genel Bakış** sayfasında, bir durum özeti ve uyarılar ilkeyle ilgili işlem yapmanız gereken durumları tanımlar. Ayrıca, Pano çalışma alanında bir durum özeti görüntülenir.



<!--HONumber=Aug16_HO2-->

