---
title: Открытие, просмотр и печать файла взаимоблокировок (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], printing files
- deadlocks [SQL Server], opening files
- opening deadlock files
- printing deadlock files
ms.assetid: 5061b13f-2cb7-457a-b8d0-fbd437b510ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08bacd7a99e45e10163216c69057b167088441ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666003"
---
# <a name="open-view-and-print-a-deadlock-file-sql-server-management-studio"></a><span data-ttu-id="35b9b-102">Открытие, просмотр и печать файла взаимоблокировок (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="35b9b-102">Open, View, and Print a Deadlock File (SQL Server Management Studio)</span></span>
  <span data-ttu-id="35b9b-103">Когда [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] создает взаимоблокировку, можно собрать и сохранить в файле сведения о взаимоблокировке.</span><span class="sxs-lookup"><span data-stu-id="35b9b-103">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] generates a deadlock, you can capture and save the deadlock information to a file.</span></span> <span data-ttu-id="35b9b-104">После того как файл взаимоблокировок был сохранен, его можно открыть в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , чтобы просмотреть или распечатать.</span><span class="sxs-lookup"><span data-stu-id="35b9b-104">After you have saved the deadlock file, you can open it in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view or print.</span></span>  
  
### <a name="to-open-and-view-a-deadlock-file"></a><span data-ttu-id="35b9b-105">Открытие и просмотр файла взаимоблокировок</span><span class="sxs-lookup"><span data-stu-id="35b9b-105">To open and view a deadlock file</span></span>  
  
1.  <span data-ttu-id="35b9b-106">В меню **файл** в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] выберите пункт **Открыть**, а затем выберите пункт **файл**.</span><span class="sxs-lookup"><span data-stu-id="35b9b-106">On the **File** menu in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="35b9b-107">В диалоговом окне **Открытие файла** выберите тип файлов XDL в списке **Файлы типа** .</span><span class="sxs-lookup"><span data-stu-id="35b9b-107">In the **Open File** dialog box, select the .xdl file type in the **Files of type** box.</span></span> <span data-ttu-id="35b9b-108">Теперь отфильтрованный список содержит только файлы взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="35b9b-108">You will now have a filtered list of only deadlock files.</span></span>  
  
### <a name="to-print-a-deadlock-file"></a><span data-ttu-id="35b9b-109">Распечатка файла взаимоблокировок</span><span class="sxs-lookup"><span data-stu-id="35b9b-109">To print a deadlock file</span></span>  
  
1.  <span data-ttu-id="35b9b-110">В меню **Файл** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]укажите **Открыть** , затем выберите пункт **Файл**.</span><span class="sxs-lookup"><span data-stu-id="35b9b-110">On the **File** menu in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="35b9b-111">В диалоговом окне **Открытие файла** выберите тип файлов XDL в списке **Файлы типа** .</span><span class="sxs-lookup"><span data-stu-id="35b9b-111">In the **Open File** dialog box, select the .xdl file type in the **Files of type** box.</span></span> <span data-ttu-id="35b9b-112">Теперь отфильтрованный список содержит только файлы взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="35b9b-112">You will now have a filtered list of only deadlock files.</span></span>  
  
3.  <span data-ttu-id="35b9b-113">Выберите файл взаимоблокировок, который необходимо распечатать, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="35b9b-113">Select the deadlock file you want to print, and click **Open**.</span></span>  
  
4.  <span data-ttu-id="35b9b-114">В меню **Файл** выберите **Печать.**</span><span class="sxs-lookup"><span data-stu-id="35b9b-114">On the **File** menu, click **Print.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b9b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="35b9b-115">See Also</span></span>  
 [<span data-ttu-id="35b9b-116">Сохранение графов взаимоблокировок (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="35b9b-116">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
  
