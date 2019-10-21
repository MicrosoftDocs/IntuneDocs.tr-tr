---
title: iOS cihazlarını kaydetme - Cihaz Kayıt Programı
titleSuffix: Microsoft Intune
description: Şirkete ait iOS cihazları Aygıt Kayıt Programı’nı kullanarak kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 339f6b9476dae438d898b97abcaf3c1759fe9cfc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503339"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme

Artık Apple'ın [Aygıt Kayıt Programı (DEP)](https://deploy.apple.com) aracılığıyla satın alınan iOS cihazlarını Intune ile yönetebilirsiniz. DEP, hiç dokunmadan çok sayıda cihazı kaydetmenizi sağlar. iPhone ve iPad’ler gibi cihazları doğrudan kullanıcılara gönderebilirsiniz. Kullanıcı cihazı açtığında, önceden yapılandırılmış ayarları ile Kurulum Yardımcısı çalıştırılır ve cihaz yönetime kaydedilir.

DEP kaydını etkinleştirmek için Intune ve Apple DEP portallarını birlikte kullanmanız gerekir. Cihazlarınızı, Intune ile yönetilmek üzere atayabilmeniz için seri numaraları listesi veya sipariş numarası gereklidir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturun.

Bu arada, DEP kaydının [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md) birlikte kullanılamayacağına dikkat edin.

> [!NOTE]
> DEP, son kullanıcı tarafından kaldırılamayan cihaz yapılandırmasını ayarlar. Bu nedenle, [DEP 'e](../fundamentals/migration-guide-considerations.md)geçmeden önce cihazın bir kullanıma hazır (yeni) duruma dönmesi için temizlenmiş olması gerekir.

## <a name="dep-and-the-company-portal"></a>DEP ve Şirket Portalı

DEP kayıtları, Şirket Portalı uygulamasının App Store sürümü ile uyumlu değildir. Kullanıcılara bir DEP cihazında Şirket Portalı uygulamasına erişim izni verebilirsiniz. Bunlara erişim sağlamak için, DEP profilinde VPP 'yi (toplu satın alma programı) **yükleme Şirket portalı** kullanarak uygulamayı cihaza gönderin. Daha fazla bilgi için bkz. [Apple aygıt kayıt programı iOS cihazlarını otomatik olarak kaydetme](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

 Şirket Portalı uygulamasını DEP ile zaten kaydedilmiş cihazlara yükleyebilirsiniz. Bunu yapmak için, [uygulama yapılandırma ilkesi](../apps/app-configuration-policies-use-ios.md) uygulanmış şekilde ıntune aracılığıyla şirket portalı uygulamasını dağıtın.

## <a name="what-is-supervised-mode"></a>Denetimli mod nedir?

Apple, iOS 5 sürümünde denetimli modu kullanıma sundu. Denetimli moddaki herhangi bir iOS cihaz, daha fazla denetimle yönetilebilir. O neden bu mod, özellikle şirkete ait cihazlar için kullanışlıdır. Intune, Apple Aygıt Kayıt Programı’nın (DEP) bir parçası olarak denetimli mod için cihazların yapılandırılmasını destekler.

Denetlenmeyen DEP cihazları destek iOS 11'de sona ermiştir. iOS 11 ve üstünde, DEP yapılandırmalı cihazların her zaman denetimli olması gerekir. Gelecekteki bir iOS sürümünde DEP denetimli bayrağı yoksayılacaktır.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Önkoşullar
- [Apple Aygıt Kayıt Programı](http://deploy.apple.com)’nda satın alınmış cihazlar
- [Mobil Cihaz Yönetimi (MDM) Yetkilisi](../fundamentals/mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Bir Apple DEP belirteci alma

iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirteci dosyasına (.p7m) ihtiyacınız vardır. Bu belirteç, Intune'un şirketinize ait olan DEP cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

DEP belirtecini oluşturmak için Apple DEP portalını kullanın. Cihazları yönetim için Intune’a atamak için DEP portalını da kullanabilirsiniz.

> [!NOTE]
> Belirteci Azure’a geçirmeden önce klasik Intune portalında silerseniz Intune, silinen bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portalından tekrar silebilirsiniz.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>1\. Adım Belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**'yi seçin.

    ![Bir kayıt programı belirteci alın.](./media/device-enrollment-program-enroll-ios/image01.png)

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>2\. Adım Anahtarınızı kullanarak Apple’dan bir belirteç indirin.

1. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı için bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.
2. Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin.

3. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.
4. **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

5. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin. .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

6. **Dağıtım Programları** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**'e gidin.
7. **Cihazları Şuna Göre Seç:** öğesinin altında cihazların nasıl tanımlanacağını belirtin:
    - **Seri Numarası**
    - **Sipariş Numarası**
    - **CSV Dosyası Yükle**.

   ![Cihazları seri numarasına göre seçme, eylem seç öğesini Sunucuya ata olarak seçme ve sunucu adını seçme ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/enrollment-program-token-specify-serial.png)

8. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Adım 3. Bu belirteci oluşturmak için kullanılan Apple kimliğini kaydedin.

Azure portalında Intune’da ileride başvurmak üzere Apple kimliğini sağlayın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>Adım 4. Belirtecinizi karşıya yükleyin ve kapsam etiketlerini seçin.

1. **Apple belirteci** kutusunda sertifika (.pem) dosyasına göz atın ve **Aç**’ı seçin.
2. Bu DEP belirtecine [kapsam etiketi](../fundamentals/scope-tags.md) uygulamak istiyorsanız **Kapsam (etiketler)** öğesini ve ardından istediğiniz kapsam etiketlerini seçin. Belirtece uygulanan kapsam etiketleri, bu belirtece eklenen profiller ve cihazlar tarafından devralınır.
3. **Oluştur**’u seçin.

Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Belirtecinizi yüklediğinize göre, DEP cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar. DEP belirteci başına 100 kayıt profili sınırı vardır.

> [!NOTE]
> Bir VPP belirteci için yeterli Şirket Portalı lisansı yoksa veya belirtecin süresi dolmuşsa cihazlar engellenir. Belirtecin süresinin dolmasına az zaman kaldığında veya lisans sayısı azaldığında Intune'da bir uyarı görüntülenir.
 

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.
2. Bir belirteç seçin, **profiller** > **Profil oluştur** > **iOS**' u seçin.

    ![Profil oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image04.png)

3. **Temel bilgiler** sayfasında, yönetim amaçları için profil Için bir **ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) hakkında daha fazla bilgi edinin.

    ![Profil adı ve açıklaması.](./media/device-enrollment-program-enroll-ios/image05.png)

4. **İleri ' yi seçin: cihaz yönetimi ayarları**.

5. **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedilmesi gerektiğini seçin.
    - **Kullanıcı Benzeşimi ile Kaydet** - Uygulamaları yükleme gibi hizmetler için Şirket Portalı’nı kullanmak isteyen kullanıcılara ait cihazlar için bu seçeneği seçin. ADFS kullanılıyorsa ve kayıt profilinde **Kurulum Yardımcısı yerine Şirket Portalı ile kimliği doğrula** ayarı **Hayır** değerine ayarlandıysa, [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) gerekir.

    - **Kullanıcı Benzeşimi Olmadan Kaydetme** - Tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği seçin. Yerel Kullanıcı verilerine erişolmayan cihazlar için bu seçeneği kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

5. **Kullanıcı Benzeşimi ile Kaydet**’i seçerseniz, kullanıcıların Şirket Portalı yerine Apple Kurulum Yardımcısı ile kimlik doğrulama gerçekleştirmelerini sağlayabilirsiniz.

    ![Şirket Portalı ile kimlik doğrulayın.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Aşağıdakilerden birini yapmak istiyorsanız, kullanıcıların **Şirket portalı** **kimlik doğrulaması gereken yeri seçin** ' i belirleyin.
    >    - çok faktörlü kimlik doğrulaması kullanma
    >    - ilk kez oturum açarken parolalarını değiştirmesi gereken kullanıcılara bunu bildirme
    >    - kayıt sırasında kullanıcılardan süresi dolmuş parolalarını sıfırlamalarını isteme
    >
    > Apple Kurulum Yardımcısı ile kimliği doğrularken bunlar desteklenmez.

6. **Kullanıcıların kimliğini doğrulamak**için **Şirket Portalı** seçtiyseniz, Şirket portalı cihaza otomatik olarak yüklemek için bir VPP belirteci kullanabilirsiniz. Bu durumda kullanıcının bir Apple Kimliği sağlamasına gerek kalmaz. VPP belirteciyle Şirket Portalı'nı yüklemek için, **VPP ile Şirket Portalı yükle**'nin altında bir belirteç seçin. Şirket Portalı VPP belirtecine zaten eklenmiş olmasını gerektirir. İlkeyi kullanıcılara gerektirecek şekilde yapılandırmayın, Intune bu kayıt profili uygulanmış cihazlara Şirket Portalı otomatik olarak yükler. Belirtecin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli cihaz lisansınız olduğundan emin olun. Belirtecin süresi dolarsa veya yeterli lisans yoksa, Intune bunun yerine App Store Şirket Portalı’nı yükler ve Apple Kimliği ister. 

    > [!NOTE]
    > **Kullanıcıların kimlik doğrulaması yapması gereken yeri seçin** **Şirket portalı**, cihaz kayıt IŞLEMININ, Şirket portalının DEP cihazına indirilmekte olan ilk 24 saat içinde gerçekleştirildiğinden emin olun. Aksi takdirde kayıt başarısız olabilir ve cihazı kaydetmek için bir fabrika sıfırlaması gerekecektir.
    
    ![VPP ile şirket portalı yükle ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. **Kullanıcıların kimlik doğrulaması yapması gereken yeri seç**Için **Kurulum Yardımcısı** ' nı seçtiyseniz, ancak aynı zamanda koşullu erişimi kullanmak veya cihazlarda şirket uygulamaları dağıtmak istiyorsanız, Şirket portalı cihazlara yüklenmelidir. Bunu yapmak için, **Şirket portalı yüklemek**için **Evet** ' i seçin.  Kullanıcıların uygulama mağazasındaki kimlik doğrulaması yapmadan Şirket Portalı almasını istiyorsanız, **VPP ile şirket portalı yüklemeyi** seçin ve bir VPP belirteci seçin. Belirtecin kullanım süreleri dolana ve Şirket Portalı uygulamasının doğru bir şekilde dağıtılması için yeterli cihaz lisansına sahip olduğunuzdan emin olun.

8. **Şirket Portalı’nı VPP ile yükle** seçeneği için bir belirteç seçtiyseniz Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı Tekli Uygulama Moduna (yani Şirket Portalı uygulaması için) kilitleyebilirsiniz. Bunun için **Kimlik doğrulaması tamamlanana kadar Şirket Portalı’nı Tekli Uygulama Modunda çalıştır** ayarını **Evet** olarak ayarlayın. Cihazı kullanmak için kullanıcının önce Şirket Portalı’nda oturum açarak kimliğini doğrulaması gerekir.

    Multi-Factor Authentication tek bir uygulama modunda kilitlenmiş tek bir cihazda desteklenmez. Bu sınırlama, cihazın ikinci kimlik doğrulama faktörünü tamamlaması için farklı bir uygulamaya geçiş yaptığından oluşur. Bu nedenle, tek bir App Mode cihazında çok faktörlü kimlik doğrulaması istiyorsanız ikinci faktör farklı bir cihazda olmalıdır.

    Bu özellik yalnızca iOS 11.3.1 ve üzeri sürümlerde desteklenir.

   ![Tek uygulama modunun ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

9. Bu profili kullanan cihazların denetimli olmasını istiyorsanız, **denetimli**için **Evet** ' i seçin.

    ![Cihaz Yönetimi Ayarları ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/supervisedmode.png)

    **Denetimli** cihazlar, varsayılan olarak size daha fazla yönetim seçeneği verir ve Etkinleştirme Kilidi’ni devre dışı bırakır. Microsoft, özellikle fazla sayıda iOS cihaz dağıtanlar için denetimli modu etkinleştirme mekanizması olarak DEP’in kullanılmasını önerir.

    Kullanıcılara cihazlarının denetimli olduğu iki yolla bildirilir:

   - Kilit ekranında “Bu iPhone, Contoso tarafından yönetilmektedir.” yazar.
   - **Ayarlar** > **Genel** > **Hakkında** kısmında “Bu iPhone denetimlidir.” yazar. ifadesi ve

     > [!NOTE]
     > Denetim olmadan kaydedilen bir cihaz, yalnızca Apple Configurator kullanılarak sıfırlanıp denetimli yapılabilir. Cihazı bu şekilde sıfırlamak için bir iOS cihazı USB kablosu ile bir Mac’e bağlamak gerekir. Bu konu hakkında daha fazla bilgi için [Apple Configurator belgelerine](http://help.apple.com/configurator/mac/2.3) bakın.

10. Bu profili kullanan cihazlarda kilitli kayıt isteyip istemediğinizi seçin. **Kilitli kayıt**, yönetim profilinin **Ayarlar** menüsünden kaldırılmasını sağlayan iOS ayarlarını devre dışı bırakır. Cihazı kaydettikten sonra cihazı silmeden bu ayarı değiştiremezsiniz. Bu cihazlarda **Denetimli** Yönetim Modu *Evet* olarak ayarlı olmalıdır. 

11. Bu profili kullanan cihazların **Bilgisayarlarla eşitleme** imkanının olup olmayacağını seçin. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

12. Önceki adımda **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz içeri aktaracak bir Apple Configurator Sertifikası seçin.

13. Her bir arka arkaya iade edildiğinde otomatik olarak uygulanan cihazlar için bir adlandırma biçimi belirtebilirsiniz. Adlandırma şablonu oluşturmak için **Cihaz adı şablonu uygula** bölümünde **Evet**'i seçin. Ardından **Cihaz Adı Şablonu**'na bu profili kullanan cihazlar için kullanılacak şablonu girin. Cihaz türünü ve seri numarasını içeren bir şablon biçimi belirtebilirsiniz. 

14. **İleri ' yi seçin: Kurulum Yardımcısı özelleştirmesi**.

15. **Kurulum Yardımcısı özelleştirmesi** sayfasında, aşağıdaki profil ayarlarını yapılandırın: ![Kurulum Yardımcısı özelleştirmesi. ](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Departman ayarları | Description |
    |---|---|
    | <strong>Departman Adı</strong> | Kullanıcı, etkinleştirme sırasında <strong>Yapılandırma Hakkında</strong> öğesine dokunduğunda görüntülenir. |
    |    <strong>Departman Telefonu</strong>     | Kullanıcı, etkinleştirme sırasında <strong>Yardım Gerekli</strong> düğmesine dokunduğunda görüntülenir. |

    Kullanıcı kurulum işlemleri sırasında cihazda Kurulum Yardımcısı ekranlarının gizlenmesini tercih edebilirsiniz.
    - **Gizle**'yi seçerseniz, kurulum sırasında ekran görüntülenmez. Cihaz kurulumu yapıldıktan sonra, kullanıcı yine **Ayarlar** menüsüne gidip özelliği ayarlayabilir.
    - **Göster**'i seçerseniz, kurulum sırasında ekran görüntülenir. Kullanıcı bazen hiçbir eylem yapmadan ekranı atlayabilir. Ama daha sonra cihazın **Ayarlar** menüsüne gidebilir ve özelliği ayarlayabilir. 


    | Kurulum Yardımcısı ekran ayarları | **Göster**'i seçerseniz, kurulum sırasında cihaz... |
    |------------------------------------------|------------------------------------------|
    | <strong>Geçiş kodu</strong> | Kullanıcıdan geçiş kodu ister. Güvenliği sağlanmayan veya erişim denetimi başka bir yolla (cihazı tek uygulamayla sınırlandıran bilgi noktası modu gibi) sağlanan cihazlar için her zaman geçiş kodu isteyin. |
    | <strong>Konum Hizmetleri</strong> | Kullanıcıdan konum ister. |
    | <strong>Geri Yükle</strong> | Uygulamalar & veri ekranını görüntüleyin. Bu ekran kullanıcıya cihazı kurarken iCloud Backup'tan verileri geri yükleme veya aktarma seçeneği sağlar. |
    | <strong>iCloud ve Apple Kimliği</strong> | Kullanıcıya Apple KIMLIĞI ile oturum açma ve iCloud kullanma seçeneklerini sunun.                         |
    | <strong>Hüküm ve Koşullar</strong> | Kullanıcının Apple'ın hüküm ve koşullarını kabul etmesini gerektirir. |
    | <strong>Touch ID</strong> | Kullanıcıya cihaz için parmak izi tanımlama özelliğini ayarlama seçeneği sağlar. |
    | <strong>Apple Pay</strong> | Kullanıcıya cihazda Apple Pay ayarlama seçeneği sağlar. |
    | <strong>Yakınlaştır</strong> | Kullanıcıya cihazı ayarlarken ekranı yakınlaştırma seçeneği sağlar. |
    | <strong>Siri</strong> | Kullanıcıya Siri'yi ayarlama seçeneği sağlar. |
    | <strong>Tanılama Verileri</strong> | Tanılama ekranını kullanıcıya görüntüleyin. Bu ekran kullanıcıya Apple'a tanılama verileri gönderme seçeneği sağlar. |
    | <strong>Görüntü Tonu</strong> | Kullanıcıya Görüntü Tonunu açma seçeneği sunar. |
    | <strong>Gizlilik</strong> | Kullanıcıya Gizlilik ekranını gösterir. |
    | <strong>Android Geçişi</strong> | Kullanıcıya Android cihazdan veri geçirme seçeneği sunar. |
    | <strong>iMessage ve FaceTime</strong> | Kullanıcıya IMessage ve çok yönlü saat ayarlama seçeneği sunun. |
    | <strong>Ekleme</strong> | Kapak Sayfası, Çok Görevli Çalışma ve Denetim Merkezi gibi kullanıcı eğitimine yönelik ekleme bilgi ekranlarının görüntülenmesini sağlar. |
    | <strong>Watch Geçişi</strong> | Kullanıcıya Watch cihazından veri geçirme seçeneği sunar. |
    | <strong>Ekran Süresi</strong> | Ekran Süresi ekranını görüntüler. |
    | <strong>Yazılım Güncelleştirmesi</strong> | Zorunlu yazılım güncelleştirmesi ekranı görüntüler. |
    | <strong>SIM Ayarları</strong> | Kullanıcıya hücresel plan ekleme seçeneği sunar. |
    | <strong>Görünüm</strong> | Kullanıcıya Görünüm ekranını gösterir. |
    | <strong>Hızlı dil</strong>| Kullanıcı için hızlı dil ekranını görüntüleyin. |
    | <strong>Tercih edilen dil</strong> | Kullanıcıya **tercih edilen dilini**seçme seçeneğini sunun. |
    | <strong>Cihazdan cihaza geçişe</strong> | Kullanıcıya verileri eski cihazlarından bu cihaza geçirme seçeneğini sunun.|
    

16. **İleri ' yi** seçerek **gözden geçir + oluştur** sayfasına gidin.

17. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune’da Azure portalında görmek için Intune’u Apple ile eşitleyebilirsiniz.

1. Azure portal Intune 'da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > > **cihazlarda** bir belirteç seçin > **eşitleme**. Kayıt programı cihazları düğümünün ve eşitleme bağlantısının ![Ekran görüntüsü. ](./media/device-enrollment-program-enroll-ios/image06.png)

   Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uygun hareket etmek için aşağıdaki kısıtlamaları getirir:
   - Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, Intune’a bağlı Apple MDM sunucusuna atanan seri numaraların tam güncelleştirilmiş bir listesini alır. Intune portalından silinen DEP cihazlarının atamasının DEP portalındaki Apple MDM sunucusundan da kaldırılması gerekir. Atamanın kaldırılmaması durumunda bu cihazlar tam eşitleme çalıştırılana kadar Intune'a yeniden aktarılamaz.   
   - Eşitleme 24 saatte bir otomatik olarak çalıştırılır. **Eşitle** düğmesine basarak da eşitleyebilirsiniz (en fazla 15 dakikada bir kez). Tüm eşitleme isteklerinin tamamlanması için 15 dakika verilir. Eşitleme tamamlanana kadar **Eşitle** düğmesi devre dışı kalır. Bu eşitleme, mevcut aygıt durumunu yeniler ve Apple MDM sunucusuna atanan yeni cihazları içeri aktarır.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

>[!NOTE]
>Ayrıca, **Apple Seri Numaraları** dikey penceresinde profillere seri numaralar da atayabilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata**'nın altında cihazlar için bir profil seçin > **Ata**’ya tıklayın.

### <a name="assign-a-default-profile"></a>Varsayılan bir profil atama

Belirli bir belirteç ile kaydedilen tüm cihazlara uygulanacak varsayılan bir profil seçebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Varsayılan Profil Ayarla**’yı seçin, açılan listeden bir profil seçin ve daha sonra **Kaydet**’e tıklayın. Profil, bu belirteçle kaydedilen tüm cihazlara uygulanacaktır.

## <a name="distribute-devices"></a>Cihazları dağıtma
Apple ve Intune arasında eşitlemeyi ve yönetimi etkinleştirdiniz ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir. Kullanıcı benzeşimi olmayan cihazlar, cihaz lisansı gerektirir. Etkinleştirilmiş bir cihaz, silinene kadar bir kayıt profili uygulayamaz.

Bkz. [iOS cihazınızı Aygıt Kayıt Programı ile Intune’a kaydetme](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>DEP belirtecini yenileme  
1. deploy.apple.com adresine gidin.  
2. **Sunucuları Yönet** altında yenilemek istediğiniz belirteç dosyasıyla ilişkili MDM sunucunuzu seçin.
3. **Yeni Belirteç Oluştur**’u seçin.

    ![Yeni belirteç oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. **Sunucu Belirteciniz**’i seçin.  
5. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri**’ne gidin ve belirteci seçin.
    ![Kayıt programı belirteçlerinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. **Belirteci yenile**’yi seçin ve orijinal belirteci oluşturmak için kullanılan Apple kimliğini girin.  
    ![Yeni belirteç oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Yeni indirilen belirteci karşıya yükleyin.  
9. **Belirteci yenile**’yi seçin. Belirtecin yenilendiğine dair onayı görürsünüz.   
    ![Onay ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/confirmation.png)