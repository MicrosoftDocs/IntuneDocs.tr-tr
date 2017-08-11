---
title: "Mobil Uygulama Yönetimi (MAM) | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Mobil Uygulama Yönetimi kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 44358d68a653760804f11668ab64d30ebf7ae9eb
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Mobil Uygulama Yönetimi (MAM) varlıkları için başvuru

**Mobil Uygulama Yönetimi** kategorisi, mobil uygulamalar için aşağıdaki gibi varlıklar içerir:

  -  Uygulamalar
  -  Örnek Sayısı
  -  İade etme durumu
  -  Sistem durumu
  -  İlke durumu
  -  Kayıt durumu
  -  Platform türleri

## <a name="mamapplication"></a>MamApplication

**MamApplication** varlığı, Mobil Uygulama Yönetimi (MAM) aracılığıyla yönetilen ancak kuruluşunuza kayıtlı olmayan iş kolu (LOB) uygulamalarını listeler.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| ApplicationKey |Veri ambarındaki MAM uygulamasının benzersiz tanıtıcısı |123 |
| ApplicationName |MAM uygulamasının adı |“Word” |
| ApplicationID |MAM uygulamasının uygulama kimliği |b66bc706-ffff-7437-0340-032819502773 |
| IsDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir. True- MAM uygulamasının bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. False- bu MAM uygulaması için en son kayıt. |Doğru/Yanlış |
| StartDateInclusiveUTC |Bu MAM uygulamasının veri ambarında oluşturulduğu tarih ve saat (UTC) |23/11/2016 00:00:00 |
| DeletedDateUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve saat (UTC) |23/11/2016 00:00:00 |
| RowLastModifiedDateTimeUTC |Bu MAM uygulamasının veri ambarında son değiştirildiği tarih ve saat (UTC) |23/11/2016 00:00:00 |

## <a name="mamapplicationinstance"></a>MamApplicationInstance

**MamApplicationInstance** varlığı, Mobil Uygulama Yönetimi (MAM) uygulamalarını kullanıcı ve cihaz başına tekil örnekler olarak listeler. Varlıkta listelenen tüm kullanıcılar ve cihazlar korunur. Örneğin, hepsine en az bir MAM İlkesi atanmıştır.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| ApplicationInstanceKey |Veri ambarındaki MAM uygulaması örneğinin benzersiz tanıtıcısı - vekil anahtar |123 |
| UserId |Bu MAM uygulamasını yükleyen kullanıcının kullanıcı kimliği |b66bc706-ffff-7437-0340-032819502773 |
| ApplicationInstanceId |MAM uygulaması örneğinin benzersiz tanıtıcısı - ApplicationInstanceKey ile benzer ancak tanımlayıcı, bir doğal anahtardır |b66bc706-ffff-7437-0340-032819502773 |
| ApplicationID |Bu MAM uygulamasının uygulama kimliği |com.microsoft.groupies-daily.<IOS> |
| ApplicationVersion |Bu MAM uygulamasının uygulama sürümü |2 |
| CreatedDate |Bu MAM uygulama örneği kaydının oluşturulduğu tarih. Değer null olabilir. |23/11/2016 00:00:00 |
| Platform |MAM uygulamasının yüklü olduğu cihazın platformu |2 |
| PlatformVersion |Bu MAM uygulamasının yüklü olduğu cihazın platform sürümü |2.2 |
| SdkVersion |Bu MAM uygulamasını sarmalayan MAM SDK sürümü |3.2 |
| DeviceId |Bu MAM uygulamasının yüklü olduğu cihazın kimliği |b66bc706-ffff-7437-0340-032819502773 |
| DeviceName |Bu MAM uygulamasının yüklü olduğu cihazın adı |"Cihazım" |
| IsDeleted |Bu MAM uygulama örneği kaydının güncelleştirilip güncelleştirilmediğini gösterir. True- bu MAM uygulaması örneğinin, bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. False- bu MAM uygulaması örneği için en son kayıt. |Doğru/Yanlış |
| StartDateInclusiveUtc |Bu MAM uygulaması örneğinin, veri ambarında oluşturulduğu tarih ve saat (UTC) |23/11/2016 00:00:00 |
| DeletedDateUtc |IsDeleted değerinin True olarak değiştirildiği tarih ve saat (UTC) |23/11/2016 00:00:00 |
| RowLastModifiedDateTimeUtc |Bu MAM uygulaması örneğinin, veri ambarında son değiştirildiği tarih ve saat (UTC) |23/11/2016 00:00:00 |

## <a name="mamcheckin"></a>MamCheckin

**MamCheckin** varlığı, bir Mobil Uygulama Yönetimi (MAM) uygulama örneği Intune Hizmetine iade etme işlemi yaparken toplanan verileri temsil eder. 

> [!Note]  
> Bir uygulama örneği gün içinde birden çok kez iade etme işlemi yaparsa, veri ambarı bunu tek bir iade etme işlemi olarak depolar.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |MAM uygulamasının iade etme işleminin, veri ambarına kaydedildiği zamanı belirten tarih anahtarı | 20160703 |
| ApplicationInstanceKey |Bu MAM uygulamasının iade etme işlemiyle ilişkili uygulama örneğinin anahtarı |2/5/1900 00:00:00 |
| UserKey |Bu MAM uygulamasının iade etme işlemiyle ilişkili kullanıcı anahtarı |12/1/1900 00:00:00 |
| ApplicationKey |İade etme işlemi yapan MAM uygulamasının anahtarı |10/1/1900 00:00:00 |
| DeviceHealthKey |Bu MAM uygulamasının iade etme işlemiyle ilişkili DeviceHealth için anahtar |2/1/1900 00:00:00 |
| PlatformKey |Bu MAM uygulamasının iade etme işlemiyle ilişkili cihaz platformunu temsil eder |1/1/1900 00:00:00 |
| EffectiveAppliedPolicyKey |İade etme işlemi yapan MAM uygulamasıyla ile ilişkili olarak uygulanan geçerli ilkeyi temsil eder. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir. |2/5/1900 00:00:00 |
| LastCheckInDate |Bu MAM uygulamasının en son iade etme işlemi yaptığı tarih ve saat. Değer null olabilir. |23/11/2016 00:00:00 |

## <a name="mamdevicehealth"></a>MamDeviceHealth

**MamDeviceHealth** varlığı, işletim sistemi kısıtlamaları kaldırılmış olsa bile Mobil Uygulama Yönetimi (MAM) ilkelerinin dağıtıldığı cihazları temsil eder.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| DeviceHealthKey |Cihazın ve cihazla ilişkili sistem durumunun, veri ambarındaki benzersiz tanıtıcısı - vekil anahtar |1/1/1900 00:00:00 |
| DeviceHealth |Cihazın ve cihazla ilişkili sistem durumunun benzersiz tanıtıcısı - DeviceHealthKey ile benzer ancak tanıtıcı, doğal bir anahtardır |1/1/1900 00:00:00 |
| DeviceHealthName |Cihazın durumunu temsil eder. Kullanılamıyor - bu cihaz hakkında bilgi yok. İyi durumda - cihazın işletim sistemi kısıtlamaları kaldırılmamış. İyi durumda değil - cihazın işletim sistemi kısıtlamaları kaldırılmış. |Kullanılamıyor, İyi durumda, İyi durumda değil |
| RowLastModifiedDateTimeUtc |Bu MAM Cihazının Sistem Durumunun, veri ambarında son değiştirildiği tarih ve saat (UTC) |23/11/2016 00:00:00 |

## <a name="mameffectivepolicy"></a>MamEffectivePolicy

**MamEffectivePolicy** varlığı, kuruluşunuzda Mobil Uygulama Yönetimi (MAM) uygulanan tüm geçerli ilkeleri listeler. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| EffectivePolicyKey |MAM geçerli ilkesinin, veri ambarındaki benzersiz tanıtıcısı |2 |
| RealPolicyKey |MAM ilkesinin, BT uzmanı tarafından yazılan benzersiz tanıtıcısı. |1 |
| RowCreatedDateTimeUtc |Bu geçerli ilkenin, veri ambarında oluşturulduğu tarih ve saat (UTC). |23/11/2016 00:00:00 |

## <a name="mamglobalapplication"></a>MamGlobalApplication

**MamGlobalApplication** varlığı, Mobil Uygulama Yönetimi (MAM) aracılığıyla yönetilen ancak kuruluşunuza kayıtlı olmayan mağaza uygulamaları listeler.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| ApplicationKey |Veri ambarındaki mağaza uygulamasının benzersiz tanıtıcısı - vekil anahtar olarak bilinir. |123 |
| ApplicationID |Mağaza uygulamasının benzersiz tanıtıcısı. Tanıtıcı, ApplicationKey ile benzer ancak doğal bir anahtardır. |com.microsoft.skydrive.<ios> |
| ApplicationName |MAM Genel Uygulama Adı. |Skydrive |
| RowLastModifiedDateTimeUtc |Bu MAM Genel Uygulamasının, veri ambarında son değiştirildiği tarih ve saat (UTC). |23/11/2016 00:00:00 |

## <a name="mamplatform"></a>MamPlatform

**MamPlatform** varlığı, Mobil Uygulama Yönetimi (MAM) uygulamasının yüklendiği platform adlarını ve türlerini listeler.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| PlatformKey |Veri ambarındaki platformun benzersiz tanıtıcısı - vekil anahtar |123 |
| Platform |Platformun benzersiz tanıtıcısı; PlatformKey ile benzer ancak doğal bir anahtardır |123 |
| PlatformName |Platform adı |Kullanılamıyor, Yok, Windows, IOS, Android |
| RowLastModifiedDateTimeUtc |Bu platformun veri ambarında son değiştirildiği tarih ve saat (UTC) |23/11/2016 00:00:00 |