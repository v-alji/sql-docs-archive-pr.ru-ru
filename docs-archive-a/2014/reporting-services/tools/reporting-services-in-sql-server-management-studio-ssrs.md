---
title: Службы Reporting Services в среде SQL Server Management Studio (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], how-to topics
ms.assetid: 60685458-9108-47bf-820a-5e7db454d408
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f4083d8b288c8816925723f4cfaef4342dd0298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736005"
---
# <a name="reporting-services-in-sql-server-management-studio-ssrs"></a><span data-ttu-id="cf110-102">Службы Reporting Services в среде SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="cf110-102">Reporting Services in SQL Server Management Studio (SSRS)</span></span>
  <span data-ttu-id="cf110-103">Администраторы сервера отчетов могут использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , чтобы сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="cf110-103">Report server administrators can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to:</span></span>  
  
-   <span data-ttu-id="cf110-104">Включить функции, задать параметры сервера по умолчанию и управлять выполнением заданий.</span><span class="sxs-lookup"><span data-stu-id="cf110-104">Enable features, set server defaults, and manage running jobs.</span></span>  
  
-   <span data-ttu-id="cf110-105">Просматривать и создавать пользовательские отчеты.</span><span class="sxs-lookup"><span data-stu-id="cf110-105">View and create custom reports.</span></span> <span data-ttu-id="cf110-106">В обозревателе объектов многие узлы показывают стандартный набор отчетов, который устанавливается с [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf110-106">In Object Explorer, many nodes display a set of standard reports that are installed with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="cf110-107">Необходимо иметь разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="cf110-107">You must have administrator permissions.</span></span> <span data-ttu-id="cf110-108">Схема пользовательского отчета должна соответствовать схеме установленных отчетов.</span><span class="sxs-lookup"><span data-stu-id="cf110-108">The schema of a custom report must match the schema of the installed reports.</span></span> <span data-ttu-id="cf110-109">Дополнительные сведения см. в статьях [Пользовательские отчеты в среде Management Studio](../../ssms/object/custom-reports-in-management-studio.md) и [Определение версии схемы определения отчета (службы SSRS)](../reports/find-the-report-definition-schema-version-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cf110-109">For more information, see [Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) and [Find the Report Definition Schema Version &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span></span>  
  
 <span data-ttu-id="cf110-110">Авторы отчетов могут использовать [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , чтобы делать следующее:</span><span class="sxs-lookup"><span data-stu-id="cf110-110">Report authors can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="cf110-111">Просматривать пространственные данные из результатов запроса для отчета-карты.</span><span class="sxs-lookup"><span data-stu-id="cf110-111">Visualize spatial data from a query result set for a map report.</span></span> <span data-ttu-id="cf110-112">После выполнения запроса для просмотра результатов воспользуйтесь вкладкой **Пространственные результаты** на панели результатов.</span><span class="sxs-lookup"><span data-stu-id="cf110-112">After you run the query, use the **Spatial results** tab in the result set pane.</span></span> <span data-ttu-id="cf110-113">Дополнительные сведения см. в статье [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="cf110-113">For more information, see [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span></span>  
  
 <span data-ttu-id="cf110-114">В этом разделе приведены пошаговые инструкции по выполнению с помощью среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]различных задач, связанных с отчетами.</span><span class="sxs-lookup"><span data-stu-id="cf110-114">This section contains step-by-step instructions for performing various reporting tasks using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="cf110-115">Создание общих расписаний и управление ими также выполняется с помощью диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="cf110-115">Creating and managing shared schedules can also be performed using Report Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf110-116">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cf110-116">In This Section</span></span>  
  
-   [<span data-ttu-id="cf110-117">Подключение к серверу отчетов в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf110-117">Connect to a Report Server in Management Studio</span></span>](connect-to-a-report-server-in-management-studio.md)  
  
-   [<span data-ttu-id="cf110-118">Установка свойств сервера отчетов (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cf110-118">Set Report Server Properties &#40;Management Studio&#41;</span></span>](set-report-server-properties-management-studio.md)  
  
-   [<span data-ttu-id="cf110-119">Создание, удаление и изменение ролей (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cf110-119">Create, Delete, or Modify a Role &#40;Management Studio&#41;</span></span>](../security/role-definitions-create-delete-or-modify.md)  
  
-   [<span data-ttu-id="cf110-120">Удаление элемента (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cf110-120">Delete an Item &#40;Management Studio&#41;</span></span>](delete-an-item-management-studio.md)  
  
-   [<span data-ttu-id="cf110-121">Отмена заданий сервера отчетов (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cf110-121">Cancel Report Server Jobs &#40;Management Studio&#41;</span></span>](cancel-report-server-jobs-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf110-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf110-122">See Also</span></span>  
 <span data-ttu-id="cf110-123">[Сервер отчетов в справке Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="cf110-123">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="cf110-124">Общие сведения о среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf110-124">Introducing SQL Server Management Studio</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
