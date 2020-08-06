---
title: Защита и обеспечение безопасности служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0f8c7a4186c5236260fb27d8de107ce8c97bd363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668082"
---
# <a name="reporting-services-security-and-protection"></a><span data-ttu-id="352de-102">Защита и обеспечение безопасности служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="352de-102">Reporting Services Security and Protection</span></span>
  <span data-ttu-id="352de-103">Этот раздел содержит сведения о средствах безопасности служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="352de-103">You can use information in this section to learn about the security features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="352de-104">В разделе также объясняются модели авторизации и поставщики проверки подлинности, поддерживаемые в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="352de-104">This section also explains the authorization models and authentication providers supported in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="extended-protection-for-authentication"></a><span data-ttu-id="352de-105">Расширенная защита для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="352de-105">Extended Protection for Authentication</span></span>  
 <span data-ttu-id="352de-106">Начиная с [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], доступна поддержка расширенной защиты для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="352de-106">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], support for Extended Protection for Authentication is available.</span></span> <span data-ttu-id="352de-107">Функция [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует привязку каналов и служб для повышения уровня защиты проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="352de-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature supports the use of channel binding and service binding to enhance protection of authentication.</span></span> <span data-ttu-id="352de-108">Функции [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно использовать в ОС, поддерживающей расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="352de-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features need to be used with an operating system that supports Extended Protection.</span></span> <span data-ttu-id="352de-109">Дополнительные сведения см. в статье [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="352de-109">For more information, see [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span></span>  
  
## <a name="authentication-and-authorization"></a><span data-ttu-id="352de-110">Аутентификация и авторизация</span><span class="sxs-lookup"><span data-stu-id="352de-110">Authentication and Authorization</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="352de-111">предусматривают несколько типов проверки подлинности клиентов и клиентских приложений для доступа к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="352de-111">provides different authentication types for users and client applications to authenticate with the report server.</span></span> <span data-ttu-id="352de-112">Использование правильного типа проверки подлинности для сервера отчетов обеспечивает уровень безопасности, необходимый для организации.</span><span class="sxs-lookup"><span data-stu-id="352de-112">Using the right authentication type for your report server enables your organization to achieve the appropriate level of security required by your organization.</span></span> <span data-ttu-id="352de-113">Дополнительные сведения см. в статье [Authentication with the Report Server](authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="352de-113">For more information, see [Authentication with the Report Server](authentication-with-the-report-server.md).</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="352de-114">также использует роли и разрешения для контроля доступа пользователей к содержимому каталога сервера отчетов (иными словами, кто к чему имеет доступ и как этот доступ осуществляется).</span><span class="sxs-lookup"><span data-stu-id="352de-114">also employs roles and permissions to control user access to content in the report server catalog (in other words, who can access what, and how s/he can access it).</span></span> <span data-ttu-id="352de-115">Дополнительные сведения см. в статье [Роли и разрешения (службы Reporting Services)](roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="352de-115">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="352de-116">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="352de-116">Related Tasks</span></span>  
  
|<span data-ttu-id="352de-117">Описания задач</span><span class="sxs-lookup"><span data-stu-id="352de-117">Task Descriptions</span></span>|<span data-ttu-id="352de-118">Ссылки</span><span class="sxs-lookup"><span data-stu-id="352de-118">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="352de-119">Настройка протокола Socket Layer (SSL) для защиты клиентских подключений к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="352de-119">Configure the Secure Socket Layer (SSL) to secure client connections to the report server.</span></span>|[<span data-ttu-id="352de-120">Настройка соединений SSL для сервера отчетов, работающего в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="352de-120">Configure SSL Connections on a Native Mode Report Server</span></span>](configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
