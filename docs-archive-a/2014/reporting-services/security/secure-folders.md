---
title: Обеспечение защиты папок| Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- high-security folders [Reporting Services]
- low-security folders
- folders [Reporting Services], security
- security [Reporting Services], folders
ms.assetid: 0fd91f77-0143-476b-9af0-87293be78e44
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483b3108713032b3aaf566208f39f6c2f705da1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656975"
---
# <a name="secure-folders"></a><span data-ttu-id="fe50d-102">Обеспечение защиты папок</span><span class="sxs-lookup"><span data-stu-id="fe50d-102">Secure Folders</span></span>
  <span data-ttu-id="fe50d-103">Безопасность папок является основой защиты всего содержимого сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fe50d-103">Folder security is the foundation for securing all content in a report server.</span></span> <span data-ttu-id="fe50d-104">Поскольку безопасность является унаследованной в структуре папок, можно определить разрешения определенного доступа для больших или маленьких разделов иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="fe50d-104">Because security is inherited throughout the folder structure, you can designate large or small sections of the folder hierarchy to allow for certain kinds of access.</span></span>  
  
 <span data-ttu-id="fe50d-105">Папки с повышенной защитой могут использоваться для хранения конфиденциальных отчетов или промежуточных областей: например, можно иметь папку, используемую для тестирования отчетов перед их перемещением в конечное расположение.</span><span class="sxs-lookup"><span data-stu-id="fe50d-105">High-security folders can be used to store confidential reports or as staging areas; for example, you can have a folder that you use to test reports before moving them to a final location.</span></span> <span data-ttu-id="fe50d-106">Для управления доступом к этой области можно определить одно назначение роли, которое позволяет добавлять и удалять элементы только авторам отчета, и второе назначение роли, которое позволяет испытателям выполнять отчеты, но исключает добавление или удаление элементов.</span><span class="sxs-lookup"><span data-stu-id="fe50d-106">To control access to this area, you can define one role assignment that allows only report authors to add and delete items, and a second role assignment that allows testers to run reports but not to add or remove items.</span></span> <span data-ttu-id="fe50d-107">Поскольку назначения ролей явным образом определены для испытателей и авторов отчетов, другие пользователи (за исключением местных системных администраторов) не смогут получить доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="fe50d-107">Because the role assignments are defined explicitly for testers and report authors, no other users (except for local system administrators) can access the folder.</span></span>  
  
 <span data-ttu-id="fe50d-108">Папки с низким уровнем безопасности могут использоваться для хранения отчетов, доступ к которым должен быть облегчен.</span><span class="sxs-lookup"><span data-stu-id="fe50d-108">Low-security folders can be used to store reports that you want to be easily accessible.</span></span>  
  
 <span data-ttu-id="fe50d-109">Безопасность папки создает основу безопасности на уровне элементов, начиная с корневого узла иерархии папки сервера отчетов, домашней папки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-109">Folder security forms the basis of item-level security, starting with the root node of the report server folder hierarchy, the Home folder.</span></span> <span data-ttu-id="fe50d-110">Поскольку свойства безопасности наследуются, то желательно установить более строгие ограничения политики безопасности на корневой папке.</span><span class="sxs-lookup"><span data-stu-id="fe50d-110">Because security is inherited, it is advisable to set a fairly restrictive security policy on the Home folder.</span></span> <span data-ttu-id="fe50d-111">Использование роли **Браузер** в назначениях ролей корневой папки делает абсолютно то же, что и предоставление доступа только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="fe50d-111">Using the **Browser** role in Home folder role assignments does exactly that by providing view-only access.</span></span>  
  
## <a name="tasks-and-folder-access"></a><span data-ttu-id="fe50d-112">Задачи и доступ к папке</span><span class="sxs-lookup"><span data-stu-id="fe50d-112">Tasks and Folder Access</span></span>  
 <span data-ttu-id="fe50d-113">Создавая назначения ролей для папок, следует обратить внимание на задачи, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fe50d-113">When creating role assignments for folders, consider the tasks listed in the following table.</span></span>  
  
|<span data-ttu-id="fe50d-114">Выберите эту задачу</span><span class="sxs-lookup"><span data-stu-id="fe50d-114">Select this task</span></span>|<span data-ttu-id="fe50d-115">Предоставить разрешение на</span><span class="sxs-lookup"><span data-stu-id="fe50d-115">To give permission to</span></span>|  
|----------------------|---------------------------|  
|<span data-ttu-id="fe50d-116">Просмотр папок</span><span class="sxs-lookup"><span data-stu-id="fe50d-116">View folders</span></span>|<span data-ttu-id="fe50d-117">Просмотр иерархии папок и свойств только для чтения, которые указывают дату изменений и создания папки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-117">View the folder hierarchy and read-only properties that indicate when the folder was created and modified.</span></span><br /><br /> <span data-ttu-id="fe50d-118">Пользователи не могут просмотреть элементы в папке, если им не назначены роли, включающие следующие задачи: "Просмотр отчетов", "Просмотр моделей", "Просмотр ресурсов" и "Просмотр источников данных".</span><span class="sxs-lookup"><span data-stu-id="fe50d-118">Users cannot view items in the folder unless they are assigned to roles that also include the following tasks: "View reports," "View models", "View resources," and "View data sources."</span></span>|  
|<span data-ttu-id="fe50d-119">Управление папками</span><span class="sxs-lookup"><span data-stu-id="fe50d-119">Manage folders</span></span>|<span data-ttu-id="fe50d-120">Просмотр свойств папки, изменение имени или описания или перемещение папки в другое расположение.</span><span class="sxs-lookup"><span data-stu-id="fe50d-120">View folder properties, change the name or description, or move the folder to another location.</span></span> <span data-ttu-id="fe50d-121">Эта задача позволяет пользователям создавать папки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-121">This task allows users to create folders.</span></span>|  
|<span data-ttu-id="fe50d-122">Управление отчетами</span><span class="sxs-lookup"><span data-stu-id="fe50d-122">Manage reports</span></span>|<span data-ttu-id="fe50d-123">Добавление отчетов из файловой системы в папку и публикация отчетов из конструктора отчетов на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="fe50d-123">Add reports from the file system to a folder and publish reports from Report Designer to the report server.</span></span>|  
|<span data-ttu-id="fe50d-124">Управление источниками данных</span><span class="sxs-lookup"><span data-stu-id="fe50d-124">Manage data sources</span></span>|<span data-ttu-id="fe50d-125">Добавление новых общих элементов источника данных в папку и последующее изменение существующих общих источников данных.</span><span class="sxs-lookup"><span data-stu-id="fe50d-125">Add new shared data source items to a folder and change existing shared data sources.</span></span>|  
|<span data-ttu-id="fe50d-126">Установка безопасности элементов</span><span class="sxs-lookup"><span data-stu-id="fe50d-126">Set security on items</span></span>|<span data-ttu-id="fe50d-127">Создание и изменение назначений ролей, управляющих доступом к папке.</span><span class="sxs-lookup"><span data-stu-id="fe50d-127">Create and modify role assignments that control access to the folder.</span></span> <span data-ttu-id="fe50d-128">Эта задача должна использоваться либо с задачей «Просмотр папок», либо с «Управление папок».</span><span class="sxs-lookup"><span data-stu-id="fe50d-128">This task must be used with either "View folders" or "Manage folders."</span></span> <span data-ttu-id="fe50d-129">Если задача не будет использовать ни просмотр, ни управление, то задача не сможет производить изменения, поскольку пользователь не сможет выбирать элементы.</span><span class="sxs-lookup"><span data-stu-id="fe50d-129">If it is not, it will have no effect because the user will not be able to select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe50d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe50d-130">See Also</span></span>  
 <span data-ttu-id="fe50d-131">[Защищенные отчеты и ресурсы](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="fe50d-131">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="fe50d-132">[Защита совместно используемых элементов источника данных](secure-shared-data-source-items.md) </span><span class="sxs-lookup"><span data-stu-id="fe50d-132">[Secure Shared Data Source Items](secure-shared-data-source-items.md) </span></span>  
 [<span data-ttu-id="fe50d-133">Предоставление разрешений на сервер отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="fe50d-133">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
