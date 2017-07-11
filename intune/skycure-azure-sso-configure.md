---
title: "Skycure’u Azure AD çoklu oturum açma kullanacak şekilde yapılandırma"
titleSuffix: Intune on Azure
description: "Skycure’u Azure AD çoklu oturum açma kullanacak şekilde yapılandırma"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0466ac4-4942-4c4c-b8af-996b597c701d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b2d8a79baf65208e87dbe85d8cc934e167710144
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Skycure’u Azure Active Directory Çoklu Oturum Açma (SSO) kullanacak şekilde yapılandırma

Intune’u Skycure ile tümleştirdiğinizde, Azure AD SSO kullanılır. Başlıca avantajları şunlardır:

-   **Yöneticiler**, Microsoft portallarında (Intune, Azure) ve Skycure Yönetim konsolundaki her oturum açma ve kapatma işleminde yeniden yazmak zorunda kalmadan aynı kimlik bilgilerini kullanabilir.

-   **Son kullanıcılar**, Skycure uygulamalarındaki her oturum açma ve kapatma işleminde yeniden yazmak zorunda kalmadan aynı Azure AD kimlik bilgilerini kullanabilir.

Aşağıda, Skycure’u Azure Active Directory Çoklu Oturum Açma (SSO) ile tümleştirme adımları verilmiştir.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Azure Active Directory Kiracı Kimliğini almak için

Azure AD Kiracı Kimliğini almanız gerekir.

1.  [Azure portalına](https://portal.azure.com/) gidin ve kimlik bilgilerinizle oturum açın.

2.  **Pano**’yu görebilirsiniz, **Azure Active Directory**’yi seçin.

    ![Azure AD Panosu](./media/skycure-sso-1.png)

3.  **Azure Active Directory** dikey penceresi açılır, **Özellikler**’i seçin.

    ![Azure AD Özellikler dikey penceresi](./media/skycure-sso-2.png)

4.  **Azure Active Directory Özellikler** dikey penceresindeki **Kiracı Dizin Kimliği**’nin altında **Kopyala simgesine** tıklayın.

5. Kopyalanan Dizin Kimliği değerini daha sonra kullanmak üzere bir metin dosyasına yapıştırın. Dizin Kimliği değeri, daha sonra Skycure ile Intune’u tümleştirme işleminde gerekecektir.

    ![Azure AD Panosu](./media/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Skycure’un Azure Active Directory ile iletişim kurmasını sağlama

1.  Aşağıdaki URL’yi tarayıcınıza girin. **DIRECTORY_ID** değeri yerine, daha önce metin dosyasına kopyalamış olduğunuz Azure Active Directory Kiracı Kimliğinizi girin.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Azure Active Directory kimlik bilgilerinizi kullanarak oturum açmalısınız. Devam etmek için **Kabul Et**’e tıklayın.

![Azure AD oturum açma sayfası](./media/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Skycure için Azure AD Güvenlik grubu oluşturma (isteğe bağlı)

Skycure çalıştıran kullanıcıları içeren özel bir kullanıcı grubu oluşturmak isteyebilirsiniz (örneğin, Skycure kullanıcıları). Raporlar aracılığıyla Skycure etkinliğini çözümlerken bu yararlı olabilir.

-   [Azure AD’de grup oluşturma ve üyeleri ekleme](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) hakkında daha fazla bilgi edinin.

> [!NOTE] 
> Ayrıca, var olan bir Azure AD güvenlik grubunu da kullanabilirsiniz.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Intune’u Skycure ile tümleştirmek için Azure AD hesabını yapılandırma

1.  [Skycure Yönetim Konsolu](https://aad.skycure.com/)’nda, daha önce metin dosyasına kaydedilmiş olan Azure Active Directory Kiracı Kimliğini girin.

![Skycure Yönetim konsolu Azure AD Kiracı Kimliği alanı](./media/skycure-sso-5.png)

> [!IMPORTANT] 
> Skycure, Azure AD’yi sorgulayarak Azure AD Kiracı Kimliğinin mevcut olduğunu doğrular; Skycure kimliği bulduğunda, yönetici sonraki adıma (Temel kurulum adımı) devam edebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Skycure iOS uygulaması yapılandırma ilkesini indirme](skycure-ios-app-configuration-policy-download.md)