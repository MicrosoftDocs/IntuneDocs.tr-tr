---
title: "Windows 10 için Intune cihaz kısıtlama ayarları | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Windows 10 cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 422826ded029eb8f17856e47e98f5a09dc36bc08


---

# <a name="windows-10-and-later-device-restriction-settings-in-intune-azure-preview"></a>Intune Azure önizlemesinde Windows 10 ve üzeri cihaz kısıtlama ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Genel
-   **Ekran yakalama** - Kullanıcının cihaz ekranını resim olarak yakalamasına olanak sağlar. (Yalnızca Windows 10 Mobile)
-   **Kopyala ve yapıştır (yalnızca mobil)** - Cihazda uygulamalar arasında kopyalama ve yapıştırma eylemlerine izin verin.
-   **El ile kayıt kaldırma** - Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
-   **El ile kök sertifika yüklemesi** -  
-   **Tanılama verileri gönderme** - Olası değerler şunlardır:
    -       **Hiçbiri** Microsoft’a hiç veri gönderilmez
    -       **Temel** Microsoft’a sınırlı bilgi gönderilir
    -       **Gelişmiş** Microsoft’a gelişmiş tanılama bilgileri gönderilir
    -       **Tam** Gelişmiş ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir
-   **Kamera** - Cihazdaki kameranın kullanılmasına izin verin veya bunu engelleyin.
-   **Çıkarılabilir depolama** - Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir.
-   **Coğrafi konum** - Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.
-   **İnternet paylaşımı** - Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.
-   **Telefon sıfırlama** - Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler.
-   **USB bağlantısı** - Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler.
-   **Hırsızlık Önleme modu** - Windows Hırsızlık Önleme modunun etkin olup olmadığını yapılandırın.
-   **İşlem merkezi bildirimleri** - Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın (yalnızca Windows 10 Mobile).
-   **Cortana** - Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
-   **Ses kaydı** - Cihazın ses kaydedicisinin kullanılmasına izin verin veya bunu engelleyin.

## <a name="password"></a>Parola
-   **Parola gerekli** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
-   **Gerekli parola türü** - Parolanın yalnızca sayısal mı yoksa alfasayısal mı olacağını belirtir.
-   **En az parola uzunluğu** - Yalnızca Windows 10 Mobile için geçerlidir.
-   **Cihaz silinmeden önceki oturum açma hatası sayısı** - Windows 10 çalıştıran cihazlar için: Cihazda BitLocker etkinse, belirttiğiniz oturum açma sayısından sonra cihaz BitLocker kurtarma moduna alınır. Cihazda BitLocker etkin değilse, bu ayar uygulanmaz.
Windows 10 Mobile çalıştıran cihazlar için: Belirttiğiniz oturum açma sayısından sonra cihaz silinir.
-   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.
-   **Parola geçerlilik süresi (gün)** - Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.
-   **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.
-   **Cihaz boşta kalma durumundan çıktığında parola isteme** - Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir (yalnızca Windows 10 Mobile).
-   **Şifreleme** - Hedeflenen cihazlarda şifrelemeyi etkinleştirin (yalnızca Windows 10 Mobile).
## <a name="app-store"></a>Uygulama Mağazası

-   **Uygulama mağazası (yalnızca mobil)** - Windows 10 Mobile cihazlarında uygulama mağazasının kullanılmasını etkinleştirin veya engelleyin.
## <a name="edge-browser"></a>Edge Tarayıcısı
-   **Microsoft Edge tarayıcısı (yalnızca mobil)** - Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verin.
-   **SmartScreen** - Sahte web sitelerini engelleyen SmartScreen’i etkinleştirir veya devre dışı bırakır.
-   **Kullanıcıyı-izleme üst bilgileri gönderme** - Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine izleme (DNT) üst bilgileri gönderecek şekilde yapılandırır.
-   **Tanılama bilgileri** - Tarayıcının İnternet tanımlama bilgilerini cihaza kaydetmesine olanak tanır.
-   **JavaScript** - Edge tarayıcısında JavaScript gibi betiklerin çalıştırılmasına izin verir.
-   **Açılır pencereler** - Tarayıcıda açılır pencereleri engeller.<br>Yalnızca Windows 10 masaüstü için geçerlidir).
-   **Arama önerileri** - Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.
-   **İntranet trafiğini Internet Explorer'a gönder** - Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar. <br>(Yalnızca Windows 10 masaüstü).
-   **Otomatik Doldurma** - Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.<br>(Yalnızca Windows 10 masaüstü)
-   **Parola Yöneticisi** - Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
-   **Kurumsal mod site listesi konumu** - Kurumsal modda açılan web siteleri listesinin nerede bulunacağını belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü).
## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **Microsoft hesabı** - Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.
-   **Microsoft olmayan hesaplar** - Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.
-   **Microsoft hesabı için ayar eşitlemesi** - Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin.
## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı
-   **Veri dolaşımı** - Verilere erişirken ağlar arasında dolaşıma izin verin.
-   **Hücresel ağ üzerinden VPN** - Cihazın hücresel ağa bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.
-   **Hücresel ağ üzerinden VPN dolaşımı** - Cihazın hücresel ağda dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.
-   **Bluetooth** - Kullanıcının cihazda Bluetooth’u etkinleştirmesine ve yapılandırmasına izin verilip verilmeyeceğini denetler.
-   **Bluetooth bulunabilirliği** - Cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
-   **Bluetooth reklamları** - Cihazın Bluetooth üzerinden reklamlar almasına olanak tanır.
-   **NFC** - Kullanıcının cihazda Yakın Alan İletişimi özelliklerini etkinleştirmesine ve yapılandırmasına olanak tanır.
-   **Wi-Fi** - Kullanıcının cihazda Wi-Fi’yi etkinleştirmesine ve yapılandırmasına olanak tanır (yalnızca Windows 10 Mobile).
-   **Wi-Fi etkin noktalarına otomatik bağlanma** - Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.
-   **El ile Wi-Fi yapılandırması** - Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin (yalnızca Windows 10 Mobile).
## <a name="defender"></a>Defender

-   **Gerçek zamanlı izleme** - Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramayı etkinleştirir.
-   **Davranış izleme** - Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar.
-   **Ağ İnceleme Sistemi (NIS)** - Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur.
-   **İndirilen tüm öğeleri tara** - Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
-   **Microsoft web tarayıcılarında yüklenen betikleri tarama** - Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.
-   **Defender'a son kullanıcı erişimi** - Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler.
Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.
-   **İmza güncelleştirme aralığı (saat olarak)** - Defender’ın yeni imza dosyalarını denetleme aralığını belirtin.
-   **Dosya ve program etkinliğini izleme** - Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir.
-   **Karantinaya alınmış kötü amaçlı yazılım silinmeden önce geçecek gün sayısı** - Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz.
-   **Tarama sırasında CPU kullanım sınırı** - Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar.
-   **Arşiv dosyalarını tara** - Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.
-   **Gelen posta iletilerini tarama** - Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.
-   **Tam tarama sırasında çıkarılabilir sürücüleri tarama** - Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.
-   **Tam tarama sırasında eşlenmiş ağ sürücülerini tarama** - Defender’ın eşlenmiş ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.
-   **Ağ klasörlerinden açılan dosyaları tarama** - Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.
Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.
-   **Bulut koruması** - Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir veya bunu engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.
-   **Örnek göndermeden önce kullanıcılara sor** - Kötü amaçlı olup olmadıklarını belirlemek için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler.
-   **Günlük hızlı tarama gerçekleştirilecek saat** - Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.
-   **Gerçekleştirilecek sistem taraması türü** - Sistem taraması zamanladığınızda gerçekleştirilecek tarama düzeyini belirtmenize olanak tanır.
## <a name="defender-exclusions"></a>Klasör Dışlamaları

-   **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosyalar ve klasörler** - Dışlama listesine **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
-   **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosya uzantıları** - Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
-   **Taramaların ve gerçek zamanlı korumanın dışında bırakılacak işlemler** - Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.



<!--HONumber=Feb17_HO1-->

