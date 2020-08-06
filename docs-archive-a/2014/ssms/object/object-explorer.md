---
title: Обозреватель объектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.objectexplorer.commandsoptions
- SQL12.SWB.SQLSERVEROBJECTEXPLORER.DHELP
- sql12.swb.objectexplorer.scriptingoptions
- sql12.swb.oe.f1
helpviewer_keywords:
- multi-select [SQL Server Management Studio]
- Registered Servers [SQL Server], Object Explorer
- Query Editor [SQL Server Management Studio], Object Explorer
- connections [SQL Server], SQL Server Management Studio
- servers [SQL Server], Registered Servers
- Object Explorer
- SQL Server Management Studio [SQL Server], connections
- viewing objects
- filtering objects [SQL Server]
- Object Explorer, about Object Explorer
ms.assetid: 469ea8e2-79b9-44c8-bb6f-f0e1c5dbf0f2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3acefcd03af1b39d467625800d8837553ff5253b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664659"
---
# <a name="object-explorer"></a><span data-ttu-id="def71-102">обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="def71-102">Object Explorer</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="def71-103">предоставляет возможности для управления объектами в экземплярах [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]и [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def71-103">provides features for managing objects in instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-object-explorer"></a><span data-ttu-id="def71-104">Преимущества обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="def71-104">Benefits of Object Explorer</span></span>  
 <span data-ttu-id="def71-105">В обозревателе объектов представлен иерархический пользовательский интерфейс для просмотра и управления объектами в каждом экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="def71-105">Object Explorer provides a hierarchical user interface to view and manage the objects in each instance of SQL Server.</span></span> <span data-ttu-id="def71-106">Панель сведений обозревателя объектов предлагает табличное представление объектов экземпляра и возможность поиска указанных объектов.</span><span class="sxs-lookup"><span data-stu-id="def71-106">The Object Explorer Details pane presents a tabular view of instance objects, and the capability to search for specific objects.</span></span> <span data-ttu-id="def71-107">Возможности обозревателя объектов могут незначительно различаться в зависимости от типа сервера, но в общем случае включают функции разработки для баз данных, а также функции управления для всех типов серверов.</span><span class="sxs-lookup"><span data-stu-id="def71-107">The capabilities of Object Explorer vary slightly depending on the type of server, but generally include the development features for databases, and management features for all server types.</span></span>  
  
## <a name="object-explorer-tasks"></a><span data-ttu-id="def71-108">Задачи обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="def71-108">Object Explorer Tasks</span></span>  
  
|<span data-ttu-id="def71-109">Description</span><span class="sxs-lookup"><span data-stu-id="def71-109">Description</span></span>|<span data-ttu-id="def71-110">Раздел</span><span class="sxs-lookup"><span data-stu-id="def71-110">Topic</span></span>|  
|-----------------|-----------|  
|<span data-ttu-id="def71-111">Содержит описание процесса открытия обозревателя объектов и настройки параметров, определяющих поведение обозревателя.</span><span class="sxs-lookup"><span data-stu-id="def71-111">Describes how to open the Object Explorer and configure the options that define the behavior of the explorer.</span></span>|[<span data-ttu-id="def71-112">Открытие и настройка обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="def71-112">Open and Configure Object Explorer</span></span>](open-and-configure-object-explorer.md)|  
|<span data-ttu-id="def71-113">Содержит описание процесса подключения обозревателя объектов к экземплярам [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]и [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def71-113">Describes how to connect Object Explorer to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>|[<span data-ttu-id="def71-114">Подключение к экземпляру из обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="def71-114">Connect to an Instance From Object Explorer</span></span>](connect-to-an-instance-from-object-explorer.md)|  
|<span data-ttu-id="def71-115">Содержит описание процесса управления объектами, представленными в виде узлов в иерархии обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="def71-115">Describes how to manage objects represented as nodes in the Object Explorer hierarchy.</span></span>|[<span data-ttu-id="def71-116">Управление объектами с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="def71-116">Manage Objects by Using Object Explorer</span></span>](manage-objects-by-using-object-explorer.md)|  
|<span data-ttu-id="def71-117">Содержит описание панели сведений обозревателя объектов для просмотра всех объектов сервера и управления ими при помощи пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="def71-117">Describes the Object Explorer Details Pane, a tabular view of all of the objects in the server with a user interface to manage them.</span></span>|[<span data-ttu-id="def71-118">Область сведений в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="def71-118">Object Explorer Details Pane</span></span>](object-explorer-details-pane.md)|  
|<span data-ttu-id="def71-119">Содержит описание способов выполнения пользовательских отчетов в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def71-119">Describes ways to run custom reports in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|[<span data-ttu-id="def71-120">Пользовательские отчеты в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="def71-120">Custom Reports in Management Studio</span></span>](custom-reports-in-management-studio.md)|  
  
  
