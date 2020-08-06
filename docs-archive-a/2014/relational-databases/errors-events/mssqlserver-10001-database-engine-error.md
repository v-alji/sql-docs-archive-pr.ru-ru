---
title: MSSQLSERVER_10001 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10001 (Database Engine error)
ms.assetid: f8fd2d8d-a4af-4b6a-ba51-9123b7e4c9bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0542f6d52a4fd194c4b0ae5d1aad501f5e3b8c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735285"
---
# <a name="mssqlserver_10001"></a><span data-ttu-id="3692f-102">MSSQLSERVER_10001</span><span class="sxs-lookup"><span data-stu-id="3692f-102">MSSQLSERVER_10001</span></span>
    
## <a name="details"></a><span data-ttu-id="3692f-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="3692f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3692f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="3692f-104">Product Name</span></span>|<span data-ttu-id="3692f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3692f-105">SQL Server</span></span>|  
|<span data-ttu-id="3692f-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3692f-106">Event ID</span></span>|<span data-ttu-id="3692f-107">10001</span><span class="sxs-lookup"><span data-stu-id="3692f-107">10001</span></span>|  
|<span data-ttu-id="3692f-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="3692f-108">Event Source</span></span>|<span data-ttu-id="3692f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3692f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3692f-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="3692f-110">Component</span></span>|<span data-ttu-id="3692f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3692f-111">SQLEngine</span></span>|  
|<span data-ttu-id="3692f-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="3692f-112">Symbolic Name</span></span>|<span data-ttu-id="3692f-113">HR_E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="3692f-113">HR_E_UNEXPECTED</span></span>|  
|<span data-ttu-id="3692f-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="3692f-114">Message Text</span></span>|<span data-ttu-id="3692f-115">Поставщик сообщил о непредвиденном глобальном сбое.</span><span class="sxs-lookup"><span data-stu-id="3692f-115">The provider reported an unexpected catastrophic failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3692f-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="3692f-116">Explanation</span></span>  
 <span data-ttu-id="3692f-117">При обработке распределенного запроса возникла типовая ошибка при обращении к поставщику OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3692f-117">Distributed query processing encountered a generic error while calling into the OLE DB provider.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3692f-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="3692f-118">User Action</span></span>  
 <span data-ttu-id="3692f-119">Соберите события трассировки OLE DB с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] и предоставьте эти данные службе поддержки продукта поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3692f-119">Collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and  provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3692f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="3692f-120">See Also</span></span>  
 <span data-ttu-id="3692f-121">[Шаблоны и разрешения приложения SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="3692f-121">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="3692f-122">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3692f-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
