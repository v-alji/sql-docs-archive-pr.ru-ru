---
title: Исключить файлы из системы управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732941"
---
# <a name="exclude-files-from-source-control"></a><span data-ttu-id="4f866-102">Исключение файлов из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="4f866-102">Exclude Files from Source Control</span></span>
  <span data-ttu-id="4f866-103">Если решение, над которым вы работаете, содержит файлы, которые не нуждаются в службах управления версиями, можно использовать команду **исключить из системы управления версиями** , чтобы исключить файл из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="4f866-103">If the solution you are working on contains files that do not require source control services, you can use the **Exclude from Source Control** command to exclude the file from source control.</span></span> <span data-ttu-id="4f866-104">В этом случае файл остается в базе данных [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, но его возврат и извлечение в проекте невозможны.</span><span class="sxs-lookup"><span data-stu-id="4f866-104">When you do this, the file remains in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database, but it is no longer checked in or out with the project.</span></span>  
  
 <span data-ttu-id="4f866-105">Следует использовать команду **исключить из системы управления версиями** только для созданных файлов.</span><span class="sxs-lookup"><span data-stu-id="4f866-105">You should use the **Exclude from Source Control** command only on generated files.</span></span> <span data-ttu-id="4f866-106">Созданный файл является файлом, который может быть полностью создан повторно в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] зависимости от содержимого другого файла в решении.</span><span class="sxs-lookup"><span data-stu-id="4f866-106">A generated file is one that can be entirely re-created by [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] based on the contents of another file in the solution.</span></span>  
  
### <a name="to-exclude-a-file-from-source-control"></a><span data-ttu-id="4f866-107">Исключение файла из управления версиями</span><span class="sxs-lookup"><span data-stu-id="4f866-107">To exclude a file from source control</span></span>  
  
1.  <span data-ttu-id="4f866-108">В обозревателе решений выберите файл, который необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="4f866-108">In Solution Explorer, select the file to exclude.</span></span>  
  
2.  <span data-ttu-id="4f866-109">В меню **файл** укажите пункт **система управления версиями**, а затем выберите пункт **исключить** *\<file name>* **из системы управления версиями**.</span><span class="sxs-lookup"><span data-stu-id="4f866-109">On the **File** menu, point to **Source Control**, and then click **Exclude** *\<file name>* **from Source Control**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f866-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f866-110">See Also</span></span>  
 <span data-ttu-id="4f866-111">[Основы системы управления версиями](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="4f866-111">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="4f866-112">[Задание параметров системы управления версиями](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="4f866-112">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="4f866-113">Изменение соединений с системой управления версиями</span><span class="sxs-lookup"><span data-stu-id="4f866-113">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)  
  
  
