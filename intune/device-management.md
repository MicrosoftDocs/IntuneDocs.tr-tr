---
title: "Intune ile cihazları yönetme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune ile yönettiğiniz cihazları görmeyi ve bu cihazlar üzerinde çeşitli işlemler yapmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1fdb86184875d7082659d608b445b41b2ad9aa9e
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune cihaz yönetimi nedir?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

**Cihazlar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır. İş yüküne erişmek için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.

Şimdi, aşağıdakilerden birini seçin:

- **Genel Bakış** Kaydettiğiniz cihazlar ve her cihazın çalıştırdığı işletim sistemleri hakkında bilgi alın.
- **Yönet** - Yönettiğiniz tüm cihazların listesini görmek için **Tüm Cihazlar**’ı seçin.
    Listedeki cihazlardan birini seçerek <*cihaz adı*> **Genel Bakış** dikey penceresini açın. Burada aşağıdakilerden birini seçebilirsiniz:
    - **Genel Bakış**  - Cihaz hakkında adı, sahibi, bir KCG cihazı olup olmadığı, en son ne zaman iade edildiği gibi genel bilgilere bakın.

    - **Donanım** - Cihaz hakkında boş depolama alanı, modeli ve üreticisi gibi daha ayrıntılı bilgilere bakın.
    ![Yönetilen cihaz donanım envanteri](./media/hardware-inventory.png)
    - **Algılanan Uygulamalar** - Intune’un cihazda yüklü olduğunu bulduğu tüm uygulamaların listesini görüntüler.
    ![Algılanan uygulamalar düğümü](./media/detected-applications.png)
- **İzleme** Yönettiğiniz cihazlarda gerçekleştirilen cihaz eylemlerinin listesini ve bu eylemlerin geçerli durumu görmek için **Cihaz Eylemleri**’ni seçin.
![Cihaz eylemlerini izleme](./media/monitor-device-actions.png)
- **Yardım ve Destek** - Sorun giderme ve destek belgelerine bağlantılar görüntüler.

## <a name="available-device-actions"></a>Kullanılabilir cihaz eylemleri

Buna ek olarak, cihaz üzerinde aşağıdaki uzak eylemleri de gerçekleştirebilirsiniz (tüm cihaz platformları tüm eylemleri desteklemez):

### <a name="remove-company-data"></a>**Şirket verilerini kaldır**
Yalnızca Intune tarafından yönetilen şirket verilerini kaldırır. Cihazdan kişisel verileri kaldırmaz. Cihaz artık Intune tarafından yönetilmez ve şirket kaynaklarına erişemez (Azure Active Directory’ye katılmış olan Windows cihazlarında desteklenmez).

### <a name="factory-reset"></a>**Fabrika sıfırlaması**
Cihazı varsayılan ayarlarına döndürür. Cihaz artık Intune tarafından yönetilmez ve hem şirket verileri hem de kişisel veriler kaldırılır. Bu eylemi geri alamazsınız.

### <a name="remote-lock"></a>**Uzaktan kilitleme**
Cihazı kilitler. Cihaz sahibinin kilidi açmak için geçiş kodunu kullanması gerekir. PIN veya parola ayarlanmış bir cihazı yalnızca uzaktan kilitleyebilirsiniz.

### <a name="reset-passcode"></a>**Geçiş Kodunu Sıfırla**
Cihaz için <*cihaz adı*> **Genel Bakış** dikey penceresinde görüntülenecek yeni bir geçiş kodu oluşturur.

### <a name="bypass-activation-lock"></a>**Etkinleştirme Kilidini Atla**
Kullanıcının Apple kimliği ve parolası olmadan iOS cihazının etkinleştirme kilidini kaldırır. Siz etkinleştirme kilidini atladıktan sonra, iPhone’umu Bul uygulaması başlatıldığında cihaz etkinleştirme kilidini yeniden açar. Etkinleştirme kilidini, ancak cihaza fiziksel erişiminiz varsa atlayın.

### <a name="fresh-start"></a>**Fresh Start**

Creators Update çalıştıran bir Windows 10 bilgisayarında yüklü tüm uygulamaları kaldırır ve ardından bilgisayarı Windows’un son sürümüne güncelleştirir.
Bu eylem genellikle yeni bir PC ile gelen önceden yüklü (OEM) uygulamaların kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz. Bu durumda uygulamalar ve ayarlar kaldırılır, ancak kullanıcıların Giriş klasörünün içeriği korunur.


### <a name="lost-mode"></a>**Kayıp modu**
Bir iOS cihazı kaybolursa veya çalınırsa kayıp modunu etkinleştirebilirsiniz. Bu, cihazın kilit ekranında görüntülenecek bir mesaj ve telefon numarası belirtmenize olanak tanır. Bunu yapmak için:
1.    iOS cihazının özellikler dikey penceresinde **Diğer** > **Kayıp modu**’nu seçin.
2.    **Kayıp modu** dikey penceresinde kayıp modunu etkinleştirin, görüntülenecek olan iletiyi ve isteğe bağlı olarak bir iletişim telefon numarası girin.
3.    **Tamam**’a tıklayın.
Kayıp modunu etkinleştirdiğinizde cihazın tüm kullanımını engellemiş olursunuz. Siz kayıp modunu devre dışı bırakmadıkça son kullanıcı cihaza erişemez. Kayıp modu etkin durumdayken **Cihazı bul** eylemini kullanarak cihazın nerede olduğunu bulabilirsiniz.
Kayıp modunu kullanmak için cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

### <a name="locate-device"></a>**Cihazı bul**
Kayıp veya çalınmış bir iOS cihazının konumunu haritada görüntülemek için bu uzak eylemi kullanın. Cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir. Bu eylemi kullanabilmek için önce cihazın kayıp moduna geçirilmiş olması gerekir.
1.    iOS cihazının özellikler dikey penceresinde **Diğer** > **Cihazı bul**’u seçin.
2.    Cihaz bulunduktan sonra konumu **Cihazı bul** dikey penceresinde görüntülenir.
    ![Cihazı bul dikey penceresi](./media/locate-device.png)

>[!NOTE]
>Gizlilik nedeniyle haritayı belirli bir oranda yakınlaştırabilirsiniz.

### <a name="restart"></a>**Yeniden başlat**
Cihazın yeniden başlatılmasına neden olur. Yeniden başlatma işlemi cihaz sahibine otomatik olarak bildirilmez, dolayısıyla cihaz sahibi çalışmasını kaybedebilir.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Intune'a gönderilir ve Azure portalında görüntülenir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kayıp modunu yapılandırırken kilit ekranında görüntülenmesi için girdiğiniz iletinin, cihazın konumunun belirlenebileceği bilgisini içermesini öneririz.
