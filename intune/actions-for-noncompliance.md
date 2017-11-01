---
title: "Intune ile uyumsuzluğa yönelik eylemler"
titleSuffix: Intune on Azure
description: "Intune ile uyumsuzluğa yönelik eylemler oluşturmayı öğrenin"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3adc3c01d4657accfdb5cd70970ff191d06a9aef
ms.sourcegitcommit: a1c751959c9b3d5678bd9d67007e762df30eab59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2017
---
# <a name="automate-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemleri otomatikleştirme

**Uyumsuzluğa yönelik eylemler**, uyumluluk ilkesi ölçütlerini sağlamayan cihazlara uygulanacak zamana göre sıralı bir dizi eylem yapılandırmanıza olanak sağlar. Bir cihazın uyumluluk ilkesi ölçütlerini sağlamadığı algılandığında, Intune varsayılan olarak bu cihazı derhal uyumsuz olarak işaretler ve Azure AD Koşullu Erişim ise cihazı engeller. **Uyumsuzluğa yönelik eylemler**, uyumlu olmayan bir cihazla ilgili ne yapılması gerektiğine karar verirken daha fazla esneklik sağlar. Örneğin, cihazı hemen engellememeye karar verebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

İki tür eylem vardır:

-   **Son kullanıcıları e-posta ile bilgilendir**: Son kullanıcıya göndermeden önce e-posta bildiriminizi özelleştirebilirsiniz. Intune konu, ileti gövdesi, şirket logosunun dahil edilmesi, iletişim bilgileri ve ek alıcılar ile ilgili özelleştirme yapılmasına olanak sağlar.

-   **Cihazı uyumsuz olarak işaretle**: Cihazın uyumsuz olarak işaretleneceği gün sayısını belirleyebilirsiniz. Bu engelleme anında olabilir ancak kullanıcıya cihazını uyumluluk ilkeleriniz ile uyumlu hale getirmesi için bir mehil süresi de tanıyabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Uyumsuzluğa yönelik eylem ayarlanabilmesi için en az bir adet cihaz uyumluluk ilkesi oluşturulmuş olmalıdır.

-   Aşağıdakiler için cihaz uyumluluk ilkesi oluşturmayı öğrenin:

    -   [Outlook Web Access (OWA)](compliance-policy-create-android.md)

    -   [Android for Work](compliance-policy-create-android-for-work.md)

    -   [Android](compliance-policy-create-ios.md)
    
    -   [macOS](compliance-policy-create-mac-os.md)

    -   [Windows](compliance-policy-create-windows.md)

Cihaz uyumluluk ilkelerini kullanarak cihazların kurumsal kaynakları kullanmasını engellemeyi planlıyorsanız Azure AD koşullu erişiminin ayarlanıp hazırlanmış olması gerekir.

- [EMS koşullu erişiminin kurulumunu yapmayı](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access) öğrenin.

Ek olarak, bir bildirim iletisi şablonu oluşturulmuş olmalıdır. Bildirim iletisi şablonu, uyumsuzluğa yönelik eylem oluşturma sürecinde kullanıcılarınıza e-posta göndermek için kullanılır.

### <a name="to-create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturmak için

1. [Azure portalında Intune](https://portal.azure.com)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune**’u seçin

4. **Cihaz uyumluluğu**’nu ve daha sonra **Yönet** bölümü altında **Bildirimler**‘i seçin.

5. **Bildirim oluştur**’u seçin ve aşağıdakileri girin:

    a.  Ad

    b.  Konu

    c.  İleti

    d.  E-posta üst bilgisi – Şirket logosunu ekle

    e.  E-posta alt bilgisi – Şirket adını ekle

    f.  E-posta alt bilgisi – İletişim bilgilerini ekle

![bildirim iletisi şablonu örneği](./media/actionsfornoncompliance-1.PNG)

Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır.

> [!NOTE] 
> Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

## <a name="to-create-actions-for-non-compliance"></a>Uyumsuzluğa yönelik eylem oluşturmak için

> [!TIP]
> Intune, varsayılan olarak uyumsuzluk eylemleri bölümünde önceden tanımlı bir eylem sağlar. Bu, cihaz uyumluluk ilkesi ölçütlerini sağlamadığı algılanan bir cihazı uyumsuz olarak işaretleme eylemidir. Algılamanın ardından cihazın ne kadar bir süre sonra uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Bu eylem kaldırılamaz.

Yeni bir cihaz uyumluluk ilkesi oluştururken veya mevcut bir cihaz uyumluluk ilkesini düzenleyerek bir eylem ekleyebilirsiniz.

1.  Intune iş yükünde **Cihaz uyumluluk ilkeleri** dikey penceresinden **Yönet** bölümünün altındaki **İlkeler**’i seçin.

2.  Bir cihaz uyumluluk ilkesine tıklayıp seçin, daha sonra **Yönet** bölümünün altındaki **Özellikler**’i seçin.

3.  **Cihaz uyumluluk ilkesi özellikleri** dikey penceresi açılır. **Uyumsuzluğa yönelik eylemler**’i seçin.

4.  Uyumsuzluğa yönelik eylemler dikey penceresi açılır. Eylem parametrelerini belirlemek için **Ekle**’yi seçin. Önceden oluşturulmuş ileti şablonunu, ek alıcıları ve mehil süresi zaman çizelgesini seçebilirsiniz. Zaman çizelgesinde gün sayısını (0 ila 365) belirtebilir ve daha sonra koşullu erişim ilkelerini zorlayabilirsiniz. Gün sayısı olarak **0** belirtilmesi, cihaz uyumluluk ilkeleriyle uyumsuz hale gelen cihazların kurumsal kaynaklara erişiminin koşullu erişim tarafından **hemen** engelleneceği anlamına gelir.

5.  Bilgileri ekledikten sonra **Ekle** ve ardından **Tamam**’ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

Cihaz uyumluluğu dikey penceresinde bulunan raporları çalıştırarak cihaz uyumluluğu etkinliğini izleyebilirsiniz. [Intune ile cihaz uyumluluğunu izleme](device-compliance-monitor.md) hakkında daha fazla bilgi edinin
