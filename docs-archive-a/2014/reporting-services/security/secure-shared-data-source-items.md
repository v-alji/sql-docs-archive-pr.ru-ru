---
title: Защита элементов общего источника данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
- security [Reporting Services], data sources
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4177834a90e2852f4079e3b2bf5a1dd85b9cd51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664691"
---
# <a name="secure-shared-data-source-items"></a><span data-ttu-id="d7b30-102">Защита совместно используемых элементов источника данных</span><span class="sxs-lookup"><span data-stu-id="d7b30-102">Secure Shared Data Source Items</span></span>
  <span data-ttu-id="d7b30-103">Можно задать параметры безопасности для общего элемента источника данных, чтобы разрешить или запретить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="d7b30-103">You can set security on a shared data source item to enable or disable access to it.</span></span>  
  
 <span data-ttu-id="d7b30-104">Пользователь с минимальным доступом к общему источнику данных (например, такой доступ предоставляется ролью **Браузер** ) может просматривать список отчетов, использующих данный элемент, при условии, что ему также разрешено просматривать сами отчеты.</span><span class="sxs-lookup"><span data-stu-id="d7b30-104">A user who has minimal access to a shared data source (for example, the access granted through the **Browser** role) can view the list of reports that use the item, provided the user is also authorized to view the reports themselves.</span></span>  
  
 <span data-ttu-id="d7b30-105">Пользователь с более широким набором прав доступа (например, предоставляемым ролью **Диспетчер содержимого** ) может просматривать и задавать свойства для общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="d7b30-105">A user who has additional access (such as that granted through the **Content Manager** role) can view and set properties for the shared data source.</span></span>  
  
 <span data-ttu-id="d7b30-106">Для настройки безопасности нужно создать назначение роли, указывающей, какой пользователь или группа имеет доступ к данному общему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="d7b30-106">To set security, you create a role assignment that specifies which user or group account has access to the shared data source.</span></span> <span data-ttu-id="d7b30-107">Пользователи, которым разрешен доступ к общему элементу источника данных, могут изменять его имя, описание, строку соединения и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d7b30-107">Users who have access to a shared data source item can change its name, description, connection string, or credential information.</span></span>  
  
## <a name="tasks-and-access-to-items"></a><span data-ttu-id="d7b30-108">Задачи и доступ к элементам</span><span class="sxs-lookup"><span data-stu-id="d7b30-108">Tasks and Access to Items</span></span>  
 <span data-ttu-id="d7b30-109">При создании назначений ролей используйте роль, у которой есть такие задачи для назначения необходимых разрешений пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="d7b30-109">When creating role assignments, use a role that has these tasks to assign appropriate permissions to users and groups.</span></span>  
  
|<span data-ttu-id="d7b30-110">Выберите эту задачу</span><span class="sxs-lookup"><span data-stu-id="d7b30-110">Select this task</span></span>|<span data-ttu-id="d7b30-111">Предоставить пользователям следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d7b30-111">To give users permission to</span></span>|  
|----------------------|---------------------------------|  
|<span data-ttu-id="d7b30-112">Просмотр источников данных</span><span class="sxs-lookup"><span data-stu-id="d7b30-112">View data sources</span></span>|<span data-ttu-id="d7b30-113">Просмотр общего элемента источника данных в иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="d7b30-113">View the shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="d7b30-114">Без этой задачи элемент будет невидим для пользователей, и они не будут знать, что этот источник данных доступен.</span><span class="sxs-lookup"><span data-stu-id="d7b30-114">Without this task, the item is not visible to users and they may not be aware that the data source is available.</span></span>|  
|<span data-ttu-id="d7b30-115">Управление источниками данных</span><span class="sxs-lookup"><span data-stu-id="d7b30-115">Manage data sources</span></span>|<span data-ttu-id="d7b30-116">Просмотр свойств, задающих имя, описание и сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="d7b30-116">View properties that specify the name, description, and connection information.</span></span> <span data-ttu-id="d7b30-117">Эта задача используется также для отображения общего элемента источника данных в иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="d7b30-117">This task is also used to display a shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="d7b30-118">Если эта задача выбрана, можно опустить задачу «Просмотр источников данных».</span><span class="sxs-lookup"><span data-stu-id="d7b30-118">If you choose this task, you can omit the "View data sources" task.</span></span>|  
|<span data-ttu-id="d7b30-119">Установка безопасности элементов</span><span class="sxs-lookup"><span data-stu-id="d7b30-119">Set security on items</span></span>|<span data-ttu-id="d7b30-120">Создание и изменение назначений ролей, управляющих доступом к общему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="d7b30-120">Create and modify role assignments that control access to the shared data source.</span></span> <span data-ttu-id="d7b30-121">Эта задача должна использоваться совместно с задачей «Просмотр источников данных» или «Управление источниками данных».</span><span class="sxs-lookup"><span data-stu-id="d7b30-121">This task must be used with either "View data source" or "Manage data sources" tasks.</span></span> <span data-ttu-id="d7b30-122">В противном случае она не будет действовать, поскольку пользователь не сможет выбрать источник.</span><span class="sxs-lookup"><span data-stu-id="d7b30-122">If it is not, it has no effect because the user cannot select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7b30-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7b30-123">See Also</span></span>  
 <span data-ttu-id="d7b30-124">[Управление источниками данных отчета](../report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="d7b30-124">[Manage Report Data Sources](../report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="d7b30-125">[Защита папок](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="d7b30-125">[Secure Folders](secure-folders.md) </span></span>  
 <span data-ttu-id="d7b30-126">[Защищенные отчеты и ресурсы](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="d7b30-126">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="d7b30-127">[Предоставление разрешений на сервер отчетов в собственном режиме](granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7b30-127">[Granting Permissions on a Native Mode Report Server](granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="d7b30-128">Сохраненные учетные данные в источнике данных Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d7b30-128">Store Credentials in a Reporting Services Data Source</span></span>](../report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  
