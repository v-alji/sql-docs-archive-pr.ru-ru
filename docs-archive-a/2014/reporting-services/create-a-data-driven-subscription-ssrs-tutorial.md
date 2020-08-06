---
title: Создание управляемой данными подписки (учебник по службам SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], tutorials
- walkthroughs [Reporting Services]
- data-driven subscriptions
ms.assetid: 79ab0572-43e9-4dc4-9b5a-cd8b627b8274
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53be7cf793d8fa38d177643c7f366115d4df8b7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735106"
---
# <a name="create-a-data-driven-subscription-ssrs-tutorial"></a><span data-ttu-id="a1cbb-102">Создание управляемой данными подписки (учебник по службам SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1cbb-102">Create a Data-Driven Subscription (SSRS Tutorial)</span></span>
  <span data-ttu-id="a1cbb-103">Службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] предоставляют управляемые данными подписки, позволяющие настроить распространение отчета на основе динамических данных подписчиков.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides data-driven subscriptions so that you can customize the distribution of a report based on dynamic subscriber data.</span></span> <span data-ttu-id="a1cbb-104">Управляемые данными подписки предназначены для следующих типов сценариев:</span><span class="sxs-lookup"><span data-stu-id="a1cbb-104">Data-driven subscriptions are intended for the following kinds of scenarios:</span></span>  
  
-   <span data-ttu-id="a1cbb-105">Распространение отчетов среди большого числа получателей, чье членство может меняться от одного цикла распространения к следующему.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-105">Distributing reports to a large recipient pool whose membership may change from one distribution to the next.</span></span> <span data-ttu-id="a1cbb-106">Например, распространение ежемесячного отчета по всем текущим заказчикам.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-106">For example, distribute a monthly report to all current customers.</span></span>  
  
-   <span data-ttu-id="a1cbb-107">Распространение отчета среди определенной группы получателей на основании предопределенного критерия.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-107">Distributing reports to a specific group of recipients based on predefined criteria.</span></span> <span data-ttu-id="a1cbb-108">Например, отправка отчета об эффективности продаж десяти менеджерам верхнего уровня в организации.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-108">For example, send a sales performance report to the top ten sales managers in an organization.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="a1cbb-109">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="a1cbb-109">What You Will Learn</span></span>  
 <span data-ttu-id="a1cbb-110">В этом учебнике содержится описание методики использования управляемых данными подписок на основе несложного примера, иллюстрирующего основные понятия.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-110">This tutorial shows you how to use data-driven subscriptions using a simple example to illustrate the concepts.</span></span>  
  
 <span data-ttu-id="a1cbb-111">Учебник разделен на три занятия.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-111">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="a1cbb-112">Урок 1. Создание образца базы данных подписчика</span><span class="sxs-lookup"><span data-stu-id="a1cbb-112">Lesson 1: Creating a Sample Subscriber Database</span></span>](lesson-1-creating-a-sample-subscriber-database.md)  
 <span data-ttu-id="a1cbb-113">На этом занятии рассматривается создание локальной базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], в которой содержатся сведения о подписчике.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-113">In this lesson you will learn how to create a local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database that contains subscriber information.</span></span>  
  
 [<span data-ttu-id="a1cbb-114">Урок 2. Изменение свойств источника данных отчета</span><span class="sxs-lookup"><span data-stu-id="a1cbb-114">Lesson 2: Modifying the Report Data Source Properties</span></span>](lesson-2-modifying-the-report-data-source-properties.md)  
 <span data-ttu-id="a1cbb-115">На этом занятии изучается изменение свойств источника данных отчета для обеспечения автоматического выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-115">In this lesson, you will learn how to modify report data source properties so that the report can run unattended.</span></span> <span data-ttu-id="a1cbb-116">Для обеспечения автоматического выполнения необходимы сохраненные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-116">Unattended processing requires stored credentials.</span></span> <span data-ttu-id="a1cbb-117">Вы также измените набор данных отчета, включив в него параметр, значение которого берется из данных подписчика.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-117">You will also modify the report dataset to include a parameter that is supplied by the subscriber data.</span></span>  
  
 [<span data-ttu-id="a1cbb-118">Урок 3. Определение управляемой данными подписки</span><span class="sxs-lookup"><span data-stu-id="a1cbb-118">Lesson 3: Defining a Data-Driven Subscription</span></span>](lesson-3-defining-a-data-driven-subscription.md)  
 <span data-ttu-id="a1cbb-119">На этом занятии рассматриваются способы определения управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-119">In this lesson you will learn how to define a data-driven subscription.</span></span> <span data-ttu-id="a1cbb-120">На этом занятии будет подробно разобрана каждая страница в мастере управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-120">This lesson guides you through each page in the Data-Driven Subscription Wizard.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1cbb-121">Требования</span><span class="sxs-lookup"><span data-stu-id="a1cbb-121">Requirements</span></span>  
 <span data-ttu-id="a1cbb-122">Управляемые данными подписки обычно создаются и поддерживаются администраторами сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-122">Data-driven subscriptions are typically created and maintained by report server administrators.</span></span> <span data-ttu-id="a1cbb-123">Для создания управляемых данными подписок требуется опыт в построении запросов, знание источников данных, которые содержат данные подписчиков, а также повышенные разрешения на доступ к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-123">The ability to create data-driven subscriptions requires expertise in building queries, knowledge of data sources that contain subscriber data, and elevated permissions on a report server.</span></span>  
  
 <span data-ttu-id="a1cbb-124">В учебнике будет использоваться отчет, созданный в учебнике [Создание простого табличного отчета &#40;служб SSRS&#41;](create-a-basic-table-report-ssrs-tutorial.md) и данные из[!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1cbb-124">The tutorial will use the report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](create-a-basic-table-report-ssrs-tutorial.md) and data from [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]</span></span>  
  
 <span data-ttu-id="a1cbb-125">Для работы с этим учебником в системе должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="a1cbb-125">Your system must have the following installed to use this tutorial:</span></span>  
  
-   <span data-ttu-id="a1cbb-126">Выпуск [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , поддерживающий управляемые данными подписки.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-126">An edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that supports data-driven subscriptions.</span></span> <span data-ttu-id="a1cbb-127">Дополнительные сведения см. в разделе [выпуски и компоненты SQL Server 2014](../sql-server/editions-and-components-of-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="a1cbb-127">For more information, see [Editions and Components of SQL Server 2014](../sql-server/editions-and-components-of-sql-server-2016.md).</span></span>  
  
-   <span data-ttu-id="a1cbb-128">Сервер отчетов должен работать в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-128">The report server must be running in native mode.</span></span> <span data-ttu-id="a1cbb-129">Пользовательский интерфейс, описанный в этом учебнике, основан на сервере отчетов, работающем в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-129">The user interface described in this tutorial is based on a native mode report server.</span></span> <span data-ttu-id="a1cbb-130">Подписки поддерживаются сервером отчетов, работающим в режиме интеграции с SharePoint, но в этом случае пользовательский интерфейс будет отличаться от описанного в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-130">Subscriptions are supported on SharePoint mode report servers but the user interface will be different than what is described in this tutorial.</span></span>  
  
-   <span data-ttu-id="a1cbb-131">Должна быть запущена служба агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-131">SQL Server Agent service must be running.</span></span>  
  
-   <span data-ttu-id="a1cbb-132">Отчет, который включает параметры.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-132">A report that includes parameters.</span></span> <span data-ttu-id="a1cbb-133">В этом учебнике используется образец отчета `Sales Orders` , созданный при работе с учебником [Создание простого табличного отчета (учебник по службам SSRS)](create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a1cbb-133">This tutorial assumes the sample report, `Sales Orders` you create using the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](create-a-basic-table-report-ssrs-tutorial.md).</span></span>  
  
-   <span data-ttu-id="a1cbb-134">Образец базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)], который предоставляет данные для образца отчета.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-134">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database, which provides data to the sample report.</span></span>  
  
-   <span data-ttu-id="a1cbb-135">Назначение ролей, которое включает задачу «Управление всеми подписками» для образца отчета.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-135">A role assignment that includes the Manage all subscriptions task on the sample report.</span></span> <span data-ttu-id="a1cbb-136">Эта задача обязательна для определения управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-136">This task is required for defining a data-driven subscription.</span></span> <span data-ttu-id="a1cbb-137">Если пользователь является администратором компьютера, назначение ролей по умолчанию для локальных администраторов предоставляет разрешения, необходимые для создания управляемых данными подписок.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-137">If you are an administrator on the computer, the default role assignment for local administrators provides the permissions necessary for creating data-driven subscriptions.</span></span> <span data-ttu-id="a1cbb-138">Дополнительные сведения см. в статье [Предоставление разрешений на сервер отчетов в собственном режиме](security/granting-permissions-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="a1cbb-138">For more information, see [Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md).</span></span>  
  
-   <span data-ttu-id="a1cbb-139">Общая папка, на которую имеется разрешение на запись.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-139">A shared folder for which you have write permissions.</span></span> <span data-ttu-id="a1cbb-140">Общая папка должна быть доступна через сетевое подключение.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-140">The shared folder must be accessible over a network connection.</span></span>  
  
 <span data-ttu-id="a1cbb-141">**Предполагаемое время для выполнения заданий учебника:** 30 минут.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-141">**Estimated time to complete the tutorial:** 30 minutes.</span></span> <span data-ttu-id="a1cbb-142">И еще 30 минут, если вы еще не прошли учебник по созданию простого отчета.</span><span class="sxs-lookup"><span data-stu-id="a1cbb-142">An additional 30 minutes if you have not completed the basic report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1cbb-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1cbb-143">See Also</span></span>  
 <span data-ttu-id="a1cbb-144">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="a1cbb-144">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="a1cbb-145">Создание простого табличного отчета (учебник по службам SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1cbb-145">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
