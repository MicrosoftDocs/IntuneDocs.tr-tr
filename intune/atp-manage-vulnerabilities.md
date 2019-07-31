---
title: Intune kullanarak Microsoft Defender ATP-Azure tarafından bulunan güvenlik açıklarını düzeltin | Microsoft Docs
description: Intune konsolunun içinden Microsoft Defender Gelişmiş tehdit koruması 'nın (ATP) bir parçası olan güvenlik görevlerinin ve tehdit & güvenlik açığı yönetimi 'nin nasıl yönetileceğini öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b58b27264e2f6955ae4f16843bb3493e5fdc993e
ms.sourcegitcommit: fe67741c62749fc9114e9191092ed8b786dd4ffa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68270288"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Intune kullanarak Microsoft Defender ATP tarafından tanımlanan güvenlik açıklarını düzeltin  

Intune 'U Microsoft Defender Gelişmiş tehdit koruması (ATP) ile tümleştirdiğinizde, ATPs tehdidi & güvenlik açığı yönetimi 'nden (TVM) yararlanabilir ve TVM tarafından tanımlanan uç nokta zayıflılığını düzeltmek için Intune 'U kullanabilirsiniz. Bu tümleştirme, ortamınızda düzeltme yanıt süresini iyileştirebilecek güvenlik açıklarının bulunmasına ve önceliklendirilmesine yönelik risk tabanlı bir yaklaşım sunar.  

[Tehdit & güvenlik açığı yönetimi](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) , [Microsoft Defender Gelişmiş tehdit koruması](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)'nın bir parçasıdır.  

## <a name="how-integration-works"></a>Tümleştirme nasıl çalışacaktır?  

Intune 'u Microsoft Defender Gelişmiş tehdit koruması 'na bağlandıktan sonra ATP, Yönetilen cihazlardan tehdit ve güvenlik açığı ayrıntılarını alır.  

Microsoft Defender Güvenlik Merkezi konsolunda, ATP güvenlik yöneticileri uç nokta güvenlik açıkları hakkındaki verileri gözden geçirir. Yöneticiler daha sonra, savunmasız cihazları düzeltmeye yönelik güvenlik görevleri oluşturmak için tek tıklama kullanır. Güvenlik görevleri, Intune yöneticilerinin bunları görüntüleyebildiği Intune konsoluna hemen geçirilir. Güvenlik görevi, güvenlik açığı, öncelik, durum ve güvenlik açığını düzeltmek için gerçekleştirilecek adımların türünü tanımlar. Intune Yöneticisi görevi kabul etmek veya reddetmek için seçer.  

Bir görev kabul edildiğinde, Intune Yöneticisi güvenlik görevinin bir parçası olarak sunulan kılavuzdan yararlanarak Intune ' da güvenlik açığını düzeltmeye çalışır.  

Düzeltme için genel eylemler şunları içerir:  
- Bir uygulamanın çalıştırılmasını **engelleyin**  
- Güvenlik açığını azaltmak için bir işletim sistemi güncelleştirmesi **dağıtın** .  
- Bir kayıt defteri değerini **değiştirin** .  
- Güvenlik açığını etkilemek için yapılandırmayı **devre dışı bırakın** veya **etkinleştirin** .  
- Sağlanması gereken uygun bir öneri olmadığında yöneticiye **dikkat edin** .  

Örnek iş akışı:  
- Microsoft Defender ATP içinde, contoso Media Player v4 adlı bir uygulamaya yönelik bir güvenlik açığı bulunur ve bir yönetici bu uygulamayı güncelleştirmek için bir güvenlik görevi oluşturur. Contoso medya oynatıcı, Intune ile dağıtılan yönetilmeyen bir uygulamadır.  

  Bu güvenlik görevi, Intune konsolunda bekliyor durumuyla görüntülenir:  
  ![Intune konsolundaki güvenlik görevlerinin listesini görüntüleme](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- Intune Yöneticisi, görevle ilgili ayrıntıları görüntülemek için güvenlik görevini seçer.  Ardından Yönetici, Intune 'daki durumu güncelleştiren **kabul et**' i seçer ve ATP ' de *kabul*edilir.  
  ![Bir güvenlik görevini kabul etme veya reddetme](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- Yönetici daha sonra, belirtilen kılavuza göre görevi düzeltir.  Rehberlik, gereken düzeltme türüne bağlı olarak farklılık gösterir. Kullanılabilir olduğunda düzeltme kılavuzu, Intune 'daki yapılandırmalara yönelik ilgili bölmeleri açan bağlantıları içerir. 

  Bu örnekteki medya oynatıcı yönetilen bir uygulama olmadığından, Intune yalnızca metin yönergeleri sağlayabilir. Uygulama yönetilmiyorsa, Intune güncelleştirilmiş bir sürümü indirmek için yönergeler sağlayabilir ve güncelleştirilmiş dosyaların dağıtıma eklenebilmesi için uygulamanın dağıtımını açmak üzere bir bağlantı sağlar. 

- Düzeltmeyi tamamladıktan sonra, Intune Yöneticisi güvenlik görevini açar ve **tamamlanmış görevi**seçer.  Düzeltme durumu, Intune ve ATP 'de, güvenlik yöneticilerinin güvenlik açığı için düzeltilen durumu doğrulayabileceği şekilde güncelleştirilir.  

## <a name="prerequisites"></a>Önkoşullar  

**Abonelikler**:  
- Microsoft Intune  
- Microsoft Defender Gelişmiş tehdit koruması ([ücretsiz deneme Için kaydolun](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink).)  

**ATP Için Intune yapılandırması**:  
- Microsoft Defender ATP ile hizmet bağlantısı için bir hizmet yapılandırın.  
- ATP tarafından değerlendirilme riskini alacak cihazlara **Microsoft Defender ATP (Windows 10 Masaüstü)** profil türüyle cihaz uyumluluk ilkesi dağıtın.
  Intune 'u ATP ile çalışacak şekilde ayarlama hakkında daha fazla bilgi için bkz. [Intune 'Da koşullu erişim Ile Microsoft Defender ATP için uyumluluğu zorlama](https://docs.microsoft.com/intune/advanced-threat-protection#enable-microsoft-defender-atp-in-intune).  

## <a name="work-with-security-tasks"></a>Güvenlik görevleriyle çalışma  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihaz güvenlik** > **güvenliği görevleri**' ne gidin.  
2. Listeden bir görev seçerek bu güvenlik görevinin ek ayrıntılarını görüntüleyen bir kaynak penceresi açın.  
3. Güvenlik görevi kaynağı penceresini görüntülerken ek bağlantılar seçebilirsiniz:  
   - YÖNETILEN uygulamalar-güvenlik açığı bulunan uygulamayı görüntüleyin. Güvenlik açığı birden çok uygulama için geçerliyse, uygulamaların filtrelenmiş bir listesini görürsünüz.  
   - CIHAZLAR-bu cihazdaki güvenlik açığıyla ilgili daha fazla ayrıntı içeren bir girişe bağlantı için kullanabileceğiniz, *güvenlik açığı bulunan cihazların*bir listesini görüntüleyin.  
   - Istek sahıbı-bu güvenlik görevini gönderen yöneticiye e-posta göndermek için bağlantıyı kullanın.  
   - Notlar-güvenlik görevini açarken istek sahibi tarafından gönderilen özel iletileri okuyun.  
4. Planlı eyleminiz için ATP 'ye bildirim göndermek için **kabul et** veya **Reddet** ' i seçin. Bir görevi kabul ettiğinizde veya reddettiğinizde, ATP 'ye gönderilen notları gönderebilirsiniz.  

5. Bir görevi kabul ettikten sonra, güvenlik görevini yeniden açın (kapalıysa) ve güvenlik açığını düzeltmek için düzeltme ayrıntılarını izleyin.  Güvenlik görevi ayrıntılarında ATP tarafından sunulan yönergeler, söz konusu güvenlik açığına bağlı olarak değişiklik gösterir.  

   Bunu yapmak mümkün olduğunda, Düzeltme yönergeleri Intune konsolundaki ilgili yapılandırma nesnelerini açan bağlantıları içerir.  

6. Düzeltme adımlarını tamamladıktan sonra, güvenlik görevini açın ve **görevi tamamlama**' yı seçin.  Bu eylem, hem Intune hem de ATP içindeki güvenlik görevi durumunu güncelleştirir.  

Düzeltme başarılı olduktan sonra, düzeltilen cihazlardan gelen yeni bilgilere bağlı olarak ATP 'deki risk etkilenme puanı düşürülemiyor. 

## <a name="next-steps"></a>Sonraki Adımlar
Intune ve [Microsoft Defender ATP](https://docs.microsoft.com/intune/advanced-threat-protection) hakkında daha fazla bilgi edinin  
Intune [Mobile Threat](https://docs.microsoft.com/intune/mobile-threat-defense) Defense 'i gözden geçirme  
Microsoft Defender ATP 'de [tehdit & güvenlik açığı yönetimi panosunu](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) gözden geçirin