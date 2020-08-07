---
title: Перемещение элементов в решении | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- moving items
- solutions [SQL Server Management Studio], item relocation
- relocating items
ms.assetid: b40a24eb-f528-4e70-b26e-5eaf6e0ed1ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: fd0a8a89686c62b4d4d00aea5479bb956fe3011f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731290"
---
# <a name="move-items-in-a-solution"></a><span data-ttu-id="d8e67-102">Перемещение элементов в решении</span><span class="sxs-lookup"><span data-stu-id="d8e67-102">Move Items in a Solution</span></span>
  <span data-ttu-id="d8e67-103">Элементами проекта в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] являются очереди, соединения и различные файлы.</span><span class="sxs-lookup"><span data-stu-id="d8e67-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="d8e67-104">В обозревателе решений можно перемещать запросы и прочие файлы между проектами, но соединения перемещать нельзя.</span><span class="sxs-lookup"><span data-stu-id="d8e67-104">You can move Queries and Miscellaneous Files between projects in Solution Explorer, but Connections cannot be moved.</span></span>  
  
### <a name="to-move-items-in-solution-explorer"></a><span data-ttu-id="d8e67-105">Перемещение элемента в обозревателе решений</span><span class="sxs-lookup"><span data-stu-id="d8e67-105">To move items in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="d8e67-106">В обозревателе решений выберите элемент, который необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="d8e67-106">In Solution Explorer, select the item you want to move.</span></span>  
  
2.  <span data-ttu-id="d8e67-107">В меню **Правка** выберите пункт **Вырезать**.</span><span class="sxs-lookup"><span data-stu-id="d8e67-107">On the **Edit** menu, click **Cut**.</span></span>  
  
3.  <span data-ttu-id="d8e67-108">Выберите адресат в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="d8e67-108">In Solution Explorer, select the destination.</span></span>  
  
4.  <span data-ttu-id="d8e67-109">В меню **Правка** выберите пункт **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="d8e67-109">On the **Edit** menu, click **Paste**.</span></span>  
  
 <span data-ttu-id="d8e67-110">Запросы и прочие файлы также можно перемещать с помощью перетаскивания внутри обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="d8e67-110">You can move items by dragging Query and Miscellaneous files within Solution Explorer.</span></span> <span data-ttu-id="d8e67-111">Перетаскивание позволяет увидеть результат операции.</span><span class="sxs-lookup"><span data-stu-id="d8e67-111">Dragging allows you to see the outcome of the drag operation.</span></span> <span data-ttu-id="d8e67-112">После перемещения запросов из одного типа проектов в другой запросы могут рассматриваться в целевом проекте как прочие файлы.</span><span class="sxs-lookup"><span data-stu-id="d8e67-112">Moving queries from one project type to another may cause queries to be considered as miscellaneous files in the target project.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8e67-113">При перемещении подключенного запроса соединение в целевой проект не перемещается.</span><span class="sxs-lookup"><span data-stu-id="d8e67-113">Moving a connected query does not move the connection to the target project.</span></span> <span data-ttu-id="d8e67-114">После перемещения запрос теряет соединение.</span><span class="sxs-lookup"><span data-stu-id="d8e67-114">The query will lose its connection after it is moved to the target project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e67-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8e67-115">See Also</span></span>  
 <span data-ttu-id="d8e67-116">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="d8e67-116">[Solution Explorer](solution-explorer.md) </span></span>  
 [<span data-ttu-id="d8e67-117">Копирование элементов в решении</span><span class="sxs-lookup"><span data-stu-id="d8e67-117">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)  
  
  
