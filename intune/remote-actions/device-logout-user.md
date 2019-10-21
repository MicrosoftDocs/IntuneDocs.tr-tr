---
title: Bir iOS cihazının kullanıcı oturumunu kapatma
titleSuffix: Microsoft Intune
description: Intune ile bir iOS cihazının geçerli kullanıcı oturumunu kapatma hakkında bilgi edinin."
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8336f5b29cd21bb6875285177071542080eb95f3
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509461"
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Intune tarafından yönetilen iOS cihazlarında geçerli kullanıcı oturumunu kapatma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

**Geçerli kullanıcının oturumunu kapat** eylemi, paylaşılan bir iPad cihazında geçerli kullanıcının oturumunu kapatır. 

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzerinde desteklenir (yalnızca paylaşılan iPad cihazlar)
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="how-to-log-out-the-current-user"></a>Geçerli kullanıcının oturumunu kapatma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazlar listesinden bir iOS cihazı seçin, ardından **Geçerli kullanıcı oturumunu kapat** uzak cihaz eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.