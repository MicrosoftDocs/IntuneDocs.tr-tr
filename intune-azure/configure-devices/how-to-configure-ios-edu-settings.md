---
title: "iOS Classroom uygulaması için Intune ayarları | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS cihazlarındaki Classroom uygulamasının ayarlarını denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: 3c7ab3e33f7a1a97cd8048be059cf2f74deb00c1
ms.contentlocale: tr-tr
ms.lasthandoff: 05/03/2017


---


# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>iOS Classroom uygulaması için Intune ayarlarını yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="introduction"></a>Giriş
[Classroom](https://itunes.apple.com/app/id1085319084), öğretmenlerin öğrenmeye yol göstermesine ve sınıftaki öğrenci cihazlarını denetlemesine yardımcı olan bir uygulamadır. Örneğin, bir öğretmen uygulamayı kullanarak şunları yapabilir:

- Öğrenci cihazlarında uygulamalar açabilir
- iPad ekranını kilitleyebilir ve ekranın kilidini açabilir
- Bir öğrencinin iPad ekranını görüntüleyebilir
- Öğrenci iPad’lerini bir yer işaretine veya kitaptaki bir bölüme yönlendirebilir
- Apple TV’de bir öğrenci iPad’inin ekranını görüntüleyebilir

Classroom uygulamasını ve bu uygulamayı çalıştıran cihazları ayarlamak için Intune iOS **Eğitim** cihaz profilini ve bu konu başlığındaki bilgileri kullanın.

## <a name="before-you-start"></a>Başlamadan önce

Bu ayarları yapılandırmaya başlamadan önce, aşağıdakilere dikkat edin:

- Hem öğretmen hem de öğrenci iPad cihazlarının Intune'a kayıtlı olması gerekir
- Öğretmenin cihazına [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) uygulamasını yüklediğinizden emin olun. Bunu el ile yapabilir veya [Intune uygulama yönetimini](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management) kullanabilirsiniz.
- Öğretmen ve öğrenci cihazları arasındaki bağlantıların kimliğini doğrulamak için sertifikaları yapılandırmanız gerekir (bkz. 2. Adım)
- Öğretmen ve öğrencilerin iPad cihazları aynı Wi-Fi ağında olmalı ve cihazların Bluetooth özellikleri etkin olmalıdır
- Classroom uygulaması iOS 9.3 veya üzerini çalıştıran denetimli iPad cihazlarında çalışır
- Bu sürümde, Intune her öğrencinin kendine ait bir iPad cihazının olduğu 1:1 senaryosunu yönetmeyi destekler


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>1. Adım - Okul verilerinizi Azure Active Directory'ye aktarın

Mevcut Öğrenci Bilgi Sisteminden (SIS) Azure Active Directory’ye (Azure AD) okul kayıtlarını içeri aktarmak için Microsoft'un School Data Sync (SDS) özelliğini kullanın.
SDS, SIS bilgilerinizi eşitler ve Azure AD'de depolar. Azure AD, kullanıcıları ve cihazları düzenlemenize yardımcı olan bir Microsoft yönetim sistemidir. Ardından öğrencilerinizi ve sınıflarınızı yönetmenize yardımcı olması için bu verileri kullanabilirsiniz. [SDS dağıtma hakkında daha fazla bilgi edinin](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>SDS kullanarak nasıl veri aktarılır?

Aşağıdakilerden birini kullanarak SDS’ye bilgi aktarabilirsiniz:

- [CSV dosyaları](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - Virgülle ayrılmış değer (.csv) dosyalarını el ile dışa aktarma ve derleme
- [PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - Azure AD ile eşitlemeyi basitleştiren bir SIS sağlayıcısı
- [Akıllı API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - Doğrudan Azure AD ile eşitlenen bir kimlik yönetimi çözümü
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - Azure AD ile eşitlemek için dışarı aktarabileceğiniz ve dönüştürebileceğiniz bir CSV biçimi

### <a name="find-out-more"></a>Daha fazla bilgi edinin

- [Şirket içi okul verilerini Azure AD’ye eşitleme deneyiminin tümü hakkında bilgi edinin](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Microsoft School Data Sync hakkında daha fazla bilgi edinin](https://sds.microsoft.com/)
- [Azure Active Directory'de lisanslama hakkında daha fazla bilgi edinin](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>2. Adım - Intune’da bir iOS Eğitim profili oluşturun ve atayın

### <a name="configure-general-settings"></a>Genel ayarları yapılandırma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3.    **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
4.    **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
5.    Profiller dikey penceresinde **Profil Oluştur**’u seçin.
6.    **Profil Oluştur** dikey penceresinde, iOS eğitim profili için **Ad** ve **Açıklama** girin.
7.    **Platform** açılan listesinden **iOS**’yi seçin.
8.    **Profil türü** açılan listesinde **Eğitim**’i seçin.
9.    **Ayarlar** > **Yapılandır**’ı seçin.


Ardından, öğretmen ve öğrencilerin iPad cihazları arasında bir güven ilişkisi kurmak için sertifikalara ihtiyacınız olacaktır. Sertifikalar, kullanıcı adları ve parolaları girmeye gerek olmadan cihazlar arasında bağlantıların kimliğini sorunsuz ve sessiz bir şekilde doğrulamak için kullanılır.

>[!IMPORTANT]
>Kullandığınız öğretmen ve öğrenci sertifikalarının, farklı sertifika yetkilileri (CA’lar) tarafından verilmiş olması gerekir. Mevcut sertifika altyapınıza bağlı iki yeni alt CA oluşturmanız gerekir; biri öğretmenler, diğeri öğrenciler için.

iOS eğitim profilleri yalnızca PFX sertifikalarını destekler; SCEP sertifikaları desteklenmez.

Oluşturduğunuz sertifikaların, kullanıcı kimlik doğrulamasına ek olarak sunucu kimlik doğrulamasını da desteklemesi gerekir.

### <a name="configure-teacher-certificates"></a>Öğretmen sertifikalarını yapılandırma

**Eğitim** dikey penceresinde, **Öğretmen sertifikaları**’nı seçin.

#### <a name="configure-teacher-root-certificate"></a>Öğretmen kök sertifikasını yapılandırma

**Öğretmen kök sertifikası** altında, .cer (DER veya Base64 ile kodlanmış) veya .P7B (tam zincir içeren veya içermeyen) uzantısına sahip öğretmen kök sertifikasını seçmek için gözat düğmesini seçin.

#### <a name="configure-teacher-pkcs12-certificate"></a>Öğretmen PKCS#12 sertifikasını yapılandırma

**Öğretmen PKCS #12 sertifikası** altında aşağıdaki değerleri yapılandırın:

- **Konu adı biçimi** - Intune, öğretmen sertifikası için **lider**, öğrenci sertifikası içinse **üye** ön ekini sertifika ortak adına otomatik olarak ekler.
- **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. 
- **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
- **Sertifika şablonu adı** - Sertifika verme yetkilisine eklenmiş bir sertifika şablonunun adını girin. 
- **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
- **Sertifika geçerlilik süresi** - Sertifikanın süresi dolmadan önce kalan süreyi belirtin.
Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, sertifika verme yetkilisinin sertifikası için kalan geçerlilik süresinden düşük olması gerekir.

Sertifikaları yapılandırmayı bitirdiğinizde **Tamam**’ı seçin.

### <a name="configure-student-certificates"></a>Öğrenci sertifikalarını yapılandırma

1.    **Eğitim** dikey penceresinde, **Öğrenci sertifikaları**’nı seçin.
2.    **Öğrenci sertifikaları** dikey penceresinde, **Öğrenci cihaz sertifikaları** türü listesinde yazın, **1:1** seçeneğini belirleyin.

#### <a name="configure-student-root-certificate"></a>Öğrenci kök sertifikasını yapılandırma

**Öğrenci kök sertifikası** altında, .cer (DER veya Base64 ile kodlanmış) veya .P7B (tam zincir içeren veya içermeyen) uzantısına sahip öğrenci kök sertifikasını seçmek için gözat düğmesini seçin.

#### <a name="configure-student-pkcs12-certificate"></a>Öğrenci PKCS#12 sertifikasını yapılandırma

**Öğrenci PKCS #12 sertifikası** altında aşağıdaki değerleri yapılandırın:

- **Konu adı biçimi** - Intune, öğretmen sertifikası için **lider**, öğrenci sertifikası içinse **üye** ön ekini sertifika ortak adına otomatik olarak ekler.
- **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. 
- **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
- **Sertifika şablonu adı** - Sertifika verme yetkilisine eklenmiş bir sertifika şablonunun adını girin. 
- **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
- **Sertifika geçerlilik süresi** - Sertifikanın süresi dolmadan önce kalan süreyi belirtin.
Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, sertifika verme yetkilisinin sertifikası için kalan geçerlilik süresinden düşük olması gerekir.

Sertifikaları yapılandırmayı bitirdiğinizde **Tamam**’ı seçin.

## <a name="finish-up"></a>Bitirme

1.    **Eğitim** dikey penceresinde, Tamam'ı seçin.
2.    **Profil Oluştur** dikey penceresinde, **Oluştur**’u seçin.
    
Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

Okul verilerinizi Azure AD ile eşitlediğinizde oluşturulan sınıf gruplarındaki öğrenci cihazlarına profili atayın (bkz. [Cihaz profilleri atama](/intune-azure/configure-devices/how-to-assign-device-profiles)).

## <a name="next-steps"></a>Sonraki adımlar

Böylece, bir öğretmen Classroom uygulamasını kullandığında, öğrenci cihazları üzerinde tam denetime sahip olur.

Classroom uygulaması hakkında daha fazla bilgi için Apple web sitesindeki [Classroom yardımı](https://help.apple.com/classroom/ipad/2.0/) bölümüne bakın.
