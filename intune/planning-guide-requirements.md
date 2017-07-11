---
title: "Kullanım örneği senaryosu gereksinimlerini belirleme"
description: "Bu makale bir Microsoft Intune yalnızca bulut uygulaması için Intune kullanım örneğini ve alt kullanım örneği senaryosu gereksinimlerini belirlemenize yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8806dc965653deaca5ab370c290403ae049e5c58
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="determine-use-case-scenario-requirements"></a>Kullanım örneği senaryosu gereksinimlerini belirleme

Bu bölümde, her kullanım örneği senaryosu içindeki tüm kuruluş grupları için gereksinimleri belirlersiniz. Bu süreç mimari ve tasarım, ekleme ve dağıtım gibi diğer Intune dağıtım planlama alanlarına hazırlanmanıza yardımcı olur. Intune dağıtım projenizle ilgili olası boşlukları ve zorlukları da tanımlamanıza yardımcı olacaktır.

Kullanım örneği ve alt kullanım örneği senaryolarınızın her biri ve bunlarla ilişkili kuruluş grupları ve mobil cihaz platformları için farklı gereksinimler kümesine sahip olabilirsiniz. Örneğin, kurumsal kullanım örneği senaryosu gereksinimleriniz, cihazların Intune’a 6 karakterli bir PIN veya devre dışı bırakılmış bulut yedeklemesi gibi daha kısıtlayıcı bir cihaz ayarları kümesiyle kaydedilmesini gerektirebilir. "Kendi cihazını getir" (KCG) kullanım örneği senaryosu daha az kısıtlayıcı olabilir ve 4 karakterli bir PIN ve bulut yedeklemesine izin verir.

Ayrıca, kurumsal kullanım örneği senaryosu için farklı gereksinimler kümesine (Örneğin PIN ayarları, Wi-Fi veya VPN profili, dağıtılan uygulamalar) sahip kuruluş gruplarınız olabilir. Gereksinimleriniz mobil cihaz platformunun yetenekleri (örneğin parmak izi okuyucu, e-posta profili) tarafından da belirlenmiş olabilir.

Her bir kullanım örneği ve alt kullanım örneği senaryosu, kuruluş grubu ve mobil cihaz platformu için farklı gereksinimler kümesini gösteren kuruluş kullanım örneği gereksinimlerine ilişkin birkaç örneği aşağıda bulabilirsiniz. Kuruluşunuzun kullanım örneği gereksinimlerini girmek için aşağıdaki tabloyu da kullanabilirsiniz:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **Gruplar** | **Cihaz platformları** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Kurumsal | Bilgi çalışanı | İK, Finans | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |                                                          
| Kurumsal | Yöneticiler | İK, Finans | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |                                                         
| Kurumsal | Bilgi noktası | Perakende | Android | Cihaz ayarları, profiller, uygulamalar |
| KCG | Bilgi çalışanı | Pazarlama, Satış | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |                                                         
| KCG | Yöneticiler | Pazarlama, Satış | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |

Kuruluşunuzun kullanım örneği ve alt kullanım örneği gereksinimlerini girmek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).


## <a name="examples-of-requirements"></a>Gereksinim örnekleri

"Gereksinimler" sütununda kullanılabilecek birkaç örnek daha verelim:

- **Güvenli e-posta**
    - Exchange Online / Şirket İçi Exchange için koşullu erişim
    - Outlook uygulaması koruma ilkeleri

- **Cihaz ayarları**
    - Dört, altı karakterli PIN ayarı
    - Bulut yedeklemeyi kısıtla

- **Profiller**
    - Wi-Fi
    - VPN
    - e-posta (Windows 10 mobile)

- **Uygulamalar**
    - Uygulama koruma ilkeleriyle Office 365
    - Uygulama koruma ilkeleri ile iş kolu (LOB)

## <a name="next-section"></a>Sonraki bölüm

Sonraki bölümde [bir Intune dağıtımı planı geliştirme](planning-guide-rollout-plan.md) hakkında yönergeler sağlanır.