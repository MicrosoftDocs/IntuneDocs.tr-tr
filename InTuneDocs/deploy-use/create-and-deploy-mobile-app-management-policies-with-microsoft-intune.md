---
title: "MAM ilkelerini oluşturma ve dağıtma | Microsoft Intune"
description: "Mobil uygulama yönetimi ilkelerini oluşturmak ve dağıtmak için, bu konu başlığı altında verilen adım adım yönergeleri kullanın."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 05b898ffdd0b76eb04d344adb3cfb20ec15aeb52


---

# <a name="create-and-deploy-mobile-app-management-policies-with-microsoft-intune"></a>Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma
Mobil uygulama yönetimi (MAM) ilkeleri, Intune tarafından yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. MAM ilkelerinin çalışmasıyla ve Intune MAM ilkeleri tarafından desteklenen senaryolarla ilgili daha ayrıntılı bir açıklama için bkz. [Mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Bu konu başlığı altında, **Azure portalında** MAM ilkesi oluşturma işlemi açıklanır. Azure portalı, MAM ilkelerinin oluşturulacağı yeni yönetim konsoludur ve MAM ilkelerini oluşturmak için bu portalı kullanmanızı öneririz. Azure portalı, aşağıdaki MAM senaryolarını destekler:
- Intune'a kayıtlı cihazlar.
- Üçüncü taraf MDM çözümleri tarafından yönetilen cihazlar.
- Hiçbir MDM çözümü tarafından yönetilmeyen cihazlar (KGC).

>[!IMPORTANT]
Şu anda cihazlarınızı yönetmek için **Intune yönetici konsolunu** kullanıyorsanız, aşağıdakileri göz önünde bulundurun:

> * [Intune yönetici konsolu](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanılarak Intune’a kaydedilmiş cihazlara yönelik uygulamaları destekleyen bir MAM ilkesi oluşturabilirsiniz.
> * Intune yönetici konsolunda oluşturulan MAM ilkeleri, Azure portalına aktarılamaz.  MAM ilkeleri, Azure portalında yeniden oluşturulmalıdır.

> * Intune yönetici konsolunda tüm MAM ilkesi ayarlarını göremeyebilirsiniz. Azure portalı, MAM ilkeleri oluşturmak için yeni yönetim konsoludur.

> * Yönetilen uygulamaları dağıtmak için, Intune yönetici konsolunda bir MAM ilkesi oluşturmalısınız. Bu durumda, hem Intune yönetici konsolunda hem de Azure portalında MAM ilkeleri oluşturmak isteyebilirsiniz: yönetilen uygulamaları dağıtabileceğinizden emin olmak için Intune yönetici konsolunda ve tüm MAM ilkesi ayarlarını barındıran yeni yönetici konsolu olduğu için Azure portalında.

> * Hem Intune yönetici konsolunda hem de Azure portalında MAM ilkeleri oluşturursanız, uygulamalara Azure portalında oluşturulan ilke uygulanır.

Android ve iOS platformlarında desteklenen ilke ayarları listesini görmek için, aşağıdakilerden birini seçin:

> [!div class="op_single_selector"]
- [iOS ilkeleri](ios-mam-policy-settings.md)
- [Android ilkeleri](android-mam-policy-settings.md)

##  <a name="create-a-mam-policy"></a>MAM ilkesi oluşturma
MAM ilkesi oluşturmadan önce, [önkoşullar ve destek](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) bilgilerini gözden geçirin.
1.  **Intune mobil uygulama yönetimi &gt; Ayarlar**’ı seçerek **Ayarlar** dikey penceresini açın.

    ![Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Azure portalını ilk kez kullanıyorsanız, portalı tanımak için öncelikle [Microsoft Intune MAM ilkeleri için Azure portalı](azure-portal-for-microsoft-intune-mam-policies.md) konusunu okuyun.

2.  **Ayarlar** dikey penceresinde **Uygulama ilkesi**’ni seçin. Yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama ilkesi** dikey penceresi açılır. **İlke ekle**‘yi seçin.

    ![İlke ekle menü seçeneğinin vurgulandığı Uygulama ilkesi dikey penceresinin ekran görüntüsü ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  İlke için bir ad yazın, kısa bir açıklama ekleyin ve iOS veya Android için ilke oluşturmak üzere platform türünü seçin. Her platform için birden çok ilke oluşturabilirsiniz.

    ![İlke ekle dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Kullanılabilir uygulamaların listesini görüntüleyen **Uygulamalar dikey penceresini** açmak için **Uygulamalar**'ı seçin. Oluşturmakta olduğunuz ilke ile ilişkilendirmek istediğiniz bir veya daha fazla uygulamayı listeden seçin. Uygulamaları seçtikten sonra, seçiminizi kaydetmek için **Uygulamalar** dikey penceresinin altındaki **Seç**'i kullanın.

    > [!IMPORTANT]
    > Bir ilke oluşturmak için en az bir uygulama seçmeniz gerekir.

5.  **İlke ekle dikey penceresinde** **Gerekli ayarları yapılandır**’ı seçerek ilke ayarları dikey penceresini açın.

    İlke ayarlarının iki kategorisi vardır: **Veri konumu değiştirme** ve **Erişim**.  Veri konumu değiştirme ilkeleri, uygulama içindeki ve dışındaki veri hareketleri için geçerlidir. Erişim ilkeleri ise son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirler.
    Başlamanıza yardımcı olması için ilke ayarlarına varsayılan değerler atanmıştır. Varsayılan değerler gereksinimlerinizi karşılıyorsa değişiklik yapmanız gerekmez.

    > [!TIP]
    > Bu ilke ayarları, yalnızca uygulamalar iş bağlamında kullanılırken uygulanır.  Son kullanıcı, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez.

    ![Ayarlar dikey penceresiyle İlke ekle dikey penceresinin birlikte ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin.  **İlke ekle** dikey penceresine geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

    ![Uygulamaların ve Ayarların yapılandırıldığını gösteren İlke ekle dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)



İlke oluşturmayı önceki yordamda açıklandığı şekilde tamamladığınızda, ilke kullanıcılara dağıtılmaz. Bir ilkeyi dağıtmak için aşağıdaki "Bir ilkeyi kullanıcılara dağıtma" bölümüne bakın.

> [!IMPORTANT]
> Uygulama için Intune yönetici konsolunu kullanarak bir MAM ilkesi ve Azure portalını kullanarak başka bir MAM ilkesi oluşturursanız, Azure portalını kullanarak oluşturduğunuz ilke önceliklidir. Ancak, Intune veya Configuration Manager konsolunda yapılan raporlamada, Intune yönetici konsolunda oluşturulan ilke ayarları belirtilir. Örneğin:
>
> -   Intune yönetici konsolunda, uygulamadan kopyalama yapılmasını engelleyen bir MAM ilkesi oluşturdunuz.
> -   Azure konsolunda, uygulamadan kopyalama yapılmasına izin veren bir MAM ilkesi oluşturdunuz.
> -   Bu ilkelerin ikisini de aynı uygulamayla ilişkilendirdiniz.
> -   Azure konsolunda oluşturduğunuz ilke öncelik kazanır ve kopyalamaya izin verilir.
> -   Ancak, Intune konsolundaki durum ve raporlar, hatalı bir şekilde kopyalamanın engellendiğini belirtir.

## <a name="deploy-a-policy-to-users"></a>Bir ilkeyi kullanıcılara dağıtma

1.  **İlke** dikey penceresinde  **Kullanıcı grupları**‘nı seçerek **Kullanıcı grupları** dikey penceresini açın. **Kullanıcı grupları** dikey penceresinde **Kullanıcı grubu ekle**’yi seçerek **Kullanıcı grubu ekle** dikey penceresini açın.

    ![Kullanıcı grubu ekle menü seçeneğinin vurgulandığı Kullanıcı grupları dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.   **Kullanıcı grubu ekle** dikey penceresinde kullanıcı gruplarının listesi gösterilir. Bu liste **Azure Active Directory**’deki tüm güvenlik gruplarını içerir. Bu ilkenin geçerli olmasını istediğiniz kullanıcı gruplarını seçin ve sonra da **Seç**'i belirleyin. **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

    ![Azure Active Directory kullanıcılarının listesini gösteren Kullanıcı grubu ekle dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    Bir ilke oluşturdunuz ve kullanıcılara dağıttınız.

Yalnızca [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansları atanmış kullanıcılar ilkeden etkilenir. Seçtiğiniz güvenlik grubunda olan ve atanmış [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı bulunmayan kullanıcılar etkilenmez.

>[!IMPORTANT]
> iOS ve Android cihazlarınızı yönetmek için Configuration Manager ile Intune kullanıyorsanız ilke yalnızca doğrudan seçtiğiniz grupta bulunan kullanıcılara uygulanır. Seçtiğiniz grubun içindeki alt grupların üyeleri etkilenmez.

Son kullanıcılar uygulamaları App Store veya Google Play’den indirebilir. Daha fazla bilgi için bkz.:
* [Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

##  <a name="change-existing-policies"></a>Mevcut ilkeleri değiştirme
Mevcut ilkeyi düzenleyebilir ve bunu hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde, uygulamalarda oturum açmış olan kullanıcılar bu değişiklikleri 8 saat boyunca görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulama oturumunu kapatması ve yeniden oturum açması gerekecektir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamalar listesini değiştirmek için

1.  **Uygulama ilkesi** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. Seçtiğiniz ilkeye özel bir dikey pencere açılır.

    ![Ayrı bir dikey pencerede açılmış mevcut ilkenin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  İlke dikey penceresinde **Hedeflenen uygulamalar**’ı seçerek uygulama listesini açın.

3.  Uygulamaları listeden kaldırın veya listeye ekleyin ve değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin.

### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için

1.  **Uygulama ilkesi** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. Seçtiğiniz ilkeye özel bir dikey pencere açılır.

2.  İlke dikey penceresinde **Kullanıcı grupları**’nı seçerek, bu ilkeye sahip geçerli kullanıcı gruplarının listesini gösteren **Kullanıcı grubu** dikey penceresini açın.

3.  İlkeye yeni kullanıcı grubu eklemek için **Kullanıcı grubu ekle**'yi seçin ve sonra da kullanıcı grubunu seçin. İlkeyi seçtiğiniz gruba dağıtmak için **Seç**öğesini seçin.

    ![İki kullanıcı grubunun seçili olduğu Kullanıcı grubu ekle dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Bir kullanıcı grubunu silmek için önce kaldırmak istediğiniz kullanıcı grubunu vurgulayın. Ardından üç noktaya (…) tıklayın ve **Sil**'i seçerek kullanıcı grubunu kaldırın.

    ![Sil seçeneğinin gösterildiği ekran görüntüsü ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>İlke ayarlarını değiştirmek için

1.  **Uygulama ilkesi** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. Seçtiğiniz ilkeye özel bir dikey pencere açılır.

    ![Ayrı bir dikey pencerede açılman mevcut ilkenin ekran görüntüsü ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  **İlke ayarları**’nı seçerek **İlke ayarları** dikey penceresini açın.

3.  Ayarları değiştirin ve **Kaydet** simgesini seçerek yaptığınız değişiklikleri kaydedin.

    ![En üstünde kaydet menü seçeneğinin gösterildiği İlke ayarları dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>İlke ayarları
iOS ve Android ilke ayarlarının tam listesini görmek için, aşağıdakilerden birini seçin:

> [!div class="op_single_selector"]
- [iOS ilkeleri](ios-mam-policy-settings.md)
- [Android ilkeleri](android-mam-policy-settings.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve kullanıcı durumunu izleme](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Ayrıca bkz.
* [Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->

