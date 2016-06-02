---
# required metadata

title: Cihaz kaydıyla ilgili sorunları giderme | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune’da cihaz kaydıyla ilgili sorunları giderme

Burada bazı cihaz kaydı sorunları, bunların nasıl giderileceği ve çözüleceği açıklanır.

> [!NOTE]
> Yönetilen cihaz kullanıcılarınız, gözden geçirmeniz için kayıt ve tanılama günlüklerini toplayabilir. Kullanıcılar için günlükleri toplama yönergeleri, şu konu başlıkları altında sağlanır:
>- [Android tanılama veri günlüklerini USB kablosu kullanarak BT yöneticinize gönderme](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
>- [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
>- [BT yöneticinize Android kayıt hatalarını gönderme](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
>- [BT yöneticinize iOS kayıt hatalarını gönderme](/intune/enduser/send-errors-to-your-it-admin-ios)


Bu bilgiler sorununuzu çözmezse, yardım almanın diğer yollarını öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).

## Cihaz Sınırına Ulaşıldı
**Sorun:** Bir kullanıcı, kayıt sırasında cihazında bir hata aldı (iOS cihazında **Şirket Portalı Geçici Olarak Devre Dışı** hatası gibi) ve Configuration Manager’daki DMPdownloader.log dosyası **DeviceCapReached** hatasını içeriyor.

**Çözüm:** Tasarım gereği, kullanıcılar 5’ten fazla cihaz kaydedemez.

### Kaydedilen ve izin verilen cihazların sayısını denetleme

1.  Intune yönetim portalında kullanıcıya 5’ten fazla cihaz atanmadığını doğrulayın

2.  Intune yönetim portalında Yönetici\Mobil Cihaz Yönetimi\Kayıt Kuralları altında Cihaz kaydı sınırı değerinin 5 olarak ayarlanıp ayarlanmadığını denetleyin

Mobil cihaz kullanıcıları şu URL’de cihazları silebilir: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/).

Yöneticiler, Azure Active Directory portalında cihazları silebilir.

### Azure Active Directory portalında cihazları silmek için

1.  [http://aka.ms/accessaad](http://aka.ms/accessaad) bağlantısına göz atın veya [https://portal.office.com](https://portal.office.com) sitesinde **Yönetici** &gt; **Azure AD**’ye tıklayın.

2.  Sayfanın sol tarafındaki bağlantıyı kullanarak Kuruluş Kimliğinizle oturum açın.

3.  Azure Aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem için kredi kartı veya ödeme gerekmez ( **Ücretsiz Azure Active Directory kaydınız** abonelik bağlantısına tıklayın).

4.   **Active Directory** ’yi ve sonra da kuruluşunuzu seçin.

5.   **Kullanıcılar** sekmesini seçin.

6.  Cihazlarını silmek istediğiniz kullanıcıyı seçin.

7.  **Cihazlar**’a tıklayın.

8.  Artık kullanımda olmayan veya tanımları yanlış olan cihazlar gibi uygun cihazları kaldırın.

> [!NOTE]

> [Şirkete ait cihazları Microsoft Intune’da Cihaz Kayıt Yöneticisi ile kaydetme](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) bölümünde açıklandığı gibi cihaz kaydı üst sınırından kaçınabilirsiniz.
>
> Bir kullanıcı oturumu için Koşullu Erişim ilkesi zorunlu tutulduysa, söz konusu kullanıcı hesabı Cihaz Kayıt Yöneticileri grubuna eklendiğinde kaydı tamamlayamaz.

## Profil yüklemesi başarısız oldu
**Sorun:** Bir kullanıcı, iOS veya Android cihazında **Profil yüklemesi başarısız oldu** hatasını alıyor.

### Başarısız olan profil yüklemesi sorunlarını giderme adımları

1.  Kullanıcıya, Intune hizmetinin kullandığınız sürümü için uygun lisansın atandığını onaylayın.

2.  Cihazın zaten başka bir MDM sağlayıcısıyla kaydedilmediğini ve cihaza önceden bir yönetim profili yüklenmediğini doğrulayın.

3.  iOS cihazları için, [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) adresine gidin ve istendiğinde profili yükleyin.

4.  iOS için Safari’nin ve Android için Chrome’un varsayılan tarayıcı olduğunu ve tanımlama bilgilerinin etkinleştirildiğini onaylayın.

## Şirket Portalı Geçici Olarak Devre Dışı
**Sorun:** Bir kullanıcı, cihazda **Şirket Portalı Geçici Olarak Devre Dışı** hatası alıyor.

### Şirket Portalı Geçici Olarak Devre Dışı hatasını giderme

1.  Intune Şirket Portalı uygulamasını cihazınızdan kaldırın.

2.  Cihazda tarayıcıyı, [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)adresine göz atın ve kullanıcı oturum açma işlemi yapmayı deneyin.

3.  Kullanıcı oturum açamazsa, başka bir ağ denemelerini sağlayın.

4.  Bu da başarısız olursa, kullanıcının kimlik bilgilerinin Azure Active Directory ile doğru eşitlendiğinden emin olun.

5.  Kullanıcı başarıyla oturum açarsa, iOS cihazı Intune Şirket Portalı uygulamasını yüklemenizi ve kaydetmenizi ister. Android cihazında Intel Şirket Portalı uygulamasını el ile yüklemeniz gerekir ve bunu yaptıktan sonra kaydetmeyi deneyebilirsiniz.

## MDM yetkilisi tanımlı değil
**Sorun:** Bir kullanıcı, **MDM yetkilisi tanımlı değil** hatası alıyor.

### MDM yetkilisi tanımlı değil hatasını giderme

1.  MDM Yetkilisinin kullandığınız Intune hizmetinin, yani Intune, O365 MDM veya Intune ile System Center Configuration Manager için uygun bir şekilde ayarlandığını doğrulayın. Intune için, MDM Yetkilisi **Yönetici** &gt; **Mobil Cihaz Yönetimi**’nde ayarlanır. Intune ile Configuration Manager için, Intune bağlayıcısını yapılandırırken ayarlarsınız ve O365’te bur bir ayardır (**Mobil Cihazlar**).

    > MDM yetkilisini ayarladıktan sonra, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) bölümünde açıklandığı gibi yalnızca Desteğe başvurarak değiştirebilirsiniz.

2.  Kullanıcının kimlik bilgilerinin Azure Active Directory’yle doğru eşitlendiğinden emin olun. Bunun için UPN değerlerinin Hesap Portalı’ndaki Active Directory bilgileriyle eşleşip eşleşmediğini denetleyin.
    UPN Active Directory bilgileriyle eşleşmiyorsa:

    1.  Yerel sunucuda DirSync’i kapatın.

    2.  Eşleşmeyen kullanıcıyı **Intune Hesap Portalı** kullanıcı listesinden silin.

    3.  Azure hizmetinin yanlış verileri kaldırması için bir saat kadar bekleyin.

    4.  DirSync’i yeniden açın ve şimdi kullanıcının doğru eşitlenip eşitlenmediğini denetleyin.

3.  Intune ile System Center Configuration Manager’ı kullandığınız senaryolarda, kullanıcının geçerli bir Bulut Kullanıcı Kimliği olduğunu doğrulayın:

    1.  SQL Management Studio'yu açın.

    2.  Uygun veritabanına bağlanın.

    3.  Veritabanları klasörünü açın ve **CM_DBName** klasörünü bulup açın; burada DBName, müşteri veritabanının adıdır.

    4.  En üstte Yeni Sorgu’ya tıklayın ve aşağıdaki sorguları yürütün:

        -   Tüm kullanıcıları görmek için:

        -   Belirli Kullanıcıları görmek için bu sorguyu kullanın; burada %testuser1%, aramak istediğiniz kullanıcının kullanıcıadı@etkialanı.com değerini temsil eder:

        Sorguyu yazdıktan sonra **!Execute** öğesine tıklayın.
        Sonuçlar döndürüldüğünde, bulut kullanıcı kimliğine bakın.  Hiç kimlik bulunmazsa, kullanıcının Intune’u kullanma lisansı yok demektir.

## Intune ile System Center Configuration Manager kullanırken mobil cihazlar kayboluyor
**Sorun:** Mobil cihazı Configuration Manager’a başarıyla kaydettikten sonra, bu cihaz mobil cihaz koleksiyonundan kayboluyor; ancak hala Yönetim Profili var ve CSS Ağ Geçidi’nde listeleniyor.

**Çözüm:** Etki alanına katılmayan cihazları kaldıran özel bir işleminiz varsa veya kullanıcı cihazı abonelikten devre dışı bırakırsa bu durum ortaya çıkabilir. Configuration Manager konsolunda cihazı hangi işlemin veya kullanıcı hesabının kaldırdığını denetlemek ve doğrulamak için, aşağıdaki adımları izleyin.

### Cihazın nasıl kaldırıldığını denetleme

1.  Configuration Manager yönetim konsolunda **İzleme** &gt; **Sistem Durumu** &gt; **Durum İletisi Sorguları**’nı seçin.

2.  **Elle Silinen Koleksiyon Üye Kaynakları**’na sağ tıklayın ve **İletileri Göster**’i seçin.

3.  Uygun bir saat/tarih seçin veya son 12 saati seçin.

4.  Söz konusu cihazı bulun ve cihazın nasıl kaldırıldığını gözden geçirin. Aşağıdaki örnekte, cihazın Bilinmeyen Uygulama yoluyla SCCMInstall hesabı tarafından silindiği gösterilir.

    ![Cihaz silme tanılamasının ekran görüntüsü](./media/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Configuration Manager’da etki alanı dışındaki, mobil veya ilgili cihazları otomatik olarak temizleyebilecek, zamanlanmış bir görev, komut dosyası veya başka bir işlemin bulunup bulunmadığını denetleyin.

## Intune’la birlikte System Center Configuration Manager kullanıldığında kayıtlı iOS cihazı konsolda gösterilmiyor
**Sorun:** Kullanıcı iOS cihazını kaydediyor ancak cihaz Configuration Manager yönetici konsolunda gösterilmiyor. Cihaz kayıtlı olduğunu göstermiyor. Olası nedenler:

- Intune Bağlayıcınızı bir hesaba kaydettikten sonra bunu başka bir hesaba kaydetmiş olabilirsiniz. 
- MDM sertifikasını bir hesaptan indirip başka bir hesapla kullanmış olabilirsiniz.


**Çözüm:** Aşağıdaki adımları uygulayın:

1. Windows Intune Bağlayıcısı’nın içinden iOS’u devre dışı bırakın. 
    1. Intune aboneliğine sağ tıklayın ve "Özellikler"i seçin.
    1. "iOS" sekmesinde "iOS kaydını etkinleştir" seçeneğinin işaretini kaldırın.



1. SQL’de, CAS DB’de aşağıdaki adımları çalıştırın
  
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%' 
    1. delete from MDMPolicy where PolicyType = 7 
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%' 
    1. delete from MDMPolicy where PolicyType = 11 
    1. delete from MDMPolicyAssignment where PolicyType = 11 
    1. DELETE Drs_Signals
1. SMS Executive Hizmeti’ni yeniden başlatın veya CM Sunucusu’nu yeniden başlatın 



1. Yeni bir APN sertifikası alın ve bunu karşıya yükleyin: Configuration Manager’ın sol bölmesinde Intune aboneliğine sağ tıklayın. **APNs sertifikası isteği oluştur**’u seçin ve yönergeleri izleyin.


## Makine zaten kaydoldu - Hata hr 0x8007064c
**Sorun:** Kayıt işlemi **Makine zaten kaydoldu** hatasıyla başarısız oluyor. Kayıt günlüğünde **hr 0x8007064c** hatası gösteriliyor
  
Bunun nedeni bilgisayarın daha önce kaydolmuş olması veya kayıtlı bir bilgisayarın kopyalanmış görüntüsünü içermesi olabilir. Önceki hesabın hesap sertifikası hala bilgisayarda duruyordur.



**Çözüm:** 

1. **Başlat** menüsünde **Çalıştır** -> **MMC** 
1. **Dosya** -> **Ek Bileşen Ekle/Kaldır**
1. **Sertifikalar**’a çift tıklayın, **Bilgisayar hesabı**’nı, **İleri**’yi ve **Yerel Bilgisayar**’ı seçin.
1. **Sertifikalar (Yerel bilgisayar)** seçeneğine çift tıklayın, **Kişisel/ Sertifikalar**’ı seçin. 
1. Sc_Online_Issuing tarafından verilen Intune sertifikasını arayın ve bulursanız silin
1. Varsa şu kayıt defteri anahtarını ve tüm alt anahtarlarını silin: ** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**.
1. Yeniden kaydetmeyi deneyin. 
1. Makine yine kaydedilmiyorsa, şu anahtarı arayın ve bulursanız silin: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95** 
1. Yeniden kaydetmeyi deneyin. 

    > [!IMPORTANT]
    > Bu bölüm, yöntem veya görev kayıt defterinde nasıl değişiklik yapacağınızı gösteren adımlar içerir. Bununla birlikte, kayıt defterinde yanlış değişiklikler yaparsanız ciddi sorunlar çıkabilir. Bu nedenle, bu adımları dikkatle izlediğinizden emin olun. Ek bir koruma için, değişiklikleri yapmadan önce kayıt defterini yedekleyin. Böylece bir sorun ortaya çıktığında kayıt defterini geri yükleyebilirsiniz.
    > Kayıt defterini yedekleme ve geri yükleme hakkında daha fazla bilgi için, [Windows’da kayıt defterini yedekleme ve geri yükleme](https://support.microsoft.com/en-us/kb/322756) konusunu okuyun.

## Şirket adı özel karakterler içeriyorsa ilke oluşturulamaz veya cihazlar kaydedilemez
**Sorun:** İlke oluşturamıyor veya cihazları kaydedemiyorsunuz.

**Çözüm:** [Office 365 yönetim merkezinde](https://portal.office.com/), şirket adından özel karakterleri kaldırın ve şirket bilgilerini kaydedin.

## Birden çok doğrulanmış etki alanınız olduğunda oturum açılamaz veya cihazlar kaydedilemez
**Sorun:** AD FS’nize ikinci bir doğrulanmış etki alanı eklediğinizde, ikinci etki alanının kullanıcı asıl adı (UPN) sonekini taşıyan kullanıcılar portallarda oturum açamayabilir veya cihazları kaydedemeyebilir. 


**Çözüm:** AD FS 2.0 aracılığıyla çoklu oturum açmayı (SSO) kullanan ve kuruluşlarında kullanıcıların UPN sonekleri için birden çok en üst düzey etki alanı bulunan (örneğin, @contoso.com veya @fabrikam.com) Microsoft Office 365 müşterilerinin, her sonek için ayrı AD FS 2.0 Federasyon Hizmeti örneği dağıtmaları gerekir.  Şimdi, ek AD FS 2.0 sunucularına gerek kalmadan AD FS sunucusunun bu senaryoyu destekleyebilmesi için, **SupportMultipleDomain** anahtarıyla birlikte çalışan bir [AD FS 2.0 dağıtımı](http://support.microsoft.com/kb/2607496) vardır. Daha fazla bilgi için [bu bloga](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) bakın.



## Hata kodları

|Hata kodu|Olası sorun|Önerilen çözüm|
|--------------|--------------------|------------------------|
|0x80CF0437 |İstemci bilgisayarındaki saat doğru zamana ayarlanmadı.|İstemci bilgisayardaki saat ve saat diliminin doğru saat ve saat dilimine ayarlandığından emin olun.
|
|0x80240438, 0x80CF0438, 0x80CF402C|Intune hizmetine bağlanılamıyor. İstemci proxy ayarlarını kontrol edin.|İstemci bilgisayardaki proxy ayarlarının Intune tarafından desteklendiğinden ve istemci bilgisayarın İnternet erişimi olduğundan emin olun.|
|0x80240438, 0x80CF0438|Internet Explorer ve Yerel Sistem proxy ayarları yapılandırılmadı.|Intune hizmetine bağlanılamıyor. İstemci proxy ayarlarını denetleyin ve istemci bilgisayardaki proxy yapılandırmasının Intune tarafından desteklendiğinden ve istemci bilgisayarın İnternet erişimi olduğundan emin olun.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Kayıt paketi güncel değil.|Yönetim çalışma alanından güncel istemci yazılımı paketini indirin ve yükleyin.|
|0x80043002, 0x80CF3002|Hesap bakım modunda.|Hesap bakım modunda olduğunda yeni istemci bilgisayarlar kaydedilemez. Hesap ayarlarınızı görüntülemek için hesabınızda oturum açın.|
|0x80043003, 0x80CF3003|Hesap silindi.|Hesabınızın ve Intune aboneliğinizin hala etki olduğunu doğrulayın. Hesap ayarlarınızı görüntülemek için hesabınızda oturum açın.|
|0x80043005, 0x80CF3005|İstemci bilgisayar devre dışı bırakıldı.|Birkaç saat bekleyin, bilgisayardan istemci yazılımının daha eski sürümlerini kaldırın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|0x80043006, 0x80CF3006|İzin verilen maksimum bilgisayar lisansı sayısına ulaşıldı.|Kuruluşunuzun hizmete daha fazla istemci bilgisayar kaydedebilmek için ek bilgisayar lisansları satın alması gerekir.|
|0x80043007, 0x80CF3007|Yükleyici programla aynı klasörde sertifika dosyası bulunamadı.|Yüklemeyi başlatmadan önce tüm dosyaları ayıklayın. Ayıklanan dosyaları yeniden adlandırmayın veya yerini değiştirmeyin: tüm dosyalar aynı klasörde bulunmalıdır; aksi takdirde yükleme başarısız olur.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|İstemci bilgisayarın yeniden başlatılması beklendiğinden yazılım yüklenemiyor.|Bilgisayarı yeniden başlatın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|0x80070032|İstemci yazılımını yüklemek için bir veya daha fazla önkoşul istemci bilgisayarda bulunamadı.|Gerekli tüm güncelleştirmelerin istemci bilgisayarda yüklü olduğundan emin olun ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|0x80043008, 0x80CF3008|Microsoft Online Management Güncelleştirmeleri hizmeti başlatılamadı.|[Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.|
|0x80043009, 0x80CF3009|İstemci bilgisayar hizmete zaten kayıtlı.|İstemci bilgisayarı bu hizmete yeniden kaydetmek için önce devre dışı bırakmanız gerekir.|
|0x8004300B, 0x80CF300B|İstemci üzerinde çalışan Windows sürümü desteklenmediğinden, istemci yazılımı yükleme paketi çalıştırılamıyor.|Intune istemci bilgisayarda çalışan Windows sürümünü desteklemiyor.|
|0xAB2|Windows Installer özel bir işlem için VBScript çalışma zamanına erişemedi.|Bu hata Dinamik Bağlantı Kitaplıkları'nı (DLLs) temel alan özel bir işlemden kaynaklanır. DLL sorunlarını giderirken, [Microsoft Desteği KB198038: Paket ve Dağıtım Sorunlarında Yararlı Araçlar](https://support.microsoft.com/en-us/kb/198038) makalesinde açıklanan araçları kullanmanız gerekebilir.|
|0x80cf0440|Hizmet uç noktası bağlantısı sonlandırıldı.|Deneme hesabı veya ücretli hesap askıya alındı. Yeni bir deneme hesabı veya ücretli hesap oluşturun ve yeniden kaydolun.|


## iOS kayıt hataları
Diğer iOS kayıt hatalarının listesi, cihaz-kullanıcı belgelerimizdeki [Cihazınızı Intune'a kaydetmeye çalışırken hatalar görüyorsunuz](/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune) bölümünde verilmiştir.

### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) bölümünde açıklandığı gibi Microsoft Desteği ile iletişim kurun.


<!--HONumber=May16_HO2-->

