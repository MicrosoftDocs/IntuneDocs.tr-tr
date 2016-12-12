---
title: "Cihazları koruma | Microsoft Intune"
description: "Intune’un cihazlarınızı yetkisiz erişime veya diğer tehditlere karşı korumanıza yardımcı olabileceği yollardan bazılarını öğrenin."
keywords: 
author: Robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 235db7eb1036bfccd074fd83b4b59e75529a5e34


---

# <a name="protect-devices-with-microsoft-intune"></a>Cihazları Microsoft Intune ile koruma

Microsoft Intune, yönettiğiniz cihazları ve bu cihazlarda depolanan verileri korumaya yardımcı olmak için tam özellik kümesi sunar. Bu özelliklerin temellerini ve daha fazla nasıl bilgi bulacağınızı öğrenmek için bu konuyu okuyun.

## <a name="general-ways-to-protect-all-devices"></a>Tüm cihazları korumanın genel yolları

### <a name="device-configuration"></a>Cihaz yapılandırması
Intune [yapılandırma ilkeleri](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md), çeşitli ayar ve özellikleri denetleyerek cihazları korumanıza ve yapılandırmanıza yardımcı olur. Örneğin:
- Cihazdaki kamera veya Bluetooth gibi donanım özelliklerinin kullanımını kısıtlayabilirsiniz.
- Uyumlu ve uyumsuz uygulamaları yapılandırabilirsiniz. Uyumsuz bir uygulama yüklenirse size uyarı verilir (ve bazı platformlar yüklemeyi engelleyebilir).

### <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Kullanıcılar kilitlenen cihazlarına erişemediğinde geçiş kodlarını sıfırlama
Mobil cihazlarda şirket verilerini korumanın ilk adımı cihazı kullanmak için bir geçiş kodu istenmesi olduğundan, bazen bir [geçiş kodunu sıfırlamanız](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ya da geçiş kodunu kaldırarak veya uzaktan geçici geçiş kodu ayarlayarak bir çalışana kodu sıfırlaması için yardımcı olmanız gerekir. Ayrıca, kaybedilirse veya çalınırsa [bir cihazı uzaktan kilitleyebilirsiniz.](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

### <a name="retire-devices-and-remove-data"></a>Cihazları devre dışı bırakma ve verileri kaldırma
Bir cihazın [Intune yönetiminden kaldırılması](retire-devices-from-microsoft-intune-management.md) gerektiğinde (örneğin, bir kullanıcı ayrıldığında veya cihaz kaybedildiğinde veya çalındığında), bu cihazdaki verileri kaldırmak isteyeceksinizdir. Intune, şirketinizin verilerinin güvenli kalmasını sağlamak için bir dizi yöntem sunar.

### <a name="require-devices-to-be-compliant"></a>Cihazların uyumlu olmasını zorunlu kılma
Intune’da, belirttiğiniz kurallarla uyumlu olmayan cihazları değerlendirmenize (ve bazı durumlarda düzeltmenize) izin veren [cihaz uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune.md) bulunur. Örneğin, kısıtlamalardan kurtulmuş iOS cihazlarını, cihazların şifreli olup olmadığını veya Windows 10 cihazların durumunun Sistem Durumu Kanıtı Hizmeti tarafından uygun olarak bildirilip bildirilmediğini rapor edebilirsiniz.

### <a name="protect-apps-and-the-data-they-use"></a>Uygulamaları ve kullandıkları verileri koruma
Intune, uygulamaları ve bunların verilerini korumanıza yardımcı olmak için size bir dizi özellik sunar. Örneğin, mobil uygulama yönetimi (MAM) ilkeleri verilerin korumalı bir uygulamadan yedeklenmesini engelleyebilir, kopyalama ve başka uygulamalara yapıştırmayı kısıtlayabilir, bir uygulamaya erişim için bir PIN isteyebilir vb. Uygulamaları koruma hakkında daha fazla ayrıntı için bkz. [Microsoft Intune ile uygulamalar ve verileri koruma](protect-apps-and-data-with-microsoft-intune.md)

## <a name="further-capabilities-for-windows-devices"></a>Windows cihazları için diğer özellikler

### <a name="add-an-additional-layer-of-protection-to-windows-devices"></a>Windows cihazlar için ek bir koruma katmanı ekleme
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md), ağdaki Windows ve Windows Phone cihazı kullanıcılarının kimliklerini doğrulamak için daha güvenli bir yoludur.  MFA ile, kullanıcıların, kimliklerini kullanıcı adı ve parolanın ötesinde, bir telefon konuşması veya kısa mesaj üzerinden doğrulaması gerekir.

### <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Windows cihazlarda İş İçin Windows Hello ayarlarını denetleme
Intune bir parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek üzere Windows 10 ve üzeri için Active Directory veya bir Azure Active Directory hesabı ile alternatif bir oturum açma yöntemi olan [İş İçin Windows Hello](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)’yu (eskiden Microsoft Passport) tümleştirmenize olanak sağlar.

## <a name="further-capabilities-for-ios-devices"></a>iOS cihazlar için diğer özellikler

### <a name="bypass-activation-lock-on-ios-devices"></a>iOS’de Etkinleştirme Kilidini Atlama
Etkinleştirme Kilidi, kullanıcılardan cihazlarını silmeden veya yeniden etkinleştirmeden önce Apple Kimliklerini ve parolalarını girmelerini isteyerek bu cihazları korumaya yardımcı olan bir özelliktir. Ancak, bu, örneğin kullanıcının kilidi kaldırmadan şirketten ayrılması durumunda sorunlara yol açabilir. [iOS Etkinleştirme Kilidi atlama](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md), denetimli iOS cihazlarından kilidi kaldırarak bu cihazları yeniden kullanıma almanıza veya silmenize yardımcı olabilir.



## <a name="protect-windows-pcs-managed-with-the-intune-client"></a>Intune istemcisiyle yönetilen Windows bilgisayarları koruma
Intune, kaydolmadığınız ancak Intune bilgisayar istemci yazılımıyla yönettiğiniz Windows bilgisayarlar için güvenlik ilkelerini desteklemeye devam etmektedir. Bu ilkelerin, Windows bilgisayarlarınızı güvenli hale getirmenize nasıl yardımcı olabileceğini öğrenmek için, bkz. [Intune istemci yazılımını çalıştıran Windows bilgisayarları korumanıza yardımcı olması için ilkeler kullanma](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Dec16_HO2-->

