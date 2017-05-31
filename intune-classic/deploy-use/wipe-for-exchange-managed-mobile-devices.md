---
title: "Exchange tarafından yönetilen mobil cihazlar için temizleme | Microsoft Docs"
description: "Microsoft Intune, Intune Exchange Connector ile Exchange ActiveSync (EAS) kullanılarak yönetilen mobil cihazları temizlemenize veya sıfırlamanıza olanak tanır"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4b0914ab12456fd3ad5f957d68a59df9de539176
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Exchange tarafından yönetilen mobil cihazlar için temizleme 

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Intune Exchange Bağlayıcısı’yla Exchange ActiveSync (EAS) kullanılarak yönetilen mobil cihazları temizlemenize veya sıfırlamanıza olanak tanır. Aşağıdaki tabloda Exchange ActiveSync aracılığıyla sağlanan temizleme özellikleri açıklanmaktadır:

|Temizleme türü|Windows 8.1 ve Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Tam temizleme|Posta hesabını ve önbelleğe alınan postaları kaldırır.|XFabrika sıfırlaması.|Fabrika sıfırlaması.|
|Seçici temizleme/e-posta|E-posta hesabını kaldırır.|Desteklenmez.|Desteklenmez.|
|Seçici temizleme/ilkeler|İlke zorlama kaldırılır, ancak ayarlar değiştirilmez|Xİlke zorlama kaldırılır, ancak ayarlar değiştirilmez.|İlke zorlaması kaldırılır, ancak ayarlar değiştirilmez.|
