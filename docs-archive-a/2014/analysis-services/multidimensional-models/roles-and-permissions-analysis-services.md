---
title: Роли и разрешения (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], about security
- security [Analysis Services - multidimensional data], about security
ms.assetid: bb885447-868b-4686-853c-8241f63d4370
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6595d931b2c2760e5fd3013ff6bec88f85106d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752440"
---
# <a name="roles-and-permissions-analysis-services"></a><span data-ttu-id="694a6-102">Роли и разрешения (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-102">Roles and Permissions (Analysis Services)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="694a6-103">включает ролевую модель авторизации, которая предоставляет доступ к операциям, объектам и данным.</span><span class="sxs-lookup"><span data-stu-id="694a6-103">provides a role-based authorization model that grants access to operations, objects, and data.</span></span> <span data-ttu-id="694a6-104">Все пользователи получают доступ к экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или базе данных в контексте некоторой роли.</span><span class="sxs-lookup"><span data-stu-id="694a6-104">All users who access an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance or database must do so within the context of a role.</span></span>  
  
 <span data-ttu-id="694a6-105">В качестве системного администратора службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , вы отвечаете за предоставление членства **роли администратора сервера** , которая передает неограниченный доступ к операциям на сервере.</span><span class="sxs-lookup"><span data-stu-id="694a6-105">As an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] system administrator, you are in charge of granting membership to the **server administrator role** that conveys unrestricted access to operations on the server.</span></span> <span data-ttu-id="694a6-106">Эта роль имеет фиксированные разрешения, и ее нельзя настраивать.</span><span class="sxs-lookup"><span data-stu-id="694a6-106">This role has fixed permissions and cannot be customized.</span></span> <span data-ttu-id="694a6-107">По умолчанию члены локальной группы администраторов автоматически являются системными администраторами служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="694a6-107">By default, members of the local Administrators group are automatically Analysis Services system administrators.</span></span>  
  
 <span data-ttu-id="694a6-108">Пользователи без прав администратора, которые запрашивают или обрабатывают данные, получают доступ через **роли базы данных**.</span><span class="sxs-lookup"><span data-stu-id="694a6-108">Non-administrative users who query or process data are granted access through **database roles**.</span></span> <span data-ttu-id="694a6-109">И системные администраторы и администраторы баз данных могут создавать роли, которые описывают разные уровни доступа в рамках заданной базы данных, а затем назначают членство каждому пользователю, которому необходим доступ.</span><span class="sxs-lookup"><span data-stu-id="694a6-109">Both system administrators and database administrators can create the roles that describe different levels of access within a given database, and then assign membership to every user who requires access.</span></span> <span data-ttu-id="694a6-110">Каждая роль обладает настраиваемым набором разрешений для доступа к объектам и операциям в рамках отдельной базы данных.</span><span class="sxs-lookup"><span data-stu-id="694a6-110">Each role has a customized set of permissions for accessing objects and operations within a particular database.</span></span> <span data-ttu-id="694a6-111">Разрешения назначаются на уровне базы данных, на уровне внутренних объектов (кубов и измерений, но не перспектив) и на уровне строк.</span><span class="sxs-lookup"><span data-stu-id="694a6-111">You can assign permissions at these levels: database, interior objects such as cubes and dimensions (but not perspectives), and rows.</span></span>  
  
 <span data-ttu-id="694a6-112">Распространенной практикой является разделение операций по созданию ролей и назначению членства.</span><span class="sxs-lookup"><span data-stu-id="694a6-112">It is common practice to create roles and assign membership as separate operations.</span></span> <span data-ttu-id="694a6-113">Часто разработчик моделей добавляет роли на этапе проектирования.</span><span class="sxs-lookup"><span data-stu-id="694a6-113">Often, the model designer adds roles during the design phase.</span></span> <span data-ttu-id="694a6-114">Таким образом, все определения ролей отражаются в файлах проекта, определяющих модели.</span><span class="sxs-lookup"><span data-stu-id="694a6-114">This way, all role definitions are reflected in the project files that define the model.</span></span> <span data-ttu-id="694a6-115">Членство в ролях обычно определяется позднее, когда база данных переносится в рабочую среду. Обычно членство назначают администраторы базы данных, которые создают скрипты для разработки, тестирования и выполнения в качестве независимой операции.</span><span class="sxs-lookup"><span data-stu-id="694a6-115">Role membership is typically rolled out later as the database moves into production, usually by database administrators who create scripts that can be developed, tested, and run as an independent operation.</span></span>  
  
 <span data-ttu-id="694a6-116">Вся авторизация выполняется по допустимому удостоверению пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="694a6-116">All authorization is predicated on a valid Windows user identity.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="694a6-117">используют для проверки подлинности удостоверений пользователей исключительно проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="694a6-117">uses Windows authentication exclusively to authenticate user identities.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="694a6-118">не предоставляет собственный метод проверки подлинности. См. статью [методологии проверки подлинности, поддерживаемые Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="694a6-118">provides no proprietary authentication method.See [Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="694a6-119">Разрешения являются аддитивными для каждого пользователя или группы Windows, по всем ролям базы данных.</span><span class="sxs-lookup"><span data-stu-id="694a6-119">Permissions are additive for each Windows user or group, across all roles in the database.</span></span> <span data-ttu-id="694a6-120">Если одна роль запрещает пользователю или группе выполнять определенные задачи или просматривать определенные данные, а другая роль предоставляет такое разрешение указанному пользователю или группе, то этому пользователю или группе будет разрешено выполнять упомянутые задачи или просматривать упомянутые данные.</span><span class="sxs-lookup"><span data-stu-id="694a6-120">If one role denies a user or group permission to perform certain tasks or view certain data, but another role grants this permission to that user or group, the user or group will have permission to perform the task or view the data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="694a6-121">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="694a6-121">In this section</span></span>  
  
-   [<span data-ttu-id="694a6-122">Предоставление доступа к объектам и операциям (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-122">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-123">Предоставление разрешений базы данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-123">Grant database permissions &#40;Analysis Services&#41;</span></span>](grant-database-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-124">Предоставление разрешений кубу или модели (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-124">Grant cube or model permissions &#40;Analysis Services&#41;</span></span>](grant-cube-or-model-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-125">Предоставление разрешений на обработку (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-125">Grant process permissions &#40;Analysis Services&#41;</span></span>](grant-process-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-126">Предоставление разрешений на чтение описания метаданным объекта (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-126">Grant read definition permissions on object metadata &#40;Analysis Services&#41;</span></span>](grant-read-definition-permissions-on-object-metadata-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-127">Предоставление разрешений объекту источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-127">Grant permissions on a data source object &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-data-source-object-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-128">Предоставление разрешений структурам интеллектуального анализа данных и моделям интеллектуального анализа данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-128">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](grant-permissions-on-data-mining-structures-and-models-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-129">Предоставление разрешений измерению (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-129">Grant permissions on a dimension &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-dimension-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-130">Предоставление настраиваемого доступа к данным измерений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-130">Grant custom access to dimension data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-dimension-data-analysis-services.md)  
  
-   [<span data-ttu-id="694a6-131">Предоставление настраиваемого доступа к данным ячейки (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="694a6-131">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="694a6-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="694a6-132">See Also</span></span>  
 [<span data-ttu-id="694a6-133">Создание ролей и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="694a6-133">Create and Manage Roles &#40;SSAS Tabular&#41;</span></span>](../tabular-models/roles-ssas-tabular.md)  
  
  
