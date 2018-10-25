---
title: Hızlı Başlangıç - Intune'da özel bir rol oluşturma ve atama
description: Hızlı Başlangıç - Uzak bir cihaz yöneticisi için özel bir rol oluşturun ve atayın.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 66426e9e22c2624b9828440906e3b1b947f4b60a
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581800"
---
# <a name="quickstart-create-and-assign-a-custom-role"></a>Hızlı Başlangıç: Özel rol oluşturma ve atama

Bu Intune hızlı başlangıcında bir güvenlik işlemleri departmanı için belirli izinleri olan özel bir rol oluşturup atayacaksınız. Ardından rolü bu tür işletmenlerden oluşan bir gruba atayacaksınız. Hemen kullanabileceğiniz birkaç varsayılan rol bulunur. Ancak bunun gibi özel roller oluşturarak mobil cihaz yönetim sisteminizin tamamı üzerinde doğru ayarlı bir erişim denetiminiz olur.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir grup oluşturmanız](quickstart-create-group.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.

## <a name="create-a-custom-role"></a>Özel rol oluşturma

Özel bir rol oluştururken çok çeşitli eylemler için izinler belirleyebilirsiniz. Güvenlik işleri rolünde, işletmenin bir cihazın yapılandırmalarını ve ilkelerini gözden geçirebilmesi için birkaç Okuma izni ayarlayacağız.

1. Intune'da **Roller** > **Tüm roller** > **Ekle**'yi seçin.
![Tarayıcı](media/quickstart-create-custom-role/add-custom-role.png)
2. **Özel rol ekle** altında, **Ad** kutusuna *Güvenlik işlemleri*'ni girin.
3. **Açıklama** kutusuna *Bu rol güvenlik işletmeninin cihaz yapılandırma ve uyumluluk bilgilerini izlemesine olanak tanır* açıklamasını girin.
4. **Okuma** > **Tamam**'ın yanındaki **Yapılandır** > **Kurumsal cihaz tanımlayıcılar** > **Evet**'i seçin.
![Tarayıcı](media/quickstart-create-custom-role/corp-device-id-read.png)
5. **Okuma** > **Tamam**'ın yanındaki **Cihaz uyumluluk ilkeleri** > **Evet**'i seçin.
6. **Okuma** > **Tamam**'ın yanındaki **Cihaz yapılandırmaları** > **Evet**'i seçin.
7. **Okuma** > **Tamam**'ın yanındaki **Kuruluş** > **Evet**'i seçin.
8. **Tamam** > **Oluştur**'u seçin.

## <a name="assign-the-role-to-a-group"></a>Rolü bir gruba atama

Güvenlik işletmeninizin yeni izinleri kullanabilmesi için önce rolü güvenlik kullanıcısını içeren bir gruba atamalısınız.

1. Intune'da **Roller** > **Tüm roller** > **Uzak cihaz yardım masası**'nı seçin.
2. **Intune rolleri** altında **Atamalar** > **Ata**'yı seçin.
3. **Atama adı** kutusuna *Güvenlik işletmenleri* ifadesini girin.
4. **Üye (Gruplar)** > **Ekle**'yi seçin.
5. **Contoso Testçileri** grubunu seçin.
6. **Seç** > **Tamam**'ı seçin.
7. **Kapsam (Gruplar)** > **Dahil edilecek grupları seç** > **Contoso Testçileri**'ni seçin.
8. **Seç** > **Tamam** > **Tamam**'ı seçin.

Artık gruptaki herkes *Güvenlik işlemleri* rolünün bir üyesidir ve bir cihaz hakkındaki şu bilgileri inceleyebilir: kurumsal cihaz tanımlayıcıları, cihaz uyumluluk ilkeleri, cihaz yapılandırmaları ve kuruluş bilgileri.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Yeni özel rolü artık kullanmak istemiyorsanız, silebilirsiniz. **Roller** > **Tüm roller**'i > rolün yanındaki üç noktayı seçin > **Sil**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta özel bir güvenlik işlemleri rolü oluşturup bir gruba atadınız. Güvenlik sorunları hakkında aşağıdaki makalede daha fazla bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)