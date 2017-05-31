---
title: "İstemci yazılımı ile bilgisayarları yönetme | Microsoft Docs"
description: "Windows bilgisayarlarını Intune istemci yazılımını yükleyerek yönetin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6bd4e3315fd27201e8005b1053fa6e15bf2c21b5
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Intune yazılımı istemcisi ile Windows PC’leri bilgisayar olarak yönetme

Intune, mobil cihazların yönetimi için kuruluşlara yönelik kapsamlı bir çözüm sağlar. Intune, Windows 10 işletim sistemine yerleşik modern cihaz yönetim özelliklerini kullanarak Windows PC’leri mobil cihaz olarak yönetebilir. Kuruluşunuzun yönetim gereksinimlerini karşılamak için Intune, Intune yazılım istemcisi ile Windows PC’leri bilgisayar olarak da yönetebilir. Bu yönetim yöntemi eski Windows işletim sistemindeki geleneksel bilgisayar yönetimi özelliklerini kullanır.

Intune yazılım istemcisi, mobil cihaz olarak yönetilemeyen Windows 7 gibi eski işletim sistemlerini çalıştıran Windows PC’ler için uygundur. Intune yazılım istemcisi PC’leri buluttan yönetmek için Grup İlkesi gibi yönetim özelliklerini kullanır.

Intune, yazılım istemcisi kullanılarak Windows PC’lerin bilgisayar olarak yönetilmesini 7000 PC’ye kadar destekler. Daha büyük dağıtımlar için Windows 10 PC’leri mobil cihaz olarak yönetin. Her Intune sürümü ve Windows 10 güncelleştirmesi, mobil cihaz yönetimi mimarisine göre yönetim özellikleri içerir. Kuruluşunuzu mobil cihaz olarak yönetilen Windows 10’a taşımanızı kesinlikle öneririz.


> [!NOTE]
> Windows 8.1 ve üzeri cihazları, Intune istemci yazılımı ile bilgisayar olarak veya mobil cihaz olarak yönetebilirsiniz. İki yöntemi aynı cihazda birlikte kullanamazsınız. Bilgisayarları Intune istemci yazılımı ile yönetmeye karar vermeden önce dikkatlice düşünün. Bu konu, yalnızca Intune istemci yazılımını kullanarak cihazları bilgisayar olarak yönetme işlemi için geçerlidir.

## <a name="requirements-for-intune-pc-client-management"></a>Intune bilgisayar istemcisi yönetimi gereksinimleri

**Donanım**: Intune istemci yazılımını yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve Bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

**Yazılım**: İstemci yazılımını yüklemeye ilişkin yazılım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|İşletim sistemi | Windows Vista veya üstünü çalıştıran Windows cihazı. </br></br>**Home Edition sürümleri desteklenmez.**|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu cihaz üzerinde yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.<br /><br />Bir bilgisayardaki Windows Installer sürümünü görüntülemek için:<br /><br />  Bilgisayarda **%windir%\System32\msiexec.exe** dosyasına sağ tıklayın ve ardından **Özellikler**’e tıklayın.<br /><br />En son Windows Installer sürümünü Microsoft Developer Network web sitesindeki [Windows Installer Yeniden Dağıtılabilir Öğeleri](http://go.microsoft.com/fwlink/?LinkID=234258) bölümünden indirebilirsiniz.|
|Uyumsuz istemci yazılımını kaldırma|Intune istemci yazılımını yüklemeden önce, bu bilgisayardan tüm Configuration Manager, Operations Manager, Operations Management Suite ve Service Manager istemci yazılımlarını kaldırmalısınız.|

## <a name="deploying-the-intune-software-client"></a>Intune yazılım istemcisini dağıtma
Bir Intune yöneticisi olarak, Intune yazılımı istemcisini çeşitli şekillerde kullanıcılara sunabilirsiniz. Yönergeler için bkz. [Windows PC’lere Intune yazılım istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Intune istemci yazılımıyla bilgisayar yönetimi özellikleri
Çoğu senaryoda, cihazlarınızı Microsoft Intune’a kaydeder ve böylece daha büyük bir özellik kümesine sahip olursunuz. Bununla birlikte, bilgisayarlarınızı yönetmek için aşağıdaki özellikleri sağlayan Intune yazılım istemcisini de kullanabilirsiniz:

-   **[Yazılım güncelleştirmelerini yönetme](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** - Bilgisayarları güncel tutup, güncelleştirmelerin ne zaman uygulanacağına karar verebilirsiniz.

-   **[Windows Güvenlik Duvarı ilkesi](/intune-classic/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** - Bu özellik şirketinizde kullanılan bilgisayarların devre dışı veya yanlış yapılandırılmış bir Windows Güvenlik Duvarı’na sahip olmamasını sağlamaya yardımcı olur.

-   **[Kötü amaçlı yazılımdan koruma](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** - Intune, bilgisayarlarınızın kötü amaçlı yazılımlara karşı korunmasına yardımcı olan Endpoint Protection’ı içerir.

-   **[Uzaktan yardım](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** - Intune kullanıcıların BT destek personeliyle bağlantı kurmasına olanak tanır ve onlar da Intune’la birlikte gelen uzak masaüstü özelliğini kullanarak yardım sağlayabilir (TeamViewer yazılımı gerekir).

-   **[Yazılım lisansı yönetimi](/intune-classic/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** - Kullanılabilir yazılım lisanslarının sayısını ve bunlardan kaç tanesinin kullanıldığını izleyin.
-   **[Uygulama dağıtımı](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** - Yönettiğiniz bilgisayarlarda yazılım dağıtımı yapın. Bilgisayarları yazılım istemcisiyle yönettiğinizde bazı uygulama yönetimi özellikleri kullanılamaz.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Intune yazılım istemcisi için ilkeler ve uygulama dağıtımları

Intune istemci yazılımı, yazılım güncelleştirmelerini, Windows güvenlik duvarını ve Endpoint Protection’ı yöneterek [bilgisayarları korumaya yardımcı olan yönetim özelliklerini](policies-to-protect-windows-pcs-in-microsoft-intune.md) desteklese de Intune istemci yazılımıyla yönetilen bilgisayarlara, mobil cihaz yönetimine özgü **Windows** ilke ayarları da dahil olmak üzere diğer Intune ilkeleri hedeflenemez.

Windows bilgisayarlarını yönetmek için Intune istemci yazılımını kullandığınızda, yalnızca **Bilgisayar Yönetimi** bölümünün altında gösterilen ilkeleri kullanabilirsiniz.

Intune, kuruluşunuzda kullanılan Windows Server Active Directory Domain Services’a /intune-classic/deploy-use/resolve-gpo-and-microsoft-intune-policy-conflicts) benzer şekilde ilkeler kullanarak Windows bilgisayarları yönetir. Daha fazla bilgi için bkz. [yeni başlayanlar için Grup İlkesi](https://technet.microsoft.com/library/hh147307.aspx).

  ![Yeni Windows bilgisayar ilkesi için şablon seçin](../media/select-template-for-pc-policy.png)

Uygulamaları dağıtırken yalnızca Windows Installer’ı (.exe, .msi) kullanabilirsiniz.

  ![Bilgisayar istemci yazılımı dosyaları için platform ve konum seçin](../media/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Windows PC’ler için ortak görevler

Intune yönetim konsolunu, istemcinin yüklendiği Windows PC’lerde diğer genel bilgisayar yönetimi görevlerini yerine getirmek için kullanabilirsiniz:
- [PC yönetimini basitleştirmek için ilkeleri kullanma](use-policies-to-simplify-windows-pc-management.md) -Intune'un **Bilgisayar Yönetimi** ilkeleri açıklanır ve Microsoft Intune Center ayarları listelenir.

- [Windows bilgisayarları için donanım ve yazılım envanterini görüntüleme](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md) - Bilgisayarların donanım özellikleri ve donanım üzerinde yüklü olan yazılım özellikleri hakkındaki bilgileri listeleyen bir raporun nasıl oluşturulacağı açıklanır. Ayrıca, güncel olduğundan emin olmak için bilgisayar envanterinin nasıl yenileneceği açıklanır.
- [Bir Windows bilgisayarını devre dışı bırakma](retire-a-windows-pc-with-microsoft-intune.md) - Bir Windows bilgisayarını devre dışı bırakma adımları ve bir bilgisayarı devre dışı bıraktığınızda ne olacağı açıklanır.
- [Windows bilgisayarlar için kullanıcı cihazı bağlamayı yönetme](manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md) - Bir kullanıcıya yazılım dağıtmadan önce bir kullanıcının bilgisayara ne zaman ve nasıl bağlamanız gerektiği açıklanır.
- [Windows bilgisayarlar için uzaktan yardım isteme ve sağlama](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md) - Intune bilgisayar kullanıcılarının sizden nasıl uzaktan yardım alabileceği, önkoşullar ve TeamViewer kurulumu açıklanır.

Yukarıdaki görevler hakkında daha fazla bilgi için [genel bilgisayar yönetimi görevlerine](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) bakın.

## <a name="management-limitations-of-the-intune-client-software"></a>Intune istemci yazılımının yönetim sınırlamaları

Bilgisayarları mobil cihaz olarak yönetmek için kullanılabilecek bazı yönetim seçenekleri, Intune istemci yazılımıyla yönetilen bilgisayarlar için kullanılamaz:

-   Tam silme (seçmeli silme bulunur)
-   Koşullu erişim

Intune yönetim konsolundaki **Güncelleştirmeler**, **Koruma** ve **Lisanslar** gibi bazı bölümlerin, yalnızca Intune istemci yazılımını kullanarak cihazları kaydettiğinizde görüntülendiğini de aklınızda bulundurun.

  ![Yalnızca bilgisayar istemcisi için gösterilen yönetim konsolu öğeleri](../media/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Sorunları gidermeye yardımcı olma

Intune istemci yazılımı genellikle fazla kullanıcı etkileşimi veya sorun giderme gerektirmeden, sessizce arka planda çalışır. Bilgisayar yönetim sorunlarını çözmeniz gerekiyorsa, günlükleri gözden geçirebilirsiniz. Intune istemci yazılımı ve ilgili günlükler, %Program Files%\Microsoft\OnlineManagement dizini altına yüklenir.

Ortaya çıkabilecek sorunları ve çözümlerini veya geçici çözümlerini denetlemek için, [Microsoft Intune’da istemci kurulumu sorunlarını giderme](/intune-classic/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) konusunu da gözden geçirebilirsiniz.
