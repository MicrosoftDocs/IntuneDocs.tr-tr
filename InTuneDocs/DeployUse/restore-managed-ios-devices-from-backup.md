---
title: "Intune yönetilen iOS cihazları yedekten geri yükleme | Microsoft Intune"
description: "Son kullanıcılara, cihazlarını yedekten geri yükledikten sonra yeniden kaydetme yönergeleri sağlar."
keywords: "geri yükleme, yönetilen, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6bb539c87c4a13a490ba98c016d814bea5c7bbc
ms.openlocfilehash: 6395e50b3e4c06e7363acc136b5ed9eb2ef75abd


---

# Intune yönetilen iOS cihazları yedekten geri yükleme

Bir kullanıcının yeni bir cihaz alması gibi, siz veya kullanıcılarınızın bir iOS cihazı yedekten geri yüklemesini gerektirecek durumlar olacaktır. Bu konu, cihaz geri yüklendikten sonra Intune yönetimini ayarlamak için atmanız gereken ek adımları açıklar.

## Yedekleri aynı cihaza geri yükleme

Yedek, aynı cihaza geri yükleniyorsa, cihazdaki kayıt durumu da geri yüklenir. Başka bir işlem yapmaya gerek yoktur.

## Yedekleri farklı cihazlara geri yükleme

Yedek, farklı bir cihaza geri yükleniyorsa, kayıt durumu yeni cihazda otomatik olarak geri yüklenmez. Kullanıcıların [iOS cihazlarını Intune’a kaydetmek](/Intune/EndUser/enroll-your-device-in-intune-ios) için Şirket Portalı uygulamasının uygulama sürümü 2.1.22 veya üzeri sürümlerdeki standart kayıt adımlarını izlemesi gerekir.

> [!NOTE]
> Koşullu erişim ilkeleriyle son kullanıcılarınızı hedefliyorsanız, yeniden kaydolduklarında şirket e-postasına erişemezler.

> [!TIP]
> Kullanıcılarınız için örnek bir iletişim aşağıdaki gibi olabilir: Yeni cihazınızı kaydetmek için Şirket Portalı uygulamasının 2.1.22 veya üzeri bir sürümde olduğundan emin olun. Sürümü denetlemek için Şirket Portalı uygulamasını açın, sağ üstteki Menü düğmesine dokunun ve ardından Hakkında’ya dokunun. Önceki bir sürüm kullanıyorsanız, Şirket Portalı uygulamasından çıkın ve App Store’u açın. Sağ alt köşedeki Güncelleştirmeler düğmesine dokunun ve ardından listedeki Şirket Portalı öğesinin yanındaki Güncelleştir düğmesine dokunun. Güncelleştirme tamamlandıktan sonra, Şirket Portalı uygulamasını başlatın ve [iOS cihazınızı Intune'a kaydedin](/Intune/EndUser/enroll-your-device-in-intune-ios).

## Geri yükleme işlemleriyle ilgili bilinen sorunları çözme

Kullanıcılar hala Şirket Portalı 2.1.21 veya önceki bir sürüme sahipken cihazlarını geri yükleyip Şirket Portalı uygulamasını başlattıklarında bazı zorluklar yaşayabilir. Bu sorunlar, kullanıcının durumuna uygun adımlar uygulanarak çözülebilir.

### Yalnızca yeni cihazlarını kullanacak kullanıcılar
Şirket Portalı uygulamasını başlatın ve geçerli cihaz kutucuğunu seçip __Kaldır__ düğmesine dokunarak kaydı silin. Kaldırdıktan sonra, [Intune'a bir iOS cihazı kaydetmek](/Intune/EndUser/enroll-your-device-in-intune-ios) için standart kayıt adımlarını uygulayın.

### Hem eski hem de yeni cihazlarını kullanacak kullanıcılar
Safari’de __Ayarlar__ > __Safari__ > __Tarihçeyi ve Web Sitesi Verilerini Sil__’e dokunarak tanımlama bilgilerini temizleyin. Temizleme sonrası, Şirket Portalı uygulamasını kaldırıp yeniden yükleyin ve ardından [Intune'a bir iOS cihazı kaydetmek](/Intune/EndUser/enroll-your-device-in-intune-ios) için standart kayıt adımlarını uygulayın.



<!--HONumber=Oct16_HO3-->

