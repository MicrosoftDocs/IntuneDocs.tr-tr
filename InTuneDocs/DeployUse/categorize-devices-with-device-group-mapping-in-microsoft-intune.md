---
title: "Cihaz grubu eşleme ile cihazları kategorilere ayırma | Microsoft Intune"
description: "Cihazların yönetimini kolaylaştırmak için, Microsoft Intune cihaz grubu eşleme özelliğini kullanarak bu cihazları kendi tanımladığınız kategoriler altında gruplandırın."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: c721df29fd71963feb151af71eea9ee7ebc2d3e4


---

# Cihazları Microsoft Intune’da cihaz grubu eşleme ile kategorilere ayırma
Cihazların yönetimini kolaylaştırmak için, Microsoft Intune **cihaz grubu eşleme** kullanarak bu cihazları kendi tanımladığınız kategoriler altında gruplandırın. 

Cihaz grubu eşleme aşağıdaki iş akışını kullanır:
1. Kullanmak istediğiniz her kategori için Intune cihaz grupları oluşturursunuz.
2. Seçtiğiniz kategoriyi oluşturduğunuz cihaz grubuna eşleyen cihaz grubu eşleme kuralları yapılandırırsınız.
3. Son kullanıcılar cihazlarını kaydettiklerinde, yapılandırdığınız kategorilerden birini seçmeleri gerekir. Bu seçimi yaptıklarında cihazları, oluşturduğunuz ilgili cihaz grubuna otomatik olarak eklenir.
4. Bundan sonra, ilkeleri ve uygulamaları dağıtırken bu cihaz gruplarını kullanabilirsiniz.

Kategori örnekleri:
* Kişisel
* Satış noktası cihazı
* Tanıtım cihazı
* Satış
* Muhasebe
* Yönetici

Öte yandan, istediğiniz tüm kategorileri yapılandırabilirsiniz.

## Cihaz grubu eşlemeyi yapılandırma
1. Kullanmak istediğiniz her cihaz kategorisi için, bir Intune cihaz grubu oluşturun. Grupları oluşturma hakkında bilgi için bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’yi seçin.
3. **Yönetim** çalışma alanında, **Mobil Cihaz Yönetimi**’ni genişletin ve ardından **Cihaz Grubu Eşleme**’yi seçin.
4. **Cihaz Grubu Eşleme** sayfasında cihaz grubu eşlemeyi etkinleştirin.
5. Yeni eşleme kuralı oluşturmak için **Ekle**’yi seçin.
6. **Cihaz grubu eşleme kuralı ekle** iletişim kutusunda, oluşturmak istediğiniz kategorinin adını girin ve ardından açılan listede bu kategoriyi eşlemek istediğiniz cihaz koleksiyonunu seçin. Bitirdiğinizde, **Ekle**’yi seçin.
7. Kategorileri ve grupları eklemeyi tamamladığınızda **Kaydet**’i seçin.

Artık, kullanıcılar cihazlarını kaydettiklerinde onlara sizin yapılandırdığınız kategori listesi gösterilir. Kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen cihaz grubuna eklenir.

### Ayrıca bkz.
[Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Jul16_HO3-->

