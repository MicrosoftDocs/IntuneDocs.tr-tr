---
title: "Windows için Şirket Portalı uygulamasını yükleme | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 0e6b7ae1794ff0857dfb203eb3c67d7ba494bd8e
ms.openlocfilehash: bde2ccc0c170a85e926357d54fcf4ffe6ee50fd9
ms.lasthandoff: 02/21/2017


---


# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-windows-device-in-intune"></a>Şirket Portalı uygulamasını yüklerseniz ve Windows cihazınızı Intune’a kaydederseniz ne olur?

Şirket Portalı uygulamasını yüklediğinizde ve bu uygulamayı kullanarak bir Windows veya Windows Phone cihazı kaydettiğinizde, BT yöneticinize şirket veya okul verilerinin güvenliğini sağlamak üzere cihazınızı yönetme izni vermiş olursunuz. Windows 10’dan önceki işletim sistemlerini çalıştıran cihazlarda neler olacağı bu konuda açıklanmıştır. Windows 10 cihazlar için bkz. [ilgili konu](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## <a name="what-happens-to-all-windows-devices-after-enrollment"></a>Kayıttan sonra tüm Windows cihazlarına ne olur?
Windows veya Windows Phone cihazınızı Intune’a kaydettiğinizde:

-   Şirket ağına, e-postalarınıza ve iş dosyalarınıza erişebilirsiniz.

-   Şirket Portalı web sitesi üzerinden şirket uygulamalarını alın. (__Not__: Windows 7 ve Windows Vista’da, şirket uygulamalarını yalnızca Şirket Portalı web sitesi üzerinden alabilirsiniz.)

-   Şirket veya okul e-posta hesabınızı otomatik olarak oluşturun.

-   Telefonunuz kaybolur veya çalınırsa fabrika ayarlarına sıfırlayabilirsiniz.

Cihazınızı kaydettiğinizde, BT yöneticinize şu tür işlemleri yapma izni vermiş olursunuz:

-   Cihazınızı üretici varsayılan ayarlarına geri döndürebilir. Cihaz çalındıysa veya kaybolduysa bu yararlıdır.

-   Yalnızca şirketle ilgili dosyaları ve iş uygulamalarını kaldırabilir. *Kişisel ayarlarınız ve verileriniz kaldırılmaz.*

-   BT yöneticiniz, kişisel olarak yüklediğiniz yazılımlar dahil olmak üzere bilgisayarda yüklü olan tüm yazılımları görüntüleyebilir.

-   Şirket verilerini korumaya yardımcı olmak için cihazınızda parola veya PIN kullanmanızı zorunlu kılma gibi gereksinimler ayarlayabilir. BT yöneticiniz ayrıca, kaç kez hatalı parola girebileceğinizi belirleyebilir ve çok sayıda hatalı giriş yaptığınızda cihazınızı kilitleyebilir.

-   Cihazınızın kaybolması veya çalınması durumunda şirket verilerinizin korunmasına yardımcı olmak için cihazınızdaki verileri şifrelemenizi isteyebilir.

-   Hüküm ve koşulları kabul etmenizi gerektirebilir.

-   Şirket ile ilgili verilerin fotoğrafını çekmenizi engelleyebilir.

## <a name="what-happens-to-all-windows-pcs-after-enrollment"></a>Kayıttan sonra tüm Windows bilgisayarlarına ne olur?

-  BT yöneticinizin bilgisayarı yönetmesine olanak tanımak, böylelikle uygulamalar ve destek bilgileri gibi şirket kaynaklarına erişmenizi sağlamak için bilgisayarınıza yazılım yüklenir. BT yöneticiniz bu yazılımı otomatik olarak güncelleştirebilir.

-  Intune Endpoint Protection bilgisayarınızda yüklü olabilir. Bu yazılım, bilgisayarı virüs ve kötü amaçlı yazılımlara karşı denetler.

-  BT yöneticiniz, bilgisayarınızın sabit sürücüsünden veri toplayabilir veya onları silebilir.

-  BT yöneticiniz aynı zamanda bilgisayarınıza uygulama ve güncelleştirme de yükleyebilir.

## <a name="what-happens-every-eight-hours-after-device-enrollment"></a>Cihaz kaydından sonra her sekiz saatte bir ne olur?

Yaklaşık her sekiz saatte bir, kayıtlı cihazlarda aşağıdakiler yapılır:

-   BT yöneticinizin kullanılabilir hale getirdiği ilke veya uygulama güncelleştirmeleri indirilir.

-   Tüm donanım envanteri güncelleştirmeleri gönderilir.

-   Tüm şirket uygulaması envanteri güncelleştirmeleri gönderilir.

Sorularınız varsa BT yöneticinizle iletişime geçin. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.
