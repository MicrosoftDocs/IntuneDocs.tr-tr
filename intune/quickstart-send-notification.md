---
title: Hızlı Başlangıç - Uyumsuz cihazlara bildirim gönderme
titlesuffix: Microsoft Intune
description: Bu hızlı başlangıçta uyumsuz cihazlara e-posta bildirimleri göndermek için Microsoft Intune’u kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: af24e1c56e43fe2edfc6a9241c31600b7cfe61a7
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186265"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Hızlı Başlangıç: Uyumsuz cihazlara bildirim gönderme

Bu hızlı başlangıçta iş gücünüzün uyumsuz cihazlara sahip üyelerine e-posta bildirimi göndermek için Microsoft Intune’u kullanacaksınız.

Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Daha sonra Azure Active Directory (AAD) [koşullu erişimi](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) cihazı engeller. Bir cihaz uyumlu olmadığında Intune, uyumsuzluk eylemleri eklemenize imkan vererek size karar verme esnekliği sağlar. Örneğin uyumsuz cihazları engellemeden önce kullanıcılara uyumlu olmaları için yetkisiz kullanım süresi sağlayabilirsiniz.

Cihazlar uyumluluk gereksinimlerini karşılamadığında yapabileceğiniz eylemlerden biri, bu son kullanıcılara e-posta göndermektir. Son kullanıcılara göndermeden önce e-posta bildirimini özelleştirebilirsiniz. Özellikle şirket logosu ve kişi bilgileri dahil olmak üzere alıcılar, konu ve ileti gövdesini özelleştirebilirsiniz. Intune ayrıca uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- Cihazların şirket kaynaklarına erişimini engellemek için cihaz uyumluluk ilkeleri kullanıldığında, AAD koşullu erişiminin ayarlanmış olması gerekir. [Cihaz uyumluluk ilkesi oluşturma](quickstart-set-password-length-android.md) hızlı başlangıcını tamamladıysanız Azure Active Directory kullanıyorsunuzdur. AAD hakkında daha fazla bilgi için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ve [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal) portalında [Genel yönetici](users-add.md#types-of-administrators) veya Intune [Hizmet yöneticisi](users-add.md#types-of-administrators) olarak oturum açın. 

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

Kullanıcılarınıza e-posta göndermek için bir bildirim iletisi şablonu oluşturun. Cihazın uyumsuz olması durumunda, şablona girdiğiniz ayrıntılar kullanıcılarınıza gönderilen e-postada görüntülenir.

1. Intune’da **Cihaz uyumluluğu** > **Bildirimler** > **Bildirim oluştur**’u seçin. 
2. Aşağıdaki bilgileri girin:

   - **Ad**: *Contoso Yöneticisi*
   - **Konu**: *Cihaz uyumluluğu*
   - **İleti**: *Cihazınız şu anda kuruluşumuzun uyumluluk gereksinimlerini karşılamıyor.*
   - **E-posta üst bilgisi – Şirket logosunu ekle**: Kuruluşunuzun logosunu göstermek için **Etkin** olarak ayarlayın.
   - **E-posta alt bilgisi – Şirket adını ekle**: Kuruluşunuzun adını göstermek için **Etkin** olarak ayarlayın.
   - **E-posta alt bilgisi – Kişi bilgilerini ekle**: Kuruluşunuzdaki kişinin bilgilerini göstermek için **Etkin** olarak ayarlayın.

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/quickstart-send-notification-01.png)

3. Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır.

    > [!NOTE]
    > Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

Şirketinizin adını, şirketinizdeki kişinin bilgilerini ve şirket logosunu ayarlama hakkında ayrıntılar için bkz. [Şirket bilgileri ve gizlilik bildirimi](company-portal-app.md#company-information-and-privacy-statement), [Destek bilgileri](company-portal-app.md#support-information) ve [Şirket kimliği markalama özelleştirmesi](company-portal-app.md#company-identity-branding-customization). 

## <a name="add-a-noncompliance-policy"></a>Uyumsuzluk ilkesi ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Bir cihaz uyumluluk ilkenize uymadığında Intune, bu cihazı otomatik olarak uyumsuz olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Ayrıca, uyumluluk ilkesi oluştururken veya mevcut uyumluluk ilkesini güncelleştirirken başka bir eylem ekleyebilirsiniz. 

Aşağıdaki adımlar, Windows 10 cihazları için uyumluluk ilkesi oluşturmayı gösterir.

1. Intune’da **Cihaz uyumluluğu**’nu seçin.
2. **İlkeler** > **İlke Oluştur**’u seçin.
3. Aşağıdaki bilgileri girin:

   - **Ad**: *Windows 10 uyumluluk*
   - **Açıklama**: *Windows 10 uyumluluk ilkesi*
   - **Platform**: Windows 10 ve üzeri

4. **Ayarlar** > **Sistem Güvenliği**’ni seçerek cihazın güvenlikle ilgili ayarlarını görüntüleyin.
5. **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli Kıl** olarak belirleyin. Bu ayar, kullanıcılara mobil cihazlarındaki bilgilere erişim verilmeden önce bu kullanıcılardan parola istenip istenmeyeceğini belirtir. 
6. **En az parola uzunluğu**’nu **6** olarak ayarlayın. Bu ayar, parolada en az kaç rakam veya karakter bulunması gerektiğini belirtir.

    ![Yeni bir uyumluluk ilkesi için Sistem Güvenliği ayarları](./media/quickstart-send-notification-02.png) 

7. Uyumluluk ilkenizi oluşturmak için **Tamam**, **Tamam** ve **Oluştur**’a tıklayın.
8. Yeni ilkenizin adını seçin: **Windows 10 uyumluluk**.
9. **Özellikler** > **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi seçin.
10. Açılan **Eylem** kutusunda **Son kullanıcılara e-posta gönder** seçeneğinin belirlendiğini doğrulayın.
11. Bu konunun öncesinde oluşturduğunuz ileti şablonunu seçmek için **İleti şablonu** > **Contoso Yöneticisi** > **Seçin**’i belirleyin.
12. Değişikliklerinizi kaydetmek için **Tamam** > **Tamam** > **Oluştur**’u seçin.

## <a name="assign-the-policy"></a>İlke atama

Uyumluluk ilkesini belirli bir kullanıcı grubuna veya tüm kullanıcılara atayabilirsiniz. Intune bir cihazın uyumsuz olduğunu algıladığında kullanıcıya uyumluluk ilkesine uyum sağlamak için cihazını güncelleştirmesi gerektiğine dair bir bildirim gider. Aşağıdaki adımlar, ilkeyi atamanızı sağlar.

1. Daha önce oluşturduğunuz **Windows 10 uyumluluk** ilkesini seçin.
2. **Atamalar**’ı seçin.
3. Açılan **Şuna ata** kutusunda **Tüm Kullanıcılar**’ı seçin. Bu eylem, tüm kullanıcıları seçer. **Windows 10 ve üzeri** cihaza sahip olan ve bu uyumluluk ilkesine uymayan tüm kullanıcılara bildirim gönderilir.

    > [!NOTE]
    > Uyumluluk ilkeleri atarken bazı grupları dahil edebilir veya dışlayabilirsiniz.

4. **Kaydet**'e tıklayın.

İlkeyi başarıyla oluşturduktan ve kaydettikten sonra **Cihaz uyumluluğu - İlkeler** listesinde görebilirsiniz. Listede **Atandı** ayarının **Evet** olarak belirlenmiş olduğuna dikkat edin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Windows 10 cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için bir uyumluluk ilkesi oluşturmak ve atamak amacıyla Intune’u kullandınız. Windows cihazları için uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da Windows cihazları için bir cihaz uyumluluk ilkesi ekleme](compliance-policy-create-windows.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: İstemci uygulaması ekleme ve atama](quickstart-add-assign-app.md)