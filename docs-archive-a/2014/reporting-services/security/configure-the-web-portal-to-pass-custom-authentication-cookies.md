---
title: Настройка диспетчер отчетов для передачи файлов cookie пользовательской проверки подлинности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: 91aeb053-149e-4562-ae4c-a688d0e1b2ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 90e8798fb91152ec64e7f290dc1522fc8eaa451c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656976"
---
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a><span data-ttu-id="f5961-102">Настройка передачи куки-файлов для нестандартной проверки подлинности пользователя в диспетчере отчетов</span><span class="sxs-lookup"><span data-stu-id="f5961-102">Configure Report Manager to Pass Custom Authentication Cookies</span></span>
  <span data-ttu-id="f5961-103">При использовании пользовательского модуля проверки подлинности необходимо настроить диспетчер отчетов для передачи куки-файлов для проверки подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5961-103">If you are using a custom authentication extension, you should configure Report Manager to transmit custom authentication cookies.</span></span> <span data-ttu-id="f5961-104">Иначе диспетчер отчетов будет передавать куки-файлы только через HTTP-запрос для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="f5961-104">Otherwise, Report Manager will only transmit cookies through HTTP requests specific to the report server.</span></span> <span data-ttu-id="f5961-105">Чтобы передать дополнительные куки-файлы, необходимо изменить файл RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="f5961-105">If you want to transmit additional cookies, you must modify the RSReportServer.Config file.</span></span>  
  
## <a name="modifying-the-rsreportserverconfig-file"></a><span data-ttu-id="f5961-106">Изменение файла RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="f5961-106">Modifying the RSReportServer.Config File</span></span>  
 <span data-ttu-id="f5961-107">Можно включить диспетчер отчетов для передачи дополнительных файлов cookie на сервер отчетов, добавив <`PassThroughCookies` элемент> в параметры конфигурации диспетчер отчетов в файле RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="f5961-107">You can enable Report Manager to transmit additional cookies through to the report server by adding a <`PassThroughCookies`> element to the Report Manager configuration settings in the RSReportServer.config file.</span></span> <span data-ttu-id="f5961-108">Использование дополнительных куки-файлов удобно в решениях однократной проверки подлинности при входе, когда требуются не только куки-файлы проверки подлинности сервера отчетов, но также куки-файлы от сторонних систем проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5961-108">Transmitting additional cookies is helpful in a single sign-on authentication solution that requires not only the report server authentication cookies, but also cookies from a third-party authentication system.</span></span>  
  
 <span data-ttu-id="f5961-109">Чтобы включить передачу дополнительных куки-файлов через HTTP-запрос при использовании диспетчера отчетов, установите следующие элементы в файле RSReportServer.config:</span><span class="sxs-lookup"><span data-stu-id="f5961-109">To enable additional cookies to be transmitted through HTTP requests when using Report Manager, set the following elements in the RSReportServer.config file:</span></span>  
  
```  
<UI>  
   <CustomAuthenticationUI>  
      ...  
      <PassThroughCookies>  
         <PassThroughCookie>cookiename1</PassThroughCookie>  
         <PassThroughCookie>cookiename2</PassThroughCookie>  
      </PassThroughCookies>  
   </CustomAuthenticationUI>  
      ...  
</UI>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5961-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5961-110">See Also</span></span>  
 <span data-ttu-id="f5961-111">[Проверка подлинности с использованием сервера отчетов](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5961-111">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="f5961-112">[Файл конфигурации RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="f5961-112">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="f5961-113">[Общие сведения о модулях безопасности](../extensions/security-extension/security-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f5961-113">[Security Extensions Overview](../extensions/security-extension/security-extensions-overview.md) </span></span>  
 [<span data-ttu-id="f5961-114">Настройка и администрирование сервера отчетов (службы Reporting Services в собственном режиме)</span><span class="sxs-lookup"><span data-stu-id="f5961-114">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
