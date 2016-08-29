---
title: "Cihazları koruma | Microsoft Intune"
description: "Intune’un cihazlarınızı yetkisiz erişime veya diğer tehditlere karşı korumanıza yardımcı olabileceği yollardan bazılarını öğrenin."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 2b33330f8ec8b46e3b4c6886463e8d3588410ab7


---

# Cihazları Microsoft Intune ile koruma
Cihazlarınızı Intune ile yönettikten sonra, yetkisiz erişim ve diğer tehditlere karşı korunmalarını sağlamak isteyeceksiniz. Aşağıda, Intune’un bunları gerçekleştirmenize yardımcı olacak bazı özellikleri verilmiştir.

> [!TIP]
> Bu konuda, Intune’un cihazlarınızı güvenli hale getirmeye yardımcı olacak tüm yöntemleri yer almamaktadır. Örneğin, cihazlarınız için, parolalar, şifreleme ayarları ve Bluetooth ve cihaz kamerası gibi donanım özellikleri yapılandırmak üzere Intune ilkelerini kullanabilirsiniz. Bu ayarlar hakkında daha fazla bilgi almak için, bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Kullanıcılar kilitlenen cihazlarına erişemediğinde geçiş kodlarını sıfırlama
Mobil cihazlarda şirket verilerini korumanın ilk adımı cihazı kullanmak için bir geçiş kodu istenmesi olduğundan, bazen bir [geçiş kodunu sıfırlamanız](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ya da geçiş kodunu kaldırarak veya uzaktan geçici geçiş kodu ayarlayarak bir çalışana kodu sıfırlaması için yardımcı olmanız gerekir. Ayrıca, kaybedilirse veya çalınırsa [bir cihazı uzaktan kilitleyebilirsiniz.](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

## Windows cihazlar için ek bir koruma katmanı ekleme
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md), ağdaki Windows ve Windows Phone cihazı kullanıcılarının kimliklerini doğrulamak için daha güvenli bir yoludur.  MFA ile kullanıcıların kimliklerini kullanıcı adı ve parolanın ötesinde, bir telefon konuşması veya kısa mesaj üzerinden doğrulaması gerekir.

## Windows cihazlarda Microsoft Passport ayarlarını denetleme
Intune, bir parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Windows 10 ve üzerinde Active Directory veya bir Azure Active Directory hesabı kullanan alternatif bir oturum açma yöntemi olan [İş İçin Microsoft Passport](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)’u tümleştirmenize olanak sağlar.

## iOS’de Etkinleştirme Kilidini Atlama
Etkinleştirme Kilidi, cihazlarını silmeden veya yeniden etkinleştirmeden önce kullanıcılardan Apple kimliklerini ve parolalarını girmelerini isteyerek bu cihazları korumaya yardımcı olan bir özelliktir. Ancak, bu, örneğin kullanıcının kilidi kaldırmadan şirketten ayrılması durumunda sorunlara yol açabilir. [iOS Etkinleştirme Kilidi atlama](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md), denetimli iOS cihazlarından kilidi kaldırarak bu cihazları yeniden kullanıma almanıza veya silmenize yardımcı olabilir.

## Intune istemcisiyle yönetilen Windows bilgisayarları koruma
Intune, kaydolmadığınız ancak Intune bilgisayar istemci yazılımıyla yönettiğiniz Windows bilgisayarlar için güvenlik ilkelerini desteklemeye devam etmektedir. Bu ilkelerin, Windows bilgisayarlarınızı güvenli hale getirmenize nasıl yardımcı olabileceğini öğrenmek için, bkz. [Intune istemci yazılımını çalıştıran Windows bilgisayarları korumanıza yardımcı olması için ilkeler kullanma](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Jul16_HO4-->

