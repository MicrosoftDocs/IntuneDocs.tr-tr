---
title: "Yönetilen tarayıcıyla web erişimini yönetme | Microsoft Intune"
description: "Web’e gözatmayı ve web verilerinin başka uygulamalara aktarımını kısıtlamak için, yönetilen tarayıcı uygulamasını dağıtın."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ms.reviewer: maxles
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2fcd53d335aa18701ba0b8c3c75569febbee2cd5
ms.openlocfilehash: d07a5dde05055c54f5b89c8aa5f49203d0a22b97


---

# Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme
Yönetilen tarayıcı, Microsoft Intune kullanarak kuruluşunuzda dağıtabileceğiniz bir web tarama uygulamasıdır. Yönetilen tarayıcı ilkesi, yönetilen tarayıcı kullanıcılarının ziyaret edebileceği web sitelerini kısıtlayan bir izin verilenler listesi veya engellenenler listesi yapılandırır.

Bu uygulama bir yönetilen uygulama olduğundan, buna mobil uygulama yönetimi ilkeleri de uygulayabilirsiniz. Bu ilkelere kesme, kopyalama ve yapıştırma denetimi, ekran yakalamalarını engelleme ve kullanıcıların seçtiği içerik bağlantılarının yalnızca diğer yönetilen uygulamalarda açılmasını sağlama dahil olabilir. Ayrıntılar için bkz. [Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> [!IMPORTANT]
>Kullanıcılar uygulama mağazasından yönetilen tarayıcıyı yüklerse ve Intune tarayıcıyı yönetmezse aşağıdaki davranış geçerlidir:<br /><br />
iOS – Yönetilen tarayıcı uygulaması temel bir web tarayıcısı olarak kullanılabilir, ancak bazı özellikler kullanılamaz ve Intune ile yönetilen diğer uygulamaların verilerine erişilemez.<br />
Android – Yönetilen tarayıcı uygulaması kullanılamaz.<br /><br />
Kullanıcılar yönetilen tarayıcıyı iOS 9'dan eski bir sürümdeki iOS cihazına kendileri yüklerse, tarayıcı oluşturduğunuz hiçbir ilke tarafından yönetilmez. Tarayıcının Intune tarafından yönetildiğinden emin olmak için kullanıcıların uygulamayı kaldırmaları ve yönetilen uygulama olarak sizin tarafınızdan dağıtılması gerekir. iOS 9 ve üstü sürümlerde kullanıcılar yönetilen tarayıcıyı kendileri yüklerse tarayıcının ilke tarafından yönetilmesine izin vermesi istenir.

Aşağıdaki cihaz türleri için yönetilen tarayıcı ilkeleri oluşturabilirsiniz:

-   Android 4 ve üzeri çalıştıran cihazlar

-   iOS 7.1 ve üzeri çalıştıran cihazlar

Intune tarafından yönetilen tarayıcı, [Microsoft Intune uygulama iş ortaklarının](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) web içeriklerini açmayı destekler.

## Yönetilen tarayıcı ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin.

2.  Aşağıdaki **Yazılım** ilkesi türlerinden birini yapılandırın:

    -   **Yönetilen Tarayıcı İlkesi (Android 4 ve üzeri)**

    -   **Yönetilen Tarayıcı İlkesi (iOS 7.1 ve üzeri)**

    İlkeleri oluşturma ve kullanma hakkında daha fazla bilgi için, [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) konusuna bakın.

3.  Yönetilen tarayıcı ilkesi ayarlarını yapılandırmanıza yardımcı olması için aşağıdakileri kullanın:

    - **Ad**. Yönetilen tarayıcı ilkesini Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad belirtin.
    - **Açıklama**. Yönetilen tarayıcı ilkesine genel bir bakış ve profili bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.
    - **Yönetilen Tarayıcının açabileceği URL'leri kısıtlamak için bir izin verilenler listesi veya engellenenler listesini etkinleştir**. Aşağıdaki seçeneklerden birini belirleyin:
        - **Yönetilen tarayıcının yalnızca aşağıda listelenen URL'leri açmasına izin ver**. Yönetilen tarayıcının açabileceği URL'lerin listesini belirtin.
        - **Yönetilen tarayıcının aşağıda listelenen URL'leri açmasını engelle**. Yönetilen tarayıcının açması engellenecek URL'lerin listesini belirtin.
**Not**: Aynı yönetilen tarayıcı ilkesine hem izin verilen hem de engellenen URL'leri ekleyemezsiniz.
Belirtebileceğiniz URL biçimleri hakkında daha fazla bilgi için, bu konudaki **İzin verilen ve engellenen URL’ler için URL biçimi** bölümüne bakın.

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görünür.

## Yönetilen tarayıcı uygulaması için bir dağıtımı oluşturma
Yönetilen tarayıcı ilkesini oluşturduktan sonra, yönetilen tarayıcı uygulaması için bir yazılım dağıtımı oluşturabilir ve bunu oluşturduğunuz yönetilen tarayıcı ilkesiyle ilişkilendirebilirsiniz.

> [!IMPORTANT]
> Yönetilen tarayıcı ilkeleri diğer Intune ilkeleriyle aynı şekilde dağıtılmaz. Bu ilke türü bir yönetilen yarayıcı yazılım paketiyle ilişkilendirilmelidir.

İlkeyi uygulamayla ilişkilendirmek için **Mobil Uygulama Yönetimi** sayfasında yönetilen tarayıcı ilkesini seçtiğinizden emin olarak uygulamayı dağıtın.

Uygulamaları dağıtma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md).

## Yönetilen tarayıcı için güvenlik ve gizlilik

-   iOS cihazlarda, kullanıcıların ziyaret ettiği süresi dolmuş veya güvenilmeyen sertifikalara sahip web siteleri açılmaz.

-   Yönetilen tarayıcı, kullanıcıların cihazlarındaki yerleşik tarayıcı için yaptığı ayarları kullanamaz. Bunun nedeni yönetilen tarayıcının bu ayarlara erişimi olmamasıdır.

-   Yönetilen tarayıcıyla ilişkilendirilmiş bir mobil uygulama yönetimi ilkesinde **Erişim için basit PIN gerektir** veya **Erişim için şirket kimlik bilgilerini gerektir** seçeneğini yapılandırırsanız ve bir kullanıcı kimlik doğrulama sayfasındaki yardım bağlantısını seçerse, yönetilen tarayıcı ilkesinde bir engelleme listesine eklenmiş olmasından bağımsız olarak herhangi bir İnternet sitesine göz atabilir.

-   Yönetilen tarayıcı sitelere yalnızca doğrudan erişildiğinde erişimi engelleyebilir. Siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullanıldığında erişimi engelleyemez.

-   Kimlik doğrulamasına izin vermek ve Intune belgelerine erişilebildiğinden emin olmak amacıyla **&#42;.microsoft.com** adresi izin verilenler veya engellenenler listesi ayarlarının dışında tutulur. Adrese her zaman izin verilir.

### Kullanım verilerini kapatma
Microsoft, ürün ve hizmetlerini geliştirmek için yönetilen tarayıcının performansı ve kullanımı hakkında otomatik olarak anonim bilgiler toplar. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur.

## Başvuru bilgileri

### İzin verilen ve engellenen URL'ler için URL biçimi
İzin verilenler ve engellenenler listesinde URL belirtirken kullanabileceğiniz izin verilen biçimler ve joker karakterler hakkında bilgi almak için aşağıdaki bilgileri kullanın:

-   ‘**&#42;**’ joker karakter sembolünü aşağıdaki izin verilen örnekler listesinde yer alan kurallara uygun olarak kullanabilirsiniz.

-   Tüm URL'leri listeye eklerken başlarına **http** veya **https** önekini yazdığınızdan emin olun.

-   Adreste bağlantı noktası numaraları belirtebilirsiniz. Bir bağlantı noktası numarası belirtmezseniz, kullanılan değerler şöyle olacaktır:

    -   http için bağlantı noktası 80

    -   https için bağlantı noktası 443

    Bağlantı noktası numarası için joker karakter kullanımı desteklenmez. Örneğin, **http&colon;//www&period;contoso&period;com:*;** ve **http&colon;//www&period;contoso&period;com: /*;** desteklenmez.

-   URL belirtirken kullanabileceğini izin verilen desenler hakkında bilgi almak için aşağıdaki tabloyu kullanın:

|URL|Ayrıntılar|Eşleşir|Eşleşmez|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Tek bir sayfayla eşleşir|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Tek bir sayfayla eşleşir|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|www.contoso.com ile başlayan tüm URL'lerle eşleşir|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|contoso.com altındaki tüm alt etki alanlarıyla eşleşir|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Tek bir klasörle eşleşir|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Bağlantı noktası numarası kullanarak tek bir sayfayla eşleşir|http://www.contoso.com:80||
    |https://www.contoso.com|Güvenli tek bir sayfayla eşleşir|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Tek bir klasör ve tüm alt klasörleriyle eşleşir|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Belirtemeyeceğiniz bazı girdi örnekleri aşağıda verilmiştir:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP adresleri

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

### İzin verilenler ve engellenenler listeleri arasındaki çakışmalar nasıl çözümlenir?
Bir cihaza birden çok yönetilen tarayıcı ilkesi dağıtılır ve ayarlar çakışırsa, hem mod (izin verme veya engelleme) hem de URL listeleri çakışmalar için incelenir. Bir çakışma durumunda aşağıdaki davranış uygulanır:

-   İki ilkenin modu aynı ancak URL listeleri farklıysa, URL'ler cihazda uygulanmaz.

-   İki ilkenin modu farklı ancak URL listeleri aynıysa, URL'ler cihazda uygulanmaz.

-   Bir cihaz ilk defa yönetilen tarayıcı ilkelerini alıyorsa ve iki ilke çakışıyorsa, URL'ler cihazda uygulanmaz. Çakışmaları görüntülemek için **İlkeler** çalışma alanının **İlke Çakışmaları** düğümünü kullanın.

-   Bir cihaz zaten bir yönetilen tarayıcı ilkesi aldıysa ve çakışan ayarlara sahip ikinci bir ilke dağıtılıyorsa, orijinal ayarlar cihazda kalır. Çakışmaları görüntülemek için **İlkeler** çalışma alanının **İlke Çakışmaları** düğümünü kullanın.



<!--HONumber=Aug16_HO1-->

