---
title: Планы обслуживания базы данных заменены | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3aea75cc4ecc94ccbaeb1f35cecd0b18ff3a65ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654756"
---
# <a name="database-maintenance-plans-superseded"></a><span data-ttu-id="22712-102">Планы обслуживания базы данных заменены</span><span class="sxs-lookup"><span data-stu-id="22712-102">Database maintenance plans superseded</span></span>
    
## <a name="component"></a><span data-ttu-id="22712-103">Компонент</span><span class="sxs-lookup"><span data-stu-id="22712-103">Component</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="22712-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Агент</span><span class="sxs-lookup"><span data-stu-id="22712-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="22712-105">Описание</span><span class="sxs-lookup"><span data-stu-id="22712-105">Description</span></span>  
 <span data-ttu-id="22712-106">Существующие планы обслуживания базы данных обновлены и продолжают функционировать.</span><span class="sxs-lookup"><span data-stu-id="22712-106">Existing database maintenance plans are upgraded and continue to work.</span></span> <span data-ttu-id="22712-107">Однако нельзя создать новые планы обслуживания базы данных с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22712-107">However, you will not be able to create new database maintenance plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="22712-108">Для просмотра планов обслуживания в обозревателе объектов раскройте узел «Управление», а затем «Объекты прежних версий».</span><span class="sxs-lookup"><span data-stu-id="22712-108">To view the maintenance plans in Object Explorer, expand Management, and then expand Legacy.</span></span> <span data-ttu-id="22712-109">Можно перенести существующие планы обслуживания базы данных в новый формат, выбрав пункт **перенести** в контекстном меню для любого плана обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="22712-109">You can migrate existing database maintenance plans to the new format by selecting **Migrate** from the context menu for any database maintenance plan.</span></span> <span data-ttu-id="22712-110">Поскольку новые функции плана обслуживания не являются прямой заменой планов обслуживания базы данных, некоторые функциональные возможности после миграции могут быть утеряны.</span><span class="sxs-lookup"><span data-stu-id="22712-110">Because the new maintenance plan feature is not a direct replacement of database maintenance plans, some functionality might be lost after migration.</span></span> <span data-ttu-id="22712-111">При миграции плана обслуживания базы данных старый план не удаляется, поэтому перед удалением старого плана обслуживания можно проверить новый.</span><span class="sxs-lookup"><span data-stu-id="22712-111">Migrating a database maintenance plan does not delete the old plan, so you can test its functionality as a maintenance plan before removing the old plan.</span></span>  
  
 <span data-ttu-id="22712-112">Следующие функции более не поддерживаются планами обслуживания базы данных:</span><span class="sxs-lookup"><span data-stu-id="22712-112">The following features are no longer supported within database maintenance plans:</span></span>  
  
-   <span data-ttu-id="22712-113">Доставка журналов</span><span class="sxs-lookup"><span data-stu-id="22712-113">Log shipping</span></span>  
  
-   <span data-ttu-id="22712-114">Параметр " **пытаться исправить все незначительные проблемы** " задачи " **Проверка целостности базы данных** "</span><span class="sxs-lookup"><span data-stu-id="22712-114">The **Attempt to repair any minor problems** option of the **Database Integrity Check** task</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="22712-115">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="22712-115">Corrective Action</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="22712-116">предотвращает включение доставки журналов в план обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="22712-116">prevents log shipping from being included in a database maintenance plan.</span></span> <span data-ttu-id="22712-117">Дополнительные сведения см. в разделе «Доставка журналов» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22712-117">For more information, see "Log Shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
