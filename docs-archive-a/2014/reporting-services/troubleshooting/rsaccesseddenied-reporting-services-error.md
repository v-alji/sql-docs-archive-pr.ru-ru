---
title: rsAccessedDenied — ошибка служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsAccessDenied error
ms.assetid: 2f76b1bf-96a2-4755-b76b-84e933220efc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 194006c2ef6f22b9bc27e9e8cbe1eebd027ed6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664677"
---
# <a name="rsaccesseddenied---reporting-services-error"></a><span data-ttu-id="2d612-102">rsAccessedDenied - Ошибка службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2d612-102">rsAccessedDenied - Reporting Services Error</span></span>
  <span data-ttu-id="2d612-103">Ошибка службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]**rsAccessedDenied** происходит, когда у пользователя нет разрешения на выполнение действия.</span><span class="sxs-lookup"><span data-stu-id="2d612-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] error **rsAccessedDenied** occurs when a user does not have permission to perform an action.</span></span> <span data-ttu-id="2d612-104">Например, у них нет назначения роли, которая позволяет им открывать отчет или они открыли свой браузер без необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="2d612-104">For, example, they do not have a role assignment that allows them to open a report or they did not open their browser with the required permissions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="2d612-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в собственном режиме | в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="2d612-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; SharePoint mode</span></span>|  
  
-   <span data-ttu-id="2d612-106">Если ошибка произошла во время доступа к серверу отчетов напрямую при помощи URL-адреса, то это исключение соответствует ошибке HTTP 401.</span><span class="sxs-lookup"><span data-stu-id="2d612-106">If the error occurred while accessing the report server directly through a URL, the exception is mapped to an HTTP 401 error.</span></span>  
  
-   <span data-ttu-id="2d612-107">Если ошибка произошла во время работы с диспетчером отчетов или другой программой, то ошибка появится на странице ошибок.</span><span class="sxs-lookup"><span data-stu-id="2d612-107">If the error occurred while using Report Manager or another tool, the error appears in an error page.</span></span>  
  
-   <span data-ttu-id="2d612-108">Если ошибка произошла во время запланированной операции, подписки или доставки, то сведения о ней появятся только в файле журнала сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2d612-108">If the error occurred during a scheduled operation, subscription, or delivery, the error will appear in the report server log file only.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2d612-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2d612-109">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d612-110">**Название продукта**</span><span class="sxs-lookup"><span data-stu-id="2d612-110">**Product Name**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="2d612-111">**Идентификатор события**</span><span class="sxs-lookup"><span data-stu-id="2d612-111">**Event ID**</span></span>|<span data-ttu-id="2d612-112">rsAccessedDenied</span><span class="sxs-lookup"><span data-stu-id="2d612-112">rsAccessedDenied</span></span>|  
|<span data-ttu-id="2d612-113">**Источник события**</span><span class="sxs-lookup"><span data-stu-id="2d612-113">**Event Source**</span></span>|<span data-ttu-id="2d612-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="2d612-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="2d612-115">**Компонент**</span><span class="sxs-lookup"><span data-stu-id="2d612-115">**Component**</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="2d612-116">**Текст сообщения**</span><span class="sxs-lookup"><span data-stu-id="2d612-116">**Message Text**</span></span>|<span data-ttu-id="2d612-117">Предоставленные пользователю 'mydomain\myAccount' разрешения недостаточны для выполнения данной операции.</span><span class="sxs-lookup"><span data-stu-id="2d612-117">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="2d612-118">(rsAccessDenied) (ReportingServicesLibrary)</span><span class="sxs-lookup"><span data-stu-id="2d612-118">(rsAccessDenied) (ReportingServicesLibrary)</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="2d612-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2d612-119">User Action</span></span>  
 <span data-ttu-id="2d612-120">Разрешения на доступ к содержимому и операциям сервера отчетов назначаются при помощи ролей.</span><span class="sxs-lookup"><span data-stu-id="2d612-120">Permission to access report server content and operations are granted through role assignments.</span></span> <span data-ttu-id="2d612-121">В новой установке только у локальных администраторов есть доступ к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="2d612-121">On a new installation, only local administrators have access to a report server.</span></span> <span data-ttu-id="2d612-122">Чтобы предоставить доступ другим пользователям, локальному администратору необходимо создать назначение ролей, описывающее учетную запись пользователя или группы домена, одну или несколько ролей, определяющих, какие задачи пользователь сможет выполнять, и область видимости (обычно корневую папку или корневой узел в иерархии папок сервера отчетов).</span><span class="sxs-lookup"><span data-stu-id="2d612-122">To grant access to other users, a local administrator must create a role assignment that specifies a domain user or group account, one or more roles that define the tasks the user can perform, and a scope (usually the Home folder or root node of the report server folder hierarchy).</span></span> <span data-ttu-id="2d612-123">Назначения ролей можно создать при помощи диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2d612-123">You can use Report Manager to create the role assignments.</span></span> <span data-ttu-id="2d612-124">Дополнительные сведения см. по ключевому слову «назначения ролей» в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d612-124">For more information, search for "Role Assignments" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="2d612-125">Данная ошибка вызывается также локальным администрирование сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2d612-125">This error is also caused by local administration of the report server.</span></span> <span data-ttu-id="2d612-126">Дополнительные сведения см. в разделе [Настройка сервера отчетов, работающего в основном режиме, для локального администрирования (службы SSRS)](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2d612-126">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d612-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d612-127">See Also</span></span>  
 <span data-ttu-id="2d612-128">[Назначения ролей](../security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="2d612-128">[Role Assignments](../security/role-assignments.md) </span></span>  
 <span data-ttu-id="2d612-129">[Предоставление разрешений на сервер отчетов в собственном режиме](../security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d612-129">[Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="2d612-130">Роли и разрешения (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="2d612-130">Roles and Permissions &#40;Reporting Services&#41;</span></span>](../security/roles-and-permissions-reporting-services.md)  
  
  
