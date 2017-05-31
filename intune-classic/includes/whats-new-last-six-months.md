## <a name="march-2017"></a>Mart 2017

### <a name="new-capabilities"></a>Yeni Özellikler

#### <a name="support-for-skycure"></a>Skycure desteği

Artık Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Skycure tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Skycure çalıştıran cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:

- Fiziksel savunma
- Ağ savunması
- Uygulama savunması
- Güvenlik açıkları savunması

Intune cihaz uyumluluk ilkeleri ile etkinleştirilen Skycure risk değerlendirmesine dayalı olarak EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumsuz cihazların şirket kaynaklarına erişimine izin vermek ya da erişimi engellemek için bu ilkeleri kullanabilirsiniz. Daha fazla bilgi için bkz. [Skycure Mobile Threat Defense bağlayıcısı](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android Şirket Portalı uygulaması için yeni kullanıcı deneyimi <!--621622-->

Android için Şirket Portalı uygulamasının kullanıcı arabirimi daha modern görünüm ve daha iyi kullanıcı deneyimi için güncelleştiriliyor. Önemli güncelleştirmeler şunlardır:

- Renkler: Şirket Portalı sekmesinin üstbilgileri BT tarafından tanımlanan marka rengindedir.
- Uygulamalar: **Uygulamalar** sekmesindeki **Öne Çıkan Uygulamalar** ve **Tüm Uygulamalar** düğmeleri güncelleştirildi.
- Arama: **Uygulamalar** sekmesinde, **Arama** düğmesi kayan eylem düğmesi şeklinde.
- Uygulamalarda Gezinme: **Tüm Uygulamalar** görünümü daha kolay gezinme için **Öne Çıkan Uygulamalar**, **Tüm Uygulamalar** ve **Kategoriler** bölümlerini sekmeler halinde gösterir.
- Destek: **Cihazlarım** ve **BT İletişim** sekmeleri okunabilirliği artırmak için güncelleştirildi.

Bu değişiklikler hakkında daha ayrıntılı bilgi için bkz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](/intune-classic/whats-new/whats-new-in-intune-app-ui).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->

Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Windows 10 Şirket Portalı için İmzalama Betiği <!--941642-->

Windows 10 Şirket Portalı uygulamasını indirmeniz ve dışarıdan yüklemeniz gerekiyorsa, artık bir betik kullanarak uygulama imzalama işlemini kuruluşunuz için basitleştirebilir ve kolaylaştırabilirsiniz.   Betiği indirmek ve kullanma yönergelerine göz atmak için TechNet Galerisi’ndeki [Windows 10 Şirket Portalı için Microsoft Intune İmzalama Betiği](https://aka.ms/win10cpscript) makalesine bakın. Bu duyuru hakkında daha ayrıntılı bilgi edinmek için Intune Destek Ekibi Blogundaki [Windows 10 Şirket Portalı uygulamanızı güncelleştirme](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) yazısına bakın.


### <a name="notices"></a>Bildirimler

#### <a name="support-for-ios-103"></a>iOS 10.3 desteği

iOS 10.3 sürümü 27 Mart 2017 tarihinden itibaren iOS kullanıcılarına sunulmaya başlandı. Mevcut tüm Intune MDM ve MAM senaryoları Apple’ın en son işletim sistemi ile uyumludur. Kullanıcılarınız cihazlarını ve uygulamalarını iOS 10.3 sürümüne yükselttiklerinde, şu anda iOS cihazlarını yönetmeye dair mevcut tüm Intune özelliklerinin sorunsuz bir şekilde çalışmaya devam etmesini bekliyoruz.

Şu anda bilinen bir sorun yoktur. iOS 10.3 ile ilgili soruna karşılaşırsanız lütfen [Intune destek ekibine](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune) ulaşın.

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Çin'de bulunan Android kullanıcıları için gelişmiş destek <!--720444-->

Çin’de Google Play Mağazası olmaması nedeniyle, Android cihazlarının uygulamaları Çin’deki uygulama mağazalarından edinmeleri gerekir. Şirket Portalı, Çin’deki Android kullanıcılarını Şirket Portalı ve Outlook uygulamalarını yerel mağazalardan yüklemeleri için yeniden yönlendirerek bu iş akışını destekler. Bu, Koşullu Erişim ilkeleri, mobil aygıt yönetimi ve mobil uygulama yönetimi için etkinleştirildiğinde, kullanıcı deneyimini geliştirir. Android için Şirket Portalı ve Outlook uygulamaları aşağıdaki Çin uygulama mağazalarında bulunabilir:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>En iyi uygulama: Şirket Portalı uygulamalarınızın güncel olduğundan emin olun <!--879465-->

Aralık 2016’da, iOS, Android, Windows 8.1+ veya Windows Phone 8.1+ cihazı kaydeden bir grup kullanıcı için çok faktörlü kimlik doğrulamasının (MFA) zorlanmasını sağlayan bir güncelleştirme yayımladık. Bu özellik, Android (v5.0.3419.0+) ve iOS (v2.1.17+) için Şirket Portalı uygulamasının belirli temel sürümleri olmadan çalışamaz.

Microsoft, Intune’u sürekli olarak geliştirmek amacıyla hem konsola hem de Şirket Portalı uygulamasına tüm desteklenen platformlarda yeni işlevler ekliyor. Bunun sonucunda, Microsoft yalnızca Şirket Portalı uygulamasının geçerli sürümünde karşılaşılan sorunlara yönelik düzeltmeler yayımlamaktadır. Bu nedenle, en iyi kullanıcı deneyiminden yararlanabilmeniz için Şirket Portalı uygulamalarının en son sürümlerini kullanmanızı öneririz.

>[!Tip]
> Kullanıcılarınızın, cihazlarında uygulamaları ilgili uygulama mağazasından otomatik olarak güncelleştirecek şekilde ayarlamalar yapmasını sağlayın. Android Şirket Portalı uygulamasını bir ağ paylaşımında kullanıma sunduysanız en son sürümü [Microsoft İndirme Merkezi](https://www.microsoft.com/download/details.aspx?id=49140)’nden indirebilirsiniz.

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams artık iOS ve Android’de MAM özelliğini kullanabiliyor

Microsoft, Microsoft Teams’in genel kullanıma sunulduğunu açıkladı. iOS ve Android için güncelleştirilmiş Microsoft Teams uygulamaları artık Intune mobil uygulama yönetimi (MAM) özelliklerine sahip olduğundan ekiplerinizin tüm cihazlarda rahatça çalışmasına olanak tanıyıp bir yandan da görüşmeleri ve kurumsal verileri her aşamada koruyabilirsiniz. Daha ayrıntılı bilgi edinmek için Enterprise Mobility and Security blogundaki [Microsoft Teams duyurusuna](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) bakın.


## <a name="february-2017"></a>Şubat 2017

### <a name="new-capabilities"></a>Yeni Özellikler

### <a name="modernizing-the-company-portal-website---753980--"></a>Şirket Portalı web sitesi modernleştiriliyor <!--753980-->
Şirket Portalı web sitesi, yönetilen cihazlara sahip olmayan kullanıcıları hedefleyen uygulamaları destekleyecek. Karşıt renklerden oluşan yeni renk düzeni ve dinamik çizimlerle yeniden tasarlanan web sitesi, yardım masası ilgili kişisine ilişkin ayrıntıların yanı sıra yönetilen mevcut cihazlara yönelik bilgilerin bulunduğu bir "hamburger menüsü" ![Şirket Portalı web sitesinin sol üst köşesine eklenmiş olan hamburger menüsünün küçük resmi](/intune-classic/whats-new/whats-new-in-intune-app-ui).

### <a name="notices"></a>Bildirimler

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Grup geçişi için iOS cihazlarda grup veya ilke güncelleştirmesi gerekmeyecek <!--898837-->
Azure Active Directory cihaz gruplarına geçiş sırasında, önceden bir Şirket Cihaz Kaydı profili tarafından atanmış olan her Intune cihaz grubu için Şirket Cihaz Kaydı profilinin adına göre AAD'de karşılık gelen bir dinamik cihaz grubu oluşturulacaktır. Bu sayede kaydı yapılan cihazların otomatik olarak gruplanması ve özgün Intune grubundakilerle aynı ilkeleri ve uygulamaları alması sağlanacaktır.

Bir kiracı gruplama ve hedefleme için geçiş işlemine girdiğinde Intune, otomatik olarak Şirket Cihaz Kaydı profili tarafından hedeflenen Intune grubuna karşılık gelecek bir dinamik AAD grubu oluşturacaktır. Intune Yöneticisinin hedef Intune grubunu silmesi halinde karşılık gelen dinamik AAD grubu silinmeyecektir. Grubun üyeleri ve dinamik sorgu silinecek ancak BT Yöneticisi AAD portalı üzerinden kaldırılana kadar grubun kendisi kalacaktır.

Benzer şekilde, BT Yöneticisinin bir Şirket Cihaz Kaydı profili ile hedeflenen Intune grubunu değiştirmesi halinde, Intune yeni profil atamasını yansıtan yeni bir dinamik grup oluşturacak ancak eski atama için oluşturulan dinamik grubu kaldırmayacaktır.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows masaüstü cihazları Windows ayarları aracılığıyla yönetmek varsayılanlara sıfırlıyor <!--663050-->
Windows 10 masaüstü cihazları kaydetmek için varsayılan davranış değişiyor. Yeni kayıtlar artık bilgisayar aracısı üzerinden değil, tipik MDM aracısı kayıt akışını izleyerek yapılacaktır. Şirket Portalı web sitesi, Windows 10 masaüstü kullanıcılarına Windows 10 masaüstü bilgisayarları mobil cihaz olarak ekleme işlemi için yönergeler sağlayacak kayıt yönergeleri temin edecektir. Bu, zaten kayıtlı olan bilgisayarları etkilemez ve [tercihe göre](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune) kuruluşunuz bilgisayar aracısını kullanarak Windows 10 masaüstü cihazları yönetmeye devam edebilir.

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Seçici silme için mobil uygulama yönetimi desteğini iyileştirme <!--581242-->
Bu verilerin "Uygulama verileri silinmeden önce çevrimdışı zaman aralığı" ilkesi nedeniyle otomatik olarak kaldırılması durumunda, son kullanıcılara iş veya okul verilerine yeniden erişim sağlama konusunda ek yönergeler verilir.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS için Şirket Portalı bağlantıları uygulamanın içinde açılır <!--665954-->
Belge ve uygulamalara yönlendirilen bağlantılar da dahil olmak üzere iOS için Şirket Portalı uygulaması içinde bulunan bağlantılar, Safari’nin uygulama içi görünümü kullanılarak doğrudan Şirket Portalı uygulamasında açılır. Bu güncelleştirme Ocak’taki hizmet güncelleştirmesinden ayrı olarak sevk edilir.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows cihazları için yeni MDM sunucusu adresi <!--893007-->
MDM sunucusu adresi olarak __manage.microsoft.com__ giren (sorulursa) Windows ve Windows Phone kullanıcıları, cihaz kaydetmeye çalıştıklarında başarısız olacaklardır. MDM sunucusu adresi __manage.microsoft.com__ yerine __enrollment.manage.microsoft.com__ olarak değiştirilmektedir. Kullanıcılarınızı, Windows veya Windows Phone cihazı kaydetmeye çalışırken sorulması halinde MDM sunucusu adresi olarak __enrollment.manage.microsoft.com__ girmeleri konusunda bilgilendirin. CNAME kurulumunuzda herhangi bir değişiklik gerekmez. Bu değişiklik hakkında daha fazla bilgi için [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) adresini ziyaret edin.

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android Şirket Portalı uygulaması için yeni kullanıcı deneyimi <!--621622-->
Mart ayından itibaren Android Şirket Portalı uygulaması [Material Design kılavuzuna](https://material.io/guidelines/material-design/introduction.html) uygun olarak modern bir tasarıma sahip olacak. Bu gelişmiş kullanıcı deneyimi şunları içeriyor olacak:

* __Renkler__: Sekme başlıklarının renkleri özel renk paletinize göre değiştirilebilir.
* __Arabirim__: Uygulamalar sekmesindeki Öne Çıkan Uygulamalar ve Tüm Uygulamalar düğmeleri güncelleştirildi. Arama düğmesi artık kayan eylem düğmesi şeklinde.
* __Gezinti__: Tüm Uygulamalar sayfasında daha kolay gezinme için Öne Çıkan Uygulamalar, Tüm Uygulamalar ve Kategoriler sekmeler halinde görüntüleniyor.
* __Hizmet__: Cihazlarım ve BT'ye Başvur sekmelerinin okunabilirliği geliştirildi.

Önce ve sonra görüntülerini [UI güncelleştirmeleri sayfasında](/intune-classic/whats-new/whats-new-in-intune-app-ui) bulabilirsiniz.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>İş İçin Windows Mağazası’yla birden çok yönetim aracını ilişkilendirme<!--926135-->
İş İçin Windows Mağazası uygulamalarını dağıtmak için birden fazla yönetim aracı kullanmanız durumunda önceden bunların yalnızca birini İş İçin Windows Mağazası ile ilişkilendirebiliyordunuz. Artık mağaza ile Intune ve Configuration Manager gibi birden fazla yönetim aracını ilişkilendirebilirsiniz. Ayrıntılar için bkz. [Microsoft Intune ile İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları yönetme](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure’da Intune yönetici deneyiminin genel önizlemesindeki yenilikler<!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](/intune/whats-new) bakın.

Azure’da Intune önizlemesindeki yenilikleri [buradan](/intune/whats-new) bulabilirsiniz.

## <a name="january-2017"></a>Ocak 2017

### <a name="new-capabilities"></a>Yeni Özellikler

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Kayıtsız MAM için konsol içi raporlar <!--677961-->
Hem kayıtlı hem kayıtlı olmayan cihazlar için yeni uygulama koruma raporları eklenmiştir. [Intune ile mobil uygulama yönetimi ilkelerini nasıl izleyebileceğinizi buradan](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune) öğrenebilirsiniz.

#### <a name="android-711-support---694397--"></a>Android 7.1.1 desteği <!--694397-->
Intune artık Android 7.1.1 sürümünü tam olarak destekler ve yönetir.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>iOS cihazlarının etkin olmaması veya yönetim konsolunun cihazlarla iletişim kuramaması sorununu çözme <!--unknown-->
Kullanıcıların cihazları Intune ile iletişimi kaybettiğinde, şirket kaynaklarına yeniden erişmeleri için kullanıcılara yeni sorun giderme adımları verebilirsiniz. Bkz. [Cihazlar etkin değil veya yönetim konsolu cihazlarla iletişim kuramıyor](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Bildirimler

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows masaüstü cihazları Windows ayarları aracılığıyla yönetmek varsayılanlara sıfırlıyor <!--663050-->
Windows 10 masaüstü cihazları kaydetmek için varsayılan davranış değişiyor. Yeni kayıtlar artık bilgisayar aracısı üzerinden değil, tipik MDM aracısı kayıt akışını izleyerek yapılacaktır.

Şirket Portalı web sitesi, Windows 10 masaüstü kullanıcılarına Windows 10 masaüstü bilgisayarları mobil cihaz olarak ekleme işlemi için yönergeler sağlayacak kayıt yönergeleri temin edecektir. Bu, zaten kayıtlı olan bilgisayarları etkilemez ve [tercihe göre](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune) kuruluşunuz bilgisayar aracısını kullanarak Windows 10 masaüstü cihazları yönetmeye devam edebilir.

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Seçici silme için mobil uygulama yönetimi desteğini iyileştirme <!--581242-->
Bu verilerin "Uygulama verileri silinmeden önce çevrimdışı zaman aralığı" ilkesi nedeniyle otomatik olarak kaldırılması durumunda, son kullanıcılara iş veya okul verilerine yeniden erişim sağlama konusunda ek yönergeler verilir.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS için Şirket Portalı bağlantıları uygulamanın içinde açılır <!--665954-->
Belge ve uygulamalara yönlendirilen bağlantılar da dahil olmak üzere iOS için Şirket Portalı uygulaması içinde bulunan bağlantılar, Safari’nin uygulama içi görünümü kullanılarak doğrudan Şirket Portalı uygulamasında açılır. Bu güncelleştirme Ocak’taki hizmet güncelleştirmesinden ayrı olarak sevk edilir.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Şirket Portalı web sitesi modernleştiriliyor <!--753980-->
Şubat ayından itibaren Şirket Portalı web sitesi, yönetilen cihazlara sahip olmayan kullanıcıları hedefleyen uygulamaları destekleyecek. Karşıt renklerden oluşan yeni renk düzeni ve dinamik çizimlerle yeniden tasarlanan web sitesi, yardım masası ilgili kişisine ilişkin ayrıntıların yanı sıra yönetilen mevcut cihazlara yönelik bilgilerin bulunduğu bir "hamburger menüsü" ![Şirket Portalı web sitesi hamburger menüsü](/intune-classic/whats-new/whats-new-in-intune-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Uygulama koruma ilkeleri için yeni belgeler <!--583398-->
Intune Uygulama Sarmalama Aracı veya Intune Uygulama SDK’sı kullanarak iOS ve Android uygulamalarında uygulama koruma ilkelerini (MAM ilkeleri olarak da bilinir) etkinleştirmek isteyen yöneticiler ve uygulama geliştiricilerine yönelik belgelerimizi güncelleştirdik.

Aşağıdaki makaleler güncelleştirilmiştir:

* [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](/intune-classic/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını mobil uygulama yönetimi için hazırlama](/intune-classic/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Microsoft Intune Uygulama SDK’sını kullanmaya başlayın](/intune-classic/develop/intune-app-sdk-get-started)
* [iOS için Intune Uygulama SDK’sı geliştirici kılavuzu](/intune-classic/develop/intune-app-sdk-ios)

Aşağıdaki makaleler belgeler kitaplığına yeni eklenmiştir:

* [Intune Uygulama SDK’sı Cordova Eklentisi](/intune-classic/develop/intune-app-sdk-cordova)
* [Intune Uygulama SDK’sı Xamarin Bileşeni](/intune-classic/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>iOS’ta Şirket Portalını başlatılırken ilerleme çubuğu <!--665978-->
iOS için Şirket Portalı, kullanıcıya gerçekleşen yükleme işlemleri hakkında bilgi sağlamak için başlatma ekranında bir ilerleme çubuğu yeniliği sunuyor. Değer değiştiricinin yerini alması için ilerleme çubuğunun aşamalı dağıtımı yapılacaktır. Yani bazı kullanıcılarınız yeni ilerleme çubuğunu görecek, diğerleri ise değer değiştiriciyi görmeye devam edecektir.

## <a name="december-2016"></a>Aralık 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi <!--736542-->
2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır. Tüm Intune kiracıları için bu portalın genel kullanılabilirliğinin yanı sıra, kiracı seçmek için bu yeni yönetici deneyiminin önizlemesini bu ay içinde kullanıma sunmaya başlayacağımızı duyurmak isteriz.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, Azure portalında Microsoft Intune hakkında bilgilere [yeni belgelerimizden](/intune/what-is-intune) ulaşabilirsiniz.

__Azure portalının genel önizlemesinde telekom gider yönetimi__ <!--747605--> Azure portalında, üçüncü taraf telekom gider yönetimi ile tümleştirme özelliğini önizlemeye sunuyoruz/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Yeni Özellikler

__Tüm platformlarda Multi-Factor Authentication__ <!--747590-->Azure Active Directory’deki Microsoft Intune Kaydı uygulamasında Multi-Factor Authentication’ı yapılandırarak, Azure Yönetim Portalı’ndan iOS, Android, Windows 8.1+ veya Windows Phone 8.1+ cihazı kaydeden belirli bir kullanıcı grubu için Multi-Factor Authentication (MFA) kullanımını zorunlu kılabilirsiniz.

__Mobil cihaz kaydını kısıtlama olanağı__ <!--747596-->Intune, kaydedilmesine izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.
* Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.
* Yalnızca iOS için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](/intune-classic/deploy-use/manage-corporate-owned-devices) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.

### <a name="notices"></a>Bildirimler

__Kayıt sırasında Multi-Factor Authentication ayarlama işlemi Azure portalına taşınıyor__ <!--VSO 750545--> Daha önce, yöneticilerin Intune kaydı sırasında MFA ayarlamak için Intune konsoluna veya Configuration Manager (Ekim 2016'dan önceki sürümler) konsoluna gitmesi gerekiyordu. Bu güncelleştirilmiş özellik sayesinde, artık [Microsoft Azure portalında](https://manage.windowsazure.com) Intune kimlik bilgilerinizi kullanarak oturum açar ve MFA ayarlarını Azure AD ile yapılandırırsınız. Bunun hakkında daha fazla bilgi için [burayı](https://aka.ms/mfa_ad) okuyun.

__Android için Şirket Portalı uygulaması Çin’de kullanıma sunuldu__ <!--VSO 658093--> Android için Şirket Portalı indirilebilir uygulamasını Çin’de yayımlıyoruz. Çin’de Google Play Mağazası olmaması nedeniyle, Android cihazlarının uygulamaları Çin’deki uygulama mağazalarından edinmeleri gerekir. Android için Şirket Portalı uygulaması aşağıdaki mağazalardan yüklenebilir:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Android için Şirket Portalı uygulaması Microsoft Intune hizmetiyle iletişim kurmak için Google Play Hizmetleri’ni kullanır. Google Play Hizmetleri henüz Çin'de kullanılamadığından, aşağıdaki görevlerin tamamlanması 8 saate kadar sürebilir. 

|Intune Yönetici Konsolu| Android için Intune Şirket Portalı uygulaması |Intune Şirket Portalı Web Sitesi|   
|---|---|---|
|Tam temizleme| Uzak bir cihazı kaldırma| Cihaz kaldırma (yerel ve uzak)|
|Seçmeli temizleme| Cihaz sıfırlama| Cihaz sıfırlama|
|Yeni veya güncelleştirilmiş uygulamaların dağıtımı| Kullanılabilir iş kolu uygulamalarını yükleme| Cihaz geçiş kodu sıfırlama|
|Uzaktan kilitleme|||
|Geçiş kodu sıfırlama|||

### <a name="deprecations"></a>Kullanım dışı bırakılanlar

__Firefox artık Silverlight’ı desteklemeyecek__ <!--VSO TBA--> Mozilla, Mart 2017’den itibaren [Firefox tarayıcısı](https://www.mozilla.org/firefox) sürüm 52’de Silverlight desteğini kaldırıyor. Sonuç olarak, 51 üzeri Firefox sürümleri kullanarak mevcut Intune konsolunda oturum açmanız artık mümkün olmayacaktır. Yönetici konsoluna erişmek için Internet Explorer 10 veya 11 ya da [Sürüm 52'den önceki bir Firefox sürümü](https://ftp.mozilla.org/pub/firefox/releases/) kullanmanızı öneririz. Intune'un Azure portalına geçişi, Silverlight bağımlılığı olmadan bir dizi [modern tarayıcı](/azure/azure-preview-portal-supported-browsers-devices) desteğine olanak sağlayacaktır.

__Exchange Online mobil gelen kutusu ilkeleri kaldırılıyor__ <!--770687-->Aralık’tan itibaren, yöneticiler artık Intune konsolu içinde Exchange Online (EAS) mobil gelen kutusu ilkelerini görüntüleme veya yapılandırma işlemlerini yapamayacak. Bu değişiklik, Aralık ve Ocak boyunca tüm Intune kiracılarına gönderilecektir. Tüm mevcut ilkeler yapılandırıldığı gibi kalır; yeni ilkeler yapılandırmak için Exchange Yönetim Kabuğu'nu kullanın. Daha fazla bilgi için [buraya](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx) göz atın.

__Intune AV Player, Image Viewer ve PDF Viewer uygulamaları Android’de artık desteklenmiyor.__ <!--747553--> Aralık 2016’nın ikinci yarısından itibaren, kullanıcılar Intune AV Player, Image Viewer ve PDF Viewer uygulamalarını kullanamayacak. Bu uygulamaların yerini Azure Information Protection uygulaması almıştır. Azure Information Protection hakkında daha fazla bilgiyi [burada](/information-protection/rms-client/mobile-app-faq) bulabilirsiniz.

## <a name="november-2016"></a>Kasım 2016

### <a name="new-capabilities"></a>Yeni özellikler

__Windows 10 cihazları için Yeni Microsoft Intune Şirket Portalı__ Microsoft, [Windows 10 cihazları için yeni bir Microsoft Intune Şirket Portalı uygulaması](https://www.microsoft.com/store/apps/9wzdncrfj3pz) piyasaya sürdü. Yeni Windows 10 Evrensel biçiminden yararlanan bu uygulama, kullanıcıya uygulama içinden güncelleştirilmiş bir kullanıcı deneyimi ve kullanıcının bugün kullanmakta olduğu işlevselliğin tümünü olanaklı kılmaya devam ederken, ister bilgisayar ister Mobil tüm Windows 10 cihazlarında aynı deneyimi sunacak.

Yeni uygulama, kullanıcının Windows 10 cihazlarında çoklu oturum açma (SSO) ve sertifika tabanlı kimlik doğrulama gibi ek platform özelliklerinden yararlanmasını da sağlar. Uygulama, mevcut Windows 8.1 Şirket Portalı ve Windows Phone 8.1 Şirket Portalı için güncelleştirme olarak Windows Mağazası'ndan yüklenir. Daha fazla ayrıntı için bkz. [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Intune ve Android for Work hakkında bir Güncelleştirme__ Android for Work uygulamalarını __Gerekli__ eylemiyle dağıtabilirsiniz ancak uygulamaları __Kullanılabilir__ olarak dağıtmak için Intune gruplarınızın yeni Azure AD grupları deneyimine geçirilmiş olması gerekir.

__Cordova için Intune Uygulama SDK'sı eklentisi artık kayıtsız MAM desteği sunuyor__ Uygulama geliştiricileri artık Cordova için Intune Uygulama SDK'sı eklentisini Android ve iOS için Cordova tabanlı uygulamalarında cihaz kaydı olmadan da MAM işlevlerini etkinleştirmek için kullanabilir. Cordova için Intune Uygulama SDK'sı eklentisine [buradan](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) ulaşabilirsiniz.

__Xamarin için Intune Uygulama SDK'sı bileşeni artık kayıtsız MAM desteği sunuyor__ Uygulama geliştiricileri artık Xamarin için Intune Uygulama SDK'sı bileşenini Android ve iOS için Xamarin tabanlı uygulamalarında cihaz kaydı olmadan da MAM işlevlerini etkinleştirmek için kullanabilir. Xamarin için Intune Uygulama SDK'sı bileşenine [buradan](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) ulaşabilirsiniz.

### <a name="notices"></a>Bildirimler

__Symantec imzalama sertifikası artık yükleme için imzalanmış Windows Phone 8 Şirket Portalı gerektirmiyor__ Symantec imzalama sertifikasını yüklemek için artık imzalı Windows Phone 8 Şirket Portalı uygulaması kullanılması gerekmiyor. Sertifika tek başına yüklenebilir.

###<a name="deprecations"></a>Kullanım dışı bırakılanlar

__Windows Phone 8 Şirket Portalı Desteği__ Windows Phone 8 Şirket Portalı desteği artık kullanım dışı bırakılacak. Windows Phone 8 ve WinRT platformları için sunulan destek de Ekim 2016'da kullanım dışı bırakıldı. Windows Phone 8 Şirket Portalı için sunulan destek de Ekim 2016'da kullanım dışı bırakıldı.

## <a name="october-2016"></a>Ekim 2016

### <a name="conditional-access-for-mobile-application-management"></a>Mobil uygulama yönetimi için koşullu destek
Yalnızca Outlook gibi Intune mobil uygulama yönetimi ilkelerini destekleyen uygulamalardan erişime izin vermek için Exchange Online’a erişimi kısıtlayabilirsiniz. [Bu yeni özellik](/intune-classic/deploy-use/allow-policy-managed-apps-access-to-o365), Intune mobil uygulama yönetimi (MAM) ilkeleriyle mükemmel bir uyum sağlar ve yerleşik posta istemcilerine veya Intune MAM ilkeleriyle yapılandırılmamış olan diğer uygulamalara erişimi engelleyebilirsiniz. Böylelikle, kullanıcılarınızın kuruluşunuzun verilerine Intune MAM kullanılarak korunan uygulamalarla erişmesi güvence altına alır. Intune mobil uygulama yönetimini Azure portalından başlatabilirsiniz. “Ayarlar” dikey penceresinde yeni Koşullu Erişim bölümünü bulun.

### <a name="conditional-access-for-windows-pcs"></a>Windows Bilgisayarlar için koşullu erişim
Artık Windows bilgisayarlarının [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)’a erişmesini engellemek için Intune yönetici konsolu aracılığıyla koşullu erişim ilkeleri oluşturabilirsiniz. Office masaüstü ve evrensel uygulamalara erişimi engellemek için de koşullu erişim ilkeleri oluşturabilirsiniz.

### <a name="android-for-work-support"></a>Android for Work desteği

> [!IMPORTANT]

> Android for Work uygulamalarını __Gerekli__ işleviyle dağıtabilirsiniz ancak uygulamaları __Kullanılabilir__ olarak dağıtmak için Intune gruplarınızın yeni Azure AD grupları deneyimine geçirilmiş olması gerekir.

Intune artık Android for Work (AfW) programının bir parçası haline gelmiştir. Bu aydan itibaren AfW özellikleri için destek sunmaya başlayacağız ve önümüzdeki birkaç ay buna devam edeceğiz. AfW’nin kullanılabilir uygulama dağıtımı, yeni gruplandırma ve hedefleme deneyimini geliştirir. Sağlanan yeni Intune Hizmet hesapları, AfW kullanmaya başladığında bu özellikten yararlanabilir.

[Android for Work için Intune desteği hakkında Microsoft'un duyurusunu okuyun](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Aşağıdaki Intune konuları yenidir veya Android for Work bilgileriyle güncelleştirilmiştir:

BT uzmanları için:
- [Android for Work’ü ayarlama](/intune-classic/deploy-use/set-up-android-for-work)
- [Intune ile Exchange Online’a ve yeni Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Intune’la Şirket İçi Exchange’e ve eski Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work uyumluluk ilkesi ayarları](/intune-classic/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work uygulamalarını dağıtma](/intune-classic/deploy-use/android-for-work-apps)
- [Android for Work uygulamalarını mobil uygulama yapılandırma ilkeleri ile yapılandırma](/intune-classic/deploy-use/afw-app-configuration-policy)
- [Android for Work ilke ayarları](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Son kullanıcılar için:
- [İş profili oluşturduğunuzda ne olur?](/intune-user-help/what-happens-when-you-create-a-work-profile-android)
- [Bir iş profili oluşturma ve cihazınızı Intune’a kaydetme](/intune-user-help/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>iOS cihazlarını korumak için Lookout tümleştirmesi
Ekim'de, Microsoft, iOS mobil cihazlardaki kötü amaçlı yazılımları, riskli uygulamaları ve diğer tehditleri algılayarak cihazları korumak için Lookout'un mobil tehdit koruma çözümüyle tümleşiyor. Lookout’ın çözümü tehdit düzeyini saptamanıza yardımcı olur ve bu ayar yapılandırılabilir. Lookout’un risk değerlendirmesi temelinde cihaz uyumluluğunu saptamak için Intune’da bir uyumluluk ilkesi kuralı oluşturabilirsiniz. Koşullu erişim ilkelerini kullanarak, cihaz uyumluluk durumuna göre şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz.

Uyumlu olmayan iOS cihazlarının son kullanıcılarının kaydolmaları istenecek ve şirket verilerine erişim kazanmak için cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamayı etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekecek. [Lookout for Work uygulamalarını yapılandırmayı ve dağıtmayı](/intune-classic/deploy-use/configure-and-deploy-lookout-for-work-apps) öğrenin.
<!--TFS 1319493-->

### <a name="intune-app-wrapping-tool-for-android"></a>Android için Intune Uygulama Sarmalama Aracı
Intune Uygulaması Sarmalama Aracı'nı kullanarak uygulamalarınızın Intune mobil uygulama yönetim (MAM) ilkelerini kullanmasını sağlayabilirsiniz. Cihaz kaydı gerektirmeden Intune MAM ilkeleri desteği artık kullanılabilir.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>MAM ilkeleriyle yönetilen uygulamalardan yazdırmayı yönetme
Artık MAM ilkeleri olan uygulamalardan şirket verilerinin yazdırılmasını engelleyebilirsiniz. Bu ayar, [Azure portalı](/intune-classic/deploy-use/android-mam-policy-settings) cihazlarında kullanılabilir.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Android cihazlarda parmak izi desteği
Android mobil uygulama yönetimi /intune-classic/deploy-use/android-mam-policy-settings).

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

Uyumlu olmayan cihazların son kullanıcılarının kaydolmaları istenir. Erişim kazanmak için Android cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamaları etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekir. Daha fazla bilgi edinmek için bkz. [Cihaz, ağ ve uygulama riskine dayalı olarak erişimi kısıtlama](/intune-classic/deploy-use/device-threat-protection).


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
Intune ürününde kullanılan bazı terimleri anlamanıza yardımcı olmak için kitaplığa yeni bir [sözlük konusu](/intune-classic/understand-explore/intune-glossary) ekledik.

## <a name="august-2016"></a>Ağustos 2016
### <a name="app-management"></a>Uygulama yönetimi

__iOS 9.3 için gizli ve gösterilen uygulamalar__ iOS 9.3 veya üzerini çalıştıran cihazlarda iOS genel yapılandırma ilkesindeki gizli ve gösterilen uygulamalar listesini kullanarak şunları yapabilirsiniz:
- Kullanıcılardan gizlenecek uygulamaların bir listesini belirtin. Kullanıcılar bu uygulamaları görüntüleyemez veya başlatamaz.
- Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların bir listesini belirtin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Belirtebileceğiniz uygulamalara hem sizin dağıttığınız uygulamalar hem de Mesajlar ve Notlar gibi yerleşik iOS uygulamaları dahildir. Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Samsung KNOX cihazlar için izin verilen ve engellenen uygulamalar ilkesi__ Artık Samsung KNOX cihazlar için aşağıdakilerden birini oluşturmanıza imkan tanıyan özel bir ilke yapılandırabilirsiniz:
- Cihazda çalışması engellenmiş uygulamaların listesi. Engellenenler listesinde tanımlanan bir uygulama cihazda yüklü olsa bile etkinleştirilemez.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung KNOX çalıştıran cihazlar tarafından kullanılabilir.
Ayrıntılar için bkz. [Özel ilkeler kullanarak Samsung KNOX cihazları için uygulamalara izin verme veya bunları engelleme](/intune-classic/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Mobil uygulama yönetimi (MAM) ilkeleriyle uyumlu yeni uygulamalar__, [iOS](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) için Yammer uygulaması, cihazın kayıtlı olup olmadığından bağımsız olarak uyumludur.

MAM ile uyumlu uygulamaların tam listesi için [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) sitesine bakın.
<!--- TFS 1252335 & 1252336 checked--->

__Intune Görüntüleyicisi uygulamaları__ Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
- Intune AV Görüntüleyicisi
- Intune PDF Görüntüleyicisi
- Google Play’den Android için Intune Resim Görüntüleyicisi

Intune Viewer uygulamaları kullanmaktan yerine, üç ayrı uygulama yerine bir uygulama dağıtarak Android cihazlarda şirket dosyalarını güvenli bir şekilde görüntülemenizi sağlayan [Rights Management uygulaması /intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) kullanmanızı öneririz. Intune görüntüleyicisi uygulamasının desteği sona erdiğinde, bu uygulama Google Store’dan kaldırılacak ve gelecekte kullanıma sunulmayacaktır.

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

- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
Eylül ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.  

- **En düşük iOS Managed Browser sürümü 8.0 olarak güncelleştirildi**<br/>
Ağustos’ta, Intune yalnızca iOS 8.0 veya üstünü çalıştıran cihazları destekleyecek, güncelleştirilmiş iOS için Microsoft Intune Managed Browser uygulamasını kullanıma sunacaktır. iOS 7.1 cihazları mevcut Managed Browser uygulamasını kullanmaya devam edebilirler, ama yeni Managed Browser özelliklerine erişebilmeleri ve bu özelliklerden tam olarak yararlanabilmeleri için lütfen kullanıcılarınızı iOS 8.0 veya üstüne güncelleştirmeye teşvik edin.  
<!---TFS 1313253--->

- **Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır** <br/>
Microsoft Intune Eylül 2016'dan itibaren Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamalarına yönelik desteği sonlandıracaktır. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->