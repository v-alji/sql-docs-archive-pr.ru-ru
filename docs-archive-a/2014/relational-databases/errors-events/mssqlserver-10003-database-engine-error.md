---
title: MSSQLSERVER_10003 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10003 (Database Engine error)
ms.assetid: 9e2cb199-f077-4d88-8117-1b7550afc696
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ea44fc9591602bfc8279924e10a1803d0d5a87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655258"
---
# <a name="mssqlserver_10003"></a><span data-ttu-id="c93d5-102">MSSQLSERVER_10003</span><span class="sxs-lookup"><span data-stu-id="c93d5-102">MSSQLSERVER_10003</span></span>
    
## <a name="details"></a><span data-ttu-id="c93d5-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c93d5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c93d5-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c93d5-104">Product Name</span></span>|<span data-ttu-id="c93d5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c93d5-105">SQL Server</span></span>|  
|<span data-ttu-id="c93d5-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c93d5-106">Event ID</span></span>|<span data-ttu-id="c93d5-107">10003</span><span class="sxs-lookup"><span data-stu-id="c93d5-107">10003</span></span>|  
|<span data-ttu-id="c93d5-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c93d5-108">Event Source</span></span>|<span data-ttu-id="c93d5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c93d5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c93d5-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c93d5-110">Component</span></span>|<span data-ttu-id="c93d5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c93d5-111">SQLEngine</span></span>|  
|<span data-ttu-id="c93d5-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c93d5-112">Symbolic Name</span></span>|<span data-ttu-id="c93d5-113">HR_E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c93d5-113">HR_E_OUTOFMEMORY</span></span>|  
|<span data-ttu-id="c93d5-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c93d5-114">Message Text</span></span>|<span data-ttu-id="c93d5-115">Поставщик исчерпал доступный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="c93d5-115">The provider ran out of memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c93d5-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c93d5-116">Explanation</span></span>  
 <span data-ttu-id="c93d5-117">Из-за нехватки системной памяти поставщик OLE DB исчерпал доступный ему объем памяти.</span><span class="sxs-lookup"><span data-stu-id="c93d5-117">Low system memory has caused the OLE DB provider to run out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c93d5-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c93d5-118">User Action</span></span>  
 <span data-ttu-id="c93d5-119">Повторно запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c93d5-119">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c93d5-120">Если это не поможет, перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="c93d5-120">If that does not help, restart the computer.</span></span> <span data-ttu-id="c93d5-121">Если проблема не исчезает, соберите события трассировки OLE DB с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] и передайте эти данные в службу технической поддержки поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c93d5-121">If the problem persists, collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93d5-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="c93d5-122">See Also</span></span>  
 <span data-ttu-id="c93d5-123">[Шаблоны и разрешения приложения SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c93d5-123">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="c93d5-124">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c93d5-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
