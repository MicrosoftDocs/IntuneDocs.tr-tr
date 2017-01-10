## <a name="november-2016"></a>Kasım 2016

### <a name="new-capabilities"></a>Yeni özellikler

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Windows 10 cihazları için Yeni Microsoft Intune Şirket Portalı__ Microsoft, [Windows 10 cihazları için yeni bir Microsoft Intune Şirket Portalı uygulaması](https://www.microsoft.com/store/apps/9wzdncrfj3pz) piyasaya sürdü. Yeni Windows 10 Evrensel biçiminden yararlanan bu uygulama, kullanıcıya uygulama içinden güncelleştirilmiş bir kullanıcı deneyimi ve kullanıcının bugün kullanmakta olduğu işlevselliğin tümünü olanaklı kılmaya devam ederken, ister bilgisayar ister Mobil tüm Windows 10 cihazlarında aynı deneyimi sunacak.

Yeni uygulama, kullanıcının Windows 10 cihazlarında çoklu oturum açma (SSO) ve sertifika tabanlı kimlik doğrulama gibi ek platform özelliklerinden yararlanmasını da sağlar. Uygulama, mevcut Windows 8.1 Şirket Portalı ve Windows Phone 8.1 Şirket Portalı için güncelleştirme olarak Windows Mağazası'ndan yüklenir. Daha fazla ayrıntı için bkz. [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Intune ve Android for Work Güncelleştirmesi__

> Android for Work uygulamalarını __Gerekli__ işleviyle dağıtabilirsiniz ancak uygulamaları __Kullanılabilir__ olarak dağıtmak için Intune gruplarınızın yeni Azure AD grupları deneyimine geçirilmiş olması gerekir.

__Cordova için Intune Uygulama SDK'sı eklentisi artık kayıtsız MAM desteği sunuyor__ Uygulama geliştiricileri artık Cordova için Intune Uygulama SDK'sı eklentisini Android ve iOS için Cordova tabanlı uygulamalarında cihaz kaydı olmadan da MAM işlevlerini etkinleştirmek için kullanabilir. Cordova için Intune Uygulama SDK'sı eklentisine [buradan](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) ulaşabilirsiniz.

__Xamarin için Intune Uygulama SDK'sı bileşeni artık kayıtsız MAM desteği sunuyor__ Uygulama geliştiricileri artık Xamarin için Intune Uygulama SDK'sı bileşenini Android ve iOS için Xamarin tabanlı uygulamalarında cihaz kaydı olmadan da MAM işlevlerini etkinleştirmek için kullanabilir. Xamarin için Intune Uygulama SDK'sı bileşenine [buradan](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) ulaşabilirsiniz.

### <a name="notices"></a>Bildirimler

__Symantec imzalama sertifikası artık yükleme için imzalanmış Windows Phone 8 Şirket Portalı gerektirmiyor__ Symantec imzalama sertifikasını yüklemek için artık imzalı Windows Phone 8 Şirket Portalı uygulaması kullanılması gerekmiyor. Sertifika tek başına yüklenebilir.

###<a name="deprecations"></a>Kullanım dışı bırakılanlar

__Windows Phone 8 Şirket Portalı Desteği__ Windows Phone 8 Şirket Portalı desteği artık kullanım dışı bırakılacak. Windows Phone 8 ve WinRT platformları için sunulan destek de Ekim 2016'da kullanım dışı bırakıldı. Windows Phone 8 Şirket Portalı için sunulan destek de Ekim 2016'da kullanım dışı bırakıldı.

## <a name="october-2016"></a>Ekim 2016

### <a name="conditional-access-for-mobile-application-management"></a>Mobil uygulama yönetimi için koşullu destek
Yalnızca Outlook gibi Intune mobil uygulama yönetimi ilkelerini destekleyen uygulamalardan erişime izin vermek için Exchange Online’a erişimi kısıtlayabilirsiniz. [Bu yeni özellik](/intune/deploy-use/allow-policy-managed-apps-access-to-o365), Intune mobil uygulama yönetimi (MAM) ilkeleriyle mükemmel bir uyum sağlar ve yerleşik posta istemcilerine veya Intune MAM ilkeleriyle yapılandırılmamış olan diğer uygulamalara erişimi engelleyebilirsiniz. Böylelikle, kullanıcılarınızın kuruluşunuzun verilerine Intune MAM kullanılarak korunan uygulamalarla erişmesi güvence altına alır. Intune mobil uygulama yönetimini Azure portalından başlatabilirsiniz. “Ayarlar” dikey penceresinde yeni Koşullu Erişim bölümünü bulun.

### <a name="conditional-access-for-windows-pcs"></a>Windows Bilgisayarlar için koşullu erişim
Artık Windows bilgisayarlarının [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) ve [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)’a erişmesini engellemek için Intune Yönetici Konsolu aracılığıyla koşullu erişim ilkeleri oluşturabilirsiniz. Office masaüstü ve evrensel uygulamalara erişimi engellemek için de koşullu erişim ilkeleri oluşturabilirsiniz.

### <a name="android-for-work-support"></a>Android for Work desteği

> [!IMPORTANT]

> Android for Work uygulamalarını __Gerekli__ işleviyle dağıtabilirsiniz ancak uygulamaları __Kullanılabilir__ olarak dağıtmak için Intune gruplarınızın yeni Azure AD grupları deneyimine geçirilmiş olması gerekir.

Intune artık Android for Work (AfW) programının bir parçası haline gelmiştir. Bu aydan itibaren AfW özellikleri için destek sunmaya başlayacağız ve önümüzdeki birkaç ay buna devam edeceğiz. AfW’nin kullanılabilir uygulama dağıtımı, yeni gruplandırma ve hedefleme deneyimini geliştirir. Sağlanan yeni Intune Hizmet hesapları, AfW kullanmaya başladığında bu özellikten yararlanabilir.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Android for Work için Intune desteği hakkında Microsoft'un duyurusunu okuyun](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Aşağıdaki Intune konuları yenidir veya Android for Work bilgileriyle güncelleştirilmiştir:

BT uzmanları için:
- [Android for Work’ü ayarlama](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Intune ile Exchange Online’a ve yeni Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Intune’la Şirket İçi Exchange’e ve eski Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work uyumluluk ilkesi ayarları](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work uygulamalarını dağıtma](/intune/deploy-use/android-for-work-apps)
- [Android for Work uygulamalarını mobil uygulama yapılandırma ilkeleri ile yapılandırma](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work ilke ayarları](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Son kullanıcılar için:
- [İş profili oluşturduğunuzda ne olur?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Bir iş profili oluşturma ve cihazınızı Intune’a kaydetme](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>iOS cihazlarını korumak için Lookout tümleştirmesi
Ekim'de, Microsoft, iOS mobil cihazlardaki kötü amaçlı yazılımları, riskli uygulamaları ve diğer tehditleri algılayarak cihazları korumak için Lookout'un mobil tehdit koruma çözümüyle tümleşiyor. Lookout’ın çözümü tehdit düzeyini saptamanıza yardımcı olur ve bu ayar yapılandırılabilir. Lookout’un risk değerlendirmesi temelinde cihaz uyumluluğunu saptamak için Intune’da bir uyumluluk ilkesi kuralı oluşturabilirsiniz. Koşullu erişim ilkelerini kullanarak, cihaz uyumluluk durumuna göre şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz.

Uyumlu olmayan iOS cihazlarının son kullanıcılarının kaydolmaları istenecek ve şirket verilerine erişim kazanmak için cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamayı etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekecek. [Lookout for Work uygulamalarını yapılandırmayı ve dağıtmayı](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps) öğrenin.
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Android için Intune Uygulama Sarmalama Aracı
Intune Uygulaması Sarmalama Aracı'nı kullanarak uygulamalarınızın Intune mobil uygulama yönetim (MAM) ilkelerini kullanmasını sağlayabilirsiniz. Cihaz kaydı gerektirmeden Intune MAM ilkeleri desteği artık kullanılabilir.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>MAM ilkeleriyle yönetilen uygulamalardan yazdırmayı yönetme
Artık MAM ilkeleri olan uygulamalardan şirket verilerinin yazdırılmasını engelleyebilirsiniz. Bu ayar, [Azure portalından](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) kullanılabilir ve gerek [iOS](/Intune/deploy-use/ios-mam-policy-settings), gerekse [Android](/Intune/deploy-use/android-mam-policy-settings) cihazlarında desteklenmektedir.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Android cihazlarda parmak izi desteği
Android mobil uygulama yönetimi (MAM) ilkeleri, artık kullanıcıların bir uygulamaya erişmek için PIN yazmak yerine parmak izi kullanmasına izin verir. Bunu ve [Android cihazları için diğer mobil uygulama yönetimi ilkesi ayarlarını burada bulabilirsiniz](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Bildirimler

__Android Samsung KNOX ile Intune uyumluluğu__ Samsung Galaxy Ace telefonunun bazı modelleri, Intune tarafından Samsung KNOX cihazları olarak yönetilemiyor. Bu cihazları Intune’a kaydettiğinizde, artık standart Android cihazları olarak yönetilecek.

Etkilenen model numaraları:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Sizin ve son kullanıcılarınızın başka bir işlem yapması gerekmez. Daha fazla bilgi için [Samsung KNOX](https://www.samsungknox.com) web sitesini ziyaret edin.

__Windows 8 için Şirket Portalı uygulaması kaldırılmıştır; Windows Phone 8 ve Windows RT platformları için destek kaldırılmaktadır__ Microsoft Intune, Ekim 2016'dan başlayarak Windows 8 Şirket Portalı için desteği kaldıracaktır. Microsoft Intune, ayrıca Windows Phone 8 ve Windows RT platformları için desteği de kaldıracaktır. Bu nedenle bundan sonra herhangi bir Windows Phone 8 veya Windows RT cihazını kaydetmeniz veya güncelleştirmeniz mümkün olmayacaktır.

Daha önce kaydedilen Windows Phone 8, Windows RT ve Windows 8 cihazlarını yönetmeye devam edebilirsiniz. Windows 8 ve Windows Phone 8 cihazlarını Windows 8.1’e ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara bir kesinti olmadan uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.

Kasım 2016'dan itibaren Windows Phone 8 Şirket Portalı için desteği kaldıracağız.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Yakında

__Windows 10 cihazları için Yeni Microsoft Intune Şirket Portalı__ Microsoft, Windows 10 cihazları için yeni bir Microsoft Intune Şirket Portalı'nı piyasaya sürüyor. Yeni Windows 10 Evrensel biçiminden yararlanan bu uygulama, kullanıcıya uygulama içinden güncelleştirilmiş bir kullanıcı deneyimi ve kullanıcının bugün kullanmakta olduğu işlevselliğin tümünü olanaklı kılmaya devam ederken, ister bilgisayar ister Mobil tüm Windows 10 cihazlarında aynı deneyimi sunacak.

Yeni uygulama, kullanıcının Windows 10 cihazlarında çoklu oturum açma (SSO) ve sertifika tabanlı kimlik doğrulama gibi ek platform özelliklerinden yararlanmasını da sağlar. Uygulama, mevcut Windows 8.1 Şirket Portalı ve Windows Phone 8.1 Şirket Portalı için güncelleştirme olarak Windows Mağazası'ndan yüklenir. Daha fazla ayrıntı için bkz. [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Eylül 2016
### <a name="new-features-announcements-and-information"></a>Yeni özellikler, duyurular ve bilgiler
* [Windows koşullu erişim](#windows-conditional-access)
* [iOS 10 desteği](#ios-10-support)
* [Uygulama Sarmalama Aracı, Android ve iOS için cihaz kaydı gerektirmeden MAM’yi destekler](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Eylül’de Intune gruplarının Azure Active Directory’ye geçişi başlıyor](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Android cihazlarını korumak için Lookout tümleştirmesi](#lookout-integration-to-protect-android-devices)
* [Android, iOS ve Windows için Şirket Portalı güncelleştirmeleri](#company-portal-updates)
* [Intune sözlüğü](#intune-glossary)
* [Yakında](#whats-coming)

### <a name="windows-conditional-access"></a>Windows koşullu erişim
Artık Windows bilgisayarlarının Exchange Online ve SharePoint Online’a erişmesini engellemek için Intune Yönetici Konsolu aracılığıyla koşullu erişim ilkeleri oluşturabilirsiniz. Office masaüstü ve evrensel uygulamalara erişimi engellemek için de koşullu erişim ilkeleri oluşturabilirsiniz.

### <a name="ios-10-support"></a>iOS 10 desteği
Mevcut Intune MDM ve MAM senaryoları iOS 10 ile uyumludur. İpuçları için [Intune Desteği Takım Blogu](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/)’na bakın.

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Uygulama Sarmalama Aracı, Android ve iOS için cihaz kaydı gerektirmeden MAM’yi destekler
Intune Uygulama Sarmalama Aracı, iOS ve Android için Intune MAM iş kolu (LOB) uygulamalarını etkinleştirmek için kullanılan bir komut satırı aracıdır. Bu, Intune MAM SDK’sını uygulamanızla tümleştirmenin en basit yoludur; böylelikle uygulamanız, Intune aracılığıyla dağıtılan MAM ilkelerini zorunlu tutabilir. MAM ilkeleri kullanarak şunları yapabilirsiniz:

1. Uygulamanın verileri şifreleyebilirsiniz.
2. Bilgi çalışanlarının uygulamayı başlatırken PIN girmesini gerektirebilirsiniz.
3. Uygulamanın yalnızca diğer yönetilen uygulamalara veri aktarmasına izin verebilirsiniz.
4. Uygulamanın Android, iTunes ve iCloud’a veri yedeklemesini önleyebilirsiniz.
5. Diğer yönetilen uygulamalarla arasında yalnızca Kes, Kopyala ve Yapıştır işlemlerine izin verebilirsiniz.

Güncelleştirilmiş Intune Uygulama Sarmalama Aracı’nın genel önizlemesi, artık iOS ve Android’deki dahili LOB uygulamalarında cihaz kaydına gerek kalmadan MAM desteği sağlar. Bu da son kullanıcılarınızın MAM özellikli LOB uygulamalarını kullanmak için cihazlarını kaydetmek zorunda olmadıkları anlamına gelir.

Genel önizleme yazılımını herkes test edebilir ve msintuneappsdk'nin GitHub’ında bulunan yardımcı belgeleri okuyabilir:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Android ve iOS Yayın öncesi Sürüm için Microsoft Intune Uygulama Sarmalayıcı’yı yükleyip kullanmadan önce:

* Android ve iOS Yayın öncesi Sürüm için Microsoft Intune Uygulama Sarmalama Aracı’nın Microsoft Lisans Koşulları’nı gözden geçirmelisiniz
* Kendi kayıtlarınız için lisans koşullarının bir kopyasını yazdırmalı ve saklamalısınız. Android Yayın Öncesi Sürüm için Microsoft Intune Uygulama Sarmalama Aracı’nı indirerek ve kullanarak bu lisans koşullarını kabul etmiş sayılırsınız. Kabul etmiyorsanız, yazılımı kullanmayın.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Eylül’de Intune gruplarının Azure Active Directory’ye geçişi başlıyor
Bazı yeni Intune hesapları, Intune kullanıcı grupları yerine Azure Active Directory güvenlik gruplarını kullanacaktır. Intune portalı gruplar sayfasında sizi Azure yönetim portalına yönlendiren bir bağlantı olacağı için, güvenlik gruplarıyla çalıştığınızı anlayabileceksiniz.

### <a name="lookout-integration-to-protect-android-devices"></a>Android cihazlarını korumak için Lookout tümleştirmesi
Microsoft, Android mobil cihazlardaki kötü amaçlı yazılımları, riskli uygulamaları ve diğer tehditleri algılayarak cihazları korumak için Lookout’un mobil tehdit koruma çözümüyle tümleştiriliyor. Lookout’ın çözümü tehdit düzeyini saptamanıza yardımcı olur ve bu ayar yapılandırılabilir. Lookout’un risk değerlendirmesi temelinde cihaz uyumluluğunu saptamak için Intune’da bir uyumluluk ilkesi kuralı oluşturabilirsiniz. Koşullu erişim ilkelerini kullanarak, cihaz uyumluluk durumuna göre şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz.

Uyumlu olmayan cihazların son kullanıcılarının kaydolmaları istenir. Erişim kazanmak için Android cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamaları etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekir. Daha fazla bilgi edinmek için bkz. [Cihaz, ağ ve uygulama riskine dayalı olarak erişimi kısıtlama](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>Şirket portalı güncelleştirmeleri

__Android__

<p style="margin-left: 40px">**Android için Şirket Portalı "Bildirimler" alanına eklemeler yapıldı**<br/>
<p style="margin-left: 40px">Şirket Portalı’nda giriş sayfasına Android için yeni Bildirimler simgesi eklendi. Bu simgeye dokunulduğunda Bildirimler sayfasına erişim sağlanır; bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilir. iOS Şirket Portalı uygulamasında bu bildirimler deneyimi önceden sağlanmıştır. Yeni Bildirimler sayfasının bulunması, cihazın önceden kaydedilmiş olması koşuluyla kullanıcının Şirket Portalı’nı her başlattığında veya sürdürdüğünde Şirket Erişim Kurulumu sayfasını artık görmeyeceği anlamına gelir. Kendi son kullanıcı yönergelerinizi oluşturuyorsanız, bu değişikliği yansıtacak şekilde belgelerinizi güncelleştirmek isteyebilirsiniz. Güncelleştirilmiş ekran görüntülerini [burada](https://aka.ms/androidcpupdate) bulabilirsiniz.  

__iOS__
<p style="margin-left: 40px">**iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
<p style="margin-left: 40px">iOS için Microsoft Intune Şirket Portalı uygulamasının tüm kullanıcılarının en son sürümü kullanmaları gerekir. Yeni kullanıcılar yalnızca en son sürümünü indirebilir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamaz veya ona kaydolamaz. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.
<!---TFS 1283165--->

<p style="margin-left: 40px">**iOS son kullanıcılarının uygulamalarını edinme şekillerine yönelik geliştirmeler**<br/>
<p style="margin-left: 40px">Kullanıcıları tüm uygulamalarda tek konuma, yani Şirket Portalı web sitesine yönlendirmek üzere iOS için Şirket Portalı uygulamasındaki uygulama kutucuklarında aşağıdaki değişiklikler yapılmıştır. Apple kısıtlamaları iş kolu uygulamalarının ve yönetilen uygulama mağazası uygulamalarının Şirket Portalı uygulamasında listelenmesini yasakladığından kullanıcıların tüm uygulamalarını bulabilmek için farklı görünümleri ziyaret etmesi gerekir.

<p style="margin-left: 40px">**Şirket Uygulamaları** kutucuğu daha önce Şirket Portalı Web sitesinin TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirmekteydi ve bu şekilde çalışmaya devam edecektir. Kutucuk adı **Tüm Uygulamalar** olarak değişmiştir.

<p style="margin-left: 40px">**Diğer Uygulamalar** kutucuğu daha önce, Şirket Portalı uygulamasında bulunan ve Apple’ın Şirket Portalı uygulamasının göstermesine izin verdiği tüm uygulamaları listeleyen görünüme yönlendiriyordu. Kutucuk adı **Öne Çıkan Uygulamalar** olarak değişmiştir ve kutucuğa dokunan kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKANLAR sekmesine götürür.

<p style="margin-left: 40px">**Kategoriler** kutucuğu daha önce Şirket Portalı uygulaması içinde bulunan ve uygulama kategorilerini listeleyen görünüme yönlendirmekteydi. Kutucuk adı değişmemiştir, ancak artık Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir. Güncelleştirilmiş ekran görüntülerini [burada](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bulabilirsiniz.
  <!---TFS 1317133--->

<p style="margin-left: 40px">**BT Uzmanının bir uygulama için bu gereksinimi ayarlaması durumunda iOS Managed Browser uygulamasını yükleme uyarısı**<br/>
<p style="margin-left: 40px">Web klibini yalnızca yönetilen bir tarayıcıda açılacak şekilde yapılandırdıysanız ve yönetilen tarayıcı bir cihazda yüklü değilse, cihazdaki Şirket Portalı uygulaması, web klibinin yüklenebilmesi için önce yönetilen tarayıcının yüklenmesi gerektiği konusunda kullanıcıyı uyarır.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Windows Phone 8.1 Şirket Portalı uygulamasına Geri Bildirim düğmesi eklendi**<br/>
<p style="margin-left: 40px">Windows Phone 8.1 Şirket Portalı uygulaması, son kullanıcıların yeni “geri bildirim gönder” düğmesini kullanarak uygulama hakkında geri bildirim göndermesine olanak tanır. Düğmeyi bulmak için, kullanıcılar Şirket Portalı uygulama ekranının sağ alt kısmındaki “üç nokta” menüsüne dokunur ve sonra da **geri bildirim gönder**’e dokunur. Toplanan anonim geri bildirimler, Microsoft’un kullanıcılar için Şirket Portalı uygulama deneyimini geliştirmesine yardımcı olacak.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Intune sözlüğü</br>
Intune ürününde kullanılan bazı terimleri anlamanıza yardımcı olmak için kitaplığa yeni bir [sözlük konusu](https://docs.microsoft.com/intune/understand-explore/intune-glossary) ekledik.

## <a name="august-2016"></a>Ağustos 2016
### <a name="app-management"></a>Uygulama yönetimi
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__iOS 9.3 için gizli ve gösterilen uygulamalar__ iOS 9.3 veya üzerini çalıştıran cihazlarda iOS genel yapılandırma ilkesindeki gizli ve gösterilen uygulamalar listesini kullanarak şunları yapabilirsiniz:
- Kullanıcılardan gizlenecek uygulamaların bir listesini belirtin. Kullanıcılar bu uygulamaları görüntüleyemez veya başlatamaz.
- Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların bir listesini belirtin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Belirtebileceğiniz uygulamalara hem sizin dağıttığınız uygulamalar hem de Mesajlar ve Notlar gibi yerleşik iOS uygulamaları dahildir. Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Samsung KNOX cihazlar için izin verilen ve engellenen uygulamalar ilkesi__ Artık Samsung KNOX cihazlar için aşağıdakilerden birini oluşturmanıza imkan tanıyan özel bir ilke yapılandırabilirsiniz:
- Cihazda çalışması engellenmiş uygulamaların listesi. Engellenenler listesinde tanımlanan bir uygulama cihazda yüklü olsa bile etkinleştirilemez.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung KNOX çalıştıran cihazlar tarafından kullanılabilir.
Ayrıntılar için bkz. [Özel ilkeler kullanarak Samsung KNOX cihazları için uygulamalara izin verme veya bunları engelleme](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Mobil uygulama yönetimi (MAM) ilkeleriyle uyumlu yeni uygulamalar__ [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) ve [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) için Yammer uygulaması, artık cihazın kayıtlı olup olmadığından bağımsız olarak [Intune mobil uygulama yönetimi (MAM) ilkeleri](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) ile uyumludur.

MAM ile uyumlu uygulamaların tam listesi için [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) sitesine bakın.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune Görüntüleyicisi uygulamaları__ Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
- Intune AV Görüntüleyicisi
- Intune PDF Görüntüleyicisi
- Google Play’den Android için Intune Resim Görüntüleyicisi

Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni [Android için Hak Yönetimi uygulamasını (RMS paylaşımı)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) kullanmanızı öneririz. Intune görüntüleyicisi uygulamasının desteği sona erdiğinde, bu uygulama Google Store’dan kaldırılacak ve gelecekte kullanıma sunulmayacaktır.

### <a name="device-management"></a>Cihaz yönetimi
__Android 7.0 desteği__ Intune, mobil cihazlar için yeni çıkacak Android 7.0 işletim sistemine yönelik olarak "0. gün" desteği sağlar.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Android 7.0 cihazlarda uzaktan geçiş kodu sıfırlama özelliğinin Google tarafından kaldırılması
Google, BT yöneticileri ve son kullanıcıların Android 7.0 cihazların parolasını uzaktan sıfırlama olanağını sona erdiriyor. Daha önce BT yöneticileri bir kullanıcının geçiş kodunu uzaktan sıfırlayabiliyor ve son kullanıcılar Şirket Portalı web sitesinden kendi parolalarını sıfırlayabiliyordu.



### <a name="company-portal-updates"></a>Şirket portalı güncelleştirmeleri
__Şirket Portalı web sitesi__
- **Şirket Portalı’ndan Microsoft’a geri bildirim bağlantısı** <br/>
Şirket portalı web sitesi, son kullanıcıların sayfanın en altındaki yeni “Geri Bildirim” bağlantısına dokunarak siteyle ilgili deneyimlerini Microsoft’a göndermesine olanak tanır. Toplanan anonim geri bildirimler, Microsoft’un kullanıcılar için Şirket Portalı web sitesi deneyimini geliştirmesine yardımcı olacak.
<!--- TFS 1313657 checked--->

__iOS__
- **En düşük iOS Managed Browser sürümü 8.0 olarak güncelleştirildi**<br/>
iOS için Microsoft Intune Managed Browser uygulaması, iOS 8.0 veya üstünü çalıştıran cihazları destekleyecek şekilde güncelleştirilmiştir. iOS 7.1 cihazları mevcut Managed Browser uygulamasını kullanmaya devam edebilirler, ama yeni Managed Browser özelliklerine erişebilmeleri ve bu özelliklerden tam olarak yararlanabilmeleri için kullanıcılarınızı iOS 8.0 veya üstüne güncelleştirmeye teşvik edin.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Yakında
__Eylül 2016’dan itibaren Intune Grupları Azure Active Directory Grupları’na geçiyor__ Intune, Intune’daki kullanıcı ve cihaz grupları olarak Azure Active Directory (AAD) güvenlik gruplarının kullanıldığı yeni bir grup yönetim deneyimi oluşturmaktadır. Bu gruplar **yeni Azure tabanlı Intune yönetici portalını kullanıma aldığımızda** tüm grup yönetimi, ilke yönetimi ve profil yönetimi için kullanılacaktır.

Bu yeni deneyim hizmetler arasında yinelenen gruplarınızın olmasını engelleyecek, **yeni bazı Azure Active Directory Premium (AADP) grup özelliklerine erişmenizi sağlayacak**, ayrıca PowerShell ve Graph kullanılarak kapsamı genişletme olanağı sağlayacaktır. Bu deneyim, kurumsal mobil kullanım yönetimi genelinde grup yönetimi deneyimini de birleştirecektir.

Güvenlik Gruplarına geçiş yapabilmek için, **geçerli yönetici konsolunda** bazı değişiklikler yapılacaktır. **Bu değişiklikler ve AAD güvenlik gruplarının kullanımı, Intune belgelerine kaydedilecektir**.

Intune’u yeni kullanmaya başlayan müşteriler, **güvenlik grubu değişikliklerinden bazılarını geçerli kiracılardan önce göreceklerdir**.

Grup yönetimindeki değişikliklere ek olarak, **aşağıdaki işlevler de kullanım dışı kalacaktır**:
- Yeni grup oluşturulurken üyeleri ve grupları dışlama
- **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** grupları
- Hizmet Yöneticisi rolündeki **Grupları Yönet** işlevi
- Bildirim Kuralları için özel grup tabanlı uyarılar
- Raporlarda gruplarla özetleme
<!--- TFS 1295329--->

__Android için Şirket Portalı’na eklenen 'Bildirimler'__ Eylül’de kullanıma sunacağımız güncelleştirmeyle Android için Şirket Portalı’nda giriş sayfasına yeni **Bildirimler** simgesi eklenecektir. Bu simgeye dokunulduğunda **Bildirimler** sayfasına erişim sağlanacak, bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilecektir. iOS Şirket Portalı uygulamasını da kullanıyorsanız, bildirimler deneyimini zaten görmüş olacaksınız. **Bildirimler** sayfası eklendikten sonra, cihazın önceden kaydedilmiş olması koşuluyla Android için Şirket Portalı’nı her başlattığınızda veya sürdürdüğünüzde **Şirket Erişim Kurulumu** sayfasını görmeyeceksiniz. Birçoğunuzun son kullanıcı kılavuzları oluşturduğunu ve kılavuzunuzun/ekran görüntülerinizin güncelleştirilmesi gerektiğinde önceden size bildirilmesini istediğinizi duyuyoruz. Lütfen deneyimdeki yaklaşan değişiklikleri yansıtacak şekilde belgelerinizi güncelleştirin. Güncelleştirilmiş ekran görüntülerini şu adreste bulabilirsiniz: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Hizmeti kullanımdan kaldırma
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
Eylül ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.  

- **En düşük iOS Managed Browser sürümü 8.0 olarak güncelleştirildi**<br/>
Ağustos’ta, Intune yalnızca iOS 8.0 veya üstünü çalıştıran cihazları destekleyecek, güncelleştirilmiş iOS için Microsoft Intune Managed Browser uygulamasını kullanıma sunacaktır. iOS 7.1 cihazları mevcut Managed Browser uygulamasını kullanmaya devam edebilirler, ama yeni Managed Browser özelliklerine erişebilmeleri ve bu özelliklerden tam olarak yararlanabilmeleri için lütfen kullanıcılarınızı iOS 8.0 veya üstüne güncelleştirmeye teşvik edin.  
<!---TFS 1313253--->

- **Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır** <br/>
Microsoft Intune Eylül 2016'dan itibaren Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamalarına yönelik desteği sonlandıracaktır. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Temmuz 2016
### <a name="app-management"></a>Uygulama yönetimi

__Uygulama sağlama profilini güncelleştirme deneyimini geliştirme__ Apple iOS iş kolu mobil uygulamaları, eklenen ve sertifika kullanılarak kodla imzalanan bir sağlama profiliyle oluşturulur. Uygulama iOS cihazında çalıştırıldığında, iOS uygulamanın bütünlüğünü onaylar ve sağlama profiliyle tanımlanan ilkeleri zorunlu tutar.

Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi normalde 3 yıldır. Öte yandan, 1 yıl sonra sağlama profilinin süresi dolar. Bu güncelleştirmeyle Intune size, sertifikası hala geçerli olduğu halde süresi dolmak üzere olan uygulamaların bulunduğu cihazlara, yeni sağlama profili ilkesini önceden dağıtmak için araçlar getirir. Daha fazla bilgi için bkz. [İş kolu uygulamalarınızın güncel kalmasını sağlamak için iOS mobil sağlama profili ilkelerini kullanma](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Intune uygulamaları için Xamarin SDK’sı sağlanır__ Intune Uygulaması SDK Xamarin bileşeni, Xamarin ile oluşturulan mobil iOS ve Android uygulamalarınızda Intune mobil uygulama yönetimi özelliklerini etkinleştirmenize olanak tanır. Bileşeni [Xamarin mağazasında](https://components.xamarin.com/view/Microsoft.Intune.MAM) veya [Microsoft Intune Github sayfasında](https://github.com/msintuneappsdk) bulabilirsiniz.
<!--- TFS 1061478 --->

### <a name="device-management"></a>Cihaz yönetimi
__Cihaz kayıt sınırlarında artış__ Intune, yapılandırılabilir cihaz kayıt sayısı üst sınırını kullanıcı başına 5 cihazdan 15 cihaza çıkardı.
<!---TFS 1289896 --->

__Intune istemci yazılımını çalıştıran Windows bilgisayarları için TeamViewer Tümleştirmesi__
 Intune istemcisini çalıştıran Windows bilgisayarlarında [TeamViewer](https://www.teamviewer.com) tümleştirmesi, son kullanıcı yardım masası departmanlarını desteklemek için Windows bilgisayarlarıyla uzaktan yardım oturumları oluşturmanıza imkan tanır. Bu, Windows 7, 8, 8.1 ve Windows 10’u içerir. Ayrıntılar için bkz. [Microsoft Intune bilgisayar istemcisiyle ortak Windows bilgisayarı yönetim görevleri](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Şirket portalı güncelleştirmeleri

__Şirket Portalı web sitesi__
- **Windows cihazlarını kaydetme işleminde geliştirilmiş son kullanıcı deneyimi**<br/>
Koşullu erişim kullanırken, Şirket Portalı web sitesindeki Windows 8.1, Windows 10 Masaüstü ve Windows 10 Mobile için kayıt adımları netleştirilmiştir. Kullanıcılara artık birbirinden ayrı “Cihaz kaydı” ve “Workplace Join” adımları gösterilir. Böylelikle cihazlarının durumunu daha kolay görebilir ve Workplace Join (WPJ) hatasıyla karşılaşırlarsa işlemi tamamlayabilirler. Ayrı adımların, BT yöneticileri için sorun giderme işlemini de basitleştirmesi beklenmektedir. Daha önce, son kullanıcılar cihazı kaydetmeyi denerken WPJ dışındaki tüm kayıt adımları başarılı olduğunda, kaydedilen cihaz kullanıcıların belirleyebilmesi için cihaz listesinde gösterilmeyebiliyor ve kullanıcılarda kafa karışıklığına neden oluyordu.

__Android__
- **Android Şirket Portalı uygulaması**<br/>
Android son kullanıcıları cihazlarında gerekli bir sertifikanın eksik olduğunu bildiren bir hata iletisi görürlerse, eksik sertifikayı yükleme [adımlarına](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) ulaşmak için “Bu nasıl çözülür” düğmesine dokunabilirler. Kullanıcılar adımları tamamladıkları halde bir “eksik sertifika” hata iletisi daha görürlerse, BT yöneticilerine başvurmaları ve bu [bağlantıyı](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) sağlamaları istenir. Bu bağlantı, BT yöneticilerinin sertifika sorununu çözmek için kullanabilecekleri adımları içerir.

- **Dışarıdan uygulama yüklemelerini kayıtlı cihazlarla kısıtlama**<br/>
Android için Intune Şirket Portalı uygulaması kullanılarak Intune’a kaydedilmeyen Android cihazları, artık Şirket Portalı web sitesi üzerinden uygulama yükleyemezler.
<!---TFS 1299082--->

__iOS__
- **iOS Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler**<br/>
Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının **Cihazlarım** bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını görüntülemez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir.

DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir. Ayrıca Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir.

Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın. Daha fazla bilgi için bkz. [Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Windows özelliklerinde ad değişiklikleri
- [Windows için Microsoft Passport](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) artık **İş için Windows Hello** olarak adlandırılıyor.
- [Kurumsal veri koruma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) artık **Windows Bilgi Koruması** olarak adlandırılıyor.

## <a name="june-2016"></a>Haziran 2016
### <a name="intune-service-health"></a>Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri Office 365 yönetim portalında, Hizmet Durumu’nun altında bulabilirsiniz. Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

### <a name="app-management"></a>Uygulama yönetimi
- **Geliştirilmiş Windows 10 kurumsal veri ilkesi yapılandırma deneyimi.** Windows 10 kurumsal veri koruma ilkesi yapılandırma deneyiminde, uygulama kuralları oluşturma, ağ sınırı tanımını belirtme ve diğer kurumsal veri koruma ayarları ile ilgili geliştirmeler yapıldı. Daha fazla bilgi için bkz: [Microsoft Intune kullanarak kurumsal veri koruma (EDP) ilkesi oluşturma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Cihaz yönetimi
- **Olası istenmeyen uygulamalara karşı koruma sağlayan Windows Defender ilke ayarı.** Windows 10 Desktop ve Mobile için genel yapılandırma ilkesine **İstenmeyebilecek Uygulama Algılama** adlı yeni bir Windows Defender ayarı eklendi. Bu ayarı kullanarak kayıtlı Windows masaüstü bilgisayarlarını, Windows Defender tarafından istenmeyebilecek yazılım olarak sınıflandırılan yazılımları çalıştırmaya karşı koruyabilirsiniz. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz. Daha fazla bilgi için, bkz. [Microsoft Intune’da Windows 10 ilke ayarları](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Koşullu erişim
- **Intune için Cisco ISE ağ erişimi denetim ilkesi.**  Cisco Identity Service Engine (ISE) 2.1 ile birlikte Microsoft Intune’u kullanan müşteriler, ISE’de bir ağ erişimi denetim ilkesi ayarlayabilir.

    Bu ilke kullandığında, ağa WiFi veya VPN ile erişmeye çalışan cihazlara erişim izni verilmesi için cihazların aşağıdaki koşulları karşılaması gerekir:

    * Intune tarafından yönetiliyor olmalıdır
    * Dağıtılmış tüm Intune uyumluluk ilkeleriyle uyumlu olmalıdır

 Uyumsuz cihazları kullanan son kullanıcıların erişim elde etmek için kaydolması ve uyumluluk sorunlarını gidermesi istenir.
- **Tarayıcı için koşullu erişim.** [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) ve [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazlarında desteklenen web tarayıcılarından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **Dynamics CRM Online koşullu erişimi destekler.** [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazları tarafından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android’de Dynamics CRM mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Intune Şirket Portalı güncelleştirmeleri

__Android Şirket Portalı uygulaması__

- BT yöneticileri yeni "Cihazların bilinmeyen kaynaklardan uygulama yüklemesine izin vermemesini sağla (Android 4.0 +)" ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, "Bilinmeyen kaynaklardan yükleme devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Güvenlik** kısmına gitmesi ve **Bilinmeyen kaynaklar**’ı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) almasını sağlar.

- BT yöneticileri yeni "Cihazların, güvenlik tehditleri için uygulamaların taranmasını etkinleştirmiş olmasını gerektir (Android 4.0 +)” ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, “Cihazı güvenlik tehditleri için tara” iletisini görür. Kullanıcıların, **Ayarlar** > **Google** > **Güvenlik** kısmına gitmesi ve **Cihazı güvenlik tehditleri için tara**’yı açması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden açmaları gerektiği hakkında daha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını sağlar.

- BT yöneticileri yeni "USB hata ayıklamanın devre dışı olmasını gerektir (Android 4.2 +)" ilkesini uyguladığında, Android 4.2 veya üstü cihazlara sahip son kullanıcılar, "USB hata ayıklama devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Geliştirici seçenekleri** kısmına gitmesi ve “**USB hata ayıklama**”yı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) almasını sağlar.

- BT yöneticileri yeni "Minimum Android güvenlik düzeltme eki düzeyi (Android 6.0 +)" ilkesini uyguladığında, Android 6.0 veya üstü cihazlara sahip son kullanıcılar, "Bu cihaz, en düşük Android güvenlik düzeltme eki düzeyini karşılamıyor" iletisini görür. Kullanıcıların, gerekli güvenlik düzeltme ekini yüklemesi gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların gerekli güvenlik düzeltme ekini nasıl yükleneceği hakkında [bilgi](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını ve mevcut durumda kendilerinde hangi güvenlik düzeltme ekinin yüklü olduğunu görmesini sağlar.

__iOS Şirket Portalı uygulaması__

- Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [iOS cihazınızı el ile eşitleme](/Intune/EndUser/sync-your-device-manually-ios).

- iOS için Microsoft Intune Şirket Portalı uygulaması, iOS 8.0 ve sonraki sürümleri desteklemek için güncelleştirildi. Bu güncelleştirme, yalnızca cihaz iOS 8.0 veya sonraki sürümleri çalışıyorsa son kullanıcıların Şirket Portalı uygulamasını yükleyebileceği ve Intune’a yeni cihazları kaydedebileceği anlamına gelir. Desteklenmeyen bir iOS sürümünü çalıştıran, önceden kayıtlı cihazları olan kullanıcılar, cihazlarında Şirket Portalı uygulamasını kullanmaya devam edebilir.


<!--HONumber=Jan17_HO1-->

