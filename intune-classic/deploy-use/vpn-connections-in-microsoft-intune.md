---
title: "VPN bağlantıları | Microsoft Docs"
description: "VPN ayarlarını kuruluşunuzdaki kullanıcılar ve cihazlara dağıtmak için VPN profillerini kullanın."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 51096dedbc29726b2622e0a156b0d2516522e497
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="vpn-connections-in-microsoft-intune"></a>Microsoft Intune’da VPN bağlantıları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir *VPN bağlantısı profili* kullanır. VPN ayarlarını kuruluşunuzdaki kullanıcılar ve cihazlara dağıtmak için Microsoft Intune’da *VPN profilleri* kullanarak ağa kolay ve güvenli bir şekilde bağlanabilmelerini sağlayın.

Örneğin, tüm iOS cihazlara kurumsal ağ üzerindeki bir dosya paylaşımına bağlanmak için gereken ayarları sağlamak istediğinizi varsayın. Kurumsal ağa bağlanmak için gereken ayarları içeren bir VPN profili oluşturur ve ardından bu profili iOS cihaz kullanan tüm kullanıcılara dağıtırsınız. Kullanıcılar VPN bağlantısını kullanılabilir ağlar listesinde görür ve ağa en az çaba ile bağlanabilir.

Aşağıdaki cihaz türlerini VPN profillerini kullanarak yapılandırabilirsiniz:

* Android 4 ve üzeri çalıştıran cihazlar
* Android for Work cihazlar
* iOS 8.0 ve üzerini çalıştıran cihazlar
* Mac OS X 10.9 ve üzerini çalıştıran cihazlar
* Windows 8.1 ve üzeri çalıştıran kayıtlı cihazlar
* Windows Phone 8.1 ve üzeri sürümleri çalıştıran cihazlar 
* Windows 10 masaüstü ve mobil sürümlerini çalıştıran cihazlar

VPN profili yapılandırma seçenekleri seçtiğiniz cihaz türüne bağlı olarak değişir.

## <a name="vpn-connection-types"></a>VPN bağlantısı türleri

Intune aşağıdaki bağlantı türlerini kullanan VPN profillerini oluşturmayı destekler:


Bağlantı türü |iOS ve Mac OS X  |Android ve Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8.1|Windows 10 Masaüstü ve Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Evet |Evet   |Hayır    |Hayır  |Hayır    | Evet, (OMA-URI, yalnızca Mobile)|     
Cisco (IPSec)|Evet |Evet   |Hayır  |Hayır  |Hayır | Hayır|
Citrix|Evet |Evet (yalnızca Android)   |Hayır  |Hayır  |Hayır | Hayır|
Pulse Secure|Evet  |Evet |Evet   |Evet  |Evet| Evet|        
F5 Edge Client|Evet |Evet |Evet |Evet  |   Evet |  Evet|   
Dell SonicWALL Mobile Connect|Evet |Evet |Evet |Evet |Evet |Evet|         
CheckPoint Mobile VPN|Evet |Evet |Evet |Evet|Evet|Evet|
Microsoft SSL (SSTP)|Hayır |Hayır |Hayır |Hayır|Hayır|VPNv1 OMA-URI*|
Microsoft Automatic|Hayır |Hayır |Hayır |Hayır|Evet (OMA-URI)|Evet|
IKEv2|iOS özel profili|Hayır |Hayır |Hayır|Evet (OMA-URI)|Evet|
PPTP|iOS özel profili|Hayır |Hayır |Hayır|Hayır|Evet|
L2TP|iOS özel profili|Hayır |Hayır |Hayır|Evet (OMA-URI)|Evet|

\* Normalde Windows 10’da bulunan ek ayarlar olmadan.

> [!IMPORTANT]
> Bir cihaza dağıtılan VPN profillerini kullanmadan önce profil için geçerli VPN uygulamasını yüklemeniz gerekir. İlgili uygulamayı Intune kullanarak dağıtmanıza yardımcı olması için [Microsoft Intune'da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md) konusunda verilen bilgileri kullanabilirsiniz.  

 [VPN profilleri için özel yapılandırmalar](create-custom-vpn-profiles.md) konu başlığı altında, URI ayarlarını kullanarak özel VPN profilleri oluşturmayı öğrenin.     

## <a name="methods-of-securing-vpn-profiles"></a>VPN profillerini güvenli hale getirme yöntemleri

VPN profilleri, farklı üreticilerden farklı bağlantı türleri ve farklı protokoller kullanabilir. Bu bağlantılar genellikle iki yöntemden biri kullanılarak güvenli hale getirilir.

### <a name="certificates"></a>Sertifikalar

VPN profilini oluştururken, Intune’da önceden oluşturduğunuz bir SCEP veya PFX sertifika profilini seçersiniz. Bu kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin verildiğini belirtmek için oluşturduğunuz bir güvenilir sertifika profiline (veya *kök sertifikaya*) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, VPN bağlantısının kimliğini doğrulayan bilgisayara dağıtılır. Bu, genellikle VPN sunucusudur.

Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Kullanıcı adı ve parola

Kullanıcı, kullanıcı adı ve parola girerek VPN sunucusunda kimliğini doğrular.

## <a name="create-a-vpn-profile"></a>VPN profili oluşturma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **İlke** > **İlke Ekle**’yi seçin.
2. İlgili cihaz türünü genişleterek yeni ilke için bir şablon seçin ve ilgili cihaz için VPN profilini belirleyin:
    * **VPN Profili (Android 4 ve üzeri)**
    * **VPN Profili (Android for Work)**
    * **VPN Profili (iOS 8.0 ve üzeri)**
    * **VPN Profili (Mac OS X 10.9 ve üzeri)**
    * **VPN Profili (Windows 8.1 ve üzeri)**
    * **VPN Profili (Windows Phone 8.1 ve üzeri)**
    * **VPN Profili (Windows 10 Masaüstü ve Mobile ile üzeri)**

 Yalnızca özel bir VPN profili ilkesi oluşturabilir ve dağıtabilirsiniz. Önerilen ayarlar kullanılamaz.

> [!Note]
> Android for Work cihazlara yönelik bir VPN profili, VPN bağlantısını yalnızca cihazın iş profilinde yüklü uygulamalar için etkinleştirir.
>
> Bazı VPN bağlantısı türleri, Android for Work cihazlarında uygulama başına VPN destekler ve Intune ile dağıtılan uygulamalarda uygulama başına VPN etkinleştirmeye yöneliktir.  

3. VPN profili ayarlarını yapılandırmanıza yardımcı olması için aşağıdaki tabloyu kullanın:

Ayar adı  |Daha fazla bilgi  
---------|---------
**Ad**     |VPN profilini Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad belirtin.         
**Açıklama**     |VPN profiline genel bir bakış ve profili bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.         
**VPN bağlantısı adı (kullanıcılara gösterilir)**     |VPN profili için bir ad belirtin. Bu, kullanıcıların cihazlarında kullanılabilir VPN bağlantıları listesinde göreceği addır.         
**Bağlantı türü**     |  VPN profilinde kullanmak için aşağıdaki bağlantı türlerinden birini seçin: **Cisco AnyConnect** (Windows 8.1 veya Windows Phone 8.1’de kullanılamaz), **Pulse Secure**, **Citrix**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**VPN sunucusu açıklaması**     | Cihazların bağlanacağı VPN sunucusu için bir açıklama belirtin. Örnek: **Contoso VPN Sunucusu**. Bağlantı türü **F5 Edge Client** olduğunda, sunucu açıklamaları ve IP adreslerini içeren bir liste belirtmek için **Sunucu listesi** alanını belirtin.
**Sunucu IP adresi veya FQDN**    |Cihazların bağlanacağı VPN sunucusunun IP adresi veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.  Bağlantı türü **F5 Edge Client** olduğunda, sunucu açıklamaları ve IP adreslerini içeren bir liste belirtmek için **Sunucu listesi** alanını belirtin.         |         
**Sunucu listesi**     |VPN bağlantısı için kullanmak üzere yeni bir VPN sunucusu eklemek için **Ekle**'yi seçin. Ayrıca hangi sunucunun bağlantı için varsayılan sunucu olacağını belirtebilirsiniz. Bu seçenek yalnızca bağlantı türü **F5 Edge Client** olduğunda görüntülenir.         
**Tüm ağ trafiğini VPN bağlantısı üzerinden gönder**     |Bu seçeneği belirlerseniz, tüm ağ trafiği VPN bağlantısı üzerinden gönderilir. Bu seçeneği belirlemezseniz, istemci üçüncü taraf VPN sunucusuna bağlandığında bölünmüş tünel için rotaları dinamik olarak belirler. Yalnızca şirket ağına bağlantılar VPN tünelinden gönderilir. İnternet üzerindeki kaynaklara bağlandığınızda VPN tüneli kullanılmaz.
**Kimlik doğrulama yöntemi**| VPN bağlantısı tarafından kullanılan kimlik doğrulama yöntemini seçin: **Sertifikalar** veya **Kullanıcı Adı ve Parola**. (**Kullanıcı adı ve Parola**, bağlantı türü Cisco AnyConnect olduğunda kullanılamaz.) **Kimlik doğrulama yöntemi** seçeneği Windows 8.1 için kullanılamaz.
**Her oturum açmada kullanıcı kimlik bilgilerini hatırla**|Kullanıcının her bağlantı kurulduğunda kimlik bilgilerini girmek zorunda kalmaması için kullanıcı kimlik bilgilerinin hatırlanmasını sağlamak üzere bu seçeneği belirleyin.
**İstemci kimlik doğrulaması (Kimlik Sertifikası) için bir istemci sertifikası seçin**|VPN bağlantısı kimlik doğrulaması için kullanılacak ve önceden oluşturduğunuz istemci SCEP sertifikasını seçin. Intune’da sertifika profillerini kullanma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md). Bu seçenek yalnızca kimlik doğrulama yöntemi **Sertifikalar** olduğunda görüntülenir.
**Rol**| Bu bağlantıya erişimi olan kullanıcı rolünün adı belirtin. Bir kullanıcı rolü, kişisel ayarları ve seçenekleri tanımlar, belirli erişim özelliklerini etkinleştirir veya devre dışı bırakır. Bu seçenek yalnızca bağlantı türü **Pulse Secure** veya **Citrix** olduğunda görüntülenir.
**Bölge**|Kullanmak istediğiniz kimlik doğrulaması bölgesi için ad belirtin. Bir kimlik doğrulaması bölgesi, Pulse Secure veya Citrix bağlantı türü tarafından kullanılan kimlik doğrulaması kaynakları gruplandırmasıdır. Bu seçenek yalnızca bağlantı türü **Pulse Secure** veya **Citrix** olduğunda görüntülenir.
**Oturum açma grubu veya etki alanı**|Bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin. Bu seçenek yalnızca bağlantı türü **Dell SonicWALL Mobile Connect** olduğunda görüntülenir.
**Parmak izi**|VPN sunucusunun güvenilir olduğunu doğrulamak için kullanılacak bir dize (örneğin "Contoso Parmak İzi Kodu") belirtin. Parmak izi, bağlanırken aynı parmak izini sunan herhangi bir sunucuya güvenmesi için istemciye gönderilebilir. Cihazda parmak izi yoksa, parmak izini göstererek kullanıcıdan bağlandığı VPN sunucusuna güvenmesini ister. (Kullanıcı parmak iznini el ile doğrular ve bağlanmak için **güven** seçeneğini belirler.) Bu seçenek yalnızca bağlantı türü **CheckPoint Mobile VPN** olduğunda görüntülenir.
**Uygulama Başına VPN**|Bu VPN bağlantısını bir Mac OS X veya iOS uygulamasıyla ilişkilendirerek bağlantının uygulama her çalıştırıldığında açılmasını sağlamak için bu seçeneği belirleyin. Yazılım dağıtımı yaparken VPN profilini bir uygulamayla ilişkilendirebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md).
**İsteğe bağlı VPN**|iOS 8.0 ve üzeri cihazlar için isteğe bağlı VPN ayarlayabilirsiniz. Bunu ayarlanmak için yönergeler [iOS cihazları için isteğe bağlı VPN](#on-demand-vpn-for-ios-devices)’de verilmiştir.
**Proxy ayarlarını otomatik olarak algıla** (yalnızca iOS, Mac OS X, Windows 8.1 ve Windows Phone 8.1 için)|VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
**Otomatik yapılandırma betiği kullan** (yalnızca iOS, Mac OS X, Windows 8.1 ve Windows Phone 8.1 için)|VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, ayarları tanımlamak için bir otomatik yapılandırma betiği isteyip istemediğinizi belirtin ve ardından ayarları içeren dosyaya bir URL belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
**Proxy sunucusu kullan** (yalnızca iOS, Mac OS X, Windows 8.1 ve Windows Phone 8.1 için)|VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, bu seçeneği belirleyin ve ardından proxy sunucusu adresi ve bağlantı noktası numarasını belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
**Yerel adresler için proxy ayarlarını atla** (yalnızca iOS, Mac OS X, Windows 8.1 ve Windows Phone 8.1 için)|VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, belirttiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
**Özel XML** (Yalnızca Windows 8.1 ve üzeri ile Windows Phone 8.1 ve üzeri)|VPN bağlantısını yapılandıran özel XML komutları belirtin. **Pulse Secure** örneği: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. **CheckPoint Mobile VPN** örneği: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. **Dell SonicWALL Mobile Connect** örneği: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. **F5 Edge İstemcisi** örneği: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Özel XML komutları yazma hakkında daha fazla bilgi için her bir üreticinin VPN belgelerine başvurun.
**DNS Soneki arama listesi** (yalnızca Windows Phone 8.1)|Her satırda bir DNS soneki belirtin. Bir web sitesine kısa ad kullanarak bağlanılırken, belirttiğiniz her DNS soneki aranır. Örneğin, **domain1.contoso.com** ve **domain2.contoso.com** DNS son eklerini belirtip **http://mywebsite** URL’sini ziyaret ettiğinizde **http://mywebsite.domain1.contoso.com** ve **http://mywebsite.domain2.contoso.com** URL’leri aranır.
**Şirket Wi-Fi ağına bağlıyken VPN'i atla** (yalnızca Windows Phone 8.1)|Bu seçeneği cihaz şirket Wi-Fi ağına bağlıyken VPN bağlantısının kullanılmayacağını belirtmek için kullanın.
**Ev Wi-Fi ağına bağlıyken VPN'i atla** (yalnızca Windows Phone 8.1)|Bu seçeneği cihaz bir ev Wi-Fi ağına bağlıyken VPN bağlantısının kullanılmayacağını belirtmek için kullanın.

Aşağıdaki ek ayarlar, Windows 10 Masaüstü ve Mobile cihazları için kullanılabilir.

Ayar adı  |Daha fazla bilgi  
---------|---------
**Ağ trafiği kuralları**|VPN bağlantısı için hangi protokollerin, yerel ve uzak bağlantı noktasının ve adres aralıklarının etkinleştirileceğini seçin. Bir ağ trafiği kuralı oluşturmazsanız, tüm protokoller, bağlantı noktaları ve adres aralıkları etkinleştirilir. Bir kural oluşturduktan sonra, VPN bağlantısı yalnızca bu kuralda veya ek kurallarda belirttiğiniz protokolleri, bağlantı noktalarını ve adres aralıklarını kullanır.
**Rotalar**|VPN bağlantısını hangi rotaların kullanacağını seçin.
**DNS sunucuları**| Bağlantı kurulduktan sonra VPN bağlantısının hangi DNS sunucularını kullanacağını seçin.         
**İlişkili uygulamalar**|VPN bağlantısını otomatik olarak kullanacak uygulamaların listesini sağlayın. Uygulamanın türü uygulama tanımlayıcısını belirler. Bir evrensel uygulama için paket aile adını belirtin. Bir masaüstü uygulaması için söz konusu uygulamanın dosya yolunu belirtin.          


> [!IMPORTANT]
> Uygulama başına VPN yapılandırmasında kullanılması için derlediğiniz tüm uygulama listelerini güvenlik altına almanızı öneririz. Yetkisiz bir kullanıcı listenizde değişiklik yaparsa ve bunu uygulama başına VPN uygulama listesine aktarırsanız, erişimi olmaması gereken uygulamalara VPN erişimi yetkisi verme olasılığınız vardır. Uygulama listelerini güvenlik altına almanın yollarından biri, erişim denetim listesi (ACL) kullanmaktır.

Kuruluş sınırları ayarlarını kullanabileceğiniz durumların bir örneği burada verilmiştir. VPN’yi yalnızca Uzak Masaüstü için etkinleştirmek istiyorsanız 3996 dış bağlantı noktasında 27 numaralı protokol için trafiğe izin veren bir ağ trafik kuralı oluşturun. Başka hiçbir trafik VPN’yi kullanmaz.

VPN bağlantı türünüz bölünmüş tünelde trafiğin nasıl işleneceğini tanımlamanıza izin vermiyorsa kuruluş sınırlarında rotaları tanımlamak faydalıdır. Bu durumda, VPN’i kullanacak rotaları listelemek için **Rotalar**’ı kullanın.

Özel bir OMA-URI ayarı oluşturarak Windows 10 cihazının VPN kullanımını belirli uygulamalarla kısıtlayabilirsiniz.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görünür.

### <a name="on-demand-vpn-for-ios-devices"></a>iOS cihazları için isteğe bağlı VPN
iOS 8.0 ve üzeri cihazlar için isteğe bağlı VPN yapılandırabilirsiniz.

> [!NOTE]
>  
> Aynı ilkede uygulama başına VPN ve isteğe bağlı VPN kullanamazsınız.

1. İlke yapılandırma sayfasında **Bu VPN bağlantısı için isteğe bağlı kurallarını** bulun. Sütunlar, kuralların denetlediği koşul olan **Eşleşme** ve koşul eşleştiğinde ilkenin tetikleyeceği **Eylem** olarak etiketlidir.
2. Kural oluşturmak için **Ekle**’yi seçin. Kuralda ayarlayabileceğiniz iki tür eşleşme vardır. Kural başına bunlardan yalnızca birini yapılandırabilirsiniz.
  - **SSIDs** - kablosuz ağları belirtir.
  - **DNS arama etki alanları** - *team. corp.contoso.com* gibi tam etki alanı adlarını veya * *.contoso.com* kullanımı ile eşit olan *contoso.com* gibi etki alanlarını kullanabilirsiniz.
3. İsteğe bağlı: kuralın deneme olarak kullandığı bir URL olan bir URL dize araştırmasını girin. Bu profilin yüklü olduğu cihaz bu URL’ye yeniden yönlendirmesiz erişebiliyorsa, VPN oluşturulur ve cihaz hedef URL’ye bağlanır. Kullanıcı, URL araştırma dizesi sitesini görmez. URL araştırma dizesine örnek, VPN’i bağlamadan önce cihaz uyumluluğunu denetleyen bir denetim Web sunucusunun adresidir. Başka bir seçenek de URL’nin, cihazı VPN aracılığıyla hedef URL’ye bağlamadan önce VPN’in bir siteye bağlanma yeteneğini test etmesidir.
4. Aşağıdaki eylemlerden birini seçin:
  - **Bağlanma**
  - **Bağlantı değerlendirme**, üç ayara sahiptir: a. **Etki alanı eylemi**  - **Gerekirse bağlan** veya **Hiçbir zaman bağlanma**
     seçeneğini işaretleyin b. **Etki alanlarının virgülle ayrılmış listesi** - bunu yalnızca **Etki alanı eylemi** olarak **Gerekirse bağlan**
     seçeneğini belirlerseniz yapılandırırsınız c. **Gerekli URL araştırma dizesi** - bir HTTP veya HTTPS (tercih edilir) URL’si; örneğin *https://vpntestprobe.contoso.com*. Kural bu adresten bir yanıt alınıp alınmadığını denetler. Alınmıyorsa ve **Etki alanı eylemi** **Gerekirse bağlan** seçeneğiyse, VPN tetiklenir.
      
     > [!TIP]
     >
     >Bu eylemi ne zaman kullanabileceğinize bir örnek, kurumsal ağınızdaki bazı sitelerin doğrudan bir VPN kurumsal ağ bağlantısı gerektirirken başkalarının bunu gerektirmemesidir. **Virgülle ayrılmış DNS arama etki alanları listesi**’nde *corp.contoso.com* adresini listelerseniz, **Gerekirse bağlan**’ı seçebilir ve sonra bu ağdaki VPN gerektirebilecek *sharepoint.corp.contoso.com* gibi belirli siteleri listeleyebilirsiniz. Kural bundan sonra *vpntestprobe.contoso.com* adresine erişilip erişilemediğini denetler. Erişilemiyorsa, Sharepoint sitesinin VPN’i tetiklenir.
  - **Yoksay** - VPN bağlantısında hiçbir değişikliğe neden olmaz. VPN bağlıysa, bağlı bırakın; değilse, bağlamayın. Örneğin, tüm iç kurumsal Web sitelerinizin VPN’ini bağlayan bir kuralınız olabilir, ancak bu iç sitelerden birini yalnızca cihaz kurumsal ağa fiilen bağlandığında erişilebilir kılmak isteyebilirsiniz. Bu durumda, yalnızca bu site için bir yoksay kuralı oluşturursunuz.
  - **Bağlantıyı kes** - koşullar eşleştiğinde cihazların VPN bağlantısını kes. Örneğin, kurumsal kablosuz ağlarınızı **SSID’ler** alanında listeleyebilir ve cihazların VPN bağlantısını bu ağlardan birine bağlandıklarında kesen bir kural oluşturabilirsiniz.

Etki alanına özgü kurallar, tüm etki alanına yönelik kurallardan önce değerlendirilir.


## <a name="deploy-the-policy"></a>İlkeyi dağıtma

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.

2.  **Dağıtımı Yönet** iletişim kutusunda:

    -   İlkeyi dağıtmak için, ilkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'ı seçin.

    -   Dağıtmadan iletişim kutusunu kapatmak için **İptal**’i seçin.


Başarılı bir şekilde dağıtıldıktan sonra, kullanıcılar VPN bağlantıları listesinde belirttiğiniz VPN bağlantısı adını cihazlarında görür.

**İlke** çalışma alanının **Genel Bakış** sayfasında, bir durum özeti ve uyarılar ilkeyle ilgili işlem yapmanız gereken durumları tanımlar. Ayrıca, Pano çalışma alanında bir durum özeti görüntülenir.
